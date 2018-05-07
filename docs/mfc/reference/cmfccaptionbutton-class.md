---
title: CMFCCaptionButton クラス |Microsoft ドキュメント
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
ms.openlocfilehash: ec36bfc82064272e165ea274cd127cc626731643
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton クラス
`CMFCCaptionButton`クラスは、ドッキング ペインまたはミニフレーム ウィンドウのキャプション バーに表示されるボタンを実装します。 通常は、フレームワークがキャプション ボタンを自動的に作成します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="constructors"></a>コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|CMFCCaptionButton オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCCaptionButton::GetHit](#gethit)|コマンド ボタンで表されるを返します。|  
|[CMFCCaptionButton::GetIconID](#geticonid)|ボタンに関連付けられているイメージ ID を返します。|  
|[CMFCCaptionButton::GetRect](#getrect)|ボタンによって占有される四角形を返します。|  
|[CMFCCaptionButton::GetSize](#getsize)|ボタンの高さと幅を返します。|  
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|タイトル バーの高さがミニ サイズに設定されているかどうかを示します。|  
|[CMFCCaptionButton::Move](#move)|ウィンドウの表示状態のボタンの描画位置を設定します。|  
|[CMFCCaptionButton::OnDraw](#ondraw)|キャプション ボタンを描画します。|  
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|タイトル バーのミニ サイズを設定します。|  
  
## <a name="remarks"></a>コメント  
 クラスを派生させる[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)保護の方法を使用して`AddButton`、ミニフレーム ウィンドウにキャプション ボタンを追加します。  
  
 CPaneFrameWnd.h には、次の 2 つの種類のキャプション ボタンのコマンド Id が定義されています。  
  
- `AFX_CAPTION_BTN_PIN`、ドッキング ペインは、自動非表示モードをサポートしているときに暗証番号 (pin) ボタンが表示されます。  
  
- `AFX_CAPTION_BTN_CLOSE`、が表示される、**閉じる**、ウィンドウの終了または非表示にできるとボタンをクリックします。  
  
## <a name="example"></a>例  
 次の例で作成する方法、`CMFCCaptionButton`オブジェクトし、ミニ タイトル バーのサイズを設定します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## <a name="requirements"></a>要件  
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
 [入力] `nHit`  
 ボタンに関連付けられているコマンド。  
  
 [入力] `bLeftAlign`  
 ボタンは、左に配置されているかどうかを指定します。  
  
 次の表に、可能な値、`nHit`パラメーター。  
  
|[値]|コマンド|  
|-----------|-------------|  
|`AFX_HTCLOSE`|閉じるボタンをクリックします。|  
|`HTMINBUTTON`|最小化ボタン。|  
|`HTMAXBUTTON`|ボタンを最大化します。|  
|`AFX_HTLEFTBUTTON`|左矢印ボタンをクリックします。|  
|`AFX_HTRIGHTBUTTON`|右矢印ボタンをクリックします。|  
|`AFX_HTMENU`|下向きの矢印のメニュー ボタン。|  
|`HTNOWHERE`|既定値です。コマンドを表すありません。|  
  
### <a name="remarks"></a>コメント  
 既定では、キャプションのボタンに関連付けられていないコマンドです。  
  
 キャプション ボタンは、いずれかで、右または左に配置されます。  
  
##  <a name="gethit"></a>  CMFCCaptionButton::GetHit  
 コマンド ボタンで表されるを返します。  
  
```  
UINT GetHit() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンで表されるコマンド。  
  
 次の表は、戻り値を一覧表示します。  
  
|[値]|コマンド|  
|-----------|-------------|  
|`AFX_HTCLOSE`|閉じるボタンをクリックします。|  
|`HTMINBUTTON`|最小化ボタン。|  
|`HTMAXBUTTON`|ボタンを最大化します。|  
|`AFX_HTLEFTBUTTON`|左矢印ボタンをクリックします。|  
|`AFX_HTRIGHTBUTTON`|右矢印ボタンをクリックします。|  
|`AFX_HTMENU`|下向きの矢印のメニュー ボタン。|  
|`HTNOWHERE`|既定値です。コマンドを表すありません。|  
  
##  <a name="geticonid"></a>  CMFCCaptionButton::GetIconID  
 ボタンに関連付けられているイメージ ID を返します。  
  
```  
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,  
    BOOL bMaximized = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHorz`  
 `TRUE` 左または右矢印の画像の Id です。`FALSE`の上向きまたは下向き矢印イメージ Id。  
  
 [入力] `bMaximized`  
 `TRUE` 最大化イメージ ID です。`FALSE`を最小化の画像の id。  
  
### <a name="return-value"></a>戻り値  
 イメージ id。  
  
### <a name="remarks"></a>コメント  
 パラメーターは、最小化にイメージ Id を指定またはキャプション ボタンを最大化します。  
  
##  <a name="getrect"></a>  CMFCCaptionButton::GetRect  
 ボタンによって占有される四角形を返します。  
  
```  
virtual CRect GetRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンの位置を表す四角形。  
  
### <a name="remarks"></a>コメント  
 ボタンが表示できない場合は、返されるサイズは 0 です。  
  
##  <a name="getsize"></a>  CMFCCaptionButton::GetSize  
 ボタンの高さと幅を返します。  
  
```  
static CSize GetSize();
```  
  
### <a name="return-value"></a>戻り値  
 ボタンの外側のディメンションです。  
  
### <a name="remarks"></a>コメント  
 返されるサイズには、ボタンのマージンと境界線が含まれています。  
  
##  <a name="isminiframebutton"></a>  CMFCCaptionButton::IsMiniFrameButton  
 タイトル バーの高さがミニ サイズに設定されているかどうかを示します。  
  
```  
BOOL IsMiniFrameButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` キャプションがミニサイズ; に設定されている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="move"></a>  CMFCCaptionButton::Move  
 ウィンドウの表示状態のボタンの描画位置を設定します。  
  
```  
void Move(
    const CPoint& ptTo,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptTo`  
 新しい位置。  
  
 [入力] `bHide`  
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
 [入力] `pDC`  
 ボタンのデバイス コンテキストへのポインター。  
  
 [入力] `bActive`  
 アクティブなボタン イメージを描画するかどうか。  
  
 [入力] `bHorz`  
 派生クラスで使用するために予約されています。  
  
 [入力] `bMaximized`  
 最大化ボタンのイメージを描画するかどうか。  
  
 [入力] `bDisabled`  
 有効になっているボタン イメージを描画するかどうか。  
  
### <a name="remarks"></a>コメント  
 `bMaximized`パラメーターは、ボタンは、最大にするときに使用または最小化ボタンをクリックします。  
  
##  <a name="setminiframebutton"></a>  CMFCCaptionButton::SetMiniFrameButton  
 タイトル バーのミニ サイズを設定します。  
  
```  
void SetMiniFramebutton(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 `TRUE` ミニ タイトル バーの高さ;`FALSE`の既定のタイトル バーの高さ。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)
