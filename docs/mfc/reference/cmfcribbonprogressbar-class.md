---
description: '詳細情報: CMFCRibbonProgressBar クラス'
title: CMFCRibbonProgressBar クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
ms.openlocfilehash: b4e91a604386a57aa7cac59294c569635583304c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321762"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar クラス

時間のかかる操作の進行状況を視覚的に示すコントロールを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|`CMFCRibbonProgressBar` オブジェクトを構築して初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonProgressBar::GetPos](#getpos)|現在の進行状況を返します。|
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|現在の範囲の最大値を返します。|
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|現在の範囲の最小値を返します。|
|[CMFCRibbonProgressBar:: GetRegularSize](#getregularsize)|リボン要素の標準サイズを返します。 ( [CMFCRibbonBaseElement:: GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)をオーバーライドします。)|
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|プログレスバーが無限モードで動作しているかどうかを指定します。|
|[CMFCRibbonProgressBar:: OnDraw](#ondraw)|リボン要素を描画するために、フレームワークによって呼び出されます。 ( [CMFCRibbonBaseElement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw)をオーバーライドします)。|
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|無限モードで動作するようにプログレスバーを設定します。|
|[CMFCRibbonProgressBar::SetPos](#setpos)|現在の進行状況を設定します。|
|[CMFCRibbonProgressBar:: SetRange](#setrange)|最小値と最大値を設定します。|

## <a name="remarks"></a>解説

は、 `CMFCRibbonProgressBar` 2 つのモード (regular と無限大) で動作できます。 通常モードでは、進行状況バーは左から右に入力され、最大値に達すると停止します。 無限モードでは、進行状況バーは、最小値から最大値まで繰り返し入力されます。 無限モードを使用すると、操作が進行中であることを示すことができますが、完了までの時間は不明です。

## <a name="example"></a>例

`CMFCRibbonProgressBar` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、無限モード (操作の完了時刻が不明な場合) で進行状況バーを設定し、進行状況バーの最小値と最大値を設定して、進行状況バーの現在位置を設定する方法を示します。 このコードスニペットは、 [MS Office 2007 Demo サンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxRibbonProgressBar

## <a name="cmfcribbonprogressbarcmfcribbonprogressbar"></a><a name="cmfcribbonprogressbar"></a> CMFCRibbonProgressBar::CMFCRibbonProgressBar

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)オブジェクトを構築し、初期化します。

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
からリボンのプログレスバーのコマンド ID を指定します。

*nWidth*<br/>
からリボンのプログレスバーの幅をピクセル単位で指定します。

*nHeight*<br/>
からリボンのプログレスバーの高さ (ピクセル単位) を指定します。

## <a name="cmfcribbonprogressbargetpos"></a><a name="getpos"></a> CMFCRibbonProgressBar::GetPos

プログレスバーの現在位置を返します。

```
int GetPos () const;
```

### <a name="return-value"></a>戻り値

プログレスバーの現在位置を表す値。

### <a name="remarks"></a>解説

設定する範囲は、 [CMFCRibbonProgressBar:: SetRange](#setrange) メソッドによって指定された範囲内である必要があります。

## <a name="cmfcribbonprogressbargetrangemax"></a><a name="getrangemax"></a> CMFCRibbonProgressBar::GetRangeMax

プログレスバーの現在の最大値を返します。

```
int GetRangeMax() const;
```

### <a name="return-value"></a>戻り値

現在の範囲の最大値。

### <a name="remarks"></a>解説

## <a name="cmfcribbonprogressbargetrangemin"></a><a name="getrangemin"></a> CMFCRibbonProgressBar::GetRangeMin

プログレスバーの現在の最小範囲値を返します。

```
int GetRangeMin() const;
```

### <a name="return-value"></a>戻り値

現在の範囲の最小値。

## <a name="cmfcribbonprogressbargetregularsize"></a><a name="getregularsize"></a> CMFCRibbonProgressBar:: GetRegularSize

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonprogressbarisinfinitemode"></a><a name="isinfinitemode"></a> CMFCRibbonProgressBar::IsInfiniteMode

プログレスバーが無限モードで動作しているかどうかを指定します。

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>戻り値

プログレスバーが無限モードの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

無限モードでは、進行状況バーは最小値から最大値に繰り返し表示されます。 無限モードを使用すると、操作が進行中であることを示すことができますが、完了までの時間は不明です。

## <a name="cmfcribbonprogressbarondraw"></a><a name="ondraw"></a> CMFCRibbonProgressBar:: OnDraw

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonprogressbarsetinfinitemode"></a><a name="setinfinitemode"></a> CMFCRibbonProgressBar::SetInfiniteMode

無限モードで動作するようにプログレスバーを設定します。

```cpp
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>パラメーター

*bSet*<br/>
からプログレスバーが無限モードであることを指定する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

通常、進行状況バーが無限モードの場合は、操作が進行中であることをユーザーに通知しますが、完了時間は不明です。 したがって、進行状況バーは、最小値から最大値まで繰り返し表示されます。

## <a name="cmfcribbonprogressbarsetpos"></a><a name="setpos"></a> CMFCRibbonProgressBar::SetPos

プログレスバーの現在位置を設定します。

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
からプログレスバーを設定する位置を指定します。

*より描画*<br/>
からプログレスバーを再描画するかどうかを指定します。

### <a name="remarks"></a>解説

設定する範囲は、 [CMFCRibbonProgressBar:: SetRange](#setrange) メソッドによって指定された範囲内である必要があります。

## <a name="cmfcribbonprogressbarsetrange"></a><a name="setrange"></a> CMFCRibbonProgressBar:: SetRange

プログレスバーの最小値と最大値を設定します。

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>パラメーター

*N1 日*<br/>
から範囲の最小値を指定します。

*N1 日*<br/>
から範囲の最大値を指定します。

### <a name="remarks"></a>解説

このメソッドを使用して、最小値と最大値を設定して進行状況バーの範囲を定義します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)
