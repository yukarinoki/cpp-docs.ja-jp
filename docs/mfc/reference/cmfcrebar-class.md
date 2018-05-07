---
title: CMFCReBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
dev_langs:
- C++
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abb880c1add83ec03d787c28b816f2e82caeddd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcrebar-class"></a>CMFCReBar クラス
A`CMFCReBar`オブジェクトは、レイアウト、永続性、および rebar コントロールの状態情報を提供するコントロール バーです。  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
## <a name="syntax"></a>構文  
  
```  
class CMFCReBar : public CPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCReBar::AddBar](#addbar)|Rebar バンドに追加します。|  
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(上書き[cbasepane::calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout))。|  
|[CMFCReBar::CanFloat](#canfloat)|(上書き[CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat))。|  
|[CMFCReBar::Create](#create)|Rebar コントロールを作成し、それにアタッチ、`CMFCReBar`オブジェクト。|  
|[CMFCReBar::EnableDocking](#enabledocking)|(上書き[CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking))。|  
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||  
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|基になるに直接アクセスできる[CReBarCtrl](../../mfc/reference/crebarctrl-class.md)コモン コントロールです。|  
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(上書き[cpane::onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu))。|  
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(上書き[CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest))。|  
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(上書き[CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/e139f06a-9793-4ee2-bc3d-517389368c77))。|  
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(上書き[CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment))。|  
  
## <a name="remarks"></a>コメント  
 A`CMFCReBar`オブジェクトは、さまざまな子ウィンドウを含めることができます。 これには、エディット ボックス、ツールバー、およびリスト ボックスが含まれます。 サイズを変更する、rebar プログラムでは、またはユーザー手動でサイズを変更できる、rebar のグリッパー バーをドラッグしています。 任意のビットマップに rebar オブジェクトの背景を設定することもできます。  
  
 Rebar オブジェクトは、ツールバーのオブジェクトと同様に動作します。 Rebar コントロールは、1 つまたは複数のバンドを含めることができ、各バンドはグリップ バー、ビットマップ、テキスト ラベル、および子ウィンドウを含めることができます。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCReBar`クラスです。 この例では、rebar コントロールを作成し、帯域外を追加する方法を示します。 バンドは、内部ツールバーとして機能します。 このコード スニペットの一部である、 [Rebar のテストのサンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRebar.h  
  
##  <a name="addbar"></a>  CMFCReBar::AddBar  
 Rebar バンドに追加します。  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pBar`  
 Rebar に挿入するのには、子ウィンドウへのポインター。 参照先オブジェクトには、 **WS_CHILD**ウィンドウ スタイル。  
  
 [入力] `pszText`  
 Rebar に表示するテキストを指定します。 テキストは、子ウィンドウの一部ではありません。 代わりに、rebar 自体に表示されます。  
  
 [in][out] `pbmp`  
 Rebar の背景に表示されるビットマップを指定します。  
  
 [入力] `dwStyle`  
 バンドに適用するスタイルが含まれています。 帯域外スタイルの一覧については、説明を参照してください。`fStyle`で、 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) Windows SDK のドキュメントの構造体。  
  
 [入力] `clrFore`  
 Rebar の前景色を表します。  
  
 [入力] `clrBack`  
 Rebar の背景色を表します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` rebar; に、帯域外を正常に追加する場合それ以外の場合、`FALSE`です。  
  
##  <a name="create"></a>  CMFCReBar::Create  
 Rebar コントロールを作成し、それにアタッチ、 [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)オブジェクト。  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out] `pParentWnd`  
 この rebar コントロールの親ウィンドウへのポインター。  
  
 [入力] `dwCtrlStyle`  
 Rebar コントロールのスタイルを指定します。 既定のスタイル値は**RBS_BANDBORDERS**」が表示されますが、rebar コントロール上の隣接するバンドの区切り線を絞り込みます。 有効なスタイルの一覧は、次を参照してください。 [Rebar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb774377)Windows SDK のドキュメントです。  
  
 [入力] `dwStyle`  
 Rebar コントロールのウィンドウ スタイル。 有効なスタイルの一覧は、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。  
  
 [入力] `nID`  
 Rebar の子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 `TRUE` rebar が正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrebarctrl"></a>  CMFCReBar::GetReBarCtrl  
 直接アクセスできる`CReBarCtrl`の基になる一般的なコントロール`CMFCReBar`オブジェクト。  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 基になるへの参照を`CReBarCtrl`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して、rebar をカスタマイズする際に、Windows rebar の一般的なコントロールの機能の活用します。  
  
##  <a name="calcfixedlayout"></a>  CMFCReBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bStretch`  
 [入力] `bHorz`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="canfloat"></a>  CMFCReBar::CanFloat  

  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enabledocking"></a>  CMFCReBar::EnableDocking  

  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrebarbandinfosize"></a>  CMFCReBar::GetReBarBandInfoSize  

  
```  
UINT GetReBarBandInfoSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowcontrolbarmenu"></a>  CMFCReBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CPoint`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ontoolhittest"></a>  CMFCReBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 [入力] `pTI`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onupdatecmdui"></a>  CMFCReBar::OnUpdateCmdUI  

  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTarget`  
 [入力] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpanealignment"></a>  CMFCReBar::SetPaneAlignment  

  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CReBarCtrl クラス](../../mfc/reference/crebarctrl-class.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)
