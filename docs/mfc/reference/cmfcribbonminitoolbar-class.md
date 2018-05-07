---
title: CMFCRibbonMiniToolBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d8aebd796e0edb587e18db910df808fa349ca37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|既定のコンストラクター|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonMiniToolBar::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(`CMFCPopupMenu::IsRibbonMiniToolBar` をオーバーライドします)。|  
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|ツール バーに表示するコマンドのリストを設定します。|  
|[CMFCRibbonMiniToolBar::Show](#show)|指定した画面座標に、ミニ ツール バーを表示します。|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|コンテキスト メニューとミニ ツール バーが表示されます。|  
  
## <a name="remarks"></a>コメント  
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonMiniToolBar.h  
  
##  <a name="setcommands"></a>  CMFCRibbonMiniToolBar::SetCommands  
 ツール バーに表示するコマンドのリストを設定します。  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRibbonBar`  
 ミニ ツールバーを表示するボタンの検索、リボン バー。  
  
 [入力] `lstCommands`  
 ミニ ツールバーに表示されるコマンドの一覧。 関連付けられたボタンを検索するには、すべてのリボン カテゴリが検索されます。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、ミニ ツールバーに表示されるコマンドの一覧を設定できます。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`SetCommands`のメソッド、`CMFCRibbonMiniToolBar`クラスです。 このコード スニペットの一部である、 [MS Office 2007 デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>  CMFCRibbonMiniToolBar::Show  
 指定した画面座標に、ミニ ツール バーを表示します。  
  
```  
BOOL Show(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 画面座標では、ミニ ツールバーの水平方向の位置を指定します。  
  
 [入力] `y`  
 画面座標では、ミニ ツールバーの垂直方向の位置を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ミニ ツールバーが正常に表示された場合それ以外の場合、`FALSE`です。  
  
##  <a name="showwithcontextmenu"></a>  CMFCRibbonMiniToolBar::ShowWithContextMenu  
 コンテキスト メニューとミニ ツール バーが表示されます。  
  
```  
BOOL ShowWithContextMenu(
    int x,  
    int y,  
    UINT uiMenuResID,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 画面座標でコンテキスト メニューの水平方向の位置を指定します。  
  
 [入力] `y`  
 画面座標でコンテキスト メニューの垂直方向の位置を指定します。  
  
 [入力] `uiMenuResID`  
 表示するコンテキスト メニューのリソース ID を指定します。  
  
 [入力] `pWndOwner`  
 コンテキスト メニューからメッセージを受信するウィンドウを識別します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` コンテキスト メニューが正常に表示された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 コンテキスト メニューのあるミニ ツールバーを表示するのにには、この関数を使用します。 コンテキスト メニューは、ミニ ツールバーの下の位置指定の 15 ピクセルです。  
  
##  <a name="iscontextmenumode"></a>  CMFCRibbonMiniToolBar::IsContextMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isribbonminitoolbar"></a>  CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
