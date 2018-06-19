---
title: CAutoHideDockSite クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
dev_langs:
- C++
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4abdb76523f0b7b1ab87beb6daaf723c4dff5cc8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353642"
---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite クラス
`CAutoHideDockSite`拡張、 [CDockSite クラス](../../mfc/reference/cdocksite-class.md)自動非表示のドッキング ペインを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CAutoHideDockSite::CAutoHideDockSite`|`CAutoHideDockSite` オブジェクトを構築します。|  
|`CAutoHideDockSite::~CAutoHideDockSite`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|示すかどうか、`CAutoHideDockSite`ウィンドウ メニューに表示されます。|  
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|基本ウィンドウのオブジェクトはから派生するかどうかを判断、 [CMFCAutoHideBar クラス](../../mfc/reference/cmfcautohidebar-class.md)です。|  
|[CAutoHideDockSite::DockPane](#dockpane)|このペインをドッキング`CAuotHideDockSite`オブジェクト。|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|画面座標でドッキング サイトのサイズを取得します。|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|上ペインを再描画、`CAutoHideDockSite`グローバル余白とボタン間のスペースを使用します。|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|ドッキング バーの左側にある余白を設定します。|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|ドッキング バーの右側にある余白を設定します。|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|呼び出し[CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode)上のオブジェクトに対して、`CAutoHideDockSite`です。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|ツールバーとドッキング バーの端の間の空白のサイズを定義します。 この領域は、左のエッジか、ドッキング領域の配置に応じて、上端から測定されます。|  
  
## <a name="remarks"></a>コメント  
 呼び出すと[CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)、フレームワークが自動的に作成、`CAutoHideDockSite`オブジェクト。 ほとんどの場合、インスタンスを作成またはこのクラスを直接使用することはできません。  
  
 ドッキング バーがドッキング ペインの左側にあるとの左側にあるギャップ、 [CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>例  
 次の例は、取得する方法を示します、`CAutoHideDockSite`オブジェクトから、`CMFCAutoHideBar`オブジェクト、およびドッキング バーの左と右余白を設定する方法です。  
  
 [!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxautohidedocksite.h  
  
##  <a name="canacceptpane"></a>  CAutoHideDockSite::CanAcceptPane  
 かどうかを基本ウィンドウ、 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)から派生したオブジェクト、または`CMFCAutoHideBar`です。  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pBar`|フレームワークをテストする基本ペインです。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合`pBar`から派生した`CMFCAutoHideBar`です。`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 派生した基本ウィンドウのオブジェクトが場合`CMFCAutoHideBar`、含めることができます、`CAutoHideDockSite`です。  
  
##  <a name="dockpane"></a>  CAutoHideDockSite::DockPane  
 このペインをドッキング[CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)オブジェクト。  
  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pWnd`|フレームワークのドッキング ウィンドウです。|  
|[入力] `dockMethod`|ウィンドウのオプションをドッキングします。|  
|[入力] `lpRect`|ドッキング ウィンドウの境界を指定する四角形。|  
  
### <a name="remarks"></a>コメント  
 既定の実装は、パラメーターを使用しない`dockMethod`、将来使用するために提供されています。  
  
 場合`lpRect`は`NULL`フレームワークは、ウィンドウをドッキング サイトの既定の場所に格納します。 ドッキング サイトが水平方向の場合は、既定の場所は、ドッキング サイトの一番左にあるです。 それ以外の場合、既定の場所は、ドッキング サイトの上部にあるです。  
  
##  <a name="getalignrect"></a>  CAutoHideDockSite::GetAlignRect  
 画面座標でドッキング サイトのサイズを取得します。  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `rect`|四角形への参照。 メソッドは、この四角形にドッキング サイトのサイズを格納します。|  
  
### <a name="remarks"></a>コメント  
 四角形は、それらは含まれないように、オフセットの余白の調整されます。  
  
##  <a name="m_nextraspace"></a>  CAutoHideDockSite::m_nExtraSpace  
 端の間の空白のサイズ、 [CAutoHideDockSite クラス](../../mfc/reference/cautohidedocksite-class.md)と[CMFCAutoHideBar クラス](../../mfc/reference/cmfcautohidebar-class.md)オブジェクト。  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>コメント  
 ときに、`CMFCAutoHideBar`にドッキングされて、 `CAutoHideDockSite`、全体のドッキング サイトを占有する必要があります。 このグローバル変数の左端または上端の枠線の間で余分なスペースを制御する、`CMFCAutoHideBar`と、対応する`CAutoHideDockSite`エッジ。 上または左のエッジを使用するかどうかは、現在の配置によって異なります。  
  
##  <a name="setoffsetleft"></a>  CAutoHideDockSite::SetOffsetLeft  
 ドッキング バーの左側にある余白を設定します。  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 新しいオフセット。  
  
### <a name="remarks"></a>コメント  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)オブジェクトが静的に配置されている、`CAutoHideDockSite`オブジェクト。 つまり、ユーザーの場所に手動で変更ことはできません`CMFCAutoHideBar`オブジェクト。 `SetOffsetLeft`メソッド、左端の左側にある間の間隔を制御する`CMFCAutoHideBar`およびの左側にある、`CAutoHideDockSite`です。  
  
##  <a name="setoffsetright"></a>  CAutoHideDockSite::SetOffsetRight  
 ドッキング バーの右側にある余白を設定します。  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nOffset`  
 新しいオフセット。  
  
### <a name="remarks"></a>コメント  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)オブジェクトが静的に配置されている、`CAutoHideDockSite`オブジェクト。 つまり、ユーザーの場所に手動で変更ことはできません、`CMFCAutoHideBar`オブジェクト。 `SetOffsetRight`メソッドは、右端の右側にある間の間隔を制御`CMFCAutoHideBar`およびの右側にある、`CAutoHideDockSite`です。  
  
##  <a name="repositionpanes"></a>  CAutoHideDockSite::RepositionPanes  
 上ペインを再描画、 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)です。  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `rectNewClientArea`|予約済みの値。|  
  
### <a name="remarks"></a>コメント  
 既定の実装が使用しない`rectNewClientArea`です。 [グローバル] ツールバーの余白とボタン間のスペースを使用して、ペインが再描画します。  
  
##  <a name="unsetautohidemode"></a>  CAutoHideDockSite::UnSetAutoHideMode  
 呼び出し[CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode)ドッキング サイト上のオブジェクト。  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pAutoHideToolbar`|ポインター、 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)オブジェクト ペインにあります、`CAutoHideDockSite`です。|  
  
### <a name="remarks"></a>コメント  
 このメソッドを含む行を検索`pAutoHideToolbar`です。 呼び出す`CMFCAutoHideBar.UnSetAutoHideMode`すべてに対して、`CMFCAutoHideBar`その行にオブジェクト。 場合`pAutoHideToolbar`が見つからないか、 `NULL`、このメソッドを呼び出します`CMFCAutoHideBar.UnSetAutoHideMode`すべて、`CMFCAutoHideBar`でオブジェクトを`CAutoHideDockSite`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockSite クラス](../../mfc/reference/cdocksite-class.md)
