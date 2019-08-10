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
ms.openlocfilehash: f9116306fd2bd6145096b055025bd4dd2075b0c1
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916886"
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
|[CPropertyPage:: CPropertyPage](#cpropertypage)|`CPropertyPage` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPropertyPage:: CancelToClose](#canceltoclose)|モーダルプロパティシートのページで回復不可能な変更が発生した後、[OK] ボタンを [閉じる] に変更し、[キャンセル] ボタンを無効にします。|
|[CPropertyPage:: Construct](#construct)|`CPropertyPage` オブジェクトを構築します。 実行`Construct`時にパラメーターを指定する場合、または配列を使用する場合は、を使用します。|
|[CPropertyPage::GetPSP](#getpsp)|`CPropertyPage`オブジェクトに関連付けられた Windows [propsheet ページ](/windows/desktop/api/prsht/ns-prsht-propsheetpagea_v2)構造体を取得します。|
|[CPropertyPage:: OnApply](#onapply)|[今すぐ適用] ボタンがクリックされたときにフレームワークによって呼び出されます。|
|[CPropertyPage:: OnCancel](#oncancel)|[キャンセル] ボタンがクリックされたときにフレームワークによって呼び出されます。|
|[CPropertyPage:: OnKillActive](#onkillactive)|現在のページがアクティブページでなくなったときにフレームワークによって呼び出されます。 ここでデータの検証を実行します。|
|[CPropertyPage:: OnOK](#onok)|[OK]、[今すぐ適用]、または [閉じる] ボタンがクリックされたときにフレームワークによって呼び出されます。|
|[CPropertyPage:: OnQueryCancel](#onquerycancel)|[キャンセル] ボタンがクリックされたときと、キャンセルが行われる前に、フレームワークによって呼び出されます。|
|[CPropertyPage:: OnReset](#onreset)|[キャンセル] ボタンがクリックされたときにフレームワークによって呼び出されます。|
|[CPropertyPage:: OnSetActive](#onsetactive)|ページがアクティブページになったときにフレームワークによって呼び出されます。|
|[CPropertyPage:: OnWizardBack](#onwizardback)|ウィザード型のプロパティシートを使用中に [戻る] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[CPropertyPage:: OnWizardFinish](#onwizardfinish)|ウィザード型のプロパティシートを使用しているときに [完了] ボタンがクリックされたときにフレームワークによって呼び出されます。|
|[CPropertyPage:: OnWizardNext](#onwizardnext)|ウィザード型のプロパティシートを使用中に [次へ] ボタンがクリックされたときにフレームワークによって呼び出されます。|
|[CPropertyPage::QuerySiblings](#querysiblings)|プロパティシートの各ページにメッセージを転送します。|
|[CPropertyPage:: SetModified](#setmodified)|を呼び出して、[今すぐ適用] ボタンをアクティブまたは非アクティブにします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPropertyPage:: m_psp](#m_psp)|Windows [Propsheet ページ](/windows/desktop/api/prsht/ns-prsht-propsheetpagea_v2)の構造体。 基本的なプロパティページパラメーターへのアクセスを提供します。|

## <a name="remarks"></a>Remarks

標準のダイアログボックスと同様に、プロパティシート内`CPropertyPage`の各ページに対してからクラスを派生させます。 派生オブジェクト`CPropertyPage`を使用するには、まず[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)オブジェクトを作成し、次に、プロパティシートに含まれる各ページに対してオブジェクトを作成します。 シート内の各ページに対して[CPropertySheet:: AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)を呼び出し、モーダルプロパティシートに[CPropertySheet::D omodal](../../mfc/reference/cpropertysheet-class.md#domodal)を呼び出すか、モードレスプロパティシートに対して[CPropertySheet:: Create](../../mfc/reference/cpropertysheet-class.md#create)を呼び出して、プロパティシートを表示します。

ウィザードと呼ばれるタブダイアログボックスの種類を作成することができます。これは、デバイスの設定やニュースレターの作成など、操作の手順をユーザーに案内する一連のプロパティページを含むプロパティシートで構成されています。 ウィザードの [型タブ] ダイアログボックスでは、プロパティページにタブはなく、一度に表示できるプロパティページは1つだけです。 また、[OK] ボタンと [今すぐ適用] ボタンは、[戻る] ボタン、[次へ] または [完了] ボタン、および [キャンセル] ボタンがあります。

ウィザードとしてプロパティシートを確立する方法の詳細については、「 [CPropertySheet:: SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)」を参照してください。 オブジェクトの使用方法`CPropertyPage`の詳細については、「[プロパティシートとプロパティページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs

##  <a name="canceltoclose"></a>CPropertyPage:: CancelToClose

モーダルプロパティシートのページ内のデータに回復不可能な変更が加えられた後に、この関数を呼び出します。

```
void CancelToClose();
```

### <a name="remarks"></a>Remarks

この関数は、[OK] ボタンを閉じて [キャンセル] ボタンを無効にします。 この変更により、変更が永続的であり、変更を取り消すことができないことがユーザーに通知されます。

この`CancelToClose`メンバー関数は、モードレスプロパティシートでは何も実行しません。既定では、モードレスプロパティシートに [キャンセル] ボタンがないためです。

### <a name="example"></a>例

  [CPropertyPage:: QuerySiblings](#querysiblings)の例を参照してください。

##  <a name="construct"></a>CPropertyPage:: Construct

オブジェクトを構築するには、 `CPropertyPage`このメンバー関数を呼び出します。

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

*nIDTemplate*<br/>
このページで使用されるテンプレートの ID。

*nIDCaption*<br/>
このページのタブに配置される名前の ID。 0の場合、このページのダイアログテンプレートから名前が取得されます。

*lpszTemplateName*<br/>
テンプレートリソースの名前である null で終わる文字列を格納します。

*nIDHeaderTitle*<br/>
プロパティページヘッダーのタイトルの場所に配置される名前の ID。 既定値は0です。

*nIDHeaderSubTitle*<br/>
プロパティページヘッダーのサブタイトルの場所に配置される名前の ID。 既定値は0です。

### <a name="remarks"></a>Remarks

オブジェクトは、次のすべての条件が満たされた後に表示されます。

- このページは、 [CPropertySheet:: AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)を使用してプロパティシートに追加されています。

- プロパティシートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)関数または[Create](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。

- ユーザーがこのページを選択しました。

他`Construct`のクラスコンストラクターのいずれかが呼び出されていない場合は、を呼び出します。 この`Construct`メンバー関数は、パラメーターステートメントを空白のままにして、コード内の任意の時点で複数のパラメーターと構築を指定できるため、柔軟性があります。

配列を操作`Construct`する場合は、を使用する必要があり`Construct`ます。また、データメンバーに適切な値が割り当てられるように、配列の各メンバーに対してを呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

##  <a name="cpropertypage"></a>CPropertyPage:: CPropertyPage

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

*nIDTemplate*<br/>
このページで使用されるテンプレートの ID。

*nIDCaption*<br/>
このページのタブに配置される名前の ID。 0の場合、このページのダイアログテンプレートから名前が取得されます。

*dwSize*<br/>
*Lpsztemplatename*このページのテンプレートの名前を格納している文字列を指します。 Nll は指定できません。

*nIDHeaderTitle*<br/>
プロパティページヘッダーのタイトルの場所に配置される名前の ID。

*nIDHeaderSubTitle*<br/>
プロパティページヘッダーのサブタイトルの場所に配置される名前の ID。

### <a name="remarks"></a>Remarks

オブジェクトは、次のすべての条件が満たされた後に表示されます。

- このページは、 [CPropertySheet:: AddPage](../../mfc/reference/cpropertysheet-class.md#addpage)を使用してプロパティシートに追加されています。

- プロパティシートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)関数または[Create](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。

- ユーザーがこのページを選択しました。

複数の`CPropertyPage`パラメーターがある場合 (たとえば、配列を使用している場合) は、ではなく[CPropertySheet:: Construct](../../mfc/reference/cpropertysheet-class.md#construct)を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

##  <a name="getpsp"></a>  CPropertyPage::GetPSP

`CPropertyPage`オブジェクトに関連付けられた Windows [propsheet ページ](/windows/desktop/api/prsht/ns-prsht-propsheetpagea_v2)構造体を取得します。

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>戻り値

`PROPSHEETPAGE`構造体への参照。

##  <a name="m_psp"></a>CPropertyPage:: m_psp

`m_psp`は、メンバーが[Propsheet ページ](/windows/desktop/api/prsht/ns-prsht-propsheetpagea_v2)の特性を格納する構造体です。

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Remarks

この構造体を使用して、プロパティページの構築後に外観を初期化します。

メンバーの一覧など、この構造の詳細については、Windows SDK `PROPSHEETPAGE`の「」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

##  <a name="onapply"></a>CPropertyPage:: OnApply

このメンバー関数は、ユーザーが [OK] または [今すぐ適用] ボタンを選択したときにフレームワークによって呼び出されます。

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>戻り値

変更が受け入れられた場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

フレームワークがこの関数を呼び出すと、プロパティシート内のすべてのプロパティページで行われた変更が受け入れられます`OnApply` 。プロパティシートはフォーカスを保持し、TRUE (値 1) を返します。 が`OnApply`フレームワークによって呼び出されるようにするには、 [SetModified](#setmodified)を呼び出し、そのパラメーターを TRUE に設定する必要があります。 これにより、ユーザーがプロパティページを変更するとすぐに [今すぐ適用] ボタンがアクティブになります。

このメンバー関数をオーバーライドして、ユーザーが [今すぐ適用] ボタンをクリックしたときにプログラムが実行するアクションを指定します。 オーバーライドする場合、関数は変更を受け入れるには TRUE を返し、変更が有効にならないように FALSE を返します。

の既定の`OnApply`実装で`OnOK`は、が呼び出されます。

ユーザーがプロパティシートで [今すぐ適用] または [OK] をクリックしたときに送信される通知メッセージの詳細については、Windows SDK の「 [PSN_APPLY](/windows/desktop/Controls/psn-apply) 」を参照してください。

### <a name="example"></a>例

  [CPropertyPage:: OnOK](#onok)の例を参照してください。

##  <a name="oncancel"></a>CPropertyPage:: OnCancel

このメンバー関数は、[キャンセル] ボタンが選択されたときにフレームワークによって呼び出されます。

```
virtual void OnCancel();
```

### <a name="remarks"></a>Remarks

キャンセルボタンの操作を実行するには、このメンバー関数をオーバーライドします。 既定では、行われたすべての変更が無視されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

##  <a name="onkillactive"></a>  CPropertyPage::OnKillActive

このメンバー関数は、ページがアクティブページでなくなったときにフレームワークによって呼び出されます。

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>戻り値

データが正常に更新された場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>Remarks

特別なデータ検証タスクを実行するには、このメンバー関数をオーバーライドします。

このメンバー関数の既定の実装では、プロパティページのコントロールから、プロパティページのメンバー変数に設定がコピーされます。 ダイアログデータ検証 (DDV) エラーが原因でデータが正常に更新されなかった場合、ページにフォーカスが保持されます。

このメンバー関数が正常に返された後、フレームワークはページの[OnOK](#onok)関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

##  <a name="onok"></a>  CPropertyPage::OnOK

ユーザーが framework 呼び出しの直後に、[ok] または [今すぐ適用] ボタンのいずれかに、このメンバー関数が、フレームワークによって呼び出されます[OnKillActive](#onkillactive)します。

```
virtual void OnOK();
```

### <a name="remarks"></a>Remarks

フレームワークが受信 OK または [適用] ボタンを選択すると、 [PSN_APPLY](/windows/desktop/Controls/psn-apply)プロパティ ページからの通知です。 `OnOK` [CPropertySheet::P ressbutton](../../mfc/reference/cpropertysheet-class.md#pressbutton)を呼び出すと、の呼び出しは行われません。この場合、プロパティページは通知を送信しません。

ユーザーがプロパティシート全体を閉じるときに、現在アクティブなページに固有の追加の動作を実装するには、このメンバー関数をオーバーライドします。

このメンバー関数の既定の実装は、データが`OnKillActive`関数で更新されたことを反映するために、ページを "クリーン" としてマークします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

##  <a name="onquerycancel"></a>CPropertyPage:: OnQueryCancel

このメンバー関数は、ユーザーが [キャンセル] をクリックしたとき、およびキャンセル操作が行われる前に、フレームワークによって呼び出されます。

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>戻り値

キャンセル操作を禁止する場合は FALSE、それを許可する場合は TRUE を返します。

### <a name="remarks"></a>Remarks

このメンバー関数をオーバーライドして、ユーザーが [キャンセル] ボタンをクリックしたときにプログラムが実行するアクションを指定します。

の既定の`OnQueryCancel`実装では、TRUE が返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

##  <a name="onreset"></a>CPropertyPage:: OnReset

このメンバー関数は、ユーザーが [キャンセル] ボタンをクリックしたときにフレームワークによって呼び出されます。

```
virtual void OnReset();
```

### <a name="remarks"></a>Remarks

フレームワークがこの関数を呼び出すと、ユーザーが [今すぐ適用] ボタンをクリックしたときに行われたすべてのプロパティページへの変更が破棄され、プロパティシートがフォーカスを保持します。

このメンバー関数をオーバーライドして、ユーザーが [キャンセル] ボタンをクリックしたときにプログラムが実行するアクションを指定します。

の既定の`OnReset`実装では、何も実行されません。

### <a name="example"></a>例

  [CPropertyPage:: OnCancel](#oncancel)の例を参照してください。

##  <a name="onsetactive"></a>CPropertyPage:: OnSetActive

このメンバー関数は、ページがユーザーによって選択され、アクティブページになったときにフレームワークによって呼び出されます。

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>戻り値

ページが正常にアクティブに設定された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

ページがアクティブになったときにタスクを実行するには、このメンバー関数をオーバーライドします。 通常、このメンバー関数をオーバーライドすると、データメンバーを更新した後に既定のバージョンが呼び出され、新しいデータでページコントロールを更新できるようになります。

既定の実装では、ページのウィンドウが作成されていない場合は作成され、アクティブなページになります。

### <a name="example"></a>例

  [CPropertySheet:: Setfinish text](../../mfc/reference/cpropertysheet-class.md#setfinishtext)の例を参照してください。

##  <a name="onwizardback"></a>CPropertyPage:: OnWizardBack

このメンバー関数は、ユーザーがウィザードの [戻る] ボタンをクリックしたときにフレームワークによって呼び出されます。

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>戻り値

0を設定すると、次のページに自動的に進みます。ページが変更されないようにする場合は-1。 次のページ以外のページにジャンプするには、表示するダイアログの識別子を返します。

### <a name="remarks"></a>Remarks

このメンバー関数をオーバーライドして、[戻る] ボタンが押されたときにユーザーが実行する必要のあるアクションを指定します。

ウィザードタイプのプロパティシートを作成する方法の詳細については、「 [CPropertySheet:: SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

##  <a name="onwizardfinish"></a>CPropertyPage:: OnWizardFinish

このメンバー関数は、ユーザーがウィザードの [完了] ボタンをクリックしたときにフレームワークによって呼び出されます。

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>戻り値

ウィザードの終了時にプロパティシートが破棄される場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>Remarks

ユーザーがウィザードの **[完了**] ボタンをクリックすると、フレームワークはこの関数を呼び出します。が`OnWizardFinish` TRUE (0 以外の値) を返すと、プロパティシートを破棄できます (実際には破棄されません)。 を`DestroyWindow`呼び出して、プロパティシートを破棄します。 からを`DestroyWindow` `OnWizardFinish`呼び出さないでください。そうすると、ヒープの破損やその他のエラーが発生します。

このメンバー関数をオーバーライドすると、[完了] ボタンが押されたときにユーザーが実行する必要のあるアクションを指定できます。 この関数をオーバーライドする場合は、プロパティシートが破棄されないように FALSE を返します。

ユーザーがウィザードのプロパティシートの [完了] ボタンをクリックしたときに送信される通知メッセージの詳細については、Windows SDK の「 [PSN_WIZFINISH](/windows/desktop/Controls/psn-wizfinish) 」を参照してください。

ウィザードタイプのプロパティシートを作成する方法の詳細については、「 [CPropertySheet:: SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

##  <a name="onwizardnext"></a>CPropertyPage:: OnWizardNext

このメンバー関数は、ユーザーがウィザードの [次へ] ボタンをクリックしたときにフレームワークによって呼び出されます。

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>戻り値

0を設定すると、次のページに自動的に進みます。ページが変更されないようにする場合は-1。 次のページ以外のページにジャンプするには、表示するダイアログの識別子を返します。

### <a name="remarks"></a>Remarks

このメンバー関数をオーバーライドして、[次へ] ボタンが押されたときにユーザーが実行する必要のあるアクションを指定します。

ウィザードタイプのプロパティシートを作成する方法の詳細については、「 [CPropertySheet:: SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

##  <a name="querysiblings"></a>  CPropertyPage::QuerySiblings

このメンバー関数を呼び出して、プロパティシート内の各ページにメッセージを転送します。

```
LRESULT QuerySiblings(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*wParam*<br/>
追加のメッセージに依存する情報を指定します。

*lParam*<br/>
追加のメッセージに依存する情報を指定します。

### <a name="return-value"></a>戻り値

プロパティシートのページからの0以外の値。または、すべてのページが0の値を返す場合は0。

### <a name="remarks"></a>Remarks

ページから0以外の値が返された場合、プロパティシートは後続のページにメッセージを送信しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

##  <a name="setmodified"></a>CPropertyPage:: SetModified

このメンバー関数を呼び出して、プロパティページの設定を適切な外部オブジェクトに適用するかどうかに基づいて [今すぐ適用] ボタンを有効または無効にします。

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>パラメーター

*bChanged*<br/>
プロパティページの設定が最後に適用されてから変更されたことを示す場合は TRUE。プロパティページの設定が適用されていることを示す場合は FALSE、無視する場合はです。

### <a name="remarks"></a>Remarks

フレームワークは、どのページが "ダーティ" であるかを追跡します。これは、を呼び出し`SetModified( TRUE )`たときのプロパティページです。 いずれかのページに対してを呼び出し`SetModified( TRUE )`た場合、[今すぐ適用] ボタンは常に有効になります。 [今すぐ適用] ボタンは、いずれかの`SetModified( FALSE )`ページに対してを呼び出すと無効になりますが、他のどのページも "ダーティ" になっている場合のみです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>関連項目

[MFC のサンプル CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)
