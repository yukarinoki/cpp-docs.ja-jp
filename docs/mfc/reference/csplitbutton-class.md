---
title: CSplitButton クラス
ms.date: 11/19/2018
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
ms.openlocfilehash: 38fceed1cc42ca0aac2e6ddaf145db273c95771d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753132"
---
# <a name="csplitbutton-class"></a>CSplitButton クラス

クラス`CSplitButton`は分割ボタン コントロールを表します。 分割ボタン コントロールは、ユーザーがボタンのメイン領域をクリックすると既定の動作を実行し、ユーザーがボタンのドロップダウン矢印をクリックするとドロップダウン メニューを表示します。

## <a name="syntax"></a>構文

```
class CSplitButton : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[スプリットボタン::Cスプリットボタン](#csplitbutton)|`CSplitButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[スプリットボタン::作成](#create)|指定したスタイルを使用して分割ボタン コントロールを作成し、現在`CSplitButton`のオブジェクトにアタッチします。|
|[スプリットボタン::セットドロップダウンメニュー](#setdropdownmenu)|ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに表示されるドロップダウン メニューを設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[スプリットボタン::オンドロップダウン](#ondropdown)|ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときにシステムが送信するBCN_DROPDOWN通知を処理します。|

## <a name="remarks"></a>解説

クラス`CSplitButton`は[CButton](../../mfc/reference/cbutton-class.md)クラスから派生します。 分割ボタン コントロールは、スタイルがBS_SPLITBUTTONボタン コントロールです。 ユーザーがドロップダウン矢印をクリックすると、カスタム メニューが表示されます。 詳細については、「[ボタン スタイル](/windows/win32/Controls/button-styles)」のBS_SPLITBUTTONおよびBS_DEFSPLITBUTTONスタイルを参照してください。

次の図は、ページャー コントロールと (1) 分割ボタン コントロールを含むダイアログ ボックスを示しています。 (2) ドロップダウン矢印が既にクリックされており、(3) サブメニューが表示されます。

![splitbutton およびページャー コントロールを含むダイアログ。](../../mfc/reference/media/splitbutton_pager.png "splitbutton およびページャー コントロールを含むダイアログ。")

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CSplitButton`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

このクラスは、Windows Vista 以降でサポートされています。

このクラスの追加要件については、「 [Windows Vista コモン コントロールのビルド要件](../../mfc/build-requirements-for-windows-vista-common-controls.md)」を参照してください。

## <a name="csplitbuttoncreate"></a><a name="create"></a>スプリットボタン::作成

指定したスタイルを使用して分割ボタン コントロールを作成し、現在`CSplitButton`のオブジェクトにアタッチします。

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
|*Dwstyle*|[in]コントロールに適用するスタイルのビットごとの組み合わせ (OR)。 詳細については、「ボタン[スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)」を参照してください。|
|*Rect*|[in]コントロールの位置とサイズを格納する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。|
|*pParentWnd*|[in]コントロールの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへの非 null ポインター。|
|*nID*|[in]コントロールの ID。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="csplitbuttoncsplitbutton"></a><a name="csplitbutton"></a>スプリットボタン::Cスプリットボタン

`CSplitButton` オブジェクトを構築します。 コンストラクターのパラメーターは、ユーザーが分割ボタン コントロールのドロップダウン矢印をクリックしたときに表示されるサブメニューを指定します。

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
|*nメニューID*|[in]メニュー バーのリソース ID。|
|*をクリックします。*|[in]サブメニューのリソース ID。|
|*メニュー*|[in]サブメニューを指定する[CMenu](../../mfc/reference/cmenu-class.md)オブジェクトへのポインター。 オブジェクト`CSplitButton`がスコープ外に`CMenu`出ると、オブジェクトと関連付けられた`CSplitButton`HMENU が削除されます。|

### <a name="remarks"></a>解説

分割ボタン コントロールを作成し、オブジェクトにアタッチするには[、CSplitButton::Create](#create) `CSplitButton`メソッドを使用します。

## <a name="csplitbuttonondropdown"></a><a name="ondropdown"></a>スプリットボタン::オンドロップダウン

ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときにシステムが送信するBCN_DROPDOWN通知を処理します。

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pNMHDR*|[in][BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown)通知に関する情報を含む[NMHDR](/windows/win32/api/richedit/ns-richedit-nmhdr)構造体へのポインター。|
|*結果*|[アウト](使用されず、値は返されません。[BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown)通知の戻り値。|

### <a name="remarks"></a>解説

ユーザーが分割ボタン コントロールのドロップダウン矢印をクリックすると、メソッドが処理するBCN_DROPDOWN通知メッセージが送信されます`OnDropDown`。 ただし、オブジェクト`CSplitButton`は、分割ボタン コントロールを含むコントロールにBCN_DROPDOWN通知を転送しません。 したがって、そのコントロールは通知に応答してカスタム 動作をサポートできません。

コントロールがサポートするカスタム 動作を実装するには、オブジェクトではなく、BS_SPLITBUTTONのスタイルを持つ[CButton](../../mfc/reference/cbutton-class.md) `CSplitButton`オブジェクトを使用します。 次に、オブジェクトにBCN_DROPDOWN通知のハンドラーを`CButton`実装します。 詳細については、「ボタン[スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)」を参照してください。

分割ボタン コントロール自体がサポートするカスタム アクションを実装するには、[メッセージ リフレクション](../../mfc/tn062-message-reflection-for-windows-controls.md)を使用します。 クラスから独自のクラスを`CSplitButton`派生させ、名前を付けます。たとえば、CMySplitButton。 次に、次のメッセージ マップをアプリケーションに追加して、BCN_DROPDOWN通知を処理します。

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

## <a name="csplitbuttonsetdropdownmenu"></a><a name="setdropdownmenu"></a>スプリットボタン::セットドロップダウンメニュー

ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックしたときに表示されるドロップダウン メニューを設定します。

```cpp
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nメニューID*|[in]メニュー バーのリソース ID。|
|*をクリックします。*|[in]サブメニューのリソース ID。|
|*メニュー*|[in]サブメニューを指定する[CMenu](../../mfc/reference/cmenu-class.md)オブジェクトへのポインター。 オブジェクト`CSplitButton`がスコープ外に`CMenu`出ると、オブジェクトと関連付けられた`CSplitButton`HMENU が削除されます。|

### <a name="remarks"></a>解説

*nMenuId*パラメーターは、メニュー バー項目の水平方向のリストであるメニュー バーを識別します。 *nSubMenuId*パラメーターは、サブメニューを識別する 0 から始まるインデックス番号です。 たとえば、一般的なアプリケーションには、メニュー バーの項目である "ファイル"、"編集"、および "ヘルプ" を含むメニューがあります。 "ファイル" メニュー バーの項目には、メニュー項目 "開く"、"閉じる"、"終了" を含むサブメニューがあります。 分割ボタン コントロールのドロップダウン矢印をクリックすると、コントロールはメニュー バーではなく指定されたサブメニューを表示します。

次の図は、ページャー コントロールと (1) 分割ボタン コントロールを含むダイアログ ボックスを示しています。 (2) ドロップダウン矢印が既にクリックされており、(3) サブメニューが表示されます。

![splitbutton およびページャー コントロールを含むダイアログ。](../../mfc/reference/media/splitbutton_pager.png "splitbutton およびページャー コントロールを含むダイアログ。")

### <a name="example"></a>例

次のコード例の最初のステートメントは、[メソッドを示](#setdropdownmenu)しています。 メニューは、メニュー バー ID と自動的に名前を付けた Visual Studio リソース エディターを使用して作成IDR_MENU1。 *nSubMenuId*パラメーターは 0 で、メニュー バーの唯一のサブメニューを参照します。

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>関連項目

[CSplitButton クラス](../../mfc/reference/csplitbutton-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)
