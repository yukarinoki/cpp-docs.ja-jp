---
title: CMFCPropertyGridToolTipCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c284f5d5fdfee09349cc6eb9cbde38da21918d25
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040962"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl クラス
ツールヒントの実装を制御する、 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)使用して、ツールヒントを表示します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|`CMFCPropertyGridToolTipCtrl` オブジェクトを構築します。|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCPropertyGridToolTipCtrl::Create](#create)|ツール ヒント コントロールのウィンドウを作成します。|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|非アクティブ化し、ツール ヒント コントロールを非表示にします。|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|ツール ヒント コントロールの最後の位置の座標を返します。|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|ツール ヒント コントロールは表示されません。|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|[TranslateMessage](../../mfc/reference/cwinapp-class.md) および [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) の各 Windows 関数にディスパッチされる前に、ウィンドウ メッセージを変換するためにクラス [CWinApp](http://msdn.microsoft.com/library/windows/desktop/ms644934) で使用されます。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|ツールヒントのテキストと、ツールヒント ウィンドウの枠線の間隔を設定します。|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|ツール ヒント コントロールを表示します。|  
  
## <a name="remarks"></a>Remarks  
 プロパティ名でポインターを合わせると、ツールヒントが表示されます。 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)クラスは、ユーザーが見やすいようににツールヒントを表示します。 通常、ツールヒントの位置は、ポインターの位置によって決まります。 このクラスを使用すると、ツールヒントに表示プロパティ名され、プロパティ名が完全に表示されるように、自然なプロパティの拡張機能のようになります。  
  
 MFC は自動的にこのコントロールを作成してでそれを使用して、 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)です。  
  
## <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCPropertyGridToolTipCtrl`クラス、およびツールヒント コントロールを表示する方法です。  
  
 [!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxpropertygridtooltipctrl.h  
  
##  <a name="cmfcpropertygridtooltipctrl"></a>  CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 `CMFCPropertyGridToolTipCtrl` オブジェクトを構築します。  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="create"></a>  CMFCPropertyGridToolTipCtrl::Create  
 ツール ヒント コントロールのウィンドウを作成します。  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndParent*  
 親ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが作成された場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="deactivate"></a>  CMFCPropertyGridToolTipCtrl::Deactivate  
 非アクティブ化し、ツール ヒント コントロールを非表示にします。  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドの最後の位置とテキストを空の値にように設定呼び出しを将来[CMFCPropertyGridToolTipCtrl::Track](#track)ツールヒントを表示します。  
  
##  <a name="getlastrect"></a>  CMFCPropertyGridToolTipCtrl::GetLastRect  
 ツール ヒント コントロールの最後の位置の座標を返します。  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*rect*  
 ツール ヒント コントロールの最後の位置が含まれています。  
  
##  <a name="hide"></a>  CMFCPropertyGridToolTipCtrl::Hide  
 ツール ヒント コントロールは表示されません。  
  
```  
void Hide();
```  
  
##  <a name="settextmargin"></a>  CMFCPropertyGridToolTipCtrl::SetTextMargin  
 ツールヒントのテキストと、ツールヒント ウィンドウの枠線の間隔を設定します。  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nTextMargin*  
 ツールヒント コントロールのテキストと、ツールヒント ウィンドウの枠線の間隔を指定します。 既定値は、10 ピクセルです。  
  
##  <a name="track"></a>  CMFCPropertyGridToolTipCtrl::Track  
 ツール ヒント コントロールを表示します。  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*rect*  
 ツール ヒント コントロールのサイズと位置を指定します。  
  
 [in]*strText*  
 ツールヒントに表示されるテキストを指定します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドで指定されたサイズと位置でツールヒント コントロールを表示する*rect*です。 位置、サイズ、およびテキストが、前回のこのメソッドが呼び出された後に変更されていない場合は、このメソッドに効果がありません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
