---
title: CMFCCaptionButton クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 356aa3448c3912c1842d5e04c697fc86fc9714c0
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338400"
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton クラス
`CMFCCaptionButton`クラスは、ドッキング ペインまたはミニフレーム ウィンドウのキャプション バーに表示されるボタンを実装します。 通常は、フレームワークがキャプション ボタンを自動的に作成します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="constructors"></a>コンストラクター  
  
|name|説明|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|CMFCCaptionButton オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|ボタンで表されるコマンドを返します。|  
|[CMFCCaptionButton::GetIconID](#geticonid)|ボタンに関連付けられているイメージ ID を返します。|  
|[CMFCCaptionButton::GetRect](#getrect)|ボタンによって占有されている四角形を返します。|  
|[CMFCCaptionButton::GetSize](#getsize)|ボタンの高さと幅を返します。|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|タイトル バーの高さはミニ サイズに設定されているかどうかを示します。|  
|[CMFCCaptionButton::Move](#move)|ウィンドウの表示状態のボタンの描画位置を設定します。|  
|[CMFCCaptionButton::OnDraw](#ondraw)|キャプション ボタンを描画します。|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|ミニ タイトル バーのサイズを設定します。|  
  
## <a name="remarks"></a>Remarks  
 クラスを派生させる[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)保護対象のメソッドを使用して`AddButton`、ミニフレーム ウィンドウにキャプション ボタンを追加します。  
  
 CPaneFrameWnd.h は、キャプション ボタンの 2 種類のコマンド Id を定義します。  
  
- AFX_CAPTION_BTN_PIN ドッキング ペインが自動的に隠すモードをサポートしている場合は、ピン留めする ボタンを表示します。  
  
- AFX_CAPTION_BTN_CLOSE で、表示、**閉じる**ボタン、ウィンドウの終了または非表示にできます。  
  
## <a name="example"></a>例  
 次の例は、構築する方法を示します、`CMFCCaptionButton`オブジェクトし、ミニ タイトル バーのサイズを設定します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcaptionbutton.h  
  
##  <a name="cmfccaptionbutton"></a>  CMFCCaptionButton::CMFCCaptionButton  
 `CMFCCaptionButton` オブジェクトを構築します。  
  
```  
CMFCCaptionButton();

 
CMFCCaptionButton(
    UINT nHit,  
    BOOL bLeftAlign = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nHit*  
 ボタンに関連付けられているコマンド。  
  
 [in]*bLeftAlign*  
 ボタンは、左に配置されているかどうかを指定します。  
  
 次の表に指定できる値の一覧、 *nHit*パラメーター。  
  
|[値]|コマンド|  
|-----------|-------------|  
|AFX_HTCLOSE|閉じるボタンをクリックします。|  
|HTMINBUTTON|最小化ボタン。|  
|HTMAXBUTTON|最大化ボタン。|  
|AFX_HTLEFTBUTTON|左矢印ボタンをクリックします。|  
|AFX_HTRIGHTBUTTON|右矢印ボタンをクリックします。|  
|AFX_HTMENU|下向きの矢印のメニュー ボタン。|  
|HTNOWHERE|既定値です。コマンドを表すありません。|  
  
### <a name="remarks"></a>Remarks  
 既定では、キャプション ボタンは、コマンドに関連付けられていません。  
  
 キャプション ボタンは、いずれかで、右または左に揃えて配置されます。  
  
##  <a name="gethit"></a>  CMFCCaptionButton::GetHit  
 ボタンで表されるコマンドを返します。  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンで表されるコマンド。  
  
 次の表では、有効な戻り値を示します。  
  
|[値]|コマンド|  
|-----------|-------------|  
|AFX_HTCLOSE|閉じるボタンをクリックします。|  
|HTMINBUTTON|最小化ボタン。|  
|HTMAXBUTTON|最大化ボタン。|  
|AFX_HTLEFTBUTTON|左矢印ボタンをクリックします。|  
|AFX_HTRIGHTBUTTON|右矢印ボタンをクリックします。|  
|AFX_HTMENU|下向きの矢印のメニュー ボタン。|  
|HTNOWHERE|既定値です。コマンドを表すありません。|  
  
##  <a name="geticonid"></a>  CMFCCaptionButton::GetIconID  
 ボタンに関連付けられているイメージ ID を返します。  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bHorz*  
 左側または右側の矢印のイメージ Id の場合は TRUE。FALSE を上下の矢印のイメージ Id。  
  
 [in]*bMaximized*  
 TRUE の最大化イメージ ID。最小化イメージ ID の場合は FALSE。  
  
### <a name="return-value"></a>戻り値  
 イメージ id。  
  
### <a name="remarks"></a>Remarks  
 パラメーターでは、最小化にイメージ Id を指定またはキャプション ボタンを最大化します。  
  
##  <a name="getrect"></a>  CMFCCaptionButton::GetRect  
 ボタンによって占有されている四角形を返します。  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンの位置を表す四角形。  
  
### <a name="remarks"></a>Remarks  
 ボタンが表示できない場合、返されるサイズは 0 です。  
  
##  <a name="getsize"></a>  CMFCCaptionButton::GetSize  
 ボタンの高さと幅を返します。  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>戻り値  
 ボタンの外部の大きさ。  
  
### <a name="remarks"></a>Remarks  
 返されるサイズには、ボタンの余白と境界線が含まれています。  
  
##  <a name="isminiframebutton"></a>  CMFCCaptionButton::IsMiniFrameButton  
 タイトル バーの高さはミニ サイズに設定されているかどうかを示します。  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 キャプションが小さなサイズに設定されている場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="move"></a>  CMFCCaptionButton::Move  
 ウィンドウの表示状態のボタンの描画位置を設定します。  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ptTo*  
 新しい位置。  
  
 [in]*bHide*  
 ボタンを表示するかどうか。  
  
##  <a name="ondraw"></a>  CMFCCaptionButton::OnDraw  
 キャプション ボタンを描画します。  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    BOOL bActive,  
    BOOL bHorz = TRUE,  
    BOOL bMaximized = TRUE,  
    BOOL bDisabled = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 ボタンのデバイス コンテキストへのポインター。  
  
 [in]*描画*  
 アクティブなボタン イメージを描画するかどうか。  
  
 [in]*bHorz*  
 派生クラスで使用するために予約されています。  
  
 [in]*bMaximized*  
 最大化ボタンのイメージを描画するかどうか。  
  
 [in]*bDisabled*  
 ボタンが有効なイメージを描画するかどうか。  
  
### <a name="remarks"></a>Remarks  
 *BMaximized*パラメーターは、ボタンは、最大にする場合に使用または最小化ボタン。  
  
##  <a name="setminiframebutton"></a>  CMFCCaptionButton::SetMiniFrameButton  
 ミニ タイトル バーのサイズを設定します。  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bSet*  
 TRUE のミニのタイトル バーの高さ。既定のタイトル バーの高さの場合は FALSE。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)
