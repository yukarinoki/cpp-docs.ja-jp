---
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
ms.openlocfilehash: 1022d05265fc7c2b349dec22e41984e7d41820b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586057"
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
|[CPalette::CPalette](#cpalette)|構築、`CPalette`接続されている Windows パレットがないオブジェクト。 初期化する必要があります、`CPalette`初期化メンバー関数を使用するのいずれかのオブジェクト。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPalette::AnimatePalette](#animatepalette)|識別される論理パレット内のエントリを置き換える、`CPalette`オブジェクト。 Windows システム パレットに、新しいエントリをすぐにマップされるため、アプリケーションは、クライアント領域の更新がありません。|
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|デバイス コンテキストのハーフトーン パレットを作成しにアタッチします、`CPalette`オブジェクト。|
|[CPalette::CreatePalette](#createpalette)|Windows カラー パレットを作成しにアタッチします、`CPalette`オブジェクト。|
|[CPalette::FromHandle](#fromhandle)|ポインターを返します、 `CPalette` Windows パレット オブジェクトへのハンドルが指定されるとします。|
|[CPalette::GetEntryCount](#getentrycount)|論理パレットのパレット エントリの数を取得します。|
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|論理パレットに色の値に最も近いエントリのインデックスを返します。|
|[CPalette::GetPaletteEntries](#getpaletteentries)|論理パレットのパレット エントリの範囲を取得します。|
|[CPalette::ResizePalette](#resizepalette)|指定された論理パレットのサイズを変更、`CPalette`エントリ数を指定するオブジェクト。|
|[CPalette::SetPaletteEntries](#setpaletteentries)|論理パレット内のエントリの範囲内の RGB カラー値とフラグを設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CPalette::operator HPALETTE](#operator_hpalette)|アタッチされている返します、HPALETTE、`CPalette`します。|

## <a name="remarks"></a>Remarks

パレットでは、アプリケーションと (ディスプレイ デバイスの場合) などの色出力デバイス間のインターフェイスを提供します。 インターフェイスは、出力デバイスの色の機能の活用を他のアプリケーションで表示される色に深刻な干渉せずにアプリケーションを使用します。 Windows では、アプリケーションの論理パレット (必要な色のリスト) と (これは、使用可能な色を定義します)、システム パレットを使用して、使用する色を決定します。

A`CPalette`のパレットを操作するオブジェクトによって参照されるオブジェクトはメンバー関数を提供します。 構築、`CPalette`オブジェクトし、そのメンバー関数を使用して、実際のパレットで、グラフィックス デバイス インターフェイス (GDI) オブジェクトを作成して、そのエントリとその他のプロパティを操作します。

使用しての詳細については`CPalette`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="animatepalette"></a>  CPalette::AnimatePalette

アタッチされている論理パレット内のエントリを置き換える、`CPalette`オブジェクト。

```
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>パラメーター

*nStartIndex*<br/>
アニメーション化するパレットの最初のエントリを指定します。

*とも*<br/>
アニメーション化するパレット内のエントリの数を指定します。

*lpPaletteColors*<br/>
配列の最初のメンバーを指す[受け取る](https://msdn.microsoft.com/library/windows/desktop/dd162769)構造で識別されるパレット エントリを置き換え*nStartIndex*と*とも*します。

### <a name="remarks"></a>Remarks

アプリケーションを呼び出すと`AnimatePalette`、ことはありません、クライアント領域を更新するため、Windows システム パレットに、新しいエントリをすぐにマップされます。

`AnimatePalette`関数は、対応する設定 PC_RESERVED フラグでエントリは変更のみ`palPaletteEntry`のメンバー、[保持](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette)構造に関連付けられている、`CPalette`オブジェクト。 この構造体の詳細については、Windows SDK での保持を参照してください。

##  <a name="cpalette"></a>  CPalette::CPalette

`CPalette` オブジェクトを構築します。

```
CPalette();
```

### <a name="remarks"></a>Remarks

オブジェクトには接続されているパレットがないを呼び出すまで`CreatePalette`いずれかをアタッチします。

##  <a name="createhalftonepalette"></a>  CPalette::CreateHalftonePalette

デバイス コンテキストのハーフトーン パレットを作成します。

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイス コンテキストを識別します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ハーフトーン パレットは、ハーフトーンをデバイス コンテキストの伸縮モードが設定されている場合、アプリケーションで作成する必要があります。 によって返される論理ハーフトーン パレット、 [CreateHalftonePalette](/windows/desktop/api/wingdi/nf-wingdi-createhalftonepalette)メンバー関数は必要がありますし、選択し、前にデバイス コンテキストに実現、 [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt)または[StretchDIBits](/windows/desktop/api/wingdi/nf-wingdi-stretchdibits)関数が呼び出されます。

に関する詳細については、Windows SDK を参照してください`CreateHalftonePalette`と`StretchDIBits`します。

##  <a name="createpalette"></a>  CPalette::CreatePalette

初期化します、`CPalette`を Windows 論理カラー パレットを作成してアタッチするオブジェクト、`CPalette`オブジェクト。

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>パラメーター

*lpLogPalette*<br/>
指す、[保持](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette)論理パレットの色に関する情報を含む構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

に関する詳細については、Windows SDK を参照してください、`LOGPALETTE`構造体。

##  <a name="fromhandle"></a>  CPalette::FromHandle

ポインターを返します、 `CPalette` Windows パレット オブジェクトへのハンドルが指定されるとします。

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>パラメーター

*hPalette*<br/>
Windows GDI カラー パレットへのハンドル。

### <a name="return-value"></a>戻り値

ポインター、`CPalette`成功。 それ以外の場合に NULL の場合は、オブジェクト。

### <a name="remarks"></a>Remarks

場合、 `CPalette` Windows パレットは、一時的にオブジェクトが既にアタッチされていない`CPalette`オブジェクトを作成し、接続されています。 この一時`CPalette`すべて一時的なグラフィックを時間があるオブジェクトは削除まで、次回、アプリケーションは、イベント ループでのアイドル時間は、専用、オブジェクトが無効です。 つまり、一時オブジェクトは 1 つのウィンドウ メッセージを処理中にのみ有効です。

##  <a name="getentrycount"></a>  CPalette::GetEntryCount

指定した論理パレット内のエントリの数を取得するには、このメンバー関数を呼び出します。

```
int GetEntryCount();
```

### <a name="return-value"></a>戻り値

論理パレット内のエントリの数。

##  <a name="getnearestpaletteindex"></a>  CPalette::GetNearestPaletteIndex

指定した色の値に最も近い論理パレットのエントリのインデックスを返します。

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>パラメーター

*crColor*<br/>
一致する色を指定します。

### <a name="return-value"></a>戻り値

論理パレット内のエントリのインデックス。 エントリには、指定した色に最も近い色が含まれています。

##  <a name="getpaletteentries"></a>  CPalette::GetPaletteEntries

論理パレットのパレット エントリの範囲を取得します。

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>パラメーター

*nStartIndex*<br/>
取得する論理パレットの最初のエントリを指定します。

*とも*<br/>
論理パレットを取得するエントリの数を指定します。

*lpPaletteColors*<br/>
配列を指す[受け取る](https://msdn.microsoft.com/library/windows/desktop/dd162769)パレット エントリを受信するデータ構造体。 配列で指定された数以上のデータ構造を含める必要があります*とも*します。

### <a name="return-value"></a>戻り値

論理パレット; から取得されたエントリの数関数が失敗した場合は 0 を返します。

##  <a name="operator_hpalette"></a>  CPalette::operator HPALETTE

接続されている Windows GDI ハンドルを取得するこの演算子を使用して、`CPalette`オブジェクト。

```
operator HPALETTE() const;
```

### <a name="return-value"></a>戻り値

かどうかは成功すると、Windows GDI オブジェクトを識別するハンドルで表される、`CPalette`オブジェクト。 それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

この演算子は、キャスト演算子です。

グラフィック オブジェクトの使用に関する詳細については、記事を参照してください。[グラフィック オブジェクト](/windows/desktop/gdi/graphic-objects)Windows SDK に含まれています。

##  <a name="resizepalette"></a>  CPalette::ResizePalette

アタッチされている論理パレットのサイズを変更、`CPalette`オブジェクトで指定されたエントリの数を*とも*します。

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>パラメーター

*とも*<br/>
サイズ変更された後、パレット内のエントリの数を指定します。

### <a name="return-value"></a>戻り値

パレットが正常にサイズを変更する場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションを呼び出す場合`ResizePalette`パレットのサイズを減らすためには、サイズ変更のパレットの残りのエントリは変更されません。 アプリケーションを呼び出す場合`ResizePalette`パレットの拡大、追加パレット エントリは黒 (赤、緑、青の値はすべて 0) に設定され、その他のすべてのエントリのフラグが 0 に設定されます。

Windows API の詳細については`ResizePalette`を参照してください[ため](/windows/desktop/api/wingdi/nf-wingdi-resizepalette)Windows SDK に含まれています。

##  <a name="setpaletteentries"></a>  CPalette::SetPaletteEntries

論理パレット内のエントリの範囲内の RGB カラー値とフラグを設定します。

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>パラメーター

*nStartIndex*<br/>
設定する論理パレットの最初のエントリを指定します。

*とも*<br/>
設定する論理パレットのエントリの数を指定します。

*lpPaletteColors*<br/>
配列を指す[受け取る](https://msdn.microsoft.com/library/windows/desktop/dd162769)パレット エントリを受信するデータ構造体。 配列で指定された数以上のデータ構造を含める必要があります*とも*します。

### <a name="return-value"></a>戻り値

論理パレット内のエントリの数を設定関数が失敗した場合は 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションを呼び出すときに、論理パレットがデバイス コンテキストに選択されるかどうか`SetPaletteEntries`、変更は反映されません、アプリケーションが[:realizepalette](../../mfc/reference/cdc-class.md#realizepalette)します。

Windows 構造体の詳細については`PALETTEENTRY`を参照してください[受け取る](https://msdn.microsoft.com/library/windows/desktop/dd162769)Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[MFC サンプル DIBLOOK](../../visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPalette::GetPaletteEntries](#getpaletteentries)<br/>
[CPalette::SetPaletteEntries](#setpaletteentries)

