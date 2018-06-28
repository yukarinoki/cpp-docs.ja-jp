---
title: CMFCSpinButtonCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
dev_langs:
- C++
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3531fd45bbccd351bd8f95ce0d4bb26de846b01
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039467"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl クラス
`CMFCSpinButtonCtrl`クラスは、スピン ボタン コントロールを描画するビジュアル マネージャーをサポートしています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|既定のコンストラクター|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|現在のスピン ボタン コントロールを再描画します。|  
  
## <a name="remarks"></a>Remarks  
 ビジュアル マネージャーを使用して、アプリケーションのスピン ボタン コントロールを描画する、交換のすべてのインスタンス、`CSpinButtonCtrl`クラス、`CMFCSpinButtonCtrl`クラスです。  
  
## <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCSpinButtonCtrl`クラスし、を使用してその`Create`メソッドです。  
  
 [!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxspinbuttonctrl.h  
  
##  <a name="ondraw"></a>  CMFCSpinButtonCtrl::OnDraw  
 現在のスピン ボタン コントロールを再描画します。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>Remarks  
 フレームワークによって、`CMFCSpinButtonCtrl::OnPaint`を処理するメソッド、 [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint)メッセージ、および、メソッドを呼び出してこの`CMFCSpinButtonCtrl::OnDraw`メソッドです。 フレームワークは、スピン ボタン コントロールを描画する方法をカスタマイズするには、このメソッドをオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)
