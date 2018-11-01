---
title: CSplitButton クラス
ms.date: 11/04/2016
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
ms.openlocfilehash: ca4899714fa336d058b2a53bcd5103c5b0c993e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547278"
---
# <a name="csplitbutton-class"></a>CSplitButton クラス

`CSplitButton`クラスは、分割ボタン コントロールを表します。 分割ボタン コントロールは、ユーザーがボタンのメイン領域をクリックすると既定の動作を実行し、ユーザーがボタンのドロップダウン矢印をクリックするとドロップダウン メニューを表示します。

## <a name="syntax"></a>構文

```
class CSplitButton : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSplitButton::CSplitButton](#csplitbutton)|`CSplitButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSplitButton::Create](#create)|指定したスタイルを使用して分割ボタン コントロールを作成し、現在に結び付けます`CSplitButton`オブジェクト。|
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに表示されるドロップダウン メニューを設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CSplitButton::OnDropDown](#ondropdown)|ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックすると、システムが送信される BCN_DROPDOWN 通知を処理します。|

## <a name="remarks"></a>Remarks

`CSplitButton`から派生したクラスは、 [CButton](../../mfc/reference/cbutton-class.md)クラス。 分割ボタン コントロールは、スタイルが button コントロールです。 ユーザーがドロップダウンの矢印をクリックすると、カスタム メニューが表示されます。 詳細については、BS_SPLITBUTTON と BS_DEFSPLITBUTTON スタイルを参照してください。[ボタンのスタイル](/windows/desktop/Controls/button-styles)します。

次の図は、ページャー コントロールと (1) の分割ボタン コントロールを含むダイアログ ボックスを示しています。 既に (2) のドロップダウン矢印をクリックし、(3) のサブメニューを表示します。

![Splitbutton およびページャー コントロールのダイアログ。](../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CSplitButton`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

Windows Vista 以降、このクラスはサポートされています。

このクラスの追加要件が記載されて[ビルド要件の Windows Vista コモン コントロール](../../mfc/build-requirements-for-windows-vista-common-controls.md)します。

##  <a name="create"></a>  CSplitButton::Create

指定したスタイルを使用して分割ボタン コントロールを作成し、現在に結び付けます`CSplitButton`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*dwStyle*|[in]コントロールに適用されるスタイルのビットごとの組み合わせ (OR)。 詳細については、次を参照してください。[ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)します。|
|*rect*|[in]参照を[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)コントロールのサイズと位置を含む構造体。|
|*pParentWnd*|[in]Null 以外のポインターを[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。|
|*nID*|[in]コントロールの ID。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

##  <a name="csplitbutton"></a>  CSplitButton::CSplitButton

`CSplitButton` オブジェクトを構築します。 コンス トラクターのパラメーターは、ユーザーは、分割ボタン コントロールのドロップダウン矢印をクリックしたときに表示されるサブメニューを指定します。

```
CSplitButton();

CSplitButton(
    UINT nMenuId,
    UINT nSubMenuId)
CSplitButton(CMenu* pMenu)
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nMenuId*|[in]メニュー バーのリソース ID。|
|*nSubMenuId*|[in]サブメニューのリソース ID。|
|*pMenu*|[in]ポインターを[CMenu](../../mfc/reference/cmenu-class.md)サブメニューを指定するオブジェクト。 `CSplitButton`オブジェクトの削除、`CMenu`オブジェクトとその関連付けられている HMENU ときに、`CSplitButton`オブジェクトがスコープ外になります。|

### <a name="remarks"></a>Remarks

使用して、 [CSplitButton::Create](#create)分割ボタン コントロールを作成し、アタッチ先メソッドを`CSplitButton`オブジェクト。

##  <a name="ondropdown"></a>  CSplitButton::OnDropDown

ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックすると、システムが送信される BCN_DROPDOWN 通知を処理します。

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pNMHDR*|[in]ポインター、 [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr)に関する情報を格納する構造体、 [BCN_DROPDOWN](/windows/desktop/Controls/bcn-dropdown)通知します。|
|*pResult*|[out](使用されません。 値は返されません)。値を返す、 [BCN_DROPDOWN](/windows/desktop/Controls/bcn-dropdown)通知します。|

### <a name="remarks"></a>Remarks

BCN_DROPDOWN 通知が送信され、ユーザーは、分割ボタン コントロールにドロップダウン矢印をクリックすると、メッセージを`OnDropDown`メソッド ハンドル。 ただし、`CSplitButton`オブジェクトは、分割ボタン コントロールを含むコントロールに BCN_DROPDOWN 通知を転送しません。 その結果、格納しているコントロールは、通知への応答でカスタム アクションをサポートできません。

格納しているコントロールをサポートするカスタム アクションを実装するには、使用、 [CButton](../../mfc/reference/cbutton-class.md)の代わりに BS_SPLITBUTTON スタイルを持つオブジェクトを`CSplitButton`オブジェクト。 BCN_DROPDOWN 通知のハンドラーを実装し、`CButton`オブジェクト。 詳細については、次を参照してください。[ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)します。

使用して、分割ボタン コントロール自体でサポートするカスタム アクションを実装する[メッセージ リフレクション](../../mfc/tn062-message-reflection-for-windows-controls.md)します。 クラスを派生、`CSplitButton`クラスし、名前を付け、CMySplitButton など。 BCN_DROPDOWN 通知を処理するアプリケーションに、次のメッセージ マップを追加します。

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

##  <a name="setdropdownmenu"></a>  CSplitButton::SetDropDownMenu

ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに表示されるドロップダウン メニューを設定します。

```
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nMenuId*|[in]メニュー バーのリソース ID。|
|*nSubMenuId*|[in]サブメニューのリソース ID。|
|*pMenu*|[in]ポインターを[CMenu](../../mfc/reference/cmenu-class.md)サブメニューを指定するオブジェクト。 `CSplitButton`オブジェクトの削除、`CMenu`オブジェクトとその関連付けられている HMENU ときに、`CSplitButton`オブジェクトがスコープ外になります。|

### <a name="remarks"></a>Remarks

*NMenuId*パラメーターは、メニュー バー、メニュー バー項目の水平方向のリストを識別します。 *NSubMenuId*パラメーターは、各メニュー バー項目に関連付けられたメニュー項目のドロップダウン リストである、サブメニューを識別する 0 から始まるインデックス番号。 たとえば、「編集」および"Help"のメニューを"File"に、メニュー バー項目を含むが一般的なアプリケーション [ファイル] メニュー バーの項目がメニュー項目を含むサブメニュー「開くには、」「閉じる」および"Exit"。 分割ボタン コントロールのドロップダウン矢印をクリックすると、コントロールはメニュー バーではなく、指定のサブメニューを表示します。

次の図は、ページャー コントロールと (1) の分割ボタン コントロールを含むダイアログ ボックスを示しています。 既に (2) のドロップダウン矢印をクリックし、(3) のサブメニューを表示します。

![Splitbutton およびページャー コントロールのダイアログ。](../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")

### <a name="example"></a>例

次のコード例の最初のステートメントを示して、 [CSplitButton::SetDropDownMenu](#setdropdownmenu)メソッド。 Visual Studio のリソースがある、メニュー エディターで、メニュー バーの ID、IDR_MENU1 の名前を自動的に作成しました。 *NSubMenuId*パラメーターが 0 の場合は、メニュー バーの唯一のサブメニューを指します。

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>関連項目

[CSplitButton クラス](../../mfc/reference/csplitbutton-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)
