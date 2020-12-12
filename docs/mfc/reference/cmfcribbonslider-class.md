---
description: '詳細情報: CMFCRibbonSlider クラス'
title: CMFCRibbonSlider クラス
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
ms.openlocfilehash: d125afdf961d97c0501742acdc75d7802c7e104d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321735"
---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider クラス

クラスは、 `CMFCRibbonSlider` リボンバーまたはリボンステータスバーに追加できるスライダーコントロールを実装します。 リボン スライダー コントロールは、Office 2007 アプリケーションに表示されるズーム スライダーに似ています。

## <a name="syntax"></a>構文

```
class CMFCRibbonSlider : public CMFCRibbonBaseElement
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|リボンスライダーコントロールを構築および初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonSlider::GetPos](#getpos)|スライダーコントロールの現在位置を返します。|
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|スライダーの最大値を返します。|
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|スライダーの最小値を返します。|
|[CMFCRibbonSlider:: GetRegularSize](#getregularsize)|リボン要素の標準サイズを返します。 ( [CMFCRibbonBaseElement:: GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)をオーバーライドします。)|
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|スライダーコントロールのズームインクリメントのサイズを返します。|
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|スライダーにズームボタンを表示するかどうかを指定します。|
|[CMFCRibbonSlider:: OnDraw](#ondraw)|リボン要素を描画するために、フレームワークによって呼び出されます。 ( [CMFCRibbonBaseElement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw)をオーバーライドします)。|
|[CMFCRibbonSlider::SetPos](#setpos)|スライダーコントロールの現在位置を設定します。|
|[CMFCRibbonSlider:: SetRange](#setrange)|最小値と最大値を設定することにより、スライダーコントロールの範囲を指定します。|
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|ズームボタンの表示と非表示を切り替えます。|
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|スライダーコントロールのズームインクリメントのサイズを設定します。|

## <a name="remarks"></a>解説

メソッドを使用して、 `SetRange` スライダーのズームの範囲を構成できます。 スライダーの現在位置は、メソッドを使用して設定でき `SetPos` ます。

メソッドを使用すると、スライダーコントロールの左側と右側に円形のズームボタンを表示でき `SetZoomButtons` ます。 既定では、スライダーは水平方向であり、左ズームボタンにマイナス記号が表示され、右ズームボタンにプラス記号が表示されます。

メソッドは、 `SetZoomIncrement` ユーザーがズームボタンをクリックしたときに、現在の位置に加算または減算するインクリメントを定義します。

## <a name="example"></a>例

次の例では、クラスのさまざまなメソッドを使用して、スライダーのプロパティを設定する方法を示し `CMFCRibbonSlider` ます。 この例では、オブジェクトを構築する方法、 `CMFCRibbonSlider` ズームボタンを表示する方法、スライダーコントロールの現在の位置を設定する方法、スライダーコントロールの値の範囲を設定する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribbonslider

## <a name="cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a> CMFCRibbonSlider::CMFCRibbonSlider

リボンのスライダーを構築します。

```
CMFCRibbonSlider(
    UINT nID,
    int nWidth=100);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
からスライダー ID。

[入力]。 *nWidth* スライダーの幅 (ピクセル単位)。

### <a name="remarks"></a>解説

スライダーが追加されるパネルカテゴリで幅が *nWidth* ピクセルになるリボンスライダーを構築します。 既定では、スライダーは水平になっています。

## <a name="cmfcribbonslidergetpos"></a><a name="getpos"></a> CMFCRibbonSlider::GetPos

スライダーコントロールの現在位置を返します。

```
int GetPos() const;
```

### <a name="return-value"></a>戻り値

スライダーコントロールの現在の位置。スライダーの開始位置を基準とする相対的な位置です。

## <a name="cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a> CMFCRibbonSlider::GetRangeMax

スライダーがスライダーコントロール上を移動できるスライダーの最大インクリメントを取得します。

```
int GetRangeMax() const;
```

### <a name="return-value"></a>戻り値

スライダーがスライダーコントロール上を移動できるスライダーの最大インクリメント。

## <a name="cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a> CMFCRibbonSlider::GetRangeMin

スライダーがスライダーコントロールで移動できる最小インクリメントを返します。

```
int GetRangeMin() const;
```

### <a name="return-value"></a>戻り値

スライダーがスライダーコントロールで移動できる最小インクリメント。

## <a name="cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a> CMFCRibbonSlider:: GetRegularSize

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a> CMFCRibbonSlider::GetZoomIncrement

スライダーコントロールのズームの増分値を取得します。

```
int GetZoomIncrement() const;
```

### <a name="return-value"></a>戻り値

スライダーコントロールのズームインクリメント。

## <a name="cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a> CMFCRibbonSlider::HasZoomButtons

スライダーにズームボタンを表示するかどうかを指定します。

```
BOOL HasZoomButtons() const;
```

### <a name="return-value"></a>戻り値

スライダーにズームボタンがある場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcribbonsliderondraw"></a><a name="ondraw"></a> CMFCRibbonSlider:: OnDraw

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonslidersetpos"></a><a name="setpos"></a> CMFCRibbonSlider::SetPos

スライダーコントロールの現在位置を設定します。

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
からスライダーに設定する位置を指定します。 位置は、スライダーの先頭からの相対位置です。

*より描画*<br/>
からTRUE の場合、スライダーは再描画されます。

## <a name="cmfcribbonslidersetrange"></a><a name="setrange"></a> CMFCRibbonSlider:: SetRange

スライダーコントロールの値の範囲を設定します。

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>パラメーター

*N1 日*<br/>
からスライダーコントロールの最小値を指定します。

*N1 日*<br/>
からスライダーコントロールの最大値を指定します。

### <a name="remarks"></a>解説

最小値と最大値を設定することにより、スライダーコントロールの値の範囲を指定します。

## <a name="cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a> CMFCRibbonSlider::SetZoomButtons

ズームボタンを表示または非表示にします。

```cpp
void SetZoomButtons(BOOL bSet=TRUE);
```

### <a name="parameters"></a>パラメーター

[入力]。 *Bset* ズームボタンを表示する場合は TRUE。非表示にする場合は FALSE。

## <a name="cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a> CMFCRibbonSlider::SetZoomIncrement

スライダーコントロールのズームインクリメントを設定します。

```cpp
void SetZoomIncrement(int nZoomIncrement);
```

### <a name="parameters"></a>パラメーター

*nZoomIncrement*<br/>
からスライダーコントロールのズームインクリメントを指定します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)
