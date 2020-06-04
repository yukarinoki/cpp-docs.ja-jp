---
title: クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 6c8bb41b82d1dca9235e1184c2152a61c07c8071
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377354"
---
# <a name="cmfctooltipctrl-class"></a>クラス

[CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)に基づいた拡張ツールヒントの実装です。 `CMFCToolTipCtrl` クラスに基づいたツールヒントは、アイコン、ラベル、および説明を表示できます。 グラデーション塗りつぶし、カスタム テキストと境界線の色、太字、角を丸く表示、またはバルーン形式を使用して、外観をカスタマイズできます。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```cpp
class CMFCToolTipCtrl : public CToolTipCtrl
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|既定のコンストラクターです。|

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

## <a name="remarks"></a>解説

`CMFCToolTipCtrl`、、`CMFCToolTipInfo`および[CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md)オブジェクトを一緒に使用して、アプリケーションにカスタマイズされたツールヒントを実装します。

たとえば、バルーン形式のツールヒントを使用するには、次の手順に従います。

1. [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)メソッドを使用して、アプリケーションのツールヒント マネージャーを初期化します。

2. `CMFCToolTipInfo` 構造体を作成し、必要な表示スタイルを指定します。

    ```cpp
    CMFCToolTipInfo params;
    params.m_bBoldLabel = FALSE;
    params.m_bDrawDescription = FALSE;
    params.m_bDrawIcon = FALSE;
    params.m_bRoundedCorners = TRUE;
    params.m_bDrawSeparator = FALSE;
    if (m_bCustomColors)
    {
        params.m_clrFill = RGB (255, 255, 255);
        params.m_clrFillGradient = RGB (228, 228, 240);
        params.m_clrText = RGB (61, 83, 80);
        params.m_clrBorder = RGB (144, 149, 168);

    }
    ```

3. [CTooltipManager::SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams)メソッドを使用して、オブジェクトで定義されたスタイルを使用して、アプリケーション内のすべてのツールチップの表示`CMFCToolTipInfo`スタイルを設定します。

    ```cpp
    theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
        RUNTIME_CLASS (CMFCToolTipCtrl), &params);
    ```

`CMFCToolTipCtrl` から新しいクラスを派生させて、ツールヒントの動作や描画を制御することもできます。 新しいツールヒント コントロール クラスを指定するには、`CTooltipManager::SetTooltipParams` メソッドを使用します。

```cpp
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMyToolTipCtrl))
```

既定のツールヒント コントロール クラスを復元し、ツールヒントの外観を既定の状態にリセットするには、`SetTooltipParams` のランタイム クラスとツールヒント情報パラメーターに NULL を指定します。

```cpp
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

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtooltipctrl.h

## <a name="cmfctooltipctrlcmfctooltipctrl"></a><a name="cmfctooltipctrl"></a>

```cpp
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*pParams*<br/>

### <a name="remarks"></a>解説

## <a name="cmfctooltipctrlgeticonsize"></a><a name="geticonsize"></a>ツールチップCtrl:::ゲットアイコンサイズ

ツールヒント内のアイコンのサイズを返します。

```cpp
virtual CSize GetIconSize();
```

### <a name="return-value"></a>戻り値

アイコンのサイズ (ピクセル単位)。

## <a name="cmfctooltipctrlgetparams"></a><a name="getparams"></a>CMFCツールチップCtrl::ゲットパラム

ツールヒントの表示設定を返します。

```cpp
const CMFCToolTipInfo& GetParams() const;
```

### <a name="return-value"></a>戻り値

現在のツールヒントの表示設定は[、CMFC ツール ヒント情報クラス](../../mfc/reference/cmfctooltipinfo-class.md)オブジェクトに格納されています。

## <a name="cmfctooltipctrlondrawborder"></a><a name="ondrawborder"></a>次の値を指定します。

ツールヒントの枠線を描画します。

```cpp
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect,
    COLORREF clrLine);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]ツールヒントの外接する四角形。

*clrLine*<br/>
[in]境界線の色。

### <a name="remarks"></a>解説

ツールヒントの境界線の外観をカスタマイズするには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfctooltipctrlondrawdescription"></a><a name="ondrawdescription"></a>次の説明を表示します。

```cpp
virtual CSize OnDrawDescription(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>
[in]*レクト*<br/>
[in]*唯一の時間*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfctooltipctrlondrawicon"></a><a name="ondrawicon"></a>CMFCツールチップCtrl::オンドローアイコン

ツールヒント内にアイコンを表示します。

```cpp
virtual BOOL OnDrawIcon(
    CDC* pDC,
    CRect rectImage);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*レクトイメージ*<br/>
[in]アイコンの座標。

### <a name="return-value"></a>戻り値

アイコンが描画された場合は TRUE。 それ以外の場合は FALSE。

### <a name="remarks"></a>解説

カスタム アイコンを表示するには、派生クラスでこのメソッドをオーバーライドします。 また、ツールヒントがテキストと説明のレイアウトを正しく計算できるようにするには[、CMFCToolTipCtrl::GetIconSize](#geticonsize)をオーバーライドする必要があります。

## <a name="cmfctooltipctrlondrawlabel"></a><a name="ondrawlabel"></a>次の値をクリックします。

ツールヒントのラベルを描画するか、ラベルのサイズを計算します。

```cpp
virtual CSize OnDrawLabel(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]ラベル領域の外接する四角形。

*唯一の時間*<br/>
[in]TRUE の場合、ラベルは描画されません。

### <a name="return-value"></a>戻り値

ラベルのサイズ (ピクセル単位)。

### <a name="remarks"></a>解説

ツールヒント ラベルの外観をカスタマイズする場合は、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfctooltipctrlondrawseparator"></a><a name="ondrawseparator"></a>をクリックします。

ツールヒント内のラベルと説明の間の区分線を描画します。

```cpp
virtual void OnDrawSeparator(
    CDC* pDC,
    int x1,
    int x2,
    int y);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*x1*<br/>
[in]区切り記号の左端の水平座標です。

*x2*<br/>
[in]セパレータの右端の水平座標です。

*Y*<br/>
[in]区切り記号の垂直座標です。

### <a name="remarks"></a>解説

既定の実装では、ポイント (x1, y) からポイント (x2, y) までの線を描画します。

区切り記号の外観をカスタマイズするには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfctooltipctrlonfillbackground"></a><a name="onfillbackground"></a>CMFCツールチップCtrl::オンフィルバックグラウンド

ツールヒントの背景を塗りつぶします。

```cpp
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect,
    COLORREF& clrText,
    COLORREF& clrLine);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]塗りつぶす領域の外接する四角形を指定します。

*clrText*<br/>
[in]ツールヒントの前景色。

*clrLine*<br/>
[in]ラベルと説明の間の境界線と区切り線の色。

### <a name="remarks"></a>解説

既定の実装では *、rect*で指定された四角形に[、CMFCToolTipCtrl::SetParams](#setparams)の最新の呼び出しで指定された色またはパターンを塗りつぶします。

ツールヒントの外観をカスタマイズする場合は、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfctooltipctrlsetdescription"></a><a name="setdescription"></a>次の説明を設定します。

ツールヒントに表示される説明を設定します。

```cpp
virtual void SetDescription(const CString strDesrciption);
```

### <a name="parameters"></a>パラメーター

*ストレーシプション*<br/>
[in]説明テキスト。

### <a name="remarks"></a>解説

説明テキストは、ツールチップの区切り記号の下に表示されます。

## <a name="cmfctooltipctrlsetfixedwidth"></a><a name="setfixedwidth"></a>コントロール::固定幅の設定

```cpp
void SetFixedWidth(
    int nWidthRegular,
    int nWidthLargeImage);
```

### <a name="parameters"></a>パラメーター

[in]*n幅正規*<br/>
[in]*大きなイメージ*<br/>

### <a name="remarks"></a>解説

## <a name="cmfctooltipctrlsethotribbonbutton"></a><a name="sethotribbonbutton"></a>ボタン

```cpp
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```

### <a name="parameters"></a>パラメーター

[in]*ボタン*<br/>

### <a name="remarks"></a>解説

## <a name="cmfctooltipctrlsetlocation"></a><a name="setlocation"></a>CMFC ツールヒントCtrl::セットロケーション

```cpp
void SetLocation(CPoint pt);
```

### <a name="parameters"></a>パラメーター

[in]*pt*<br/>

### <a name="remarks"></a>解説

## <a name="cmfctooltipctrlsetparams"></a><a name="setparams"></a>CMFCツールチップCtrl::セットパラム

[CMFC ツール ヒント情報クラス](../../mfc/reference/cmfctooltipinfo-class.md)オブジェクトを使用して、ツールヒントの外観を指定します。

```cpp
void SetParams(CMFCToolTipInfo* pParams);
```

### <a name="parameters"></a>パラメーター

*pParams*<br/>
[in]表示パラメーターを含む[CMFC ツール ヒント情報クラス](../../mfc/reference/cmfctooltipinfo-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

ツールヒントが表示されるたびに *、pParams*で指定された色と表示スタイルを使用して描画されます。 *pParams*の値は、指定された外観を`m_Params`維持するために[、CMFC ツールヒントCtrl:::オンドローボーダー](#ondrawborder) [、CMFCツールチップCtrl:::オンドローアイコン](#ondrawicon)[、CMFCツールヒントCtrl::オンドローラベル](#ondrawlabel)[、CMFCツールヒントCtrl::または](#ondrawseparator) [CMFCToolTipCtrl:または CMFCToolTipCtrl:オンフィルバックグラウンド](#onfillbackground)をオーバーライドする派生クラスによってアクセスできるプロテクトメンバーに格納されます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/ctooltipctrl-class.md)<br/>
[クラス](../../mfc/reference/ctooltipmanager-class.md)<br/>
[クラス](../../mfc/reference/cmfctooltipinfo-class.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
