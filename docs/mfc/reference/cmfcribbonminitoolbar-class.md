---
title: CMFCRibbonMiniToolBar クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
ms.openlocfilehash: 5e5ac6c923640b7584d89a9c6f75d941deadddf3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754081"
---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar クラス

コンテキスト ポップアップ ツール バーを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|既定のコンストラクターです。|
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCRibbonMiniToolBar::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|( `CMFCPopupMenu::IsRibbonMiniToolBar`をオーバーライドします)。|
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|ツール バーに表示するコマンドのリストを設定します。|
|[CMFCRibbonMiniToolBar::Show](#show)|指定した画面座標に、ミニ ツール バーを表示します。|
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|コンテキスト メニューとミニ ツール バーが表示されます。|

## <a name="remarks"></a>解説

ミニ ツール バーは、通常、ユーザーがドキュメント内のオブジェクトを選択した後に表示されます。 たとえば、ユーザーがワード プロセッサ プログラム内のテキストを選択すると、アプリケーションでテキストの書式設定コマンドを含むミニ ツール バーが表示されます。

マウス ポインターがミニ ツール バーの境界外にあるときは、ミニ ツール バーは透明になります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

`CMFCRibbonPanelMenu`

[CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRibbonミニツールバー.h

## <a name="cmfcribbonminitoolbarsetcommands"></a><a name="setcommands"></a>コマンドバーを設定します。

ツール バーに表示するコマンドのリストを設定します。

```cpp
void SetCommands(
    CMFCRibbonBar* pRibbonBar,
    const CList<UINT,UINT>& lstCommands);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ミニ ツールバーが表示するボタンを検索するリボン バー。

*コマンド*<br/>
[in]ミニ ツールバーに表示するコマンドの一覧。 すべてのリボン カテゴリが検索され、関連付けられているボタンが検索されます。

### <a name="remarks"></a>解説

ミニ ツールバーに表示するコマンドの一覧を設定するには、この関数を使用します。

### <a name="example"></a>例

クラスのメソッドの使用方法を`SetCommands`次の例に示します`CMFCRibbonMiniToolBar`。 このコード スニペットは、 [MS Office 2007 デモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]

## <a name="cmfcribbonminitoolbarshow"></a><a name="show"></a>CMFCリボンミニツールバー::ショー

指定した画面座標に、ミニ ツール バーを表示します。

```
BOOL Show(
    int x,
    int y);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
[in]ミニ ツールバーの水平方向の位置を画面座標で指定します。

*Y*<br/>
[in]ミニ ツールバーの垂直位置を画面座標で指定します。

### <a name="return-value"></a>戻り値

ミニ ツールバーが正常に表示された場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcribbonminitoolbarshowwithcontextmenu"></a><a name="showwithcontextmenu"></a>メニューメニューを使用します。

コンテキスト メニューとミニ ツール バーが表示されます。

```
BOOL ShowWithContextMenu(
    int x,
    int y,
    UINT uiMenuResID,
    CWnd* pWndOwner);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
[in]画面座標でのコンテキスト メニューの水平位置を指定します。

*Y*<br/>
[in]画面座標でのコンテキスト メニューの垂直方向の位置を指定します。

*をクリックします。*<br/>
[in]表示するコンテキスト メニューのリソース ID を指定します。

*オーナー*<br/>
[in]コンテキスト メニューからメッセージを受信するウィンドウを識別します。

### <a name="return-value"></a>戻り値

コンテキスト メニューが正常に表示された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数を使用して、コンテキスト メニューを持つミニ ツールバーを表示します。 コンテキスト メニューは、ミニ ツールバーの 15 ピクセル下に配置されます。

## <a name="cmfcribbonminitoolbariscontextmenumode"></a><a name="iscontextmenumode"></a>メニューモードを使用します。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
BOOL IsContextMenuMode() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonminitoolbarisribbonminitoolbar"></a><a name="isribbonminitoolbar"></a>CMFCリボンミニツールバー::イズリボンミニツールバー

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual BOOL IsRibbonMiniToolBar() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
