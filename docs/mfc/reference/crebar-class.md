---
title: CReBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ea2a1047864c19be3f5bbd6c303b4b00fb132dc
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078770"
---
# <a name="crebar-class"></a>CReBar クラス
Rebar コントロールのレイアウト、永続性、および状態に関する情報を提供するコントロール バーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CReBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CReBar::AddBar](#addbar)|Rebar バンドに追加します。|  
|[CReBar::Create](#create)|Rebar コントロールを作成し、それにアタッチ、`CReBar`オブジェクト。|  
|[CReBar::GetReBarCtrl](#getrebarctrl)|基になる一般的なコントロールに直接アクセスをできます。|  
  
## <a name="remarks"></a>Remarks  
 Rebar オブジェクトは、子ウィンドウ、通常その他のコントロール、編集ボックス、ツールバー、リスト ボックスなどのさまざまなを含めることができます。 Rebar オブジェクトは、指定したビットマップをその子ウィンドウを表示できます。 アプリケーションに自動的にサイズを変更できる、rebar またはユーザー手動でサイズを変更できる、rebar をクリックするかのグリッパー バーをドラッグします。  
  
 ![RebarMenu の](../../mfc/reference/media/vc4sc61.gif "vc4sc61")  
  
## <a name="rebar-control"></a>Rebar コントロール  
 Rebar オブジェクトは、ツールバーのオブジェクトと同様に動作します。 Rebar では、クリックおよびドラッグ メカニズムを使用して、そのバンドのサイズを変更します。 Rebar コントロールでは、グリップ バー、ビットマップ、テキスト ラベル、および子ウィンドウの任意の組み合わせを 1 つまたは複数のバンドを含めることができます。 ただし、バンドは、1 つ以上の子ウィンドウを含めることはできません。  
  
 `CReBar` 使用して、 [CReBarCtrl](../../mfc/reference/crebarctrl-class.md)その実装を提供するクラス。 使用して rebar コントロールにアクセスすることができます[GetReBarCtrl](#getrebarctrl)コントロールのカスタマイズのオプションを活用するためにします。 Rebar コントロールの詳細については、次を参照してください。`CReBarCtrl`です。 Rebar コントロールの使用に関する詳細については、次を参照してください。[を使用して CReBarCtrl](../../mfc/using-crebarctrl.md)です。  
  
> [!CAUTION]
>  Rebar および rebar コントロール オブジェクトでは、MFC コントロール バーのドッキングはサポートされません。 場合`CRebar::EnableDocking`が呼び出されると、アプリが評価されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxext.h  
  
##  <a name="addbar"></a>  CReBar::AddBar  
 Rebar バンドを追加するには、このメンバー関数を呼び出します。  
  
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
 *pBar*  
 ポインター、 `CWnd` rebar に挿入する子ウィンドウであるオブジェクト。 参照先オブジェクトには、 **WS_CHILD**です。  
  
 *lpszText*  
 Rebar に表示するテキストを含む文字列へのポインター。 **NULL**既定です。 含まれるテキスト*lpszText* ; の子ウィンドウの一部ではない自体 rebar 上にあります。  
  
 *pbmp*  
 ポインター、 `CBitmap` rebar の背景に表示するオブジェクト。 **NULL**既定です。  
  
 *dwStyle*  
 A `DWORD` rebar に適用するスタイルを含むです。 参照してください、**は**関数の Win32 構造説明[REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393)バンド スタイルの完全な一覧についてはします。  
  
 *clrFore*  
 A **COLORREF** rebar の前景色を表す値です。  
  
 *clrBack*  
 A **COLORREF** rebar の背景色を表す値です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]  
  
##  <a name="create"></a>  CReBar::Create  
 Rebar を作成するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentWnd*  
 ポインター、`CWnd`ウィンドウ、ステータス バーの親であるオブジェクト。 通常、フレーム ウィンドウです。  
  
 *ツール バー*  
 Rebar コントロールのスタイル。 既定では、 **RBS_BANDBORDERS**を絞り込む rebar コントロール内の隣接するバンドの区切り線を表示します。 参照してください[Rebar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb774377)スタイルの一覧については、Windows SDK に含まれています。  
  
 *dwStyle*  
 Rebar ウィンドウ スタイル。  
  
 *nID*  
 Rebar の子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照して[CReBar::AddBar](#addbar)です。  
  
##  <a name="getrebarctrl"></a>  CReBar::GetReBarCtrl  
 このメンバー関数は、基になる一般的なコントロールに直接アクセスを許可します。  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照、 [CReBarCtrl](../../mfc/reference/crebarctrl-class.md)オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数、rebar のカスタマイズに Windows rebar のコモン コントロールの機能を活用するために呼び出します。 呼び出すと`GetReBarCtrl`への参照オブジェクトが返されます、`CReBarCtrl`オブジェクトのメンバー関数の両方のセットを使用できるようにします。  
  
 使用しての詳細については`CReBarCtrl`、rebar をカスタマイズするを参照してください。[を使用して CReBarCtrl](../../mfc/using-crebarctrl.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCIE](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



