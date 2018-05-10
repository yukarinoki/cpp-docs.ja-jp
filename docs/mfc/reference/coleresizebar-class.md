---
title: COleResizeBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs:
- C++
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf000b45e2bd24ec40e1ae15001c3df46d1b12c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="coleresizebar-class"></a>COleResizeBar クラス
OLE の埋め込み先アイテムのサイズ変更をサポートするコントロール バーの一種です。  
  
## <a name="syntax"></a>構文  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](#coleresizebar)|`COleResizeBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleResizeBar::Create](#create)|作成し、Windows 子ウィンドウを初期化しに関連付けます、`COleResizeBar`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `COleResizeBar` オブジェクトとして表示されます、 [CRectTracker](../../mfc/reference/crecttracker-class.md)斜線の外枠でと外側のハンドルのサイズを変更します。  
  
 `COleResizeBar` オブジェクトから派生するフレーム ウィンドウ オブジェクトの通常の埋め込みのメンバーである、 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)クラスです。  
  
 詳細については、記事を参照してください。[アクティベーション](../../mfc/activation-cpp.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="coleresizebar"></a>  COleResizeBar::COleResizeBar  
 `COleResizeBar` オブジェクトを構築します。  
  
```  
COleResizeBar();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す**作成**をサイズ変更バー オブジェクトを作成します。  
  
##  <a name="create"></a>  COleResizeBar::Create  
 子ウィンドウを作成しに関連付けます、`COleResizeBar`オブジェクト。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 サイズ変更バーの親ウィンドウへのポインター。  
  
 `dwStyle`  
 指定します、[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)属性。  
  
 `nID`  
 子ウィンドウのサイズ変更バーの id。  
  
### <a name="return-value"></a>戻り値  
 サイズ変更バーが作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)
