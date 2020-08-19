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
ms.openlocfilehash: 484cef2787c9e5c166a7b20b017251b559d7221c
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562546"
---
# <a name="csplitbutton-class"></a>CSplitButton クラス

クラスは、 `CSplitButton` 分割ボタンコントロールを表します。 分割ボタン コントロールは、ユーザーがボタンのメイン領域をクリックすると既定の動作を実行し、ユーザーがボタンのドロップダウン矢印をクリックするとドロップダウン メニューを表示します。

## <a name="syntax"></a>構文

```
class CSplitButton : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSplitButton:: CSplitButton](#csplitbutton)|`CSplitButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSplitButton:: Create](#create)|指定されたスタイルを使用して分割ボタンコントロールを作成し、現在のオブジェクトにアタッチし `CSplitButton` ます。|
|[CSplitButton:: SetDropDownMenu](#setdropdownmenu)|ユーザーが現在の分割ボタンコントロールのドロップダウン矢印をクリックしたときに表示されるドロップダウンメニューを設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|Name|説明|
|----------|-----------------|
|[CSplitButton:: OnDropDown](#ondropdown)|ユーザーが現在の分割ボタンコントロールのドロップダウン矢印をクリックしたときにシステムが送信する BCN_DROPDOWN 通知を処理します。|

## <a name="remarks"></a>解説

クラスは、 `CSplitButton` [CButton](../../mfc/reference/cbutton-class.md) クラスから派生します。 分割ボタンコントロールは、スタイルが BS_SPLITBUTTON ボタンコントロールです。 ユーザーがドロップダウン矢印をクリックすると、カスタムメニューが表示されます。 詳細については、「BS_SPLITBUTTON [」](/windows/win32/Controls/button-styles)および「BS_DEFSPLITBUTTON スタイル」を参照してください。

次の図は、ページャーコントロールと (1) 分割ボタンコントロールを含むダイアログボックスを示しています。 (2) ドロップダウン矢印が既にクリックされており、(3) サブメニューが表示されています。

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

このクラスの追加要件については、「 [Windows Vista コモンコントロールのビルド要件](../../mfc/build-requirements-for-windows-vista-common-controls.md)」を参照してください。

## <a name="csplitbuttoncreate"></a><a name="create"></a> CSplitButton:: Create

指定されたスタイルを使用して分割ボタンコントロールを作成し、現在のオブジェクトにアタッチし `CSplitButton` ます。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*\
からコントロールに適用されるスタイルのビットごとの組み合わせ (または)。 詳細については、「 [ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)」を参照してください。

*rect*\
からコントロールの位置とサイズを格納している [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体への参照。

*pParentWnd*\
からコントロールの親ウィンドウである [CWnd](../../mfc/reference/cwnd-class.md) オブジェクトへの null 以外のポインター。

*nID*\
からコントロールの ID。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="csplitbuttoncsplitbutton"></a><a name="csplitbutton"></a> CSplitButton:: CSplitButton

`CSplitButton` オブジェクトを構築します。 コンストラクターのパラメーターは、ユーザーが分割ボタンコントロールのドロップダウン矢印をクリックしたときに表示されるサブメニューを指定します。

```
CSplitButton();

CSplitButton(
    UINT nMenuId,
    UINT nSubMenuId)
CSplitButton(CMenu* pMenu)
```

### <a name="parameters"></a>パラメーター

*nMenuId*\
からメニューバーのリソース ID。

*nSubMenuId*\
からサブメニューのリソース ID。

*pMenu*\
からサブメニューを指定する [CMenu](../../mfc/reference/cmenu-class.md) オブジェクトへのポインター。 オブジェクトは、オブジェクトが `CSplitButton` `CMenu` スコープ外に出ると、オブジェクトとそれに関連付けられている HMENU を削除し `CSplitButton` ます。

### <a name="remarks"></a>解説

[CSplitButton:: Create](#create)メソッドを使用して分割ボタンコントロールを作成し、それをオブジェクトにアタッチし `CSplitButton` ます。

## <a name="csplitbuttonondropdown"></a><a name="ondropdown"></a> CSplitButton:: OnDropDown

ユーザーが現在の分割ボタンコントロールのドロップダウン矢印をクリックしたときにシステムが送信する BCN_DROPDOWN 通知を処理します。

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>パラメーター

*pNMHDR*\
から[BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown)通知に関する情報を格納している[NMHDR](/windows/win32/api/richedit/ns-richedit-nmhdr)構造体へのポインター。

*pResult*\
入出力(使用されません。値は返されません)。 [BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown) 通知の戻り値。

### <a name="remarks"></a>解説

分割ボタンコントロールのドロップダウン矢印をクリックすると、システムによって BCN_DROPDOWN 通知メッセージが送信されます。このメッセージは、メソッドによって `OnDropDown` 処理されます。 ただし、オブジェクトは、 `CSplitButton` 分割ボタンコントロールを含むコントロールに BCN_DROPDOWN 通知を転送しません。 そのため、格納しているコントロールは、通知に応答してカスタム動作をサポートすることはできません。

格納しているコントロールがサポートするカスタム動作を実装するには、オブジェクトではなく、BS_SPLITBUTTON のスタイルを持つ [CButton](../../mfc/reference/cbutton-class.md) オブジェクトを使用し `CSplitButton` ます。 次に、オブジェクトに BCN_DROPDOWN 通知のハンドラーを実装し `CButton` ます。 詳細については、「 [ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)」を参照してください。

分割ボタンコントロール自体がサポートするカスタムアクションを実装するには、 [メッセージリフレクション](../../mfc/tn062-message-reflection-for-windows-controls.md)を使用します。 クラスから独自のクラスを派生させ `CSplitButton` 、CMySplitButton などの名前を指定します。 次に、BCN_DROPDOWN 通知を処理するために、次のメッセージマップをアプリケーションに追加します。

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

## <a name="csplitbuttonsetdropdownmenu"></a><a name="setdropdownmenu"></a> CSplitButton:: SetDropDownMenu

ユーザーが現在の分割ボタンコントロールのドロップダウン矢印をクリックしたときに表示されるドロップダウンメニューを設定します。

```cpp
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>パラメーター

*nMenuId*\
からメニューバーのリソース ID。

*nSubMenuId*\
からサブメニューのリソース ID。

*pMenu*\
からサブメニューを指定する [CMenu](../../mfc/reference/cmenu-class.md) オブジェクトへのポインター。 オブジェクトは、オブジェクトが `CSplitButton` `CMenu` スコープ外に出ると、オブジェクトとそれに関連付けられている HMENU を削除し `CSplitButton` ます。

### <a name="remarks"></a>解説

*Nmenuid*パラメーターは、メニューバー項目の水平方向の一覧であるメニューバーを識別します。 *Nsubmenuid*パラメーターは、サブメニューを識別する0から始まるインデックス番号です。これは、各メニューバー項目に関連付けられているメニュー項目のドロップダウンリストです。 たとえば、一般的なアプリケーションには、メニューバー項目 "File"、"Edit"、および "Help" を含むメニューがあります。 "ファイル" メニューバー項目には、メニュー項目 "Open"、"Close"、および "Exit" を含むサブメニューがあります。 分割ボタンコントロールのドロップダウン矢印をクリックすると、コントロールにはメニューバーではなく、指定されたサブメニューが表示されます。

次の図は、ページャーコントロールと (1) 分割ボタンコントロールを含むダイアログボックスを示しています。 (2) ドロップダウン矢印が既にクリックされており、(3) サブメニューが表示されています。

![splitbutton およびページャー コントロールを含むダイアログ。](../../mfc/reference/media/splitbutton_pager.png "splitbutton およびページャー コントロールを含むダイアログ。")

### <a name="example"></a>例

次のコード例の最初のステートメントは、 [CSplitButton:: SetDropDownMenu](#setdropdownmenu) メソッドを示しています。 Visual Studio リソースエディターを使用してメニューを作成しました。このメニューには、メニューバー ID、IDR_MENU1 という名前が自動的に付けられます。 *Nsubmenuid*パラメーター (ゼロ) は、メニューバーの唯一のサブメニューを参照します。

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>関連項目

[CSplitButton クラス](../../mfc/reference/csplitbutton-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)
