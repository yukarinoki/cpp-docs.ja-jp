---
title: CMFCToolTipCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09a701498b47957f64558fe42408ff64351c238b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372957"
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl クラス
[CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)に基づいた拡張ツールヒントの実装です。 `CMFCToolTipCtrl` クラスに基づいたツールヒントは、アイコン、ラベル、および説明を表示できます。 グラデーション塗りつぶし、カスタム テキストと境界線の色、太字、角を丸く表示、またはバルーン形式を使用して、外観をカスタマイズできます。  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolTipCtrl : public CToolTipCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|ツールヒント内のアイコンのサイズを返します。|  
|[CMFCToolTipCtrl::GetParams](#getparams)|ツールヒントの表示設定を返します。|  
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|ツールヒントの枠線を描画します。|  
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||  
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|ツールヒント内にアイコンを表示します。|  
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|ツールヒントのラベルを描画するか、ラベルのサイズを計算します。|  
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|ツールヒント内のラベルと説明の間の区分線を描画します。|  
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|ツールヒントの背景を塗りつぶします。|  
|[CMFCToolTipCtrl::SetDescription](#setdescription)|ツールヒントに表示される説明を設定します。|  
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||  
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||  
|[CMFCToolTipCtrl::SetLocation](#setlocation)||  
|[CMFCToolTipCtrl::SetParams](#setparams)|`CMFCToolTipInfo` オブジェクトを使用して、ツールヒントの外観を指定します。|  
  
## <a name="remarks"></a>コメント  
 使用して`CMFCToolTipCtrl`、 `CMFCToolTipInfo`、および[CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md)アプリケーションでカスタマイズされたツールヒントを実装するオブジェクト。  
  
 たとえば、バルーン形式のツールヒントを使用するには、次の手順に従います。  
  
 1. 使用して、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)アプリケーション内でツールヒント マネージャーを初期化します。  
  
 2. `CMFCToolTipInfo` 構造体を作成し、必要な表示スタイルを指定します。  
  
```  
CMFCToolTipInfo params;  
    params.m_bBoldLabel = FALSE;  
    params.m_bDrawDescription = FALSE;  
    params.m_bDrawIcon = FALSE;  
    params.m_bRoundedCorners = TRUE;  
    params.m_bDrawSeparator = FALSE;  
    if (m_bCustomColors)  
 {  
    params.m_clrFill = RGB (255,
    255,
    255);

    params.m_clrFillGradient = RGB (228,
    228,
    240);

    params.m_clrText = RGB (61,
    83,
    80);

    params.m_clrBorder = RGB (144,
    149,
    168);

 }  
```  
3. 使用して、 [:settooltipparams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams)で定義されたスタイルを使用して、アプリケーションのすべてのツールヒントの視覚スタイルを設定する方法、`CMFCToolTipInfo`オブジェクト。  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);
```  
`CMFCToolTipCtrl` から新しいクラスを派生させて、ツールヒントの動作や描画を制御することもできます。 新しいツールヒント コントロール クラスを指定するには、`CTooltipManager::SetTooltipParams` メソッドを使用します。  
  
```  
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMyToolTipCtrl))  
```  
既定のツールヒント コントロール クラスを復元し、ツールヒントの外観を既定の状態にリセットするには、`SetTooltipParams` のランタイム クラスとツールヒント情報パラメーターに NULL を指定します。  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    NULL,
    NULL);
```  
  
## <a name="example"></a>例  
 次の例では、`CMFCToolTipCtrl` オブジェクトを作成し、ツールヒントに表示される説明とツールヒント コントロールの幅を設定する方法を示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)  
  
 [CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtooltipctrl.h  
  
##  <a name="cmfctooltipctrl"></a>  CMFCToolTipCtrl::CMFCToolTipCtrl  

  
```  
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParams`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="geticonsize"></a>  CMFCToolTipCtrl::GetIconSize  
 ツールヒント内のアイコンのサイズを返します。  
  
```  
virtual CSize GetIconSize();
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、アイコンのサイズ。  
  
##  <a name="getparams"></a>  CMFCToolTipCtrl::GetParams  
 ツールヒントの表示設定を返します。  
  
```  
const CMFCToolTipInfo& GetParams() const;  
```  
  
### <a name="return-value"></a>戻り値  
 格納されている、現在のツールヒントの表示設定、 [CMFCToolTipInfo クラス](../../mfc/reference/cmfctooltipinfo-class.md)オブジェクト。  
  
##  <a name="ondrawborder"></a>  CMFCToolTipCtrl::OnDrawBorder  
 ツールヒントの枠線を描画します。  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] pDC`  
 デバイス コンテキストへのポインター。  
  
 `[in] rect`  
 ツールヒントの外接する四角形。  
  
 `[in] clrLine`  
 罫線の色。  
  
### <a name="remarks"></a>コメント  
 ツールヒントの境界線の外観をカスタマイズする派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="ondrawdescription"></a>  CMFCToolTipCtrl::OnDrawDescription  

  
```  
virtual CSize OnDrawDescription(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bCalcOnly`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawicon"></a>  CMFCToolTipCtrl::OnDrawIcon  
 ツールヒント内にアイコンを表示します。  
  
```  
virtual BOOL OnDrawIcon(
    CDC* pDC,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rectImage`  
 アイコンの座標です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、アイコンが描画されています。 それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 カスタム アイコンを表示する派生クラスでは、このメソッドをオーバーライドします。 オーバーライドする必要がありますも[CMFCToolTipCtrl::GetIconSize](#geticonsize)ツールヒントのテキストと説明のレイアウトを正しく計算を有効にします。  
  
##  <a name="ondrawlabel"></a>  CMFCToolTipCtrl::OnDrawLabel  
 ツールヒントのラベルを描画するか、ラベルのサイズを計算します。  
  
```  
virtual CSize OnDrawLabel(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] pDC`  
 デバイス コンテキストへのポインター。  
  
 `[in] rect`  
 ラベル領域の外接する四角形。  
  
 `[in] bCalcOnly`  
 場合`TRUE`ラベルは描画されません。  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、ラベルのサイズ。  
  
### <a name="remarks"></a>コメント  
 ツールヒントのラベルの外観をカスタマイズする場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="ondrawseparator"></a>  CMFCToolTipCtrl::OnDrawSeparator  
 ツールヒント内のラベルと説明の間の区分線を描画します。  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    int x1,  
    int x2,  
    int y);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `x1`  
 区切り記号の左端の水平座標。  
  
 [入力] `x2`  
 区切り記号の右端の水平座標。  
  
 [入力] `Y`  
 区切り記号の垂直方向の座標。  
  
### <a name="remarks"></a>コメント  
 既定の実装の点からの線の描画 (x1, y) をポイント (x2, y)。  
  
 区切り記号の外観をカスタマイズする派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="onfillbackground"></a>  CMFCToolTipCtrl::OnFillBackground  
 ツールヒントの背景を塗りつぶします。  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    CRect rect,  
    COLORREF& clrText,  
    COLORREF& clrLine);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] pDC`  
 デバイス コンテキストへのポインター。  
  
 `[in] rect`  
 塗りつぶす領域に外接する四角形を指定します。  
  
 `[in] clrText`  
 ツールヒントの前景色です。  
  
 `[in] clrLine`  
 枠線とラベルと説明の間の区切り線の色です。  
  
### <a name="remarks"></a>コメント  
 既定の実装によって指定される四角形で塗りつぶします`rect`色または最新の呼び出しで指定されたパターンで[CMFCToolTipCtrl::SetParams](#setparams)です。  
  
 ツールヒントの外観をカスタマイズする場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="setdescription"></a>  CMFCToolTipCtrl::SetDescription  
 ツールヒントに表示される説明を設定します。  
  
```  
virtual void SetDescription(const CString strDesrciption);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] strDesrciption`  
 説明テキストです。  
  
### <a name="remarks"></a>コメント  
 説明のテキストは、区切り記号の下のツールヒントに表示されます。  
  
##  <a name="setfixedwidth"></a>  CMFCToolTipCtrl::SetFixedWidth  

  
```  
void SetFixedWidth(
    int nWidthRegular,  
    int nWidthLargeImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nWidthRegular`  
 [入力] `nWidthLargeImage`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sethotribbonbutton"></a>  CMFCToolTipCtrl::SetHotRibbonButton  

  
```  
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRibbonButton`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setlocation"></a>  CMFCToolTipCtrl::SetLocation  

  
```  
void SetLocation(CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pt`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setparams"></a>  CMFCToolTipCtrl::SetParams  
 使用して、ツールヒントの外観を指定します、 [CMFCToolTipInfo クラス](../../mfc/reference/cmfctooltipinfo-class.md)オブジェクト。  
  
```  
void SetParams(CMFCToolTipInfo* pParams);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] pParams`  
 ポインター、 [CMFCToolTipInfo クラス](../../mfc/reference/cmfctooltipinfo-class.md)ディスプレイのパラメーターを含むオブジェクトです。  
  
### <a name="remarks"></a>コメント  
 ツールヒントが表示されます、カラーを使用して描画され、visual スタイルを`pParams`を指定します。 値`pParams`プロテクト メンバーに格納されて`m_Params`、オーバーライドする派生クラスでアクセスできる[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)、 [CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)、 [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)、 [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)、または[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)維持するために、指定した外観です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CToolTipCtrl クラス](../../mfc/reference/ctooltipctrl-class.md)   
 [CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipInfo クラス](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
