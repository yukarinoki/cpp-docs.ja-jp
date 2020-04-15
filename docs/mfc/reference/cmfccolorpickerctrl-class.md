---
title: CMFCColorPickerCtrl クラス
ms.date: 11/19/2018
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
ms.openlocfilehash: c3c11db448ab31324367b7f314cd6bfe44c2e96d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367684"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl クラス

この`CMFCColorPickerCtrl`クラスは、色の選択に使用されるコントロールの機能を提供します。

## <a name="syntax"></a>構文

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コントロール](#cmfccolorpickerctrl)|`CMFCColorPickerCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#getcolor)|ユーザーが選択した色を取得します。|
|[をクリックします。](#gethls)|ユーザーが選択した色の色相、輝度、彩度の値を取得します。|
|[をクリックします。](#gethue)|ユーザーが選択した色の色相のコンポーネントを取得します。|
|[をクリックします。](#getluminance)|ユーザーが選択した色の輝度コンポーネントを取得します。|
|[彩度を取得します。](#getsaturation)|ユーザーが選択した色の彩度コンポーネントを取得します。|
|[セル六角形を選択します。](#selectcellhexagon)|現在の色を、指定した RGB カラー コンポーネントまたは指定したセルの六角形で定義された色に設定します。|
|[をクリックします。](#setcolor)|現在のカラーを指定した RGB カラー値に設定します。|
|[をクリックします。](#sethls)|現在の色を指定した HLS カラー値に設定します。|
|[をクリックします。](#sethue)|現在選択されている色の色相の部分を変更します。|
|[輝度を設定します。](#setluminance)|現在選択されている色の輝度コンポーネントを変更します。|
|[コントロール::ルミナンスバー幅の設定](#setluminancebarwidth)|カラー ピッカー コントロールの輝度バーの幅を設定します。|
|[カラーリングコントロール::オリジナルカラーを設定](#setoriginalcolor)|最初に選択した色を設定します。|
|[をクリックします。](#setpalette)|現在のカラー パレットを設定します。|
|[コントロール::設定飽和](#setsaturation)|現在選択されている色の彩度成分を変更します。|
|[をクリックします。](#settype)|表示するカラー ピッカー コントロールの種類を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[を:D](#drawcursor)|選択した色を指すカーソルが表示される前に、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

標準色は六角形のカラーパレットから選択され、色が赤/緑/青表記または色/収率/輝度表記を使用して指定される輝度バーから選択されます。

次の図は、いくつかの`CMFCColorPickerCtrl`オブジェクトを示しています。

![CMFCColorPickerCtrl ダイアログ ボックス](../../mfc/reference/media/colorpicker.png "CMFCColorPickerCtrl ダイアログ ボックス")

では`CMFCColorPickerCtrl`、2 組のスタイルをサポートします。 HEX スタイルと HEX_GREYSCALE スタイルは、標準の色選択に適しています。 ピッカーと輝度のスタイルは、カスタムカラーの選択に適しています。

ダイアログ ボックスにコントロールを組`CMFCColorPickerCtrl`み込むには、次の手順を実行します。

1. **ClassWizard**を使用する場合は、ダイアログ ボックス テンプレートに新しいボタン コントロール`CMFCColorPickerCtrl`を`CButton`挿入します (クラスはクラスから継承されるため)。

1. 新しいボタン コントロールに関連付けられているメンバー変数をダイアログ ボックス クラスに挿入します。 次に、変数の型`CButton`を`CMFCColorPickerCtrl`から に変更します。

1. ダイアログ`WM_INITDIALOG`ボックス クラスのメッセージ ハンドラーを挿入します。 ハンドラーで、コントロールの型、パレット、および最初に選択した色を`CMFCColorPickerCtrl`設定します。

## <a name="example"></a>例

クラスのさまざまなメソッドを使用してオブジェクトを構成`CMFCColorPickerCtrl`する方法を次の例に`CMFCColorPickerCtrl`示します。 この例では、ピッカー コントロールの種類を設定する方法と、色、色、輝度、および彩度を設定する方法を示します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcolorpickerctrl.h

## <a name="cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a>コントロール

`CMFCColorPickerCtrl` オブジェクトを構築します。

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a>を:D

選択した色を指すカーソルが表示される前に、フレームワークによって呼び出されます。

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]選択した色の周囲の四角形の領域を指定します。

### <a name="remarks"></a>解説

選択した色を指すカーソルの形状を変更する必要がある場合は、このメソッドをオーバーライドします。

## <a name="cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a>をクリックします。

ユーザーが選択した色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

選択した色の RGB 値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlgethls"></a><a name="gethls"></a>をクリックします。

ユーザーが選択した色の色相、輝度、彩度の値を取得します。

```
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>パラメーター

*色相*<br/>
[アウト]色相情報を受け取る倍精度浮動小数点型の変数へのポインター。

*輝度*<br/>
[アウト]輝度情報を受け取る倍精度浮動小数点型の変数へのポインター。

*彩度*<br/>
[アウト]飽和情報を受け取る double 型の変数へのポインター。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlgethue"></a><a name="gethue"></a>をクリックします。

ユーザーが選択した色の色相のコンポーネントを取得します。

```
double GetHue() const;
```

### <a name="return-value"></a>戻り値

選択した色の色相成分。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a>をクリックします。

ユーザーが選択した色の輝度コンポーネントを取得します。

```
double GetLuminance() const;
```

### <a name="return-value"></a>戻り値

選択した色の輝度コンポーネント。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a>彩度を取得します。

ユーザーが選択した色の彩度値を取得します。

```
double GetSaturation() const;
```

### <a name="return-value"></a>戻り値

選択した色の彩度成分。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a>セル六角形を選択します。

現在の色を、指定した RGB カラー コンポーネントまたは指定したセルの六角形で定義された色に設定します。

```
void SelectCellHexagon(
    BYTE R,
    BYTE G,
    BYTE B);

BOOL SelectCellHexagon(
    int x,
    int y);
```

### <a name="parameters"></a>パラメーター

*R*<br/>
[in]赤の色コンポーネント。

*G*<br/>
[in]緑色のコンポーネント。

*B*<br/>
[in]青の色のコンポーネント。

*X*<br/>
[in]セルの六角形を指すカーソルの x 座標。

*Y*<br/>
[in]セルの六角形を指すカーソルの y 座標。

### <a name="return-value"></a>戻り値

このメソッドの 2 番目のオーバーロードは常に FALSE を返します。

### <a name="remarks"></a>解説

このメソッドの最初のオーバーロードでは、現在の色を、色選択コントロールの指定した赤、緑、青の各色のコンポーネントに対応する色に設定します。

このメソッドの 2 番目のオーバーロードは、現在の色を、指定されたカーソル位置が指すセルの六角形の色に設定します。

## <a name="cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a>をクリックします。

現在のカラーを指定した RGB カラー値に設定します。

```
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>パラメーター

*Color*<br/>
[in]RGB カラー値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsethls"></a><a name="sethls"></a>をクリックします。

現在の色を指定した HLS カラー値に設定します。

```
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>パラメーター

*色相*<br/>
[in]色相の値。

*輝度*<br/>
[in]輝度値。

*彩度*<br/>
[in]飽和値。

*b検証*<br/>
[in]ウィンドウを新しい色にすぐに更新する場合は TRUE。それ以外の場合は FALSE。 デフォルトは TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsethue"></a><a name="sethue"></a>をクリックします。

現在選択されている色の色相を変更します。

```
void SetHue(double Hue);
```

### <a name="parameters"></a>パラメーター

*Hue*<br/>
[in]色相の値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a>輝度を設定します。

現在選択されている色の輝度を変更します。

```
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>パラメーター

*輝度*<br/>
[in]輝度値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a>コントロール::ルミナンスバー幅の設定

カラー ピッカー コントロールの輝度バーの幅を設定します。

```
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>パラメーター

*W*<br/>
[in]輝度バーの幅をピクセル単位で指定します。

### <a name="remarks"></a>解説

このメソッドは、カラー ピッカー コントロールの **[カスタム**] タブにある輝度バーのサイズを変更するために使います。 *w*パラメータは、輝度バーの新しい幅を指定します。 width 値は、クライアント領域の幅の 4 分の 3 を超える場合は無視されます。

## <a name="cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a>カラーリングコントロール::オリジナルカラーを設定

最初に選択した色を設定します。

```
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>パラメーター

*ref*<br/>
[in]RGB カラー値。

### <a name="remarks"></a>解説

カラー ピッカー コントロールが初期化されるときに、このメソッドを呼び出します。

## <a name="cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a>をクリックします。

現在のカラー パレットを設定します。

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]カラー パレットへのポインター。

### <a name="remarks"></a>解説

カラー パレットは、カラー ピッカー コントロールに表示される色の配列を定義します。

## <a name="cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a>コントロール::設定飽和

現在選択されている色の彩度を変更します。

```
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>パラメーター

*[鮮やかさ]*<br/>
[in]飽和値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsettype"></a><a name="settype"></a>をクリックします。

表示するカラー ピッカー コントロールの種類を設定します。

```
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>パラメーター

*カラータイプ*<br/>
[in]カラー ピッカー コントロールの種類。

型は`CMFCColorPickerCtrl::COLORTYPE`列挙体によって定義されます。 可能なタイプは、輝度、ピッカー、16 進数、HEX_GREYSCALEです。 既定の型はピッカーです。

### <a name="remarks"></a>解説

カラー ピッカー コントロールの種類を指定するには、Windows コントロールを作成する前にこのメソッドを呼び出します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)
