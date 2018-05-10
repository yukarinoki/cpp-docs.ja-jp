---
title: CMFCLinkCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
dev_langs:
- C++
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b91bc8fec3eebba5f3037633b5840d9b1abca731
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl クラス
`CMFCLinkCtrl`クラスは、ボタンをハイパーリンクとして表示し、ボタンがクリックされたときに、リンクのターゲットを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|ボタンのテキストとして指定された URL を表示します。|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|暗黙的なプロトコルを設定します (たとえば、"http:")、URL のです。|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|ボタンのテキストまたはビットマップを格納するボタンのサイズを変更します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|ボタンのフォーカスされた四角形が描画される前に、フレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 派生したボタンをクリックすると、`CMFCLinkCtrl`クラス、フレームワーク、ボタンの URL をパラメーターとして渡しますを`ShellExecute`メソッドです。 続いて、`ShellExecute`メソッドは、URL のターゲットを開きます。  
  
## <a name="example"></a>例  
 次の例でのサイズを設定する方法、`CMFCLinkCtrl`オブジェクト、および url とのツールヒントを設定する方法、`CMFCLinkCtrl`オブジェクト。 この例の一部である、[新しいコントロール サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxlinkctrl.h  
  
##  <a name="ondrawfocusrect"></a>  CMFCLinkCtrl::OnDrawFocusRect  
 ボタンのフォーカスされた四角形が描画される前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rectClient`  
 リンク コントロールに外接する四角形。  
  
### <a name="remarks"></a>コメント  
 独自のコードを使用して、ボタンのフォーカスされた四角形を描画する場合は、このメソッドをオーバーライドします。  
  
##  <a name="seturl"></a>  CMFCLinkCtrl::SetURL  
 ボタンのテキストとして指定された URL を表示します。  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszURL`  
 表示するボタンのテキスト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="seturlprefix"></a>  CMFCLinkCtrl::SetURLPrefix  
 暗黙的なプロトコルを設定します (たとえば、"http:")、URL のです。  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszPrefix`  
 URL のプロトコルのプレフィックス。  
  
### <a name="remarks"></a>コメント  
 URL プレフィックスを設定するのにには、このメソッドを使用します。 プレフィックスは、ボタンの表面上は表示されませんが、これを使用するには URL のターゲットを参照しやすくします。  
  
##  <a name="sizetocontent"></a>  CMFCLinkCtrl::SizeToContent  
 ボタンのテキストまたはビットマップを格納するボタンのサイズを変更します。  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bVCenter`  
 `TRUE` ボタンのテキストと、リンク コントロールの上下の垂直方向にビットマップの中央にそれ以外の場合、`FALSE`です。 既定値は `FALSE` です。  
  
 [入力] `bHCenter`  
 `TRUE` ボタンのテキストと、リンク コントロールの左右の間で水平方向にビットマップの中央にそれ以外の場合、`FALSE`です。 既定値は `FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)リンク コントロールの新しいサイズを含むオブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl クラス](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)
