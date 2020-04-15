---
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
ms.openlocfilehash: 063f8ce560af84d350abc0114644f6a63f969f95
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368861"
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
|[バー::CMFCリボンプログレスバー](#cmfcribbonprogressbar)|`CMFCRibbonProgressBar` オブジェクトを構築して初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[バー::ゲットポス](#getpos)|現在の進行状況を返します。|
|[バー::ゲットレンジマックス](#getrangemax)|現在の範囲の最大値を返します。|
|[バー::ゲットレンジミン](#getrangemin)|現在の範囲の最小値を返します。|
|[バー::一般化](#getregularsize)|リボン要素の標準サイズを返します。 (オーバーライドします[。](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)|
|[バー::イズインフィニットモード](#isinfinitemode)|プログレス バーが無限モードで動作しているかどうかを指定します。|
|[バー::オンドロー](#ondraw)|リボン要素を描画するために、フレームワークによって呼び出されます。 (オーバーライド[CMFCリボンベース要素::オンドロー](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[バー::設定無限モード](#setinfinitemode)|プログレス バーを無限モードで動作するように設定します。|
|[バー::セットポス](#setpos)|現在の進行状況を設定します。|
|[バー::セットレンジ](#setrange)|最小値と最大値を設定します。|

## <a name="remarks"></a>解説

A`CMFCRibbonProgressBar`は、標準モードと無限モードの 2 つのモードで動作できます。 通常モードでは、プログレスバーは左から右に塗りつぶされ、最大値に達すると停止します。 無限モードでは、進行状況バーは最小値から最大値まで繰り返し塗りつぶされます。 無限モードを使用して、操作が進行中であるが、完了時間が不明であることを示すことができます。

## <a name="example"></a>例

`CMFCRibbonProgressBar` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、進行状況バーを無限モード (操作の完了時間が不明) で動作するように設定し、進行状況バーの最小値と最大値を設定し、進行状況バーの現在位置を設定する方法を示します。 このコード スニペットは、 [MS Office 2007 デモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRibbon プログレスバー.h

## <a name="cmfcribbonprogressbarcmfcribbonprogressbar"></a><a name="cmfcribbonprogressbar"></a>バー::CMFCリボンプログレスバー

[オブジェクトを](../../mfc/reference/cmfcribbonprogressbar-class.md)構築して初期化します。

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]リボン プログレス バーのコマンド ID を指定します。

*n幅*<br/>
[in]リボンプログレス バーの幅をピクセル単位で指定します。

*nHeight*<br/>
[in]リボンプログレス バーの高さをピクセル単位で指定します。

## <a name="cmfcribbonprogressbargetpos"></a><a name="getpos"></a>バー::ゲットポス

プログレス バーの現在位置を返します。

```
int GetPos () const;
```

### <a name="return-value"></a>戻り値

プログレス バーの現在位置を表す値。

### <a name="remarks"></a>解説

設定される範囲は[、CMFCRibbonProgressBar::SetRange](#setrange)メソッドで指定された範囲内になければなりません。

## <a name="cmfcribbonprogressbargetrangemax"></a><a name="getrangemax"></a>バー::ゲットレンジマックス

プログレス バーの現在の最大値を返します。

```
int GetRangeMax() const;
```

### <a name="return-value"></a>戻り値

現在の範囲の最大値。

### <a name="remarks"></a>解説

## <a name="cmfcribbonprogressbargetrangemin"></a><a name="getrangemin"></a>バー::ゲットレンジミン

プログレス バーの現在の最小範囲の値を返します。

```
int GetRangeMin() const;
```

### <a name="return-value"></a>戻り値

現在の範囲の最小値。

## <a name="cmfcribbonprogressbargetregularsize"></a><a name="getregularsize"></a>バー::一般化

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonprogressbarisinfinitemode"></a><a name="isinfinitemode"></a>バー::イズインフィニットモード

プログレス バーが無限モードで動作しているかどうかを指定します。

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>戻り値

プログレス バーが無限モードの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

無限モードでは、進行状況バーは最小値から最大値まで繰り返し塗りつぶされます。 無限モードを使用して、操作が進行中であるが、完了時間が不明であることを示すことができます。

## <a name="cmfcribbonprogressbarondraw"></a><a name="ondraw"></a>バー::オンドロー

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonprogressbarsetinfinitemode"></a><a name="setinfinitemode"></a>バー::設定無限モード

プログレス バーを無限モードで動作するように設定します。

```
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>パラメーター

*bセット*<br/>
[in]プログレス バーが無限モードであることを指定する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

通常、プログレス バーが無限モードの場合、操作は進行中ですが、完了時間は不明であることをユーザーに伝えています。 したがって、進行状況バーは最小値から最大値まで繰り返し塗りつぶされます。

## <a name="cmfcribbonprogressbarsetpos"></a><a name="setpos"></a>バー::セットポス

プログレス バーの現在位置を設定します。

```
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
[in]プログレス バーを設定する位置を指定します。

*引き出し*<br/>
[in]プログレス バーを再描画するかどうかを指定します。

### <a name="remarks"></a>解説

設定される範囲は[、CMFCRibbonProgressBar::SetRange](#setrange)メソッドで指定された範囲内になければなりません。

## <a name="cmfcribbonprogressbarsetrange"></a><a name="setrange"></a>バー::セットレンジ

プログレス バーの最小値と最大値を設定します。

```
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
[in]範囲の最小値を指定します。

*nMax*<br/>
[in]範囲の最大値を指定します。

### <a name="remarks"></a>解説

このメソッドは、最小値と最大値を設定してプログレス バーの範囲を定義するために使います。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[クラス](../../mfc/reference/cmfcribbonbar-class.md)
