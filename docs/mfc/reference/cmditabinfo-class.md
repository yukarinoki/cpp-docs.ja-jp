---
title: CMDITabInfo クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
dev_langs:
- C++
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b95706603c8fe8a8f53be8cd0db405cd649271f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmditabinfo-class"></a>CMDITabInfo クラス
`CMDITabInfo`クラスを使用するパラメーターを渡すを[cmdiframewndex::enablemditabbedgroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups)メソッドです。 MDI タブ付きグループの動作を制御するために、このクラスのメンバーを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMDITabInfo   
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMDITabInfo::Serialize](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMDITabInfo::m_bActiveTabCloseButton です。](#m_bactivetabclosebutton_)|指定するかどうか、**閉じる**ボタンがアクティブなタブのラベルに表示されます。|  
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|MDI タブ カラーするかどうかを指定します。|  
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|タブ グループが開かれたドキュメントの一覧を表示またはスクロール ボタンを表示するポップアップ メニューを表示するかどうかを指定します。|  
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|ユーザーがドラッグすることでタブの位置を入れ替えることができるかどうかを指定します。|  
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|タブのフレームがフラットかどうかを指定します。|  
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|各タブのラベルを表示するかどうかを指定、**閉じる**ボタンをクリックします。|  
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|カスタムのツールヒントが有効になっているかどうかを指定します。|  
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|MDI タブ上のアイコンを表示するかどうかを指定します。|  
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|各タブ ウィンドウの境界線のサイズを指定します。|  
|[CMDITabInfo::m_style](#m_style)|タブ ラベルのスタイルを指定します。|  
|[CMDITabInfo::m_tabLocation](#m_tablocation)|タブのラベルが最上部またはページの下部にあるかどうかを指定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、フレームワークによって作成される MDI タブ グループのパラメーターを指定します。  
  
## <a name="example"></a>例  
 次の例は、さまざまなメンバー変数の値を設定する方法を示します`CMDITabInfo`クラスです。  
  
 [!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmdiclientareawnd.h  
  
##  <a name="m_bactivetabclosebutton_"></a>  CMDITabInfo::m_bActiveTabCloseButton です。  
 指定するかどうか、**閉じる**ボタンがアクティブなタブのラベルに表示されます。  
  
```  
BOOL m_bActiveTabCloseButton;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、アクティブなタブのラベルが表示されます、**閉じる**ボタンをクリックします。 **閉じる**ボタンがタブ領域の右上隅から削除されます。 それ以外の場合、アクティブなタブのラベルは表示されない、**閉じる**ボタンをクリックします。 **閉じる**ボタンがタブ領域の右上隅に表示されます。  
  
##  <a name="m_bautocolor"></a>  CMDITabInfo::m_bAutoColor  
 各 MDI タブで、独自の色を持つかどうかを指定します。  
  
```  
BOOL m_bAutoColor;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、各タブは、独自の色になります。 色のセットは、MFC ライブラリによって管理されます。 それ以外の場合、タブは、空白で表示されます。 既定値は `FALSE` です。  
  
##  <a name="m_bdocumentmenu"></a>  CMDITabInfo::m_bDocumentMenu  
 各タブが開いているドキュメント タブ領域の右端の一覧を表示するポップアップ メニューを表示するかどうかを指定します。  
  
```  
BOOL m_bDocumentMenu;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、各タブ ウィンドウがタブ領域の右端に開かれたドキュメントの一覧を表示するポップアップ メニューを表示しますそれ以外の場合、タブ ウィンドウがタブ領域の右端にスクロール ボタンを表示します。 既定値は `FALSE` です。  
  
##  <a name="m_benabletabswap"></a>  CMDITabInfo::m_bEnableTabSwap  
 ユーザーがドラッグすることでタブの位置を入れ替えることができるかどうかを指定します。  
  
```  
BOOL m_bEnableTabSwap;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`ユーザーは、タブをドラッグしてタブの位置を変更することができます。 それ以外の場合、ユーザーは、タブの位置を変更することはできません。 既定値は `TRUE` です。  
  
##  <a name="m_bflatframe"></a>  CMDITabInfo::m_bFlatFrame  
 各タブ ウィンドウ フレームがフラットかどうかを指定します。  
  
```  
BOOL m_bFlatFrame;  
```  
  
##  <a name="m_btabclosebutton"></a>  CMDITabInfo::m_bTabCloseButton  
 各タブ ウィンドウを表示するかどうかを指定、**閉じる**ボタンをクリックします。  
  
```  
BOOL m_bTabCloseButton;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、各タブ ウィンドウが表示されます、**閉じる** タブの右端にボタンをクリックします。それ以外の場合、**閉じる**ボタンは表示されません。 既定値は `TRUE` です。  
  
##  <a name="m_btabcustomtooltips"></a>  CMDITabInfo::m_bTabCustomTooltips  
 タブにツールヒントを表示するかどうかを指定します。  
  
```  
BOOL m_bTabCustomTooltips;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、アプリケーションは、送信、`AFX_WM_ON_GET_TAB_TOOLTIP`メインフレームへのメッセージ。 このメッセージを処理するを使用して、`ON_REGISTERED_MESSAGE`マクロです。  
  
##  <a name="m_btabicons"></a>  CMDITabInfo::m_bTabIcons  
 MDI タブ上のアイコンを表示するかどうかを指定します。  
  
```  
BOOL m_bTabIcons;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、各 MDI タブのアイコンが表示されます。それ以外の場合、アイコンは、タブには表示されません。 既定値は `FALSE` です。  
  
##  <a name="m_ntabbordersize"></a>  CMDITabInfo::m_nTabBorderSize  
 (ピクセル単位) の各タブ ウィンドウの境界線のサイズを指定します。  
  
```  
int m_nTabBorderSize;  
```  
  
### <a name="remarks"></a>コメント  
 [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize)既定値を返します。  
  
##  <a name="m_style"></a>  CMDITabInfo::m_style  
 タブ ラベルのスタイルを指定します。  
  
```  
CMFCTabCtrl::Style m_style  
```  
  
### <a name="remarks"></a>コメント  
 タブ ラベルのスタイルのいずれかを指定します。  
  
 `STYLE_3D`  
 3D スタイル。  
  
 `STYLE_3D_ONENOTE`  
 Microsoft OneNote スタイルです。  
  
 `STYLE_3D_VS2005`  
 Microsoft Visual Studio 2005 スタイルです。  
  
 `STYLE_3D_SCROLLED`  
 四角形 タブのラベルが付いた 3D スタイル。  
  
 `STYLE_FLAT_SHARED_HORZ_SCROLL`  
 共有の水平スクロール バーのフラット スタイルです。  
  
 `STYLE_3D_ROUNDED_SCROLL`  
 Round タブのラベルが付いた 3D スタイル。  
  
##  <a name="m_tablocation"></a>  CMDITabInfo::m_tabLocation  
 タブのラベルが最上部またはページの下部にあるかどうかを指定します。  
  
```  
CMFCTabCtrl::Location m_tabLocation;  
```  
  
### <a name="remarks"></a>コメント  
 次の場所のフラグの 1 つのタブに適用されます。  
  
-   LOCATION_BOTTOM: タブのラベルは、ページの下部にあります。  
  
-   LOCATION_TOP: タブのラベルは、ページの上部にあります。  
  
##  <a name="serialize"></a>  CMDITabInfo::Serialize  
 読み取りまたはアーカイブからまたはアーカイブは、このオブジェクトに書き込みます。  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
 A [CArchive クラス](../../mfc/reference/carchive-class.md)シリアル化するオブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)   
 [MDI タブ付きグループ](../../mfc/mdi-tabbed-groups.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
