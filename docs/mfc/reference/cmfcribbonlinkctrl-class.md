---
title: CMFCRibbonLinkCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CopyFrom
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetCompactSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetRegularSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetToolTipText
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::IsDrawTooltipImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDraw
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDrawMenuImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnMouseMove
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnSetIcon
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OpenLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::SetLink
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLinkCtrl [MFC], CMFCRibbonLinkCtrl
- CMFCRibbonLinkCtrl [MFC], CopyFrom
- CMFCRibbonLinkCtrl [MFC], GetCompactSize
- CMFCRibbonLinkCtrl [MFC], GetLink
- CMFCRibbonLinkCtrl [MFC], GetRegularSize
- CMFCRibbonLinkCtrl [MFC], GetToolTipText
- CMFCRibbonLinkCtrl [MFC], IsDrawTooltipImage
- CMFCRibbonLinkCtrl [MFC], OnDraw
- CMFCRibbonLinkCtrl [MFC], OnDrawMenuImage
- CMFCRibbonLinkCtrl [MFC], OnMouseMove
- CMFCRibbonLinkCtrl [MFC], OnSetIcon
- CMFCRibbonLinkCtrl [MFC], OpenLink
- CMFCRibbonLinkCtrl [MFC], SetLink
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9267dd6ab89871bcf8058529f32eb3686be937df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368437"
---
# <a name="cmfcribbonlinkctrl-class"></a>CMFCRibbonLinkCtrl クラス
リボン上に配置するハイパーリンクを実装します。 ハイパーリンクをクリックすると、Web ページが表示されます。  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonLinkCtrl : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl](#cmfcribbonlinkctrl)|`CMFCRibbonLinkCtrl` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonLinkCtrl::CopyFrom](#copyfrom)|(`CMFCRibbonButton::CopyFrom` をオーバーライドします)。|  
|[CMFCRibbonLinkCtrl::GetCompactSize](#getcompactsize)|(上書き[cmfcribbonbutton::getcompactsize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize))。|  
|[CMFCRibbonLinkCtrl::GetLink](#getlink)|ハイパーリンクの値を返します。|  
|[CMFCRibbonLinkCtrl::GetRegularSize](#getregularsize)|(上書き[cmfcribbonbutton::getregularsize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize))。|  
|[CMFCRibbonLinkCtrl::GetToolTipText](#gettooltiptext)|(上書き[cmfcribbonbutton::gettooltiptext](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext))。|  
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](#isdrawtooltipimage)|(`CMFCRibbonButton::IsDrawTooltipImage` をオーバーライドします)。|  
|[CMFCRibbonLinkCtrl::OnDraw](#ondraw)|(上書き[cmfcribbonbutton::ondraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw))。|  
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](#ondrawmenuimage)|(上書き[cmfcribbonbaseelement::ondrawmenuimage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage))。|  
|[CMFCRibbonLinkCtrl::OnMouseMove](#onmousemove)|(`CMFCRibbonButton::OnMouseMove` をオーバーライドします)。|  
|[CMFCRibbonLinkCtrl::OnSetIcon](#onseticon)||  
|[CMFCRibbonLinkCtrl::OpenLink](#openlink)|ハイパーリンクで指定されている Web ページを開きます。|  
|[CMFCRibbonLinkCtrl::SetLink](#setlink)|ハイパーリンクの値を設定します。|  
  
## <a name="remarks"></a>コメント  
 ハイパーリンクを作成した後に追加パネルを呼び出して[cmfcribbonpanel::add](../../mfc/reference/cmfcribbonpanel-class.md#add)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md) [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonLinkCtrl.h  
  
##  <a name="cmfcribbonlinkctrl"></a>  CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl  
 構築して初期化、 [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)オブジェクト。  
  
```  
CMFCRibbonLinkCtrl(
    UINT nID,  
    LPCTSTR lpszText,  
    LPCTSTR lpszLink);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 リンク コントロールがクリックされたときに実行されるコマンドのコマンド ID を指定します。  
  
 [入力] `lpszText`  
 リンク コントロールに表示するラベルを指定します。  
  
 [入力] `lpszLink`  
 リンク コントロールに関連付けられているハイパーリンクを指定します。  
  
### <a name="example"></a>例  
 次の例でのコンス トラクターを使用する方法、`CMFCRibbonLinkCtrl`クラスです。 このコード スニペットの一部である、[リボン ガジェット サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]  
  
##  <a name="copyfrom"></a>  CMFCRibbonLinkCtrl::CopyFrom  

  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcompactsize"></a>  CMFCRibbonLinkCtrl::GetCompactSize  

  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getlink"></a>  CMFCRibbonLinkCtrl::GetLink  
 ハイパーリンクの値を返します。  
  
```  
LPCTSTR GetLink() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ハイパーリンクの現在の値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getregularsize"></a>  CMFCRibbonLinkCtrl::GetRegularSize  

  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettooltiptext"></a>  CMFCRibbonLinkCtrl::GetToolTipText  

  
```  
virtual CString GetToolTipText() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawmenuimage"></a>  CMFCRibbonLinkCtrl::OnDrawMenuImage  

  
```  
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CDC*`  
 [入力] `CRect`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdrawtooltipimage"></a>  CMFCRibbonLinkCtrl::IsDrawTooltipImage  

  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondraw"></a>  CMFCRibbonLinkCtrl::OnDraw  

  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onmousemove"></a>  CMFCRibbonLinkCtrl::OnMouseMove  

  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onseticon"></a>  CMFCRibbonLinkCtrl::OnSetIcon  

  
```  
virtual void OnSetIcon();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="openlink"></a>  CMFCRibbonLinkCtrl::OpenLink  
 ハイパーリンクで指定されている Web ページを開きます。  
  
```  
BOOL OpenLink();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 関連付けられている Web ページが正常に開かれた場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 関連付けられているハイパーリンクを使用し、web ページを開き、`CMFCRibbonLinkCtrl`オブジェクト。  
  
##  <a name="setlink"></a>  CMFCRibbonLinkCtrl::SetLink  
 ハイパーリンクの値を設定します。  
  
```  
void SetLink(LPCTSTR lpszLink);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLink`  
 ハイパーリンクのテキストを指定します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)
