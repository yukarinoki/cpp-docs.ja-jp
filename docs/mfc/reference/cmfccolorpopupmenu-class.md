---
title: CMFCColorPopupMenu クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66bdd0cdf9e9c13ceac6eb01716ae8c859462524
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu クラス
ユーザー、ドキュメントやアプリケーションで色を選択に使用するポップアップ メニューを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|`CMFCColorPopupMenu` オブジェクトを構築します。|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|ドッキング可能なティアオフ カラー バーを作成します。 (上書き[CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar))。|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|返します、 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)ポップアップ メニュー内に埋め込まれています。 (上書き[CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar))。|  
|`CMFCColorPopupMenu::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|オブジェクトを設定、プロパティ グリッド コントロールの埋め込み`CMFCColorBar`オブジェクト。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`m_bEnabledInCustomizeMode`|カラー バーを表示するかどうかを決定するブール値。|  
|`m_wndColorBar`|`CMFCColorBar`の色の選択を提供するオブジェクト。|  
  
### <a name="remarks"></a>コメント  
 このクラスは継承のポップアップ メニュー機能、`CMFCPopupMenu`クラスし、管理、`CMFCColorBar`の色の選択を提供するオブジェクト。 カスタマイズ モードでは、ツールバー framework が場合と`m_bEnabledInCustomizeMode`に設定されているメンバー `FALSE`、カラー バー オブジェクトは表示されません。 カスタマイズ モードの詳細については、次を参照してください[CMFCToolBar::IsCustomizeMode。](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 詳細については`CMFCColorBar`を参照してください[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcolorpopupmenu.h  
  
##  <a name="cmfccolorpopupmenu"></a>  CMFCColorPopupMenu::CMFCColorPopupMenu  
 `CMFCColorPopupMenu` オブジェクトを構築します。  
  
```  
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    int nHorzDockRows,  
    int nVertDockColumns,  
    COLORREF colorAutomatic,  
    UINT uiCommandID,  
    BOOL bStdColorDlg = FALSE);

 
CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic);

 
CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `colors`  
 フレームワークがポップアップ メニューに表示される色の配列。  
  
 [入力] `color`  
 既定値は、色を選択します。  
  
 [入力] `lpszAutoColor`  
 テキスト ラベル、*自動*(既定値) の色 ボタンまたは`NULL`です。  
  
 自動ボタンの標準のラベルは**自動**です。  
  
 [入力] `lpszOtherColor`  
 テキスト ラベル、*他*ボタンを他の色を表示、または`NULL`です。  
  
 その他のボタンの標準のラベルは**他の色**。  
  
 [入力] `lpszDocColors`  
 ドキュメントの色のボタンのテキスト ラベル。 ドキュメントのカラー パレットは、ドキュメントが現在使用されているすべての色を示します。  
  
 [入力] `lstDocColors`  
 ドキュメントが現在使用されている色の一覧。  
  
 [入力] `nColumns`  
 色の配列は、列の数。  
  
 [入力] `nHorzDockRows`  
 カラー バーが水平にドッキングされている行の数。  
  
 [入力] `nVertDockColumns`  
 カラー バーが垂直方向にドッキングされている列の数。  
  
 [入力] `colorAutomatic`  
 自動ボタンをクリックすると、フレームワークが適用される既定の色。  
  
 [入力] `uiCommandID`  
 カラー バー コントロールのコマンド id。  
  
 [入力] `bStdColorDlg`  
 標準のシステム カラー ダイアログ ボックスを表示するかどうかを示すブール値、または[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  ダイアログ ボックス。  
  
 [入力] `pParentBtn`  
 親ボタンへのポインター。  
  
 [入力] `nID`  
 コマンド ID。  
  
### <a name="remarks"></a>コメント  
 それぞれのオーバー ロードされたコンス トラクターのセット、`m_bEnabledInCustomizeMode`メンバー`FALSE`です。  
  
### <a name="example"></a>例  
 次の例で作成する方法、`CMFCColorPopupMenu`オブジェクト。  
  
 [!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar  
 ドッキング可能なティアオフ カラー バーを作成します。  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pWndMain`|ティアオフ バーの親ウィンドウへのポインター。|  
|[入力] `uiID`|ティアオフ バーのコマンド ID。|  
|[入力] `lpszName`|ティアオフ バーのウィンドウのテキスト。|  
  
### <a name="return-value"></a>戻り値  
 新しいティアオフ コントロール バー オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドを作成、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクトおよびにキャスト、 [CPane クラス](../../mfc/reference/cpane-class.md)ポインター。 この値をキャストすることができますに戻す、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)で説明するキャスト マクロのいずれかを使用してポインター [MFC クラス オブジェクトの型キャスト](../../mfc/reference/type-casting-of-mfc-class-objects.md)です。  
  
##  <a name="getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar  
 返します、 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)ポップアップ メニュー内に埋め込まれています。  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>戻り値  
 埋め込まれたへのポインター`CMFCPopupMenuBar`です。  
  
### <a name="remarks"></a>コメント  
 色のポップアップ メニューが埋め込まれた[CMFCPopupMenuBar クラス](../../mfc/reference/cmfcpopupmenubar-class.md)オブジェクト。 アプリケーションが別の埋め込み型を使用する場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="setproplist"></a>  CMFCColorPopupMenu::SetPropList  
 オブジェクトを設定、プロパティ グリッド コントロールの埋め込み`CMFCColorBar`オブジェクト。  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndList`  
 プロパティ グリッド コントロール オブジェクトへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
