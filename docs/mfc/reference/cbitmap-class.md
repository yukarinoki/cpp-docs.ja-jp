---
title: クラス
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
ms.openlocfilehash: 9a33a6e1bea601422e043d7f2a80029c72d97e50
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352744"
---
# <a name="cbitmap-class"></a>クラス

Windows のグラフィック デバイス インターフェイス (GDI: Graphics Device Interface) のビットマップをカプセル化したもので、ビットマップを操作するためのメンバー関数を提供します。

## <a name="syntax"></a>構文

```
class CBitmap : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[C ビットマップ::C ビットマップ](#cbitmap)|`CBitmap` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を作成します。](#createbitmap)|指定した幅、高さ、およびビット パターンを持つデバイスに依存するメモリ ビットマップを使用してオブジェクトを初期化します。|
|[Cビットマップ::ビットマップインダイレクトの作成](#createbitmapindirect)|構造体に指定された幅、高さ、およびビット パターン (指定されている場合) を使用して、ビットマップ`BITMAP`を使用してオブジェクトを初期化します。|
|[を使用します。](#createcompatiblebitmap)|指定したデバイスと互換性があるように、ビットマップを使用してオブジェクトを初期化します。|
|[を作成します。](#creatediscardablebitmap)|指定したデバイスと互換性のある破棄可能なビットマップを使用してオブジェクトを初期化します。|
|[ハンドルを受け取る](#fromhandle)|Windows`HBITMAP`ビットマップへのハンドル`CBitmap`が与えられた場合、オブジェクトへのポインターを返します。|
|[を取得します。](#getbitmap)|ビットマップに関`BITMAP`する情報を構造体に塗りつぶします。|
|[をクリックします。](#getbitmapbits)|指定したビットマップのビットを指定したバッファーにコピーします。|
|[をクリックします。](#getbitmapdimension)|ビットマップの幅と高さを返します。 高さと幅は、以前に[SetBitmapDimension](#setbitmapdimension)メンバー関数によって設定されているものと見なされます。|
|[を読み込む](#loadbitmap)|アプリケーションの実行可能ファイルから名前付きビットマップ リソースを読み込み、そのビットマップをオブジェクトにアタッチして、オブジェクトを初期化します。|
|[ビットマップ::マップされたビットマップ](#loadmappedbitmap)|ビットマップをロードし、色を現在のシステム カラーにマップします。|
|[を使用します。](#loadoembitmap)|定義済みの Windows ビットマップを読み込み、そのビットマップをオブジェクトにアタッチして、オブジェクトを初期化します。|
|[をクリックします。](#setbitmapbits)|ビットマップのビットを指定されたビット値に設定します。|
|[を指定します。](#setbitmapdimension)|ビットマップに幅と高さを 0.1 ミリメートル単位で割り当てます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[を使用します。](#operator_hbitmap)|オブジェクトにアタッチされた Windows`CBitmap`ハンドルを返します。|

## <a name="remarks"></a>解説

オブジェクトを`CBitmap`使用するには、オブジェクトを構築し、初期化メンバー関数を使用してオブジェクトにビットマップ ハンドルをアタッチしてから、オブジェクトのメンバー関数を呼び出します。

などの`CBitmap`グラフィックオブジェクトの使用の詳細については、「[グラフィックオブジェクト](../../mfc/graphic-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cbitmapcbitmap"></a><a name="cbitmap"></a>C ビットマップ::C ビットマップ

`CBitmap` オブジェクトを構築します。

```
CBitmap();
```

### <a name="remarks"></a>解説

結果のオブジェクトは、初期化メンバー関数のいずれかで初期化する必要があります。

## <a name="cbitmapcreatebitmap"></a><a name="createbitmap"></a>を作成します。

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

*n幅*<br/>
ビットマップの幅 (ピクセル単位) を指定します。

*nHeight*<br/>
ビットマップの高さ (ピクセル単位) を指定します。

*nプレーン*<br/>
ビットマップ内でのカラー プレーンの数を指定します。

*ビット数*<br/>
表示ピクセルごとのカラー ビット数を指定します。

*lp ビット*<br/>
初期のビットマップのビット値を含むバイト配列を指します。 NULL の場合、新しいビットマップは初期化されないままになります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

カラー ビットマップの場合 *、nPlanes*または*nBitcount*パラメーターを 1 に設定する必要があります。 両方のパラメーターを 1 に設定すると、 `CreateBitmap` によってモノクロのビットマップが作成されます。

表示デバイス用のビットマップを直接選択することはできませんが、 [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) を使用して「メモリ デバイス コンテキスト」の現在のビットマップとして選択し、それを [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) 関数を使用して互換性のある任意のデバイス コンテキストにコピーできます。

`CBitmap` 関数によって作成された `CreateBitmap` オブジェクトでの作業終了後、デバイス コンテキスト外のビットマップを最初に選択し、次に `CBitmap` オブジェクトを削除します。

詳細については、構造内のフィールドの`bmBits`説明を`BITMAP`参照してください。 [BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap) 構造体については、 [CBitmap::CreateBitmapIndirect](#createbitmapindirect) メンバー関数の下で説明されています。

## <a name="cbitmapcreatebitmapindirect"></a><a name="createbitmapindirect"></a>Cビットマップ::ビットマップインダイレクトの作成

*lpBitmap*で指定された構造体に指定されている幅、高さ、およびビット パターン (指定されている場合) を持つビットマップを初期化します。

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>パラメーター

*lp ビットマップ*<br/>
ビットマップに関する情報を含む[BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap)構造体へのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ビットマップは表示デバイスに対して直接選択することはできませんが[、CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject)を使用してメモリ デバイス コンテキストの現在のビットマップとして選択し[、CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt)または[CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt)関数を使用して互換性のあるデバイス コンテキストにコピーできます。 [(CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt)関数は、現在のブラシのビットマップを表示デバイス コンテキストに直接コピーできます)。

*lpBitmap*パラメーターによって指定された`GetObject``BITMAP`構造体が関数を使用して入力された場合、ビットマップのビットは指定されず、ビットマップは初期化されません。 ビットマップを初期化するには、アプリケーションは[CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt)や[SetDIBits](/windows/win32/api/wingdi/nf-wingdi-setdibits)などの関数を使用して、 の最初の`CGdiObject::GetObject`パラメーターで識別されるビットマップから作成された`CreateBitmapIndirect`ビットマップにビットをコピーできます。

関数で`CBitmap``CreateBitmapIndirect`作成したオブジェクトを終了したら、まずデバイス コンテキストからビットマップを選択してから、オブジェクトを`CBitmap`削除します。

## <a name="cbitmapcreatecompatiblebitmap"></a><a name="createcompatiblebitmap"></a>を使用します。

*pDC*で指定されたデバイスと互換性のあるビットマップを初期化します。

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイス コンテキストを指定します。

*n幅*<br/>
ビットマップの幅 (ピクセル単位) を指定します。

*nHeight*<br/>
ビットマップの高さ (ピクセル単位) を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ビットマップのカラー プレーン数またはピクセルあたりのビット数は、指定したデバイス コンテキストと同じです。 *これは、pDC*で指定されたメモリ デバイスと互換性のある、現在のビットマップとして選択できます。

*pDC*がメモリ デバイス コンテキストの場合、返されるビットマップは、そのデバイス コンテキストで現在選択されているビットマップと同じ形式になります。 "メモリ デバイス コンテキスト" は、表示サーフェスを表すメモリ ブロックです。 互換性のあるデバイスの実際の表示面にコピーする前に、メモリ内のイメージを準備するために使用できます。

メモリ デバイス コンテキストが作成されると、GDI は、そのデバイス のモノクロのストック ビットマップを自動的に選択します。

カラー メモリ デバイス コンテキストでは、カラー ビットマップまたはモノクロ ビットマップを選択できるため、`CreateCompatibleBitmap`関数によって返されるビットマップの形式は必ずしも同じではありません。ただし、メモリ以外のデバイス コンテキストに対する互換性のあるビットマップの形式は、常にデバイスの形式になります。

関数で作成されたオブジェクト`CBitmap`を使用し終わったら、まずデバイス コンテキストからビットマップを選択してから、オブジェクトを`CBitmap`削除します。 `CreateCompatibleBitmap`

## <a name="cbitmapcreatediscardablebitmap"></a><a name="creatediscardablebitmap"></a>を作成します。

*pDC*で識別されるデバイス コンテキストと互換性のある破棄可能なビットマップを初期化します。

```
BOOL CreateDiscardableBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイス コンテキストを指定します。

*n幅*<br/>
ビットマップの幅をビット単位で指定します。

*nHeight*<br/>
ビットマップの高さをビット単位で指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ビットマップのカラー プレーン数またはピクセルあたりのビット数は、指定したデバイス コンテキストと同じです。 アプリケーションは *、このビットマップを、pDC*で指定されたデバイスと互換性のあるメモリ デバイスの現在のビットマップとして選択できます。

Windows は、アプリケーションが表示コンテキストに選択していない場合にのみ、この関数によって作成されたビットマップを破棄できます。 Windows がビットマップを選択していないときに破棄し、アプリケーションが後で選択しようとすると[、CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject)関数は NULL を返します。

関数で作成されたオブジェクト`CBitmap`を使用し終わったら、まずデバイス コンテキストからビットマップを選択してから、オブジェクトを`CBitmap`削除します。 `CreateDiscardableBitmap`

## <a name="cbitmapfromhandle"></a><a name="fromhandle"></a>ハンドルを受け取る

Windows GDI`CBitmap`ビットマップへのハンドルが与えられた場合、オブジェクトへのポインターを返します。

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>パラメーター

*hビットマップ*<br/>
Windows GDI ビットマップを指定します。

### <a name="return-value"></a>戻り値

成功した場合は`CBitmap`オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

オブジェクトが`CBitmap`ハンドルにまだアタッチされていない場合は、一時`CBitmap`オブジェクトが作成され、アタッチされます。 この一`CBitmap`時オブジェクトは、アプリケーションがイベント ループで次にアイドル時間を持つまで有効で、その時点ですべての一時グラフィック オブジェクトが削除されます。 もう 1 つの言い方は、一時オブジェクトが 1 つのウィンドウ メッセージの処理中にのみ有効であるというものです。

## <a name="cbitmapgetbitmap"></a><a name="getbitmap"></a>を取得します。

アタッチされたビットマップのイメージ プロパティを取得します。

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>パラメーター

*ビットマップ*<br/>
イメージプロパティを受け取る[BITMAP](/windows/win32/api/wingdi/ns-wingdi-bitmap)構造体へのポインター。 このパラメーターは NULL にすることはできません。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

## <a name="cbitmapgetbitmapbits"></a><a name="getbitmapbits"></a>をクリックします。

指定したバッファーに、アタッチされたビットマップのビット パターンをコピーします。

```
DWORD GetBitmapBits(
    DWORD dwCount,
    LPVOID lpBits) const;
```

### <a name="parameters"></a>パラメーター

*カウントカウント*<br/>
バッファーにコピーするバイト数。

*lp ビット*<br/>
ビットマップを受け取るバッファーへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合にバッファーにコピーされたバイト数。それ以外の場合は 0。

### <a name="remarks"></a>解説

必要なバッファ サイズを決定するには[、CBitmap::GetBitmap](#getbitmap)を使用します。

## <a name="cbitmapgetbitmapdimension"></a><a name="getbitmapdimension"></a>をクリックします。

ビットマップの幅と高さを返します。

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>戻り値

0.1 ミリメートル単位で測定されるビットマップの幅と高さ。 高さは`cy``CSize`オブジェクトのメンバーにあり、幅はメンバー内にあります`cx`。 を使用`SetBitmapDimension`してビットマップの幅と高さが設定されていない場合、戻り値は 0 です。

### <a name="remarks"></a>解説

高さと幅は[、SetBitmapDimension](#setbitmapdimension)メンバー関数を使用して以前に設定されているものと見なされます。

## <a name="cbitmaploadbitmap"></a><a name="loadbitmap"></a>を読み込む

*lpszResourceName*で指定されたビットマップ リソースを読み込みますか、アプリケーションの実行可能ファイルから*nIDResource*の ID 番号で識別されます。

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>パラメーター

*リソース名*<br/>
ビットマップ リソースの名前を含む null で終わる文字列へのポイント。

*リソース*<br/>
ビットマップ リソースのリソース ID 番号を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

読み込まれたビットマップがオブジェクト`CBitmap`にアタッチされます。

*lpszResourceName*で識別されるビットマップが存在しない場合、またはビットマップを読み込むためのメモリが不足している場合、関数は 0 を返します。

[CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)関数を使用して、関数によって読み込`LoadBitmap`まれたビットマップを削除`CBitmap`するか、デストラクターによってオブジェクトが削除されます。

> [!CAUTION]
> オブジェクトを削除する前に、デバイス コンテキストで選択されていないかどうかを確認します。

次のビットマップは、Windows バージョン 3.1 以降に追加されました。

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

これらのビットマップは、Windows 3.0 以前のバージョンのデバイス ドライバーには見つかりません。 ビットマップの完全な一覧とその外観の表示については、Windows SDK を参照してください。

## <a name="cbitmaploadmappedbitmap"></a><a name="loadmappedbitmap"></a>ビットマップ::マップされたビットマップ

ビットマップを読み込み、色を現在のシステム カラーにマップします。

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>パラメーター

*を示すビットマップ*<br/>
ビットマップ リソースの ID。

*Nflags*<br/>
ビットマップのフラグ。 ゼロまたはCMB_MASKEDを指定できます。

*カラーマップ*<br/>
ビットマップのマップに`COLORMAP`必要な色情報を含む構造体へのポインター。 このパラメーターが NULL の場合、関数はデフォルトのカラーマップを使用します。

*nマップサイズ*<br/>
*lpColorMap*が指すカラー マップの数。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

デフォルトでは、`LoadMappedBitmap`ボタングリフで一般的に使用される色がマップされます。

マップされたビットマップの作成の詳細については、Windows SDK の「マップ[されたビットマップの作成](https://go.microsoft.com/fwlink/p/?linkid=230562)」機能と[カラーマップ](/windows/win32/api/commctrl/ns-commctrl-colormap)構造を参照してください。

## <a name="cbitmaploadoembitmap"></a><a name="loadoembitmap"></a>を使用します。

Windows で使用される定義済みのビットマップを読み込みます。

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>パラメーター

*を示すビットマップ*<br/>
定義済みの Windows ビットマップの ID 番号。 使用可能な値は、WINDOWS から以下に示します。H：

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

### <a name="remarks"></a>解説

OBM_OLDで始まるビットマップ名は、3.0 より前のバージョンの Windows で使用されるビットマップを表します。

定数 OEMRESOURCE は、WINDOWS をインクルードする前に定義する必要があることに注意してください。h は **、OBM_** 定数のいずれかを使用する。

## <a name="cbitmapoperator-hbitmap"></a><a name="operator_hbitmap"></a>を使用します。

この演算子を使用して、オブジェクトの添付された Windows `CBitmap` GDI ハンドルを取得します。

```
operator HBITMAP() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトによって表される Windows GDI`CBitmap`オブジェクトへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子はキャスト演算子で、オブジェクトの直接使用を`HBITMAP`サポートします。

グラフィックオブジェクトの使用の詳細については、Windows SDK の[グラフィックオブジェクト](/windows/win32/gdi/graphic-objects)を参照してください。

## <a name="cbitmapsetbitmapbits"></a><a name="setbitmapbits"></a>をクリックします。

ビットマップのビットを*lpBits*で指定されたビット値に設定します。

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>パラメーター

*カウントカウント*<br/>
*lpBits*が指すバイト数を指定します。

*lp ビット*<br/>
オブジェクトにコピーするピクセル値を含む BYTE 配列へのポイント。 `CBitmap` ビットマップがイメージを正しくレンダリングできるようにするには、値を、CBitmap インスタンスの作成時に指定した高さ、幅、および色深度の値に合わせて書式設定する必要があります。 詳細については[、「CBitmap::CreateBitmap」を参照してください](#createbitmap)。

### <a name="return-value"></a>戻り値

ビットマップ ビットの設定に使用されるバイト数。関数が失敗した場合は 0。

## <a name="cbitmapsetbitmapdimension"></a><a name="setbitmapdimension"></a>を指定します。

ビットマップに幅と高さを 0.1 ミリメートル単位で割り当てます。

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*n幅*<br/>
ビットマップの幅を 0.1 ミリ単位で指定します。

*nHeight*<br/>
ビットマップの高さを 0.1 ミリ単位で指定します。

### <a name="return-value"></a>戻り値

前のビットマップのサイズ。 高さはオブジェクトの`cy`メンバー変数内`CSize`にあり、幅はメンバー変数内にあります`cx`。

### <a name="remarks"></a>解説

GDI は、アプリケーションが[GetBitmapDimension](#getbitmapdimension)メンバー関数を呼び出すときに返す以外は、これらの値を使用しません。

## <a name="see-also"></a>関連項目

[MDI のサンプル](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
