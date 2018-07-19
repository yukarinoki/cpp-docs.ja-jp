---
title: CMFCLinkCtrl クラス |Microsoft Docs
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
ms.openlocfilehash: 13f411f9f50b1a498dba718b41245f8fbb7c6e79
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851588"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl クラス
`CMFCLinkCtrl`クラス ボタンをハイパーリンクとして表示し、ボタンがクリックされたときに、リンクのターゲットを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|ボタンのテキストとして指定された URL が表示されます。|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|暗黙的なプロトコルを設定します (たとえば、"http:") の URL。|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|ボタンのテキストまたはビットマップを格納するボタンのサイズを変更します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|ボタンのフォーカスされた四角形が描画される前に、フレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>Remarks  
 派生したボタンをクリックすると、`CMFCLinkCtrl`クラス、フレームワークのパラメーターとして、ボタンの URL を渡して、`ShellExecute`メソッド。 次に、`ShellExecute`メソッドは、URL のターゲットを開きます。  
  
## <a name="example"></a>例  
 次の例のサイズを設定する方法を示します、`CMFCLinkCtrl`オブジェクト、および url と、ツールヒントを設定する方法、`CMFCLinkCtrl`オブジェクト。 この例は、[新しいコントロール サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxlinkctrl.h  
  
##  <a name="ondrawfocusrect"></a>  CMFCLinkCtrl::OnDrawFocusRect  
 ボタンのフォーカスされた四角形が描画される前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター。  
  
 [in]*rectClient*  
 リンク コントロールの外接する四角形にします。  
  
### <a name="remarks"></a>Remarks  
 ボタンのフォーカスされた四角形を描画するために、独自のコードを使用する場合に、このメソッドをオーバーライドします。  
  
##  <a name="seturl"></a>  CMFCLinkCtrl::SetURL  
 ボタンのテキストとして指定された URL が表示されます。  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszURL*  
 表示するボタンのテキスト。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="seturlprefix"></a>  CMFCLinkCtrl::SetURLPrefix  
 暗黙的なプロトコルを設定します (たとえば、"http:") の URL。  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszPrefix*  
 URL のプロトコルのプレフィックス。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用すると、URL プレフィックスを設定できます。 プレフィックスは、ボタンの表面上は表示されませんが、これを使用するには、URL のターゲットを参照します。  
  
##  <a name="sizetocontent"></a>  CMFCLinkCtrl::SizeToContent  
 ボタンのテキストまたはビットマップを格納するボタンのサイズを変更します。  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bVCenter*  
 ボタンのテキストと、リンク コントロールの上下の間に垂直方向にビットマップを中央揃えする場合は TRUEそれ以外の場合、FALSE です。 既定値は FALSE です。  
  
 [in]*bHCenter*  
 ボタンのテキストと、リンク コントロールの左側および右側との間の水平方向にビットマップを中央揃えする場合は TRUEそれ以外の場合、FALSE です。 既定値は FALSE です。  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)リンク コントロールの新しいサイズを格納しているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl クラス](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)
