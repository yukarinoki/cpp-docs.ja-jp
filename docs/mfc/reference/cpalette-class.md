---
title: Cパレットクラス
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
ms.openlocfilehash: 83cd125fa7ab64aa39c606bc048022400d158e72
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374758"
---
# <a name="cpalette-class"></a>Cパレットクラス

Windows のカラー パレットをカプセル化します。

## <a name="syntax"></a>構文

```
class CPalette : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cパレット::Cパレット](#cpalette)|Windows パレット`CPalette`がアタッチされていないオブジェクトを構築します。 オブジェクトを使用する`CPalette`前に、初期化メンバー関数のいずれかを使用してオブジェクトを初期化する必要があります。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cパレット::アニメーションパレット](#animatepalette)|オブジェクトによって識別される論理パレットの項目を`CPalette`置き換えます。 Windows は新しいエントリをシステム パレットにすぐにマップするため、アプリケーションはクライアント領域を更新する必要はありません。|
|[パレット::ハーフトーンを作成します。](#createhalftonepalette)|デバイス コンテキストのハーフトーン パレットを作成し、オブジェクトに`CPalette`アタッチします。|
|[Cパレット::パレットの作成](#createpalette)|Windows カラー パレットを作成し、オブジェクトに`CPalette`アタッチします。|
|[Cパレット::ハンドルから](#fromhandle)|Windows パレット オブジェクト`CPalette`へのハンドルが与えられた場合、オブジェクトへのポインターを返します。|
|[を使用します。](#getentrycount)|論理パレット内のパレット エントリの数を取得します。|
|[パレット::最も近いパレットインデックス](#getnearestpaletteindex)|カラー値に最も近い論理パレットのエントリのインデックスを返します。|
|[パレット::パレットエントリを取得します。](#getpaletteentries)|論理パレットのパレット エントリの範囲を取得します。|
|[Cパレット::サイズ変更パレット](#resizepalette)|オブジェクトで指定された論理パレットのサイズを`CPalette`、指定した数のエントリに変更します。|
|[Cパレット::パレットエントリを設定します。](#setpaletteentries)|論理パレットのエントリ範囲に RGB カラー値とフラグを設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cパレット::演算子Hパレット](#operator_hpalette)|にアタッチされた HPALETTE`CPalette`を返します。|

## <a name="remarks"></a>解説

パレットは、アプリケーションとカラー出力デバイス (ディスプレイ デバイスなど) の間のインターフェイスを提供します。 このインターフェイスを使用すると、アプリケーションは、他のアプリケーションによって表示される色に重大な影響を与えることなく、出力デバイスの色機能を最大限に活用できます。 Windows では、アプリケーションの論理パレット (必要な色のリスト) とシステム パレット (使用可能な色を定義) を使用して、使用する色を決定します。

オブジェクト`CPalette`は、オブジェクトによって参照されるパレットを操作するためのメンバー関数を提供します。 オブジェクトを`CPalette`構築し、そのメンバー関数を使用して、実際のパレット、グラフィックス デバイス インターフェイス (GDI) オブジェクトを作成し、そのエントリやその他のプロパティを操作します。

の使用方法`CPalette`の詳細については、「[グラフィック オブジェクト](../../mfc/graphic-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cpaletteanimatepalette"></a><a name="animatepalette"></a>Cパレット::アニメーションパレット

`CPalette`オブジェクトにアタッチされている論理パレットのエントリを置き換えます。

```
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>パラメーター

*インデックスを作成します。*<br/>
パレット内の最初の項目を指定します。

*エントリー*<br/>
アニメーション化するパレットのエントリ数を指定します。

*カラー*<br/>
*nStartIndex*と nNumEntries で識別されるパレット エントリを置き換えるために、[パレットエントリ](/previous-versions/dd162769\(v=vs.85\))構造体の配列の最初のメンバー*を指します*。

### <a name="remarks"></a>解説

アプリケーションが 呼`AnimatePalette`び出すとき、新しいエントリがシステム パレットに直ちにマップされるため、クライアント領域を更新する必要はありません。

この`AnimatePalette`関数は、`CPalette`オブジェクトにアタッチされている[LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette)構造体の`palPaletteEntry`対応するメンバーに PC_RESERVED フラグが設定されている項目のみを変更します。 この構造体の詳細については、Windows SDK の「LOGPALETTE」を参照してください。

## <a name="cpalettecpalette"></a><a name="cpalette"></a>Cパレット::Cパレット

`CPalette` オブジェクトを構築します。

```
CPalette();
```

### <a name="remarks"></a>解説

オブジェクトには、アタッチするパレットを呼び`CreatePalette`出すまで、パレットはアタッチされません。

## <a name="cpalettecreatehalftonepalette"></a><a name="createhalftonepalette"></a>パレット::ハーフトーンを作成します。

デバイス コンテキストのハーフトーン パレットを作成します。

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイス コンテキストを識別します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

デバイス コンテキストの伸縮モードが HALFTONE に設定されている場合、アプリケーションはハーフトーン パレットを作成する必要があります。 [CreateHalftonePalette](/windows/win32/api/wingdi/nf-wingdi-createhalftonepalette)メンバー関数によって返される論理ハーフトーン パレットは[、CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt)関数または[StretchDIBits](/windows/win32/api/wingdi/nf-wingdi-stretchdibits)関数が呼び出される前に、デバイス コンテキストに対して選択および実現する必要があります。

および`CreateHalftonePalette``StretchDIBits`の詳細については、Windows SDK を参照してください。

## <a name="cpalettecreatepalette"></a><a name="createpalette"></a>Cパレット::パレットの作成

Windows の`CPalette`論理カラー パレットを作成し、オブジェクトにアタッチすることによって、オブジェクト`CPalette`を初期化します。

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>パラメーター

*パレット*<br/>
論理パレットの色に関する情報を含む[LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette)構造体へのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

構造の詳細については、Windows SDK`LOGPALETTE`を参照してください。

## <a name="cpalettefromhandle"></a><a name="fromhandle"></a>Cパレット::ハンドルから

Windows パレット オブジェクト`CPalette`へのハンドルが与えられた場合、オブジェクトへのポインターを返します。

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>パラメーター

*hパレット*<br/>
Windows GDI カラー パレットへのハンドル。

### <a name="return-value"></a>戻り値

成功した場合は`CPalette`オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

`CPalette`オブジェクトが Windows パレットにまだアタッチされていない場合は、一`CPalette`時オブジェクトが作成され、アタッチされます。 この一`CPalette`時オブジェクトは、アプリケーションがイベント ループで次にアイドル時間を持つまで有効で、その時点ですべての一時グラフィック オブジェクトが削除されます。 つまり、一時オブジェクトは、1 つのウィンドウ メッセージの処理中にのみ有効です。

## <a name="cpalettegetentrycount"></a><a name="getentrycount"></a>を使用します。

指定された論理パレットのエントリ数を取得します。

```
int GetEntryCount();
```

### <a name="return-value"></a>戻り値

論理パレット内のエントリ数。

## <a name="cpalettegetnearestpaletteindex"></a><a name="getnearestpaletteindex"></a>パレット::最も近いパレットインデックス

指定した色の値に最も近い論理パレット内のエントリのインデックスを返します。

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>パラメーター

*Crcolor*<br/>
一致する色を指定します。

### <a name="return-value"></a>戻り値

論理パレット内のエントリのインデックス。 エントリには、指定した色とほぼ一致する色が含まれています。

## <a name="cpalettegetpaletteentries"></a><a name="getpaletteentries"></a>パレット::パレットエントリを取得します。

論理パレットのパレット エントリの範囲を取得します。

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>パラメーター

*インデックスを作成します。*<br/>
取得する論理パレットの最初のエントリを指定します。

*エントリー*<br/>
取得する論理パレットのエントリ数を指定します。

*カラー*<br/>
パレット項目を受け取る[パレットエントリ](/previous-versions/dd162769\(v=vs.85\))のデータ構造の配列を指します。 配列には *、nNumEntries*で指定された数のデータ構造が含まれている必要があります。

### <a name="return-value"></a>戻り値

論理パレットから取得されたエントリの数。関数が失敗した場合は 0。

## <a name="cpaletteoperator-hpalette"></a><a name="operator_hpalette"></a>Cパレット::演算子Hパレット

この演算子を使用して、オブジェクトの添付された Windows `CPalette` GDI ハンドルを取得します。

```
operator HPALETTE() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトによって表される Windows GDI`CPalette`オブジェクトへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子はキャスト演算子で、HPALETTE オブジェクトの直接使用をサポートします。

グラフィック オブジェクトの使用の詳細については、Windows SDK の記事[「グラフィック オブジェクト](/windows/win32/gdi/graphic-objects)」を参照してください。

## <a name="cpaletteresizepalette"></a><a name="resizepalette"></a>Cパレット::サイズ変更パレット

オブジェクトにアタッチされた論理パレットのサイズを`CPalette` *nNumEntries*で指定されたエントリ数に変更します。

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>パラメーター

*エントリー*<br/>
サイズ変更後のパレットのエントリ数を指定します。

### <a name="return-value"></a>戻り値

パレットのサイズが正常に変更された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

パレットのサイズを`ResizePalette`小さくするためにアプリケーションが呼び出した場合、サイズ変更されたパレットに残っているエントリは変更されません。 パレットを拡大するために`ResizePalette`アプリケーションが呼び出した場合、追加のパレットエントリは黒 (赤、緑、青の値はすべて 0)に設定され、追加のエントリのフラグはすべて 0 に設定されます。

Windows API`ResizePalette`の詳細については、「Windows SDK の[サイズ変更パレット](/windows/win32/api/wingdi/nf-wingdi-resizepalette)」を参照してください。

## <a name="cpalettesetpaletteentries"></a><a name="setpaletteentries"></a>Cパレット::パレットエントリを設定します。

論理パレットのエントリ範囲に RGB カラー値とフラグを設定します。

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>パラメーター

*インデックスを作成します。*<br/>
論理パレットの最初のエントリを指定します。

*エントリー*<br/>
設定する論理パレットのエントリ数を指定します。

*カラー*<br/>
パレット項目を受け取る[パレットエントリ](/previous-versions/dd162769\(v=vs.85\))のデータ構造の配列を指します。 配列には *、nNumEntries*で指定された数のデータ構造が含まれている必要があります。

### <a name="return-value"></a>戻り値

論理パレットに設定されたエントリの数。関数が失敗した場合は 0。

### <a name="remarks"></a>解説

アプリケーションが呼び出したときに`SetPaletteEntries`論理パレットがデバイス コンテキストに選択されている場合、アプリケーションが[CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette)を呼び出すまで、変更は有効になりません。

詳細については、Windows SDK[のパレットエントリ](/previous-versions/dd162769\(v=vs.85\))を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル ディブルック](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[パレット::パレットエントリを取得します。](#getpaletteentries)<br/>
[Cパレット::パレットエントリを設定します。](#setpaletteentries)
