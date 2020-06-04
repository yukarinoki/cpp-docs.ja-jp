---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
ms.openlocfilehash: 304581371c68817c6031153c3cec227137771c5d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754062"
---
# <a name="cmfcribbonslider-class"></a>クラス

この`CMFCRibbonSlider`クラスは、リボン バーまたはリボン ステータス バーに追加できるスライダー コントロールを実装します。 リボン スライダー コントロールは、Office 2007 アプリケーションに表示されるズーム スライダーに似ています。

## <a name="syntax"></a>構文

```
class CMFCRibbonSlider : public CMFCRibbonBaseElement
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCリボンスライダー::CMFCリボンスライダー](#cmfcribbonslider)|リボン スライダー コントロールを構築および初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コトリボンスライダー::ゲットポス](#getpos)|スライダー コントロールの現在位置を返します。|
|[CMFCリボンスライダー::ゲットレンジマックス](#getrangemax)|スライダーの最大値を返します。|
|[CMFCリボンスライダー::ゲットレンジミン](#getrangemin)|スライダーの最小値を返します。|
|[CMFCリボンスライダー::ゲットレギュラーサイズ](#getregularsize)|リボン要素の標準サイズを返します。 (オーバーライドします[。](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)|
|[CMFCリボンスライダー::ゲットズームインクリメント](#getzoomincrement)|スライダー コントロールのズームの増分のサイズを返します。|
|[CMFCリボンスライダー::ハスズームボタン](#haszoombuttons)|スライダーにズーム ボタンがあるかどうかを指定します。|
|[CMFCリボンスライダー::オンドロー](#ondraw)|リボン要素を描画するために、フレームワークによって呼び出されます。 (オーバーライド[CMFCリボンベース要素::オンドロー](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCリボンスライダー::セットポス](#setpos)|スライダー コントロールの現在位置を設定します。|
|[CMFCリボンスライダー::セットレンジ](#setrange)|最小値と最大値を設定して、スライダー コントロールの範囲を指定します。|
|[CMFCリボンスライダー::セットズームボタン](#setzoombuttons)|ズーム ボタンの表示と非表示を切り替えます。|
|[CMFCリボンスライダー::セットズームインクリメント](#setzoomincrement)|スライダー コントロールのズームの増分のサイズを設定します。|

## <a name="remarks"></a>解説

この方法を`SetRange`使用して、スライダーのズーム増分の範囲を設定できます。 この方法を使用して、スライダーの現在位置を`SetPos`設定できます。

このメソッドを使用すると、スライダー コントロールの左右に円形ズーム ボタンを`SetZoomButtons`表示できます。 既定ではスライダーは水平、左ズーム ボタンにはマイナス記号が表示され、右ズーム ボタンにはプラス記号が表示されます。

この`SetZoomIncrement`メソッドは、ユーザーがズーム ボタンをクリックしたときに現在位置に加算または減算する増分を定義します。

## <a name="example"></a>例

クラスのさまざまなメソッドを使用してスライダーのプロパティを`CMFCRibbonSlider`設定する方法を次の例に示します。 この例では、オブジェクトの作成`CMFCRibbonSlider`方法、ズーム ボタンの表示方法、スライダー コントロールの現在位置の設定方法、およびスライダー コントロールの値の範囲を設定する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribbonslider.h

## <a name="cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a>CMFCリボンスライダー::CMFCリボンスライダー

リボン スライダーを作成します。

```
CMFCRibbonSlider(
    UINT nID,
    int nWidth=100);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]スライダー ID。

[in]。 *n幅*スライダーの幅 (ピクセル単位)。

### <a name="remarks"></a>解説

スライダーが追加されるパネル カテゴリの*幅が nWidth*ピクセルのリボン スライダーを構築します。 既定では、スライダーは水平です。

## <a name="cmfcribbonslidergetpos"></a><a name="getpos"></a>コトリボンスライダー::ゲットポス

スライダー コントロールの現在位置を返します。

```
int GetPos() const;
```

### <a name="return-value"></a>戻り値

スライダー コントロールの現在位置は、スライダーの開始位置を基準にしています。

## <a name="cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a>CMFCリボンスライダー::ゲットレンジマックス

スライダー コントロール上でスライダーが移動できるスライダーの最大増分を取得します。

```
int GetRangeMax() const;
```

### <a name="return-value"></a>戻り値

スライダー コントロール上でスライダーが移動できるスライダーの最大増分値。

## <a name="cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a>CMFCリボンスライダー::ゲットレンジミン

スライダー コントロール上でスライダーが移動できる最小増分を返します。

```
int GetRangeMin() const;
```

### <a name="return-value"></a>戻り値

スライダー コントロール上でスライダーが移動できる最小増分。

## <a name="cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a>CMFCリボンスライダー::ゲットレギュラーサイズ

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a>CMFCリボンスライダー::ゲットズームインクリメント

スライダー コントロールのズームの増分を取得します。

```
int GetZoomIncrement() const;
```

### <a name="return-value"></a>戻り値

スライダー コントロールのズームのインクリメント。

## <a name="cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a>CMFCリボンスライダー::ハスズームボタン

スライダーにズーム ボタンがあるかどうかを指定します。

```
BOOL HasZoomButtons() const;
```

### <a name="return-value"></a>戻り値

スライダーにズーム ボタンがある場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcribbonsliderondraw"></a><a name="ondraw"></a>CMFCリボンスライダー::オンドロー

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonslidersetpos"></a><a name="setpos"></a>CMFCリボンスライダー::セットポス

スライダー コントロールの現在位置を設定します。

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
[in]スライダーに設定する位置を指定します。 位置は、スライダーの始めを基準にしています。

*引き出し*<br/>
[in]TRUE の場合、スライダーが再描画されます。

## <a name="cmfcribbonslidersetrange"></a><a name="setrange"></a>CMFCリボンスライダー::セットレンジ

スライダー コントロールの値の範囲を設定します。

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
[in]スライダー コントロールの最小値を指定します。

*nMax*<br/>
[in]スライダー コントロールの最大値を指定します。

### <a name="remarks"></a>解説

最小値と最大値を設定して、スライダー コントロールの値の範囲を指定します。

## <a name="cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a>CMFCリボンスライダー::セットズームボタン

ズーム ボタンの表示と非表示を切り替えます。

```cpp
void SetZoomButtons(BOOL bSet=TRUE);
```

### <a name="parameters"></a>パラメーター

[in]。 *bセット*ズーム ボタンを表示する場合は TRUE。FALSE を指定すると、非表示になります。

## <a name="cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a>CMFCリボンスライダー::セットズームインクリメント

スライダー コントロールのズームの増分を設定します。

```cpp
void SetZoomIncrement(int nZoomIncrement);
```

### <a name="parameters"></a>パラメーター

*インクリメント*<br/>
[in]スライダー コントロールのズームインクリメントを指定します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)
