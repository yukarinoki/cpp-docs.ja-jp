---
title: CReBar クラス |Microsoft Docs
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
ms.openlocfilehash: 1acc2d5918bea040e1f004e8a1d11ceee3146f89
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848620"
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
|[CReBar::Create](#create)|Rebar コントロールを作成し、それにアタッチします、`CReBar`オブジェクト。|  
|[CReBar::GetReBarCtrl](#getrebarctrl)|基になる一般的なコントロールに直接アクセスをできます。|  
  
## <a name="remarks"></a>Remarks  
 Rebar オブジェクトは、さまざまな子ウィンドウ、通常は他のコントロールのエディット ボックス、ツールバー、リスト ボックスなどを含めることができます。 Rebar オブジェクトは、指定したビットマップをその子ウィンドウを表示できます。 アプリケーションに自動的に、rebar にサイズを変更または、ユーザーがクリックしてまたはグリッパー バーをドラッグして、rebar を手動でサイズ変更します。  
  
 ![RebarMenu の](../../mfc/reference/media/vc4sc61.gif "vc4sc61")  
  
## <a name="rebar-control"></a>Rebar コントロール  
 Rebar オブジェクトは、ツールバーのオブジェクトと同様に動作します。 Rebar はバンドのサイズを変更するのに をクリック アンド ドラッグ メカニズムを使用します。 Rebar コントロールのグリップ バー、ビットマップ、テキスト ラベル、および子ウィンドウの任意の組み合わせを 1 つまたは複数のバンドを含めることができます。 ただし、バンドは、1 つ以上の子ウィンドウを含めることはできません。  
  
 `CReBar` 使用して、 [crebarctrl の比較](../../mfc/reference/crebarctrl-class.md)その実装を提供するクラス。 を通じて rebar コントロールにアクセスすることができます[GetReBarCtrl](#getrebarctrl)コントロールのカスタマイズのオプションを活用するためにします。 Rebar コントロールの詳細については、次を参照してください。`CReBarCtrl`します。 Rebar コントロールの使用方法の詳細については、次を参照してください。[を使用して CReBarCtrl](../../mfc/using-crebarctrl.md)します。  
  
> [!CAUTION]
>  Rebar および rebar コントロールのオブジェクトでは、MFC コントロール バーのドッキングはサポートされません。 場合`CRebar::EnableDocking`が呼び出されると、アプリケーションがアサートされます。  
  
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
 ポインター、 `CWnd` rebar に挿入する子ウィンドウにあるオブジェクト。 参照先オブジェクトには、WS_CHILD 必要があります。  
  
 *lpszText*  
 Rebar に表示するテキストを含む文字列へのポインター。 既定では NULL です。 含まれるテキスト*lpszText* ; の子ウィンドウの一部でない rebar 自体で実行されます。  
  
 *pbmp*  
 ポインター、 `CBitmap` rebar の背景に表示するオブジェクト。 既定では NULL です。  
  
 *dwStyle*  
 Rebar に適用するスタイルを含む DWORD。 参照してください、`fStyle`関数の説明で、Win32 構造[REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393)バンド スタイルの完全な一覧についてはします。  
  
 *clrFore*  
 Rebar の前景色を表す COLORREF 値。  
  
 *clrBack*  
 Rebar の背景色を表す COLORREF 値。  
  
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
 ポインター、`CWnd`ステータス バーの親である Windows ウィンドウを持つオブジェクト。 通常、フレーム ウィンドウです。  
  
 *ツール バー*  
 Rebar コントロールのスタイル。 既定では、RBS_BANDBORDERS rebar コントロール内の隣接するバンドを分離する細い線を表示します。 参照してください[Rebar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb774377)スタイルの一覧については、Windows SDK に含まれています。  
  
 *dwStyle*  
 Rebar のウィンドウ スタイル。  
  
 *nID*  
 Rebar の子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例をご覧ください[CReBar::AddBar](#addbar)します。  
  
##  <a name="getrebarctrl"></a>  CReBar::GetReBarCtrl  
 このメンバー関数は、基になる一般的なコントロールに直接アクセスをできます。  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照を[crebarctrl の比較](../../mfc/reference/crebarctrl-class.md)オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 Windows rebar の一般的なコントロール、rebar のカスタマイズでの機能を活用するには、このメンバー関数を呼び出します。 呼び出すと`GetReBarCtrl`への参照オブジェクトが返されます、`CReBarCtrl`オブジェクト メンバー関数のいずれかのセットを使用できるようにします。  
  
 使用しての詳細については`CReBarCtrl`、rebar をカスタマイズするを参照してください。[を使用して CReBarCtrl](../../mfc/using-crebarctrl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCIE](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



