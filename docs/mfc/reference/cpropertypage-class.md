---
title: CPropertyPage クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bfdc096950e16c912503d95612855211af812cb9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060625"
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
|[CPropertyPage::CPropertyPage](#cpropertypage)|`CPropertyPage` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPropertyPage::CancelToClose](#canceltoclose)|[閉じる] ボタンに変更して、モーダル プロパティ シートのページで、回復不可能な変更後、[キャンセル] ボタンを無効にします。|
|[CPropertyPage::Construct](#construct)|`CPropertyPage` オブジェクトを構築します。 使用`Construct`、実行時に、パラメーターを指定する場合、または配列を使用している場合。|
|[CPropertyPage::GetPSP](#getpsp)|Windows の取得[PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2)構造に関連付けられている、`CPropertyPage`オブジェクト。|
|[CPropertyPage::OnApply](#onapply)|今すぐ適用 ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[CPropertyPage::OnCancel](#oncancel)|[キャンセル] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[CPropertyPage::OnKillActive](#onkillactive)|現在のページがアクティブでなくなったときに、フレームワークによって呼び出されます。 ここでデータの検証を実行します。|
|[送るに](#onok)|Ok、今すぐ適用または 閉じる ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[CPropertyPage::OnQueryCancel](#onquerycancel)|キャンセルが行われる前に、[キャンセル] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[CPropertyPage::OnReset](#onreset)|[キャンセル] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[CPropertyPage::OnSetActive](#onsetactive)|ページには、アクティブなページが行われたときに、フレームワークによって呼び出されます。|
|[CPropertyPage::OnWizardBack](#onwizardback)|ウィザード形式のプロパティ シートを使用しているときに、[戻る] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|ウィザード形式のプロパティ シートを使用しているときに、[完了] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[CPropertyPage::OnWizardNext](#onwizardnext)|ウィザード形式のプロパティ シートを使用しているときに、[次へ] ボタンがクリックされたときに、フレームワークによって呼び出されます。|
|[CPropertyPage::QuerySiblings](#querysiblings)|プロパティ シートの各ページにメッセージを転送します。|
|[CPropertyPage::SetModified](#setmodified)|今すぐ適用 ボタンをアクティブまたは非アクティブの呼び出しです。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2)構造体。 基本的なプロパティ ページのパラメーターへのアクセスを提供します。|

## <a name="remarks"></a>Remarks

クラスを派生する標準ダイアログ ボックスで、`CPropertyPage`プロパティ シートのページごとにします。 使用する`CPropertyPage`-派生オブジェクトは、まずを作成、 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)オブジェクトし、プロパティ シートに移動する各ページのオブジェクトを作成します。 呼び出す[が](../../mfc/reference/cpropertysheet-class.md#addpage)各シートのページし、呼び出すことによって、プロパティ シートを表示[する](../../mfc/reference/cpropertysheet-class.md#domodal)モーダル プロパティ シート、または[CPropertySheet:。作成](../../mfc/reference/cpropertysheet-class.md#create)モードレス プロパティ シートです。

一連のデバイスの設定やニュースレターを作成するなどの操作の手順を追ってプロパティ ページのプロパティ シートで構成される、ウィザードと呼ばれるタブ ダイアログ ボックスの種類を作成できます。 ウィザードの種類 タブのダイアログ ボックスでは、プロパティ ページのタブがないと、一度に 1 つのプロパティ ページが表示されます。 また、ボタンが ok と 今すぐ適用するのではなく、ウィザードの種類 タブ ダイアログには、戻る ボタン、次へ または 完了 ボタン、および キャンセル ボタン。

ウィザードとプロパティ シートを確立する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)します。 使用しての詳細については`CPropertyPage`オブジェクトは、記事をご覧ください。[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CPropertyPage`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

##  <a name="canceltoclose"></a>  CPropertyPage::CancelToClose

モーダル プロパティ シートのページ内のデータに、回復不可能な変更が行われた後は、この関数を呼び出します。

```
void CancelToClose();
```

### <a name="remarks"></a>Remarks

この関数は、[ok] ボタンを閉じるに変更し、[キャンセル] ボタンを無効にします。 これは、変更、アラートの変更が確定され、変更があるユーザーを取り消すことができません。

`CancelToClose`モードレス プロパティ シートでは、既定では、[キャンセル] ボタンはありませんのでメンバー関数は、モードレス プロパティ シートではありません。

### <a name="example"></a>例

  例をご覧ください[CPropertyPage::QuerySiblings](#querysiblings)します。

##  <a name="construct"></a>  CPropertyPage::Construct

作成するには、このメンバー関数を呼び出す、`CPropertyPage`オブジェクト。

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
このページで使用するテンプレートの ID。

*nIDCaption*<br/>
このページのタブに配置する名前の ID。 0 の場合は、このページのダイアログ テンプレートから、名前を取得します。

*lpszTemplateName*<br/>
テンプレート リソースの名前を表す null で終わる文字列が含まれています。

*nIDHeaderTitle*<br/>
プロパティ ページのヘッダーのタイトルの位置に配置する名前の ID。 既定で 0。

*nIDHeaderSubTitle*<br/>
プロパティ ページのヘッダーのサブタイトルの場所に配置する名前の ID。 既定で 0。

### <a name="remarks"></a>Remarks

すべての次の条件が満たされた場合は、オブジェクトが表示されます。

- 使用してプロパティ シートにページが追加された[が](../../mfc/reference/cpropertysheet-class.md#addpage)します。

- プロパティ シートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)または[作成](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。

- ユーザーが選択 (タブ) このページ。

呼び出す`Construct`他のクラスのコンス トラクターのいずれかが呼び出されていない場合。 `Construct`パラメーター ステートメントを空白のままにして、コードで複数のパラメーターと任意の時点の構築を指定できるので、メンバー関数は柔軟です。

使用する必要があります`Construct`ときに、配列を使用して、呼び出す必要があります`Construct`配列の各メンバーのデータ メンバーには、適切な値が割り当てられるようにします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]

##  <a name="cpropertypage"></a>  CPropertyPage::CPropertyPage

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
このページで使用するテンプレートの ID。

*nIDCaption*<br/>
このページのタブに配置する名前の ID。 0 の場合は、このページのダイアログ テンプレートから、名前を取得します。

*ない dwSize*<br/>
*lpszTemplateName*このページのテンプレートの名前を含む文字列を指します。 Nll は指定できません。

*nIDHeaderTitle*<br/>
プロパティ ページのヘッダーのタイトルの位置に配置する名前の ID。

*nIDHeaderSubTitle*<br/>
プロパティ ページのヘッダーのサブタイトルの場所に配置する名前の ID。

### <a name="remarks"></a>Remarks

すべての次の条件が満たされた場合は、オブジェクトが表示されます。

- 使用してプロパティ シートにページが追加された[が](../../mfc/reference/cpropertysheet-class.md#addpage)します。

- プロパティ シートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)または[作成](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。

- ユーザーが選択 (タブ) このページ。

使用して、複数のパラメーター (たとえば、配列を使用している場合) があれば、[まず、](../../mfc/reference/cpropertysheet-class.md#construct)の代わりに`CPropertyPage`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]

##  <a name="getpsp"></a>  CPropertyPage::GetPSP

Windows の取得[PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2)構造に関連付けられている、`CPropertyPage`オブジェクト。

```
const PROPSHEETPAGE& GetPSP() const;

PROPSHEETPAGE& GetPSP();
```

### <a name="return-value"></a>戻り値

参照、`PROPSHEETPAGE`構造体。

##  <a name="m_psp"></a>  CPropertyPage::m_psp

`m_psp` メンバーの特性を格納する構造体は、 [PROPSHEETPAGE](/windows/desktop/api/prsht/ns-prsht-_propsheetpagea_v2)します。

```
PROPSHEETPAGE m_psp;
```

### <a name="remarks"></a>Remarks

この構造体を使用して、構築した後、プロパティ ページの外観を初期化します。

そのメンバーの一覧を含む、この構造の詳細については、次を参照してください。 `PROPSHEETPAGE` Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]

##  <a name="onapply"></a>  CPropertyPage::OnApply

このメンバー関数は、ユーザーが [OK] または [適用] ボタンに、フレームワークによって呼び出されます。

```
virtual BOOL OnApply();
```

### <a name="return-value"></a>戻り値

変更が受け付けられた場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

フレームワークは、この関数を呼び出すと、プロパティ シートにすべてのプロパティ ページで行った変更が受け入れられた、プロパティ シートは、フォーカスを保持し、 `OnApply` (値 1) は TRUE を返します。 前に`OnApply`呼び出すことができます、フレームワークによってする必要がありますが呼び出さ[SetModified](#setmodified)し、そのパラメーターを TRUE に設定します。 今すぐ適用 ボタン、ユーザーは、プロパティ ページで変更を行うとすぐにアクティブになります。

今すぐ適用 ボタンをクリックすると、プログラムの動作を指定するには、このメンバー関数をオーバーライドします。 オーバーライドする場合、変更を反映する場合は TRUE と FALSE を有効になってからの変更を防ぐために、関数を返します。

既定の実装`OnApply`呼び出し`OnOK`します。

ユーザー プロパティ シートで、今すぐ適用または [ok] ボタンを押したときに送信される通知メッセージの詳細については、次を参照してください。 [PSN_APPLY](/windows/desktop/Controls/psn-apply) Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[送るに](#onok)します。

##  <a name="oncancel"></a>  CPropertyPage::OnCancel

[キャンセル] ボタンを選択すると、このメンバー関数は、フレームワークによって呼び出されます。

```
virtual void OnCancel();
```

### <a name="remarks"></a>Remarks

[キャンセル] ボタンのアクションを実行するには、このメンバー関数をオーバーライドします。 既定では、行われた変更を否定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]

##  <a name="onkillactive"></a>  CPropertyPage::OnKillActive

ページがアクティブでなくなったときに、このメンバー関数は、フレームワークによって呼び出されます。

```
virtual BOOL OnKillActive();
```

### <a name="return-value"></a>戻り値

データが正常に更新された場合は 0 以外。 それ以外の場合に 0 です。

### <a name="remarks"></a>Remarks

特別なデータの検証タスクを実行するには、このメンバー関数をオーバーライドします。

このメンバー関数の既定の実装では、プロパティ ページのメンバー変数にプロパティ ページのコントロールから設定をコピーします。 ダイアログ データ検証 (DDV) エラーのため、データが正常に更新しない場合、ページには、フォーカスが保持されます。

このメンバー関数が正常に返された後に、フレームワークがページを呼び出しますが[OnOK](#onok)関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]

##  <a name="onok"></a>  送るに

ユーザーが [framework 呼び出しの直後に、[ok] または [今すぐ適用] ボタンのいずれかに、このメンバー関数が、フレームワークによって呼び出されます[OnKillActive](#onkillactive)します。

```
virtual void OnOK();
```

### <a name="remarks"></a>Remarks

フレームワークが受信 OK または [適用] ボタンを選択すると、 [PSN_APPLY](/windows/desktop/Controls/psn-apply)プロパティ ページからの通知です。 呼び出し`OnOK`を呼び出す場合に行われたしません[CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton)プロパティ ページによる通知の送信がそうでないためです。

ユーザーがプロパティ シート全体を閉じる場合に、現在アクティブなページに固有の追加動作を実装するには、このメンバー関数をオーバーライドします。

このメンバー関数の既定の実装で、データが更新されたことを反映するには、「クリーン」、ページをマークする、`OnKillActive`関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]

##  <a name="onquerycancel"></a>  CPropertyPage::OnQueryCancel

[キャンセル] ボタンをクリックし、キャンセルする前に動作が発生したときに、このメンバー関数がフレームワークによって呼び出されます。

```
virtual BOOL OnQueryCancel();
```

### <a name="return-value"></a>戻り値

取り消し操作を防止する場合は FALSE または許可する場合は TRUE を返します。

### <a name="remarks"></a>Remarks

ユーザーが [キャンセル] ボタンをクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライドします。

既定の実装`OnQueryCancel`TRUE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]

##  <a name="onreset"></a>  CPropertyPage::OnReset

ユーザーが [キャンセル] ボタンを選択すると、このメンバー関数は、フレームワークによって呼び出されます。

```
virtual void OnReset();
```

### <a name="remarks"></a>Remarks

フレームワークは、この関数を呼び出すの適用 ボタンを選択したユーザーによって行われたすべてのプロパティ ページに変更を破棄して、プロパティ シートにフォーカスが保持されます。

ユーザーが [キャンセル] ボタンをクリックすると、プログラムの動作を指定するには、このメンバー関数をオーバーライドします。

既定の実装`OnReset`何も行われません。

### <a name="example"></a>例

  例をご覧ください[CPropertyPage::OnCancel](#oncancel)します。

##  <a name="onsetactive"></a>  CPropertyPage::OnSetActive

このメンバー関数は、ページは、ユーザーが選択され、アクティブになったときにフレームワークによって呼び出されます。

```
virtual BOOL OnSetActive();
```

### <a name="return-value"></a>戻り値

ページを正常にアクティブに設定されている場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

ページがアクティブになったときにタスクを実行するには、このメンバー関数をオーバーライドします。 このメンバー関数のオーバーライドはページ コントロールを新しいデータで更新を許可するように、データ メンバーを更新した後は通常、既定のバージョンを呼び出します。

既定の実装は、ページ、ウィンドウを作成するかどうか、以前に作成し、アクティブなページになります。

### <a name="example"></a>例

  例をご覧ください[CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext)します。

##  <a name="onwizardback"></a>  CPropertyPage::OnWizardBack

ユーザーが、ウィザードの [戻る] ボタンをクリックすると、このメンバー関数は、フレームワークによって呼び出されます。

```
virtual LRESULT OnWizardBack();
```

### <a name="return-value"></a>戻り値

次のページに自動的に進行するには 0ページの変更を防ぐためには-1。 次の 1 つ以外のページにジャンプするには、ダイアログを表示するの識別子を返します。

### <a name="remarks"></a>Remarks

[戻る] ボタンがクリックされたときに、ユーザーが操作を指定するには、このメンバー関数をオーバーライドします。

ウィザード形式のプロパティ シートを作成する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]

##  <a name="onwizardfinish"></a>  CPropertyPage::OnWizardFinish

ユーザーがウィザードで、[完了] をクリックすると、このメンバー関数は、フレームワークによって呼び出されます。

```
virtual BOOL OnWizardFinish();
```

### <a name="return-value"></a>戻り値

0 以外の場合、ウィザードが完了したら; プロパティ シートが破棄される場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

ユーザーがクリックすると、**完了**ウィザードのフレームワークのボタンは、この関数を呼び出すときに`OnWizardFinish`は破壊することができます (は実際には破棄されません) (0 以外の値)、プロパティ シートに TRUE を返します。 呼び出す`DestroyWindow`プロパティ シートを破棄します。 呼び出さない`DestroyWindow`から`OnWizardFinish`; そうは原因ヒープの破損またはその他のエラー。

[完了] ボタンがクリックされたときに、ユーザーが操作を指定するには、このメンバー関数をオーバーライドすることができます。 この関数をオーバーライドする場合に、プロパティ シートが破棄されていることを防ぐために FALSE が返されます。

ウィザードのプロパティ シートで、ユーザーが [完了] ボタンを押したときに送信される通知メッセージの詳細については、次を参照してください。 [PSN_WIZFINISH](/windows/desktop/Controls/psn-wizfinish) Windows SDK に含まれています。

ウィザード形式のプロパティ シートを作成する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]

[!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]

[!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]

[!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]

##  <a name="onwizardnext"></a>  CPropertyPage::OnWizardNext

ウィザードの [次へ] をクリックすると、このメンバー関数は、フレームワークによって呼び出されます。

```
virtual LRESULT OnWizardNext();
```

### <a name="return-value"></a>戻り値

次のページに自動的に進行するには 0ページの変更を防ぐためには-1。 次の 1 つ以外のページにジャンプするには、ダイアログを表示するの識別子を返します。

### <a name="remarks"></a>Remarks

[次へ] ボタンが押されたときに、ユーザーが操作を指定するには、このメンバー関数をオーバーライドします。

ウィザード形式のプロパティ シートを作成する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]

##  <a name="querysiblings"></a>  CPropertyPage::QuerySiblings

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
追加のメッセージに依存する情報を指定します

### <a name="return-value"></a>戻り値

0 以外の値 0 の場合、またはプロパティ シート内のページからすべてのページは、値 0 を返します。

### <a name="remarks"></a>Remarks

ページが 0 以外の値を返す場合、プロパティ シートは後続のページにメッセージを送信しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]

[!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]

##  <a name="setmodified"></a>  CPropertyPage::SetModified

有効にするまたは適用 ボタン、適切な外部オブジェクトにプロパティ ページの設定を適用するかどうかに基づいてを無効にするには、このメンバー関数を呼び出します。

```
void SetModified(BOOL bChanged = TRUE);
```

### <a name="parameters"></a>パラメーター

*bChanged*<br/>
前回適用された後、プロパティ ページの設定が変更されていることを指定する場合は TRUEプロパティ ページの設定が適用されているか、無視するかを示す場合は FALSE。

### <a name="remarks"></a>Remarks

フレームワークは、ページの「ダーティ」、つまり追跡、呼び出した対象のプロパティ ページを保持`SetModified( TRUE )`します。 今すぐ適用 ボタンを呼び出す場合に常に有効`SetModified( TRUE )`ページのいずれか。 呼び出すと、今すぐ適用 ボタンは無効になります`SetModified( FALSE )`のみ場合のどの他のページは「ダーティ」、ページの 1 つの

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)<br/>
[MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)<br/>
[MFC サンプル PROPDLG](../../visual-cpp-samples.md)<br/>
[MFC サンプル SNAPVW](../../visual-cpp-samples.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)
