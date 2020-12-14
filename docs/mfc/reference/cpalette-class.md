---
description: '詳細情報: CPalette クラス'
title: CPalette クラス
ms.date: 11/04/2016
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
ms.openlocfilehash: c83638d6e9a0fd049b431c424ddbc0c9ce315f0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345200"
---
# <a name="cpalette-class"></a>CPalette クラス

Windows のカラー パレットをカプセル化します。

## <a name="syntax"></a>構文

```
class CPalette : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CPalette:: CPalette](#cpalette)|`CPalette`Windows パレットがアタッチされていないオブジェクトを構築します。 オブジェクトを使用する `CPalette` には、初期化メンバー関数のいずれかを使用してオブジェクトを初期化する必要があります。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPalette:: AnimatePalette](#animatepalette)|オブジェクトで識別される論理パレット内のエントリを置き換え `CPalette` ます。 新しいエントリは、Windows によってすぐにシステムパレットにマップされるため、アプリケーションでクライアント領域を更新する必要はありません。|
|[CPalette:: CreateHalftonePalette](#createhalftonepalette)|デバイスコンテキスト用のハーフトーンパレットを作成し、オブジェクトにアタッチし `CPalette` ます。|
|[CPalette:: CreatePalette](#createpalette)|Windows カラーパレットを作成し、オブジェクトにアタッチし `CPalette` ます。|
|[CPalette:: FromHandle](#fromhandle)|`CPalette`Windows パレットオブジェクトへのハンドルが指定された場合に、オブジェクトへのポインターを返します。|
|[CPalette:: GetEntryCount](#getentrycount)|論理パレット内のパレットエントリの数を取得します。|
|[CPalette:: Getnearestパレットインデックス](#getnearestpaletteindex)|色の値に最も近い論理パレット内のエントリのインデックスを返します。|
|[CPalette:: Getパレットエントリ](#getpaletteentries)|論理パレット内のパレットエントリの範囲を取得します。|
|[CPalette:: ResizePalette](#resizepalette)|オブジェクトで指定された論理パレットのサイズ `CPalette` を、指定されたエントリ数に変更します。|
|[CPalette:: Setパレットエントリ](#setpaletteentries)|論理パレットのエントリ範囲の RGB 色の値とフラグを設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CPalette:: operator HPALETTE](#operator_hpalette)|にアタッチされている HPALETTE を返し `CPalette` ます。|

## <a name="remarks"></a>解説

パレットには、アプリケーションとカラー出力デバイス (ディスプレイデバイスなど) との間のインターフェイスが用意されています。 インターフェイスを使用すると、アプリケーションは、他のアプリケーションによって表示される色に大きな影響を与えずに、出力デバイスの色の機能を最大限に活用することができます。 Windows では、アプリケーションの論理パレット (必要な色の一覧) とシステムパレット (使用可能な色を定義) を使用して、使用する色を決定します。

オブジェクトは、 `CPalette` オブジェクトによって参照されるパレットを操作するためのメンバー関数を提供します。 オブジェクトを構築 `CPalette` し、そのメンバー関数を使用して、実際のパレット、グラフィックスデバイスインターフェイス (GDI) オブジェクト、およびそのエントリとその他のプロパティを操作します。

の使用方法の詳細について `CPalette` は、「 [グラフィックオブジェクト](../../mfc/graphic-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cpaletteanimatepalette"></a><a name="animatepalette"></a> CPalette:: AnimatePalette

オブジェクトにアタッチされている論理パレット内のエントリを置き換え `CPalette` ます。

```cpp
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>パラメーター

*nStartIndex*<br/>
アニメーション化するパレットの最初のエントリを指定します。

*nNumEntries*<br/>
パレット内のアニメーション化するエントリの数を指定します。

*lpPaletteColors*<br/>
は、palette [エントリ](/previous-versions/dd162769\(v=vs.85\)) 構造体の配列の最初のメンバーを指し、 *Nstartindex* および *nnumentries* によって識別されるパレットエントリを置き換えます。

### <a name="remarks"></a>解説

Windows では `AnimatePalette` 、新しいエントリがシステムパレットにすぐにマップされるため、アプリケーションがを呼び出すと、クライアント領域を更新する必要はありません。

関数は、 `AnimatePalette` `palPaletteEntry` オブジェクトにアタッチされている [logpalette](/windows/win32/api/wingdi/ns-wingdi-logpalette) 構造体の対応するメンバーに PC_RESERVED フラグが設定されているエントリのみを変更し `CPalette` ます。 この構造の詳細については、Windows SDK の LOGPALETTE に関する説明を参照してください。

## <a name="cpalettecpalette"></a><a name="cpalette"></a> CPalette:: CPalette

`CPalette` オブジェクトを構築します。

```
CPalette();
```

### <a name="remarks"></a>解説

オブジェクトには、を呼び出してアタッチするパレットがありません `CreatePalette` 。

## <a name="cpalettecreatehalftonepalette"></a><a name="createhalftonepalette"></a> CPalette:: CreateHalftonePalette

デバイスコンテキストのハーフトーンパレットを作成します。

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイスコンテキストを識別します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

アプリケーションは、デバイスコンテキストの伸縮モードがハーフトーンに設定されている場合に、ハーフトーンパレットを作成する必要があります。 次に、 [CreateHalftonePalette](/windows/win32/api/wingdi/nf-wingdi-createhalftonepalette) メンバー関数によって返される論理ハーフトーンパレットを選択し、 [CDC:: StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) または [StretchDIBits](/windows/win32/api/wingdi/nf-wingdi-stretchdibits) 関数が呼び出される前にデバイスコンテキストに認識されるようにする必要があります。

およびの詳細については、Windows SDK を参照してください `CreateHalftonePalette` `StretchDIBits` 。

## <a name="cpalettecreatepalette"></a><a name="createpalette"></a> CPalette:: CreatePalette

Windows の `CPalette` 論理カラーパレットを作成し、オブジェクトにアタッチすることによって、オブジェクトを初期化し `CPalette` ます。

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>パラメーター

*lpLogPalette*<br/>
論理パレットの色に関する情報を含む [Logpalette](/windows/win32/api/wingdi/ns-wingdi-logpalette) 構造体を指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

構造の詳細については、Windows SDK を参照してください `LOGPALETTE` 。

## <a name="cpalettefromhandle"></a><a name="fromhandle"></a> CPalette:: FromHandle

`CPalette`Windows パレットオブジェクトへのハンドルが指定された場合に、オブジェクトへのポインターを返します。

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>パラメーター

*hPalette*<br/>
Windows GDI カラーパレットを処理するハンドル。

### <a name="return-value"></a>戻り値

成功した場合はオブジェクトへのポインター、 `CPalette` それ以外の場合は NULL。

### <a name="remarks"></a>解説

`CPalette`オブジェクトが Windows パレットにまだアタッチされていない場合は、一時 `CPalette` オブジェクトが作成され、アタッチされます。 この一時 `CPalette` オブジェクトは、アプリケーションが次にそのイベントループ内でアイドル状態になったときにのみ有効です。その時点で、すべての一時グラフィックオブジェクトが削除されます。 つまり、一時オブジェクトは、1つのウィンドウメッセージの処理中にのみ有効です。

## <a name="cpalettegetentrycount"></a><a name="getentrycount"></a> CPalette:: GetEntryCount

このメンバー関数を呼び出して、指定された論理パレット内のエントリの数を取得します。

```
int GetEntryCount();
```

### <a name="return-value"></a>戻り値

論理パレット内のエントリの数。

## <a name="cpalettegetnearestpaletteindex"></a><a name="getnearestpaletteindex"></a> CPalette:: Getnearestパレットインデックス

指定された色の値に最も近い論理パレット内のエントリのインデックスを返します。

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>パラメーター

*crColor*<br/>
照合する色を指定します。

### <a name="return-value"></a>戻り値

論理パレット内のエントリのインデックス。 エントリには、指定した色に最も近い色が含まれています。

## <a name="cpalettegetpaletteentries"></a><a name="getpaletteentries"></a> CPalette:: Getパレットエントリ

論理パレット内のパレットエントリの範囲を取得します。

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>パラメーター

*nStartIndex*<br/>
取得する論理パレットの最初のエントリを指定します。

*nNumEntries*<br/>
取得する論理パレット内のエントリの数を指定します。

*lpPaletteColors*<br/>
パレットエントリを受け取るパレット [エントリ](/previous-versions/dd162769\(v=vs.85\)) データ構造体の配列をポイントします。 配列には、少なくとも *Nnumentries* によって指定された数のデータ構造体が含まれている必要があります。

### <a name="return-value"></a>戻り値

論理パレットから取得されたエントリの数。関数が失敗した場合は0。

## <a name="cpaletteoperator-hpalette"></a><a name="operator_hpalette"></a> CPalette:: operator HPALETTE

オブジェクトのアタッチされた Windows GDI ハンドルを取得するには、この演算子を使用し `CPalette` ます。

```
operator HPALETTE() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトによって表される Windows GDI オブジェクトへのハンドル `CPalette` 。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は、HPALETTE オブジェクトの直接使用をサポートするキャスト演算子です。

グラフィックオブジェクトの使用方法の詳細については、Windows SDK の「 [グラフィックオブジェクト](/windows/win32/gdi/graphic-objects) 」を参照してください。

## <a name="cpaletteresizepalette"></a><a name="resizepalette"></a> CPalette:: ResizePalette

オブジェクトにアタッチされている論理パレットのサイズ `CPalette` を、 *Nnumentries* によって指定されたエントリの数に変更します。

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>パラメーター

*nNumEntries*<br/>
サイズを変更した後のパレット内のエントリの数を指定します。

### <a name="return-value"></a>戻り値

パレットのサイズが正常に変更された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

アプリケーションがを呼び出してパレットのサイズを縮小した場合、サイズを `ResizePalette` 変更したパレットの残りのエントリは変更されません。 アプリケーションがを呼び出して `ResizePalette` パレットを拡大すると、追加のパレットエントリは黒 (赤、緑、および青の値はすべて 0) に設定され、すべての追加エントリのフラグは0に設定されます。

Windows API の詳細については、 `ResizePalette` Windows SDK の「 [ResizePalette](/windows/win32/api/wingdi/nf-wingdi-resizepalette) 」を参照してください。

## <a name="cpalettesetpaletteentries"></a><a name="setpaletteentries"></a> CPalette:: Setパレットエントリ

論理パレットのエントリ範囲の RGB 色の値とフラグを設定します。

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>パラメーター

*nStartIndex*<br/>
設定する論理パレットの最初のエントリを指定します。

*nNumEntries*<br/>
設定する論理パレット内のエントリの数を指定します。

*lpPaletteColors*<br/>
パレットエントリを受け取るパレット [エントリ](/previous-versions/dd162769\(v=vs.85\)) データ構造体の配列をポイントします。 配列には、少なくとも *Nnumentries* によって指定された数のデータ構造体が含まれている必要があります。

### <a name="return-value"></a>戻り値

論理パレットに設定されているエントリの数。関数が失敗した場合は0。

### <a name="remarks"></a>解説

アプリケーションがを呼び出したときに論理パレットがデバイスコンテキストに選択されている場合 `SetPaletteEntries` 、アプリケーションが [CDC:: RealizePalette](../../mfc/reference/cdc-class.md#realizepalette)を呼び出すまで、変更は有効になりません。

詳細については、Windows SDK の「 [パレットエントリ](/previous-versions/dd162769\(v=vs.85\)) 」を参照してください。

## <a name="see-also"></a>関連項目

[MFC のサンプル DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPalette:: Getパレットエントリ](#getpaletteentries)<br/>
[CPalette:: Setパレットエントリ](#setpaletteentries)
