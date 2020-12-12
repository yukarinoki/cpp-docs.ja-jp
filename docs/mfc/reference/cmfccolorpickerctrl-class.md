---
description: '詳細情報: CMFCColorPickerCtrl クラス'
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
ms.openlocfilehash: e4363c08af86dee96df1492e9a029414d9902435
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313074"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl クラス

クラスは、 `CMFCColorPickerCtrl` 色の選択に使用されるコントロールの機能を提供します。

## <a name="syntax"></a>構文

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCColorPickerCtrl:: CMFCColorPickerCtrl](#cmfccolorpickerctrl)|`CMFCColorPickerCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCColorPickerCtrl:: GetColor](#getcolor)|ユーザーが選択した色を取得します。|
|[CMFCColorPickerCtrl:: GetHLS](#gethls)|ユーザーが選択した色の色合い、明るさ、および鮮やかさの値を取得します。|
|[CMFCColorPickerCtrl:: GetHue](#gethue)|ユーザーが選択した色の色合い成分を取得します。|
|[CMFCColorPickerCtrl:: GetLuminance](#getluminance)|ユーザーが選択した色の輝度成分を取得します。|
|[CMFCColorPickerCtrl:: GetSaturation](#getsaturation)|ユーザーが選択した色の鮮やかさの部分を取得します。|
|[CMFCColorPickerCtrl:: SelectCellHexagon 形](#selectcellhexagon)|現在の色を、指定した RGB カラーコンポーネントまたは指定したセル六角形で定義された色に設定します。|
|[CMFCColorPickerCtrl:: SetColor](#setcolor)|現在の色を、指定した RGB カラー値に設定します。|
|[CMFCColorPickerCtrl:: SetHLS](#sethls)|現在の色を、指定された HLS 色の値に設定します。|
|[CMFCColorPickerCtrl:: SetHue](#sethue)|現在選択されている色の色合い成分を変更します。|
|[CMFCColorPickerCtrl:: SetLuminance](#setluminance)|現在選択されている色の輝度コンポーネントを変更します。|
|[CMFCColorPickerCtrl:: SetLuminanceBarWidth](#setluminancebarwidth)|カラーピッカーコントロールの輝度バーの幅を設定します。|
|[CMFCColorPickerCtrl:: SetOriginalColor](#setoriginalcolor)|最初に選択した色を設定します。|
|[CMFCColorPickerCtrl:: SetPalette](#setpalette)|現在のカラーパレットを設定します。|
|[CMFCColorPickerCtrl:: SetSaturation](#setsaturation)|現在選択されている色の鮮やかさコンポーネントを変更します。|
|[CMFCColorPickerCtrl:: SetType](#settype)|表示するカラーピッカーコントロールの種類を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCColorPickerCtrl::D rawCursor](#drawcursor)|選択した色を指すカーソルが表示される前に、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

標準色は、六角色パレットから選択されます。色が指定されている輝度バーの色は、赤、緑、青、または色相/satuaration と輝度表記のいずれかを使用して選択します。

次の図は、いくつかの `CMFCColorPickerCtrl` オブジェクトを示しています。

![CMFCColorPickerCtrl ダイアログ ボックス](../../mfc/reference/media/colorpicker.png "CMFCColorPickerCtrl ダイアログ ボックス")

は `CMFCColorPickerCtrl` 2 つのスタイルのペアをサポートしています。 16進数と HEX_GREYSCALE スタイルは、標準の色の選択に適しています。 ピッカーと輝度のスタイルは、ユーザー設定の色の選択に適しています。

コントロールをダイアログボックスに組み込むには、次の手順を実行し `CMFCColorPickerCtrl` ます。

1. **ClassWizard** を使用する場合は、ダイアログボックステンプレートに新しいボタンコントロールを挿入します ( `CMFCColorPickerCtrl` クラスはクラスから継承されているため `CButton` )。

1. 新しいボタンコントロールに関連付けられているメンバー変数をダイアログボックスクラスに挿入します。 次に、変数の型をからに変更し `CButton` `CMFCColorPickerCtrl` ます。

1. `WM_INITDIALOG`ダイアログボックスクラスのメッセージハンドラーを挿入します。 ハンドラーで、コントロールの種類、パレット、および最初に選択した色を設定し `CMFCColorPickerCtrl` ます。

## <a name="example"></a>例

`CMFCColorPickerCtrl`クラスのさまざまなメソッドを使用してオブジェクトを構成する方法を次の例に示し `CMFCColorPickerCtrl` ます。 この例では、ピッカーコントロールの型を設定する方法と、その色、色合い、輝度、および鮮やかさを設定する方法を示します。 この例は、「 [新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxcolorpickerctrl

## <a name="cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a> CMFCColorPickerCtrl:: CMFCColorPickerCtrl

`CMFCColorPickerCtrl` オブジェクトを構築します。

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a> CMFCColorPickerCtrl::D rawCursor

選択した色を指すカーソルが表示される前に、フレームワークによって呼び出されます。

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rect*<br/>
から選択した色の周囲の四角形の領域を指定します。

### <a name="remarks"></a>解説

選択した色をポイントするカーソルの形状を変更する必要がある場合は、このメソッドをオーバーライドします。

## <a name="cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a> CMFCColorPickerCtrl:: GetColor

ユーザーが選択した色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

選択された色の RGB 値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlgethls"></a><a name="gethls"></a> CMFCColorPickerCtrl:: GetHLS

ユーザーが選択した色の色合い、明るさ、および鮮やかさの値を取得します。

```cpp
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>パラメーター

*hue*<br/>
入出力色合い情報を受け取る double 型の変数へのポインター。

*明るさ*<br/>
入出力輝度情報を受け取る double 型の変数へのポインター。

*飽和*<br/>
入出力彩度情報を受け取る double 型の変数へのポインター。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlgethue"></a><a name="gethue"></a> CMFCColorPickerCtrl:: GetHue

ユーザーが選択した色の色合い成分を取得します。

```
double GetHue() const;
```

### <a name="return-value"></a>戻り値

選択された色の色合いコンポーネント。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a> CMFCColorPickerCtrl:: GetLuminance

ユーザーが選択した色の輝度成分を取得します。

```
double GetLuminance() const;
```

### <a name="return-value"></a>戻り値

選択された色の輝度コンポーネント。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a> CMFCColorPickerCtrl:: GetSaturation

ユーザーが選択した色の彩度の値を取得します。

```
double GetSaturation() const;
```

### <a name="return-value"></a>戻り値

選択された色の鮮やかさコンポーネント。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a> CMFCColorPickerCtrl:: SelectCellHexagon 形

現在の色を、指定した RGB カラーコンポーネントまたは指定したセル六角形で定義された色に設定します。

```cpp
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
から赤のカラーコンポーネント。

*G*<br/>
から緑のカラー成分。

*B*<br/>
から青のカラーコンポーネント。

*x*<br/>
からセルの六角形を指すカーソルの x 座標。

*y*<br/>
からセルの六角形を指すカーソルの y 座標。

### <a name="return-value"></a>戻り値

このメソッドの2番目のオーバーロードは常に FALSE を返します。

### <a name="remarks"></a>解説

このメソッドの最初のオーバーロードでは、色の選択コントロールの赤、緑、および青の色コンポーネントに対応する色に現在の色が設定されます。

このメソッドの2番目のオーバーロードは、現在の色を、指定されたカーソル位置によってポイントされているセル六角形の色に設定します。

## <a name="cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a> CMFCColorPickerCtrl:: SetColor

現在の色を、指定した RGB カラー値に設定します。

```cpp
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
からRGB カラー値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsethls"></a><a name="sethls"></a> CMFCColorPickerCtrl:: SetHLS

現在の色を、指定された HLS 色の値に設定します。

```cpp
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>パラメーター

*hue*<br/>
から色合いの値。

*明るさ*<br/>
から輝度値。

*飽和*<br/>
から鮮やかさの値。

*ビン検証*<br/>
からウィンドウを強制的に新しい色に更新する場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsethue"></a><a name="sethue"></a> CMFCColorPickerCtrl:: SetHue

現在選択されている色の色合いを変更します。

```cpp
void SetHue(double Hue);
```

### <a name="parameters"></a>パラメーター

*Hue*<br/>
から色合いの値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a> CMFCColorPickerCtrl:: SetLuminance

現在選択されている色の輝度を変更します。

```cpp
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>パラメーター

*輝度*<br/>
から輝度値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a> CMFCColorPickerCtrl:: SetLuminanceBarWidth

カラーピッカーコントロールの輝度バーの幅を設定します。

```cpp
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>パラメーター

*w*<br/>
から輝度バーの幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドを使用して、カラーピッカーコントロールの [ **カスタム** ] タブにある輝度バーのサイズを変更します。 *W* パラメーターは、輝度バーの新しい幅を指定します。 幅の値がクライアント領域の幅の 3 3/4 を超える場合は無視されます。

## <a name="cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a> CMFCColorPickerCtrl:: SetOriginalColor

最初に選択した色を設定します。

```cpp
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>パラメーター

*ref*<br/>
からRGB カラー値。

### <a name="remarks"></a>解説

カラーピッカーコントロールが初期化されるときに、このメソッドを呼び出します。

## <a name="cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a> CMFCColorPickerCtrl:: SetPalette

現在のカラーパレットを設定します。

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>パラメーター

*pPalette*<br/>
からカラーパレットへのポインター。

### <a name="remarks"></a>解説

カラーパレットでは、カラーピッカーコントロールに表示される色の配列を定義します。

## <a name="cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a> CMFCColorPickerCtrl:: SetSaturation

現在選択されている色の鮮やかさを変更します。

```cpp
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>パラメーター

*[鮮やかさ]*<br/>
から鮮やかさの値。

### <a name="remarks"></a>解説

## <a name="cmfccolorpickerctrlsettype"></a><a name="settype"></a> CMFCColorPickerCtrl:: SetType

表示するカラーピッカーコントロールの種類を設定します。

```cpp
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>パラメーター

*colorType*<br/>
からカラーピッカーコントロール型。

型は列挙体によって定義され `CMFCColorPickerCtrl::COLORTYPE` ます。 使用できる種類は、輝度、ピッカー、16進数、および HEX_GREYSCALE です。 既定の種類はピッカーです。

### <a name="remarks"></a>解説

カラーピッカーコントロール型を指定するには、Windows コントロールが作成される前にこのメソッドを呼び出します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)
