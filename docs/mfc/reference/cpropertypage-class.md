---
title: CPropertyPage クラス
ms.date: 11/04/2016
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
helpviewer_keywords:
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
ms.openlocfilehash: 816948ea17f674c3cd693331502df33cce62610c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363999"
---
# <a name="cpropertypage-class"></a>CPropertyPage クラス

タブ ダイアログ ボックスとして知られているプロパティ シートの各ページを表します。

## <a name="syntax"></a>構文

```
class CPropertyPage : public CDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[プロパティページ::Cプロパティページ](#cpropertypage)|`CPropertyPage` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[閉じるには](#canceltoclose)|モーダル プロパティ シートのページで回復不可能な変更を行った後、[OK] ボタンを [閉じる] を変更し、[キャンセル] ボタンを無効にします。|
|[プロパティページ::コンストラクト](#construct)|`CPropertyPage` オブジェクトを構築します。 実行時`Construct`にパラメーターを指定する場合、または配列を使用する場合に使用します。|
|[プロパティページ::ゲットプスプ](#getpsp)|オブジェクトに関連付けられている Windows[の PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2)構造体を`CPropertyPage`取得します。|
|[プロパティページ::オン・適用](#onapply)|[今すぐ適用] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[プロパティページ::キャンセル時](#oncancel)|[キャンセル] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[プロパティページ::オンキルアクティブ](#onkillactive)|現在のページがアクティブなページでなくなったときに、フレームワークによって呼び出されます。 ここでデータ検証を実行します。|
|[プロパティページ::オノク](#onok)|[OK]、[今すぐ適用]、または [閉じる] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[プロパティページ::クエリキャンセル](#onquerycancel)|[キャンセル] ボタンがクリックされたとき、およびキャンセルが行われる前に、フレームワークによって呼び出されます。|
|[プロパティページ::オンリセット](#onreset)|[キャンセル] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[プロパティページ::オンセットアクティブ](#onsetactive)|ページがアクティブなページになったときに、フレームワークによって呼び出されます。|
|[プロパティページ::オンウィザードバック](#onwizardback)|ウィザード型のプロパティ シートを使用しているときに [戻る] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[プロパティページ::ウィザード完了](#onwizardfinish)|ウィザード型のプロパティ シートを使用しているときに [完了] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[プロパティページ::オンウィザード次](#onwizardnext)|ウィザード型のプロパティ シートを使用しているときに [次へ] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[プロパティページ::クエリ兄弟](#querysiblings)|プロパティ シートの各ページにメッセージを転送します。|
|[プロパティページ::セット修正](#setmodified)|[今すぐ適用] ボタンをアクティブまたは非アクティブ化する場合に呼び出します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[プロパティページ::m_psp](#m_psp)|構造体[を表示します](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2)。 基本的なプロパティ ページ パラメーターへのアクセスを提供します。|

## <a name="remarks"></a>解説

標準のダイアログ ボックスと同様に、プロパティ`CPropertyPage`シートの各ページのクラスを派生させます。 派生オブジェクト`CPropertyPage`を使用するには、まず[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)オブジェクトを作成し、プロパティ シートに表示される各ページのオブジェクトを作成します。 呼び出し[CPropertySheet::AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)シート内の各ページのプロパティ シートを表示するには、モーダル プロパティ シートの[CPropertySheet::DoModal、](../../mfc/reference/cpropertysheet-class.md#domodal)またはモードレス プロパティ シートの[作成を呼び](../../mfc/reference/cpropertysheet-class.md#create)出します。

ウィザードと呼ばれるタブ ダイアログ ボックスの種類を作成できます。 ウィザードの種類のタブ ダイアログ ボックスでは、プロパティ ページにはタブが表示されず、一度に表示されるプロパティ ページは 1 つだけです。 また、[OK] ボタンと [今すぐ適用] ボタンを使用する代わりに、ウィザードタイプのタブ ダイアログ ボックスには[戻る] ボタン、[次へ] または [完了] ボタン、[キャンセル] ボタンがあります。

ウィザードとしてのプロパティ シートの設定の詳細については[、「CPropertySheet::SetWizardMode」](../../mfc/reference/cpropertysheet-class.md#setwizardmode)を参照してください。 オブジェクトの使用方法`CPropertyPage`の詳細については、「[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="cpropertypagecanceltoclose"></a><a name="canceltoclose"></a>閉じるには

モーダル プロパティ シートのページ内のデータに対して、回復不可能な変更が行われた後にこの関数を呼び出します。

```
void CancelToClose();
```

### <a name="remarks"></a>解説

この機能は、[OK] ボタンを [閉じる] に変更し、[キャンセル] ボタンを無効にします。 この変更により、変更が永続的であり、変更を取り消すことができないことがユーザーに警告されます。

モード`CancelToClose`レス プロパティ シートには既定で [キャンセル] ボタンがないため、メンバ関数はモードレス プロパティ シートでは何も行いません。

### <a name="example"></a>例

  [「プロパティ ページ::クエリ兄弟](#querysiblings)」の例を参照してください。

## <a name="cpropertypageconstruct"></a><a name="construct"></a>プロパティページ::コンストラクト

オブジェクトを構築するには、このメンバー`CPropertyPage`関数を呼び出します。

```
void Construct(
    UINT nIDTemplate,
    UINT nIDCaption = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0);

void Construct(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);

void Construct(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
このページで使用するテンプレートの ID です。

*nIDキャプション*<br/>
このページのタブに配置する名前の ID です。 0 の場合、このページのダイアログ テンプレートから名前が取得されます。

*テンプレート名*<br/>
テンプレート リソースの名前である null で終わる文字列を格納します。

*ヘッダータイトル*<br/>
プロパティ ページ ヘッダーのタイトルの場所に配置される名前の ID。 デフォルトでは 0。

*サブタイトル*<br/>
プロパティ ページ ヘッダーのサブタイトルの場所に配置される名前の ID。 デフォルトでは 0。

### <a name="remarks"></a>解説

オブジェクトは、次のすべての条件が満たされた後に表示されます。

- ページは、プロパティ シートに[追加されました](../../mfc/reference/cpropertysheet-class.md#addpage)。

- プロパティ シートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)関数または[作成](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。

- ユーザーがこのページを選択しました (タブ付き)。

他`Construct`のクラス コンストラクターのいずれかが呼び出されていない場合に呼び出します。 メンバー`Construct`関数は、パラメーター ステートメントを空白のままにして、コード内の任意の位置で複数のパラメーターと構築を指定できるため、柔軟性があります。

配列を操作`Construct`するときに使用し、データ メンバーに適切な値`Construct`を割り当てるように、配列の各メンバーを呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

## <a name="cpropertypagecpropertypage"></a><a name="cpropertypage"></a>プロパティページ::Cプロパティページ

`CPropertyPage` オブジェクトを構築します。

```
CPropertyPage();

explicit CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

explicit CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));

CPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption,
    UINT nIDHeaderTitle,
    UINT nIDHeaderSubTitle = 0,
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
このページで使用するテンプレートの ID です。

*nIDキャプション*<br/>
このページのタブに配置する名前の ID です。 0 の場合、このページのダイアログ テンプレートから名前が取得されます。

*Dwsize*<br/>
*テンプレート名*このページのテンプレート名を含む文字列へのアクセスをポイントします。 Nll は指定できません。

*ヘッダータイトル*<br/>
プロパティ ページ ヘッダーのタイトルの場所に配置される名前の ID。

*サブタイトル*<br/>
プロパティ ページ ヘッダーのサブタイトルの場所に配置される名前の ID。

### <a name="remarks"></a>解説

オブジェクトは、次のすべての条件が満たされた後に表示されます。

- ページは、プロパティ シートに[追加されました](../../mfc/reference/cpropertysheet-class.md#addpage)。

- プロパティ シートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)関数または[作成](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。

- ユーザーがこのページを選択しました (タブ付き)。

複数のパラメーターがある場合 (たとえば、配列を使用している場合) は、の代わりに[CPropertySheet::Construct を](../../mfc/reference/cpropertysheet-class.md#construct)使用`CPropertyPage`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

## <a name="cpropertypagegetpsp"></a><a name="getpsp"></a>プロパティページ::ゲットプスプ

オブジェクトに関連付けられている Windows[の PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2)構造体を`CPropertyPage`取得します。

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>戻り値

`PROPSHEETPAGE`構造体への参照。

## <a name="cpropertypagem_psp"></a><a name="m_psp"></a>プロパティページ::m_psp

`m_psp`は、メンバーが[PROPSHEETPAGE](/windows/win32/api/prsht/ns-prsht-propsheetpagea_v2)の特性を格納する構造体です。

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>解説

この構造体を使用して、プロパティ ページの構築後の外観を初期化します。

この構造体の詳細については、そのメンバーの一覧を含む、Windows SDK を参照してください`PROPSHEETPAGE`。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

## <a name="cpropertypageonapply"></a><a name="onapply"></a>プロパティページ::オン・適用

このメンバー関数は、ユーザーが [OK] または [今すぐ適用] ボタンを選択したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>戻り値

変更が受け入れられる場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

フレームワークがこの関数を呼び出すと、プロパティ シートのすべてのプロパティ ページに対して行われた変更が受け入れられ、`OnApply`プロパティ シートはフォーカスを保持し、TRUE (値 1) を返します。 フレームワーク`OnApply`から呼び出す前に[、SetModified](#setmodified)を呼び出して、そのパラメーターを TRUE に設定しておく必要があります。 これにより、ユーザーがプロパティ ページで変更を行うとすぐに [今すぐ適用] ボタンがアクティブになります。

ユーザーが [今すぐ適用] ボタンをクリックしたときにプログラムが実行する動作を指定するには、このメンバー関数をオーバーライドします。 オーバーライドする場合、関数は TRUE を返して変更を受け入れ、変更が有効にならないように FALSE を返します。

呼び出し`OnApply``OnOK`の既定の実装。

ユーザーがプロパティ シートの [今すぐ適用] または [OK] ボタンをクリックしたときに送信される通知メッセージの詳細については、Windows SDK の[PSN_APPLY](/windows/win32/Controls/psn-apply)を参照してください。

### <a name="example"></a>例

  [「CPropertyPage::OnOK」](#onok)の例を参照してください。

## <a name="cpropertypageoncancel"></a><a name="oncancel"></a>プロパティページ::キャンセル時

このメンバー関数は、[キャンセル] ボタンが選択されたときにフレームワークによって呼び出されます。

```
virtual void OnCancel();
```

### <a name="remarks"></a>解説

このメンバー関数をオーバーライドして、キャンセル ボタンアクションを実行します。 デフォルトでは、行われた変更はすべて否定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

## <a name="cpropertypageonkillactive"></a><a name="onkillactive"></a>プロパティページ::オンキルアクティブ

このメンバー関数は、ページがアクティブページでなくなったときに、フレームワークによって呼び出されます。

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>戻り値

データが正常に更新された場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

特殊なデータ検証タスクを実行するには、このメンバー関数をオーバーライドします。

このメンバー関数の既定の実装では、プロパティ ページのコントロールからプロパティ ページのメンバー変数に設定がコピーされます。 ダイアログ データ検証 (DDV) エラーが原因でデータが正常に更新されなかった場合、ページはフォーカスを保持します。

このメンバー関数が正常に返された後、フレームワークはページの[OnOK](#onok)関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

## <a name="cpropertypageonok"></a><a name="onok"></a>プロパティページ::オノク

このメンバー関数は、フレームワークが[OnKillActive](#onkillactive)を呼び出した直後に、ユーザーが [OK] または [今すぐ適用] ボタンを選択したときに、フレームワークによって呼び出されます。

```
virtual void OnOK();
```

### <a name="remarks"></a>解説

ユーザーが [OK] または [今すぐ適用] ボタンを選択すると、フレームワークはプロパティ ページから[PSN_APPLY](/windows/win32/Controls/psn-apply)通知を受け取ります。 プロパティ ページ`OnOK`は通知を送信しないため[、CPropertySheet::PresButton](../../mfc/reference/cpropertysheet-class.md#pressbutton)を呼び出した場合、呼び出しは行われません。

ユーザーがプロパティ シート全体を閉じたときに、現在アクティブなページに固有の追加の動作を実装するには、このメンバー関数をオーバーライドします。

このメンバー関数の既定の実装では、データが関数で更新されたことを反映するために、ページを "clean" としてマークします`OnKillActive`。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

## <a name="cpropertypageonquerycancel"></a><a name="onquerycancel"></a>プロパティページ::クエリキャンセル

このメンバー関数は、ユーザーが [キャンセル] ボタンをクリックしたとき、およびキャンセルアクションが実行される前に、フレームワークによって呼び出されます。

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>戻り値

キャンセル操作を禁止するには FALSE を返し、許可する場合は TRUE を返します。

### <a name="remarks"></a>解説

ユーザーが [キャンセル] ボタンをクリックしたときにプログラムが実行するアクションを指定するには、このメンバー関数をオーバーライドします。

既定の実装では`OnQueryCancel`TRUE が返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

## <a name="cpropertypageonreset"></a><a name="onreset"></a>プロパティページ::オンリセット

このメンバー関数は、ユーザーが [キャンセル] ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual void OnReset();
```

### <a name="remarks"></a>解説

フレームワークがこの関数を呼び出すと、以前に [今すぐ適用] ボタンを選択したユーザーによって行われたすべてのプロパティ ページへの変更は破棄され、プロパティ シートはフォーカスを保持します。

ユーザーが [キャンセル] ボタンをクリックしたときにプログラムが実行する動作を指定するには、このメンバー関数をオーバーライドします。

の既定の`OnReset`実装では何も実行されません。

### <a name="example"></a>例

  [「C プロパティ ページ::キャンセルの](#oncancel)実行」の例を参照してください。

## <a name="cpropertypageonsetactive"></a><a name="onsetactive"></a>プロパティページ::オンセットアクティブ

このメンバー関数は、ユーザーがページを選択してアクティブ ページになったときに、フレームワークによって呼び出されます。

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>戻り値

ページが正常にアクティブに設定された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ページがアクティブになったときにタスクを実行するには、このメンバー関数をオーバーライドします。 このメンバー関数をオーバーライドすると、通常は、データ メンバーの更新後に既定のバージョンが呼び出され、新しいデータでページ コントロールを更新できるようになります。

既定の実装では、ページのウィンドウが作成されます (以前作成されていない場合) 、アクティブなページになります。

### <a name="example"></a>例

  次の例[を](../../mfc/reference/cpropertysheet-class.md#setfinishtext)参照してください。

## <a name="cpropertypageonwizardback"></a><a name="onwizardback"></a>プロパティページ::オンウィザードバック

このメンバー関数は、ユーザーがウィザードの [戻る] ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>戻り値

自動的に次のページに進む場合は 0。-1 ページが変更されないようにします。 次のページ以外のページにジャンプするには、表示するダイアログの識別子を返します。

### <a name="remarks"></a>解説

このメンバー関数をオーバーライドして、戻るボタンが押されたときにユーザーが実行する必要のあるアクションを指定します。

ウィザードタイプのプロパティシートを作成する方法の詳細については[、「CPropertySheet::SetWizardMode」](../../mfc/reference/cpropertysheet-class.md#setwizardmode)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

## <a name="cpropertypageonwizardfinish"></a><a name="onwizardfinish"></a>プロパティページ::ウィザード完了

このメンバー関数は、ユーザーがウィザードの [完了] ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>戻り値

ウィザードの終了時にプロパティ シートが破棄された場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ユーザーがウィザードの [**完了**] ボタンをクリックすると、フレームワークはこの関数を呼び出します。TRUE `OnWizardFinish` (ゼロ以外の値) を返すと、プロパティ シートは破棄されます (実際には破棄されません)。 プロパティ`DestroyWindow`シートを破棄する呼び出し。 から`OnWizardFinish`呼び`DestroyWindow`出さないで下に。この操作を行うと、ヒープの破損やその他のエラーが発生します。

このメンバー関数をオーバーライドして、完了ボタンが押されたときにユーザーが実行する必要のあるアクションを指定できます。 この関数をオーバーライドする場合は、FALSE を返してプロパティ シートが破棄されないようにします。

ユーザーがウィザードのプロパティ シートで [完了] ボタンを押したときに送信される通知メッセージの詳細については、Windows SDK の[PSN_WIZFINISH](/windows/win32/Controls/psn-wizfinish)を参照してください。

ウィザードタイプのプロパティシートを作成する方法の詳細については[、「CPropertySheet::SetWizardMode」](../../mfc/reference/cpropertysheet-class.md#setwizardmode)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

## <a name="cpropertypageonwizardnext"></a><a name="onwizardnext"></a>プロパティページ::オンウィザード次

このメンバー関数は、ユーザーがウィザードの [次へ] ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>戻り値

自動的に次のページに進む場合は 0。-1 ページが変更されないようにします。 次のページ以外のページにジャンプするには、表示するダイアログの識別子を返します。

### <a name="remarks"></a>解説

このメンバー関数をオーバーライドして、ユーザーが [次へ] ボタンを押したときに実行する必要のあるアクションを指定します。

ウィザードタイプのプロパティシートを作成する方法の詳細については[、「CPropertySheet::SetWizardMode」](../../mfc/reference/cpropertysheet-class.md#setwizardmode)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

## <a name="cpropertypagequerysiblings"></a><a name="querysiblings"></a>プロパティページ::クエリ兄弟

プロパティ シートの各ページにメッセージを転送するには、このメンバー関数を呼び出します。

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*wParam*<br/>
メッセージに依存する追加情報を指定します。

*lParam*<br/>
メッセージに依存する追加情報を指定します。

### <a name="return-value"></a>戻り値

プロパティ シートのページの 0 以外の値。またはすべてのページが 0 を返す場合は 0。

### <a name="remarks"></a>解説

ページが 0 以外の値を返す場合、プロパティ シートはメッセージを後続のページに送信しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

## <a name="cpropertypagesetmodified"></a><a name="setmodified"></a>プロパティページ::セット修正

プロパティ ページの設定を適切な外部オブジェクトに適用するかどうかを基に、[Apply Now] ボタンを有効または無効にするには、このメンバー関数を呼び出します。

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>パラメーター

*b変更*<br/>
プロパティ ページの設定が最後に適用されてから変更されたことを示す場合は TRUE。プロパティ ページの設定が適用されたことを示す場合は FALSE、または無視する必要があることを示します。

### <a name="remarks"></a>解説

フレームワークは、どのページが "ダーティ" であるのか、つまり、呼び出`SetModified( TRUE )`したプロパティ ページを追跡します。 いずれかのページを呼び出`SetModified( TRUE )`すと、[今すぐ適用] ボタンが常に有効になります。 [今すぐ適用] ボタンは、いずれかの`SetModified( FALSE )`ページを呼び出すときに無効になりますが、他のどのページも "ダーティ" ではない場合のみです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>関連項目

[サンプル CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[サンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル のプロップル](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル スナップVW](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)
