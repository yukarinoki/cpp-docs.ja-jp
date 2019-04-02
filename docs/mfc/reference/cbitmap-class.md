---
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
ms.openlocfilehash: 11e210680bdf68f1a1dcbfaed18ae56ce006c8ad
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769902"
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
|[CBitmap::CBitmap](#cbitmap)|`CBitmap` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CBitmap::CreateBitmap](#createbitmap)|デバイスに依存するメモリのビットマップを指定した幅、高さ、およびビット パターンを持つオブジェクトを初期化します。|
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|指定されたビットマップの幅、高さ、および (指定されている) 場合、ビット パターンを持つオブジェクトを初期化します、`BITMAP`構造体。|
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|指定されたデバイスと互換性のあるあるように、ビットマップでオブジェクトを初期化します。|
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|指定されたデバイスと互換性がある破棄できるビットマップでオブジェクトを初期化します。|
|[CBitmap::FromHandle](#fromhandle)|ポインターを返します、`CBitmap`を Windows にハンドルが指定されると`HBITMAP`ビットマップ。|
|[CBitmap::GetBitmap](#getbitmap)|入力、`BITMAP`ビットマップについての情報を含む構造体。|
|[列](#getbitmapbits)|指定したビットマップのビットを指定されたバッファーにコピーします。|
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|ビットマップの高さと幅を返します。 高さと幅にして以前に設定されていると見なされます、[呼び出す](#setbitmapdimension)メンバー関数。|
|[CBitmap::LoadBitmap](#loadbitmap)|名前付きのビットマップ リソースを読み込み、アプリケーションの実行可能ファイルからビットマップをオブジェクトにアタッチして、オブジェクトを初期化します。|
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|ビットマップを読み込み、現在のシステム カラーを色にマップします。|
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|定義済みの Windows ビットマップを読み込み、ビットマップをオブジェクトにアタッチして、オブジェクトを初期化します。|
|[CBitmap::SetBitmapBits](#setbitmapbits)|ビットマップのビットを指定したビット値に設定します。|
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|0.1 ミリメートル単位でのビットマップの幅と高さを割り当てます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CBitmap::operator HBITMAP](#operator_hbitmap)|アタッチされている Windows ハンドルを返します、`CBitmap`オブジェクト。|

## <a name="remarks"></a>Remarks

使用する、`CBitmap`オブジェクトでオブジェクトを構築、ビットマップ ハンドル、メンバー関数の初期化のいずれかでそれにアタッチし、オブジェクトのメンバー関数を呼び出します。

グラフィック オブジェクトのような使用の詳細については`CBitmap`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cbitmap"></a>  CBitmap::CBitmap

`CBitmap` オブジェクトを構築します。

```
CBitmap();
```

### <a name="remarks"></a>Remarks

結果として得られるオブジェクトは、メンバーの初期化関数のいずれかで初期化する必要があります。

##  <a name="createbitmap"></a>  CBitmap::CreateBitmap

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

*nplanes 1i*<br/>
ビットマップ内でのカラー プレーンの数を指定します。

*nBitcount*<br/>
表示ピクセルごとのカラー ビット数を指定します。

*lpBits*<br/>
初期のビットマップのビット値を含むバイト配列を指します。 新しいビットマップのまま NULL の場合、初期化されていません。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

色のビットマップのいずれか、 *nplanes 1i*または*nBitcount*パラメーターを 1 に設定する必要があります。 両方のパラメーターを 1 に設定すると、 `CreateBitmap` によってモノクロのビットマップが作成されます。

表示デバイス用のビットマップを直接選択することはできませんが、 [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) を使用して「メモリ デバイス コンテキスト」の現在のビットマップとして選択し、それを [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) 関数を使用して互換性のある任意のデバイス コンテキストにコピーできます。

`CBitmap` 関数によって作成された `CreateBitmap` オブジェクトでの作業終了後、デバイス コンテキスト外のビットマップを最初に選択し、次に `CBitmap` オブジェクトを削除します。

詳細については、の説明を参照して、`bmBits`フィールドに、`BITMAP`構造体。 [BITMAP](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) 構造体については、 [CBitmap::CreateBitmapIndirect](#createbitmapindirect) メンバー関数の下で説明されています。

##  <a name="createbitmapindirect"></a>  CBitmap::CreateBitmapIndirect

ビットマップの幅、高さ、およびが指す構造体で指定されたビット パターン (指定されている) 場合のある初期化*lpBitmap*します。

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>パラメーター

*lpBitmap*<br/>
指す、[ビットマップ](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap)ビットマップについての情報を含む構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ディスプレイ デバイスのビットマップを直接選択することはできませんが選択できるメモリ デバイス コンテキストの現在のビットマップとしてを使用して[cdc::selectobject](../../mfc/reference/cdc-class.md#selectobject) を使用して任意の互換性のあるデバイスコンテキストにコピーおよび[Cdc::bitblt](../../mfc/reference/cdc-class.md#bitblt)または[CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt)関数。 (、 [Cdc::patblt](../../mfc/reference/cdc-class.md#patblt)関数は、現在のブラシのビットマップをディスプレイ デバイス コンテキストに直接コピーできます)。

場合、`BITMAP`によって示される構造体、 *lpBitmap*を使用してパラメーターが入力されている、`GetObject`関数の場合、ビットマップのビットが指定されていないと、ビットマップは初期化されていません。 ビットマップを初期化するためにアプリケーション関数など、使用できる[cdc::bitblt](../../mfc/reference/cdc-class.md#bitblt)または[SetDIBits](/windows/desktop/api/wingdi/nf-wingdi-setdibits)の最初のパラメーターで識別されるビットマップからのビットをコピーする`CGdiObject::GetObject`によって作成されたビットマップ`CreateBitmapIndirect`.

終了したら、`CBitmap`オブジェクトを作成した`CreateBitmapIndirect`関数、まず、デバイス コンテキスト外のビットマップを選択し、削除、`CBitmap`オブジェクト。

##  <a name="createcompatiblebitmap"></a>  CBitmap::CreateCompatibleBitmap

指定されたデバイスと互換性があるビットマップを初期化します*pDC*します。

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイス コンテキストを指定します。

*nWidth*<br/>
ビットマップの幅 (ピクセル単位) を指定します。

*nHeight*<br/>
ビットマップの高さ (ピクセル単位) を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ビットマップは、同じ数のカラー プレーンまたは指定したデバイス コンテキストと同じビット/ピクセル形式を持ちます。 指定したのと互換性がある任意のメモリ デバイスの現在のビットマップとして選択できる*pDC*します。

場合*pDC*メモリ デバイス コンテキストでは、返されるビットマップは、そのデバイス コンテキストで現在選択されているビットマップと同じ形式を持ちます。 「メモリ デバイス コンテキスト」は、表示サーフェイスを表すメモリのブロックです。 互換性のあるデバイスの実際の表示画面にコピーする前にメモリ内のイメージを準備するために使用します。

メモリ デバイス コンテキストが作成されると、GDI をストックのモノクロ ビットマップを自動的に選択します。

ビットマップの形式がによって返される色メモリ デバイス コンテキストが持つカラーかモノクロのビットマップが選択されているため、`CreateCompatibleBitmap`関数常に同じではありませんただし、メモリ デバイス コンテキストの互換性のあるビットマップの形式はでは常に、。デバイスの形式です。

終了したら、`CBitmap`オブジェクトを作成した、`CreateCompatibleBitmap`関数、まず、デバイス コンテキスト外のビットマップを選択し、削除、`CBitmap`オブジェクト。

##  <a name="creatediscardablebitmap"></a>  CBitmap::CreateDiscardableBitmap

破棄できるビットマップで識別されるデバイス コンテキストと互換性がある初期化*pDC*します。

```
BOOL CreateDiscardableBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイス コンテキストを指定します。

*nWidth*<br/>
(Bits) で、ビットマップの幅を指定します。

*nHeight*<br/>
(Bits) で、ビットマップの高さを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ビットマップは、同じ数のカラー プレーンまたは指定したデバイス コンテキストと同じビット/ピクセル形式を持ちます。 指定したのと互換性があるメモリ デバイスの現在のビットマップとして、アプリケーションがこのビットマップの選択*pDC*します。

Windows では、アプリケーションでは表示コンテキストに選択しない場合にのみ、この関数によって作成されたビットマップを破棄できます。 Windows が選択されていない、後でアプリケーションが、それを選択しようとした場合、ビットマップを破棄する場合、 [cdc::selectobject](../../mfc/reference/cdc-class.md#selectobject)関数は NULL を返します。

終了したら、`CBitmap`オブジェクトを作成した、`CreateDiscardableBitmap`関数、まず、デバイス コンテキスト外のビットマップを選択し、削除、`CBitmap`オブジェクト。

##  <a name="fromhandle"></a>  CBitmap::FromHandle

ポインターを返します、 `CBitmap` Windows GDI ビットマップを識別するハンドルが指定されるとします。

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>パラメーター

*hBitmap*<br/>
Windows GDI ビットマップを指定します。

### <a name="return-value"></a>戻り値

ポインター、`CBitmap`成功。 それ以外の場合に NULL の場合は、オブジェクト。

### <a name="remarks"></a>Remarks

場合、`CBitmap`ハンドル、一時的にオブジェクトが既にアタッチされていない`CBitmap`オブジェクトを作成し、接続されています。 この一時`CBitmap`すべて一時的なグラフィックを時間があるオブジェクトは削除まで、次回、アプリケーションは、イベント ループでのアイドル時間は、専用、オブジェクトが無効です。 言い換えると、別の方法は、1 つのウィンドウ メッセージを処理中に一時オブジェクトが有効でのみことです。

##  <a name="getbitmap"></a>  CBitmap::GetBitmap

接続されているビットマップ画像のプロパティを取得します。

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>パラメーター

*pBitMap*<br/>
ポインターを[ビットマップ](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap)画像のプロパティを受信する構造体。 このパラメーターには、NULL は指定できません。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

##  <a name="getbitmapbits"></a>  CBitmap::GetBitmapBits

指定されたバッファーに割り当てられているビットマップのビット パターンをコピーします。

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

メソッドが成功した場合、バッファーにコピーされたバイト数それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

使用[CBitmap::GetBitmap](#getbitmap)必要なバッファー サイズを決定します。

##  <a name="getbitmapdimension"></a>  CBitmap::GetBitmapDimension

ビットマップの高さと幅を返します。

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>戻り値

ビットマップの高さと幅は、0.1 ミリメートル単位で測定されます。 高さは、`cy`のメンバー、`CSize`オブジェクト、および幅が、`cx`メンバー。 使用して、ビットマップの幅と高さを設定されているがない場合`SetBitmapDimension`、戻り値は 0。

### <a name="remarks"></a>Remarks

高さと幅を使用して、先ほど設定したと見なされます、[呼び出す](#setbitmapdimension)メンバー関数。

##  <a name="loadbitmap"></a>  CBitmap::LoadBitmap

指定されたビットマップ リソースを読み込みます*lpszResourceName*の ID 番号で識別されるまたは*可能*アプリケーションの実行可能ファイルからです。

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>パラメーター

*lpszResourceName*<br/>
ビットマップ リソースの名前を含む null で終わる文字列へのポインター。

*可能*<br/>
ビットマップ リソースのリソース ID 番号を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

読み込まれたビットマップが接続されている、`CBitmap`オブジェクト。

ビットマップがで識別される場合*lpszResourceName*が存在しないか、メモリ不足のビットマップを読み込む場合がある場合、関数は 0 を返します。

使用することができます、 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)によって読み込まれるビットマップを削除する関数、`LoadBitmap`関数、または`CBitmap`デストラクターでは、オブジェクトを削除できます。

> [!CAUTION]
>  オブジェクトを削除する前に、デバイス コンテキストに選択されていないことを確認してください。

次のビットマップは、Windows バージョン 3.1 以降に追加されました。

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

これらのビットマップは 3.0 と以前のバージョンの Windows のデバイス ドライバーにありませんでした。 ビットマップと表示形式の完全な一覧は、Windows SDK を参照してください。

##  <a name="loadmappedbitmap"></a>  CBitmap::LoadMappedBitmap

ビットマップを読み込みし、現在のシステム カラーを色にマップするには、このメンバー関数を呼び出します。

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>パラメーター

*nIDBitmap*<br/>
ビットマップ リソースの ID。

*nFlags*<br/>
ビットマップのフラグ。 0 または CMB_MASKED できます。

*lpColorMap*<br/>
ポインターを`COLORMAP`ビットマップをマップするために必要な色の情報を含む構造体。 このパラメーターが NULL の場合、関数は、既定のカラー マップを使用します。

*nMapSize*<br/>
マップの色の数が指す*lpColorMap*します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

既定では、`LoadMappedBitmap`ボタンのグリフでよく使用する色にマップされます。

マップされたビットマップを作成する方法の詳細については、Windows の関数を参照してください。 [CreateMappedBitmap](http://go.microsoft.com/fwlink/p/?linkid=230562)と[カラーマップ](/windows/desktop/api/commctrl/ns-commctrl-_colormap)Windows SDK の構造体。

##  <a name="loadoembitmap"></a>  CBitmap::LoadOEMBitmap

Windows で使用される定義済みのビットマップを読み込みます。

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>パラメーター

*nIDBitmap*<br/>
定義済みの Windows ビットマップの ID 番号。 使用可能な値は、WINDOWS から、以下に示します。H:

|||
|-|-|
|OBM_BTNCORNERS|OBM_OLD_RESTORE|
|OBM_BTSIZE|OBM_OLD_RGARROW|
|OBM_CHECK|OBM_OLD_UPARROW|
|OBM_CHECKBOXES|OBM_OLD_ZOOM|
|OBM_CLOSE|OBM_REDUCE|
|OBM_COMBO|OBM_REDUCED|
|OBM_DNARROW|OBM_RESTORE|
|OBM_DNARROWD|OBM_RESTORED|
|OBM_DNARROWI|OBM_RGARROW|
|OBM_LFARROW|OBM_RGARROWD|
|OBM_LFARROWD|OBM_RGARROWI|
|OBM_LFARROWI|OBM_SIZE|
|OBM_MNARROW|OBM_UPARROW|
|OBM_OLD_CLOSE|OBM_UPARROWD|
|OBM_OLD_DNARROW|OBM_UPARROW|
|OBM_OLD_LFARROW|OBM_ZOOM|
|OBM_OLD_REDUCE|OBM_ZOOMD|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

OBM_OLD で始まるビットマップの名前は、Windows のバージョン 3.0 より前で使用されるビットマップを表します。

WINDOWS をインクルードする前に定数 OEMRESOURCE を定義する必要がありますに注意してください。いずれかを使用するには H、 **OBM_** 定数。

##  <a name="operator_hbitmap"></a>  CBitmap::operator HBITMAP

接続されている Windows GDI ハンドルを取得するこの演算子を使用して、`CBitmap`オブジェクト。

```
operator HBITMAP() const;
```

### <a name="return-value"></a>戻り値

かどうかは成功すると、Windows GDI オブジェクトを識別するハンドルで表される、`CBitmap`オブジェクト。 それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

この演算子はキャスト演算子の`HBITMAP`オブジェクト。

グラフィック オブジェクトの使用に関する詳細については、次を参照してください。[グラフィック オブジェクト](/windows/desktop/gdi/graphic-objects)Windows SDK に含まれています。

##  <a name="setbitmapbits"></a>  CBitmap::SetBitmapBits

ビットマップのビットを設定で指定されたビット値に*lpBits*します。

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>パラメーター

*dwCount*<br/>
によって示されるバイト数を指定*lpBits*します。

*lpBits*<br/>
コピーされるピクセル値を格納するバイト配列を指す、`CBitmap`オブジェクト。 そのイメージを正常にレンダリングできるビットマップは、値を CBitmap インスタンスの作成時に指定された高さ、幅と色の深度値に準拠するための書式設定。 詳細については、次を参照してください。 [CBitmap::CreateBitmap](#createbitmap)します。

### <a name="return-value"></a>戻り値

ビットマップのビットを設定で使用されるバイト数関数が失敗した場合は 0。

##  <a name="setbitmapdimension"></a>  CBitmap::SetBitmapDimension

0.1 ミリメートル単位でのビットマップの幅と高さを割り当てます。

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
(0.1 ミリメートル単位) で、ビットマップの幅を指定します。

*nHeight*<br/>
(0.1 ミリメートル単位) で、ビットマップの高さを指定します。

### <a name="return-value"></a>戻り値

前のビットマップの大きさ。 高さは、`cy`のメンバー変数、`CSize`オブジェクト、および幅が、`cx`メンバー変数。

### <a name="remarks"></a>Remarks

GDI はこれらの値を返すにアプリケーションを呼び出す以外を使用しない、 [GetBitmapDimension](#getbitmapdimension)メンバー関数。

## <a name="see-also"></a>関連項目

[MFC サンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
