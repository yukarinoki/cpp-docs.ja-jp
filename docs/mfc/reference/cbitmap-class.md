---
description: '詳細情報: CBitmap クラス'
title: CBitmap クラス
ms.date: 11/04/2016
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
ms.openlocfilehash: e3d54a87cb53757f4751558b77e9c0c187484410
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122721"
---
# <a name="cbitmap-class"></a>CBitmap クラス

Windows のグラフィック デバイス インターフェイス (GDI: Graphics Device Interface) のビットマップをカプセル化したもので、ビットマップを操作するためのメンバー関数を提供します。

## <a name="syntax"></a>構文

```
class CBitmap : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CBitmap:: CBitmap](#cbitmap)|`CBitmap` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CBitmap:: CreateBitmap](#createbitmap)|指定した幅、高さ、およびビットパターンを持つデバイス依存のメモリビットマップを使用して、オブジェクトを初期化します。|
|[CBitmap:: CreateBitmapIndirect](#createbitmapindirect)|構造体に指定されている幅、高さ、ビットパターンが指定されている場合は、ビットマップを使用してオブジェクトを初期化し `BITMAP` ます。|
|[CBitmap:: CreateCompatibleBitmap](#createcompatiblebitmap)|指定したデバイスとの互換性を確保するために、ビットマップを使用してオブジェクトを初期化します。|
|[CBitmap:: CreateDiscardableBitmap](#creatediscardablebitmap)|指定したデバイスと互換性のある破棄できないビットマップを使用して、オブジェクトを初期化します。|
|[CBitmap:: FromHandle](#fromhandle)|`CBitmap`Windows ビットマップへのハンドルが指定された場合に、オブジェクトへのポインターを返し `HBITMAP` ます。|
|[CBitmap:: GetBitmap](#getbitmap)|`BITMAP`構造体にビットマップに関する情報を格納します。|
|[CBitmap:: GetBitmapBits](#getbitmapbits)|指定したビットマップのビットを、指定したバッファーにコピーします。|
|[CBitmap:: GetBitmapDimension](#getbitmapdimension)|ビットマップの幅と高さを返します。 高さと幅は、以前に [Setbitmapdimension](#setbitmapdimension) メンバー関数によって設定されていると見なされます。|
|[CBitmap:: LoadBitmap](#loadbitmap)|アプリケーションの実行可能ファイルから名前付きビットマップリソースを読み込み、オブジェクトにビットマップをアタッチすることによって、オブジェクトを初期化します。|
|[CBitmap:: LoadMappedBitmap](#loadmappedbitmap)|ビットマップを読み込み、色を現在のシステムカラーにマップします。|
|[CBitmap:: LoadOEMBitmap](#loadoembitmap)|定義済みの Windows ビットマップを読み込み、オブジェクトにビットマップをアタッチすることによって、オブジェクトを初期化します。|
|[CBitmap:: SetBitmapBits](#setbitmapbits)|ビットマップのビットを、指定したビット値に設定します。|
|[CBitmap:: SetBitmapDimension](#setbitmapdimension)|0.1-ミリメートル単位でビットマップに幅と高さを割り当てます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CBitmap:: operator HBITMAP](#operator_hbitmap)|オブジェクトにアタッチされている Windows ハンドルを返し `CBitmap` ます。|

## <a name="remarks"></a>解説

オブジェクトを使用するには、オブジェクトを構築し、 `CBitmap` 初期化メンバー関数のいずれかを使用してビットマップハンドルをそのオブジェクトにアタッチしてから、オブジェクトのメンバー関数を呼び出します。

などのグラフィックオブジェクトの使用方法の詳細について `CBitmap` は、「 [グラフィックオブジェクト](../../mfc/graphic-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cbitmapcbitmap"></a><a name="cbitmap"></a> CBitmap:: CBitmap

`CBitmap` オブジェクトを構築します。

```
CBitmap();
```

### <a name="remarks"></a>解説

生成されたオブジェクトは、初期化メンバー関数のいずれかを使用して初期化する必要があります。

## <a name="cbitmapcreatebitmap"></a><a name="createbitmap"></a> CBitmap:: CreateBitmap

指定した幅、高さ、ビット パターンに設定されている、デバイス依存のメモリ ビットマップを初期化します。

```
BOOL CreateBitmap(
    int nWidth,
    int nHeight,
    UINT nPlanes,
    UINT nBitcount,
    const void* lpBits);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
ビットマップの幅 (ピクセル単位) を指定します。

*nHeight*<br/>
ビットマップの高さ (ピクセル単位) を指定します。

*nPlanes*<br/>
ビットマップ内でのカラー プレーンの数を指定します。

*nBitcount*<br/>
表示ピクセルごとのカラー ビット数を指定します。

*lpBits*<br/>
初期のビットマップのビット値を含むバイト配列を指します。 NULL の場合、新しいビットマップは初期化されないままになります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

色ビットマップの場合は、 *Nplanes* または *nbitcount* パラメーターを1に設定する必要があります。 両方のパラメーターを 1 に設定すると、 `CreateBitmap` によってモノクロのビットマップが作成されます。

表示デバイス用のビットマップを直接選択することはできませんが、 [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) を使用して「メモリ デバイス コンテキスト」の現在のビットマップとして選択し、それを [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) 関数を使用して互換性のある任意のデバイス コンテキストにコピーできます。

`CBitmap` 関数によって作成された `CreateBitmap` オブジェクトでの作業終了後、デバイス コンテキスト外のビットマップを最初に選択し、次に `CBitmap` オブジェクトを削除します。

詳細については、構造体のフィールドの説明を参照してください `bmBits` `BITMAP` 。 [BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap) 構造体については、 [CBitmap::CreateBitmapIndirect](#createbitmapindirect) メンバー関数の下で説明されています。

## <a name="cbitmapcreatebitmapindirect"></a><a name="createbitmapindirect"></a> CBitmap:: CreateBitmapIndirect

*Lpbitmap* が指す構造体に指定されている幅、高さ、ビットパターンを持つビットマップを初期化します (指定されている場合)。

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>パラメーター

*lpBitmap*<br/>
ビットマップに関する情報を格納している [ビットマップ](/windows/win32/api/wingdi/ns-wingdi-bitmap) 構造体を指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ディスプレイデバイスに対してビットマップを直接選択することはできませんが、 [cdc:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) を使用してメモリデバイスコンテキストの現在のビットマップとして選択し、 [Cdc:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) または [cdc:: StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) 関数を使用して互換性のある任意のデバイスコンテキストにコピーすることができます。 ( [CDC::P atBlt](../../mfc/reference/cdc-class.md#patblt) 関数は、現在のブラシのビットマップを、ディスプレイデバイスコンテキストに直接コピーできます)。

`BITMAP` *Lpbitmap* パラメーターによって示される構造体が関数を使用して入力されている場合 `GetObject` 、ビットマップのビットは指定されず、ビットマップは初期化されません。 ビットマップを初期化するには、アプリケーションで [CDC:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) や [setdibits](/windows/win32/api/wingdi/nf-wingdi-setdibits) などの関数を使用して、の最初のパラメーターで識別されるビットマップのビットを、 `CGdiObject::GetObject` によって作成されたビットマップにコピーし `CreateBitmapIndirect` ます。

`CBitmap`関数で作成されたオブジェクトを終了したら `CreateBitmapIndirect` 、まずデバイスコンテキストからビットマップを選択し、次にオブジェクトを削除し `CBitmap` ます。

## <a name="cbitmapcreatecompatiblebitmap"></a><a name="createcompatiblebitmap"></a> CBitmap:: CreateCompatibleBitmap

*PDC* によって指定されたデバイスと互換性のあるビットマップを初期化します。

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイスコンテキストを指定します。

*nWidth*<br/>
ビットマップの幅 (ピクセル単位) を指定します。

*nHeight*<br/>
ビットマップの高さ (ピクセル単位) を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ビットマップには、指定されたデバイスコンテキストと同じ数のカラープレーンまたは同じビット/ピクセル形式があります。 *PDC* によって指定されたものと互換性のある任意のメモリデバイスの現在のビットマップとして選択できます。

*PDC* がメモリデバイスコンテキストの場合、返されるビットマップは、そのデバイスコンテキストで現在選択されているビットマップと同じ形式です。 "メモリデバイスコンテキスト" は、表示サーフェイスを表すメモリのブロックです。 互換性のあるデバイスの実際の表示画面にコピーする前に、イメージをメモリ内に準備するために使用できます。

メモリデバイスコンテキストが作成されると、GDI は自動的にモノクロの株価ビットマップを選択します。

カラーメモリデバイスコンテキストでは、カラービットマップまたはモノクロビットマップを選択できます。そのため、関数によって返されるビットマップの形式は `CreateCompatibleBitmap` 常に同じではありません。ただし、メモリデバイスコンテキスト以外では、互換性のあるビットマップの形式は常にデバイスの形式になります。

`CBitmap`関数で作成されたオブジェクトを終了したら `CreateCompatibleBitmap` 、まずデバイスコンテキストからビットマップを選択し、次にオブジェクトを削除し `CBitmap` ます。

## <a name="cbitmapcreatediscardablebitmap"></a><a name="creatediscardablebitmap"></a> CBitmap:: CreateDiscardableBitmap

*PDC* によって識別されるデバイスコンテキストと互換性のある破棄できないビットマップを初期化します。

```
BOOL CreateDiscardableBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイスコンテキストを指定します。

*nWidth*<br/>
ビットマップの幅 (ビット単位) を指定します。

*nHeight*<br/>
ビットマップの高さ (ビット単位) を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ビットマップには、指定されたデバイスコンテキストと同じ数のカラープレーンまたは同じビット/ピクセル形式があります。 アプリケーションでは、 *pDC* によって指定されたものと互換性のあるメモリデバイスの現在のビットマップとして、このビットマップを選択できます。

Windows は、この関数によって作成されたビットマップを、アプリケーションが表示コンテキストに選択していない場合にのみ破棄できます。 Windows が選択されていないビットマップを破棄し、後でそのビットマップを選択しようとすると、 [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) 関数は NULL を返します。

`CBitmap`関数で作成されたオブジェクトを終了したら `CreateDiscardableBitmap` 、まずデバイスコンテキストからビットマップを選択し、次にオブジェクトを削除し `CBitmap` ます。

## <a name="cbitmapfromhandle"></a><a name="fromhandle"></a> CBitmap:: FromHandle

`CBitmap`WINDOWS GDI ビットマップへのハンドルが指定された場合に、オブジェクトへのポインターを返します。

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>パラメーター

*hBitmap*<br/>
Windows GDI ビットマップを指定します。

### <a name="return-value"></a>戻り値

成功した場合はオブジェクトへのポインター、 `CBitmap` それ以外の場合は NULL。

### <a name="remarks"></a>解説

`CBitmap`オブジェクトがハンドルにまだアタッチされていない場合は、一時 `CBitmap` オブジェクトが作成され、アタッチされます。 この一時 `CBitmap` オブジェクトは、アプリケーションが次にそのイベントループ内でアイドル状態になったときにのみ有効です。その時点で、すべての一時グラフィックオブジェクトが削除されます。 別の方法として、一時オブジェクトは1つのウィンドウメッセージの処理中にのみ有効であるということもあります。

## <a name="cbitmapgetbitmap"></a><a name="getbitmap"></a> CBitmap:: GetBitmap

添付ビットマップのイメージプロパティを取得します。

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>パラメーター

*pBitMap*<br/>
イメージのプロパティを受け取る [ビットマップ](/windows/win32/api/wingdi/ns-wingdi-bitmap) 構造体へのポインター。 このパラメーターを NULL にすることはできません。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

## <a name="cbitmapgetbitmapbits"></a><a name="getbitmapbits"></a> CBitmap:: GetBitmapBits

添付ビットマップのビットパターンを、指定したバッファーにコピーします。

```
DWORD GetBitmapBits(
    DWORD dwCount,
    LPVOID lpBits) const;
```

### <a name="parameters"></a>パラメーター

*dwCount*<br/>
バッファーにコピーするバイト数。

*lpBits*<br/>
ビットマップを受け取るバッファーへのポインター。

### <a name="return-value"></a>戻り値

メソッドが正常に終了した場合にバッファーにコピーされたバイト数。それ以外の場合は0です。

### <a name="remarks"></a>解説

必要なバッファーサイズを決定するには、 [CBitmap:: GetBitmap](#getbitmap) を使用します。

## <a name="cbitmapgetbitmapdimension"></a><a name="getbitmapdimension"></a> CBitmap:: GetBitmapDimension

ビットマップの幅と高さを返します。

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>戻り値

ビットマップの幅と高さ。0.1 単位で計測されます。 高さは `cy` オブジェクトのメンバーにあり、 `CSize` 幅はメンバーに含まれてい `cx` ます。 ビットマップの幅と高さがを使用して設定されていない場合 `SetBitmapDimension` 、戻り値は0になります。

### <a name="remarks"></a>解説

高さと幅は、 [Setbitmapdimension](#setbitmapdimension) メンバー関数を使用して以前に設定されたものと見なされます。

## <a name="cbitmaploadbitmap"></a><a name="loadbitmap"></a> CBitmap:: LoadBitmap

アプリケーションの実行可能ファイルから、 *nIDResource* 内の ID 番号で識別された、 *lpszresourcename* よって指定されたビットマップリソースを読み込みます。

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>パラメーター

*lpszResourceName*<br/>
ビットマップリソースの名前を含む null で終わる文字列を指します。

*nIDResource*<br/>
ビットマップリソースのリソース ID 番号を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

読み込まれたビットマップがオブジェクトにアタッチされ `CBitmap` ます。

*Lpszresourcename* よって識別されるビットマップが存在しない場合、またはビットマップを読み込むためのメモリが不足している場合、この関数は0を返します。

[CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject)関数を使用して、関数によって読み込まれたビットマップを削除したり、デストラクターがオブジェクトを削除したりすることができ `LoadBitmap` `CBitmap` ます。

> [!CAUTION]
> オブジェクトを削除する前に、そのオブジェクトがデバイスコンテキストに選択されていないことを確認してください。

次のビットマップが Windows バージョン3.1 以降に追加されました。

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

これらのビットマップは、Windows バージョン3.0 以前のデバイスドライバーでは見つかりません。 ビットマップの完全な一覧とそれらの外観の表示については、Windows SDK を参照してください。

## <a name="cbitmaploadmappedbitmap"></a><a name="loadmappedbitmap"></a> CBitmap:: LoadMappedBitmap

ビットマップを読み込み、色を現在のシステムカラーにマップするには、このメンバー関数を呼び出します。

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>パラメーター

*nIDBitmap*<br/>
ビットマップリソースの ID。

*nFlags*<br/>
ビットマップのフラグ。 0または CMB_MASKED を指定できます。

*lpColorMap マップ*<br/>
`COLORMAP`ビットマップをマップするために必要な色情報を格納している構造体へのポインター。 このパラメーターが NULL の場合、関数は既定のカラーマップを使用します。

*nMapSize*<br/>
*Lpcolormap* マップが指すカラーマップの数。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

既定で `LoadMappedBitmap` は、ボタンのグリフでよく使用される色がによってマップされます。

マップされたビットマップの作成の詳細については、Windows SDK の「Windows 関数 [CreateMappedBitmap](/windows/win32/api/commctrl/nf-commctrl-createmappedbitmap) 」と「 [カラーマップ](/windows/win32/api/commctrl/ns-commctrl-colormap) の構造」を参照してください。

## <a name="cbitmaploadoembitmap"></a><a name="loadoembitmap"></a> CBitmap:: LoadOEMBitmap

Windows によって使用される定義済みのビットマップを読み込みます。

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>パラメーター

*nIDBitmap*<br/>
定義済みの Windows ビットマップの ID 番号。 使用可能な値は、WINDOWS の下に一覧表示されています。始め

:::row:::
   :::column span="":::
      OBM_BTNCORNERS \
      OBM_BTSIZE \
      OBM_CHECK \
      OBM_CHECKBOXES \
      OBM_CLOSE \
      OBM_COMBO \
      OBM_DNARROW \
      OBM_DNARROWD \
      OBM_DNARROWI \
      OBM_LFARROW \
      OBM_LFARROWD \
      OBM_LFARROWI
   :::column-end:::
   :::column span="":::
      OBM_MNARROW \
      OBM_OLD_CLOSE \
      OBM_OLD_DNARROW \
      OBM_OLD_LFARROW \
      OBM_OLD_REDUCE \
      OBM_OLD_RESTORE \
      OBM_OLD_RGARROW \
      OBM_OLD_UPARROW \
      OBM_OLD_ZOOM \
      OBM_REDUCE \
      OBM_REDUCED
   :::column-end:::
   :::column span="":::
      OBM_RESTORE \
      OBM_RESTORED \
      OBM_RGARROW \
      OBM_RGARROWD \
      OBM_RGARROWI \
      OBM_SIZE \
      OBM_UPARROW \
      OBM_UPARROW \
      OBM_UPARROWD \
      OBM_ZOOM \
      OBM_ZOOMD
   :::column-end:::
:::row-end:::

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

OBM_OLD で始まるビットマップ名は、3.0 より前の Windows バージョンで使用されるビットマップを表します。

定数 OEMRESOURCE は、WINDOWS を含める前に定義する必要があることに注意してください。 **OBM_** 定数を使用するための H。

## <a name="cbitmapoperator-hbitmap"></a><a name="operator_hbitmap"></a> CBitmap:: operator HBITMAP

オブジェクトのアタッチされた Windows GDI ハンドルを取得するには、この演算子を使用し `CBitmap` ます。

```
operator HBITMAP() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトによって表される Windows GDI オブジェクトへのハンドル `CBitmap` 。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は、オブジェクトの直接使用をサポートするキャスト演算子です `HBITMAP` 。

グラフィックオブジェクトの使用方法の詳細については、「Windows SDK の [グラフィックオブジェクト](/windows/win32/gdi/graphic-objects) 」を参照してください。

## <a name="cbitmapsetbitmapbits"></a><a name="setbitmapbits"></a> CBitmap:: SetBitmapBits

ビットマップのビットを、 *Lpbits* によって指定されたビット値に設定します。

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>パラメーター

*dwCount*<br/>
*Lpbits* が指すバイト数を指定します。

*lpBits*<br/>
オブジェクトにコピーされるピクセル値を格納しているバイト配列を指し `CBitmap` ます。 ビットマップがイメージを正しく表示できるようにするには、CBitmap インスタンスの作成時に指定した高さ、幅、および色深度の値に合わせて値を書式設定する必要があります。 詳細については、「 [CBitmap:: CreateBitmap](#createbitmap)」を参照してください。

### <a name="return-value"></a>戻り値

ビットマップビットの設定に使用されるバイト数。関数が失敗した場合は0。

## <a name="cbitmapsetbitmapdimension"></a><a name="setbitmapdimension"></a> CBitmap:: SetBitmapDimension

0.1-ミリメートル単位でビットマップに幅と高さを割り当てます。

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
ビットマップの幅を指定します (0.1 ミリメートル単位)。

*nHeight*<br/>
ビットマップの高さを指定します (0.1 ミリメートル単位)。

### <a name="return-value"></a>戻り値

前のビットマップのサイズ。 高さは、 `cy` オブジェクトのメンバー変数に `CSize` あり、width はメンバー変数に含まれてい `cx` ます。

### <a name="remarks"></a>解説

GDI は、アプリケーションが [Getbitmapdimension](#getbitmapdimension) メンバー関数を呼び出すときにこれらの値を返さない限り、これらの値を使用しません。

## <a name="see-also"></a>関連項目

[MFC のサンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
