---
title: CBrush クラス
ms.date: 11/04/2016
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
ms.openlocfilehash: 15132bb5497886638edfe431ae769dd446785df8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352479"
---
# <a name="cbrush-class"></a>CBrush クラス

Windows のグラフィック デバイス インターフェイス (GDI) のブラシをカプセル化します。

## <a name="syntax"></a>構文

```
class CBrush : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cブラシ::Cブラシ](#cbrush)|`CBrush` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cブラシ::ブラシ間接的な作成](#createbrushindirect)|[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush)構造体で指定されたスタイル、色、およびパターンを使用してブラシを初期化します。|
|[Cブラシ::作成DIBパターンブラシ](#createdibpatternbrush)|デバイスに依存しないビットマップ (DIB) で指定されたパターンを使用してブラシを初期化します。|
|[Cブラシ::ハッチブラシを作成します。](#createhatchbrush)|指定したハッチ パターンと色でブラシを初期化します。|
|[Cブラシ::パターンブラシの作成](#createpatternbrush)|ビットマップで指定されたパターンを使用してブラシを初期化します。|
|[Cブラシ::ソリッドブラシを作成します。](#createsolidbrush)|指定した純色でブラシを初期化します。|
|[Cブラシ::作成シスカラーブラシ](#createsyscolorbrush)|既定のシステム カラーであるブラシを作成します。|
|[Cブラシ::ハンドルから](#fromhandle)|Windows`HBRUSH`オブジェクトへのハンドル`CBrush`が渡されたときに、オブジェクトへのポインターを返します。|
|[Cブラシ::ゲットログブラシ](#getlogbrush)|ログ[ブラシ](/windows/win32/api/wingdi/ns-wingdi-logbrush)構造体を取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cブラシ::オペレータHブラシ](#operator_hbrush)|オブジェクトにアタッチされた Windows`CBrush`ハンドルを返します。|

## <a name="remarks"></a>解説

オブジェクトを`CBrush`使用するには、オブジェクトを`CBrush`構築し、ブラシを必要`CDC`とする任意のメンバー関数に渡します。

ブラシは、ソリッド、ハッチング、またはパターン化できます。

の詳細については、「[グラフィック オブジェクト](../../mfc/graphic-objects.md)」を参照してください。 `CBrush`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cbrushcbrush"></a><a name="cbrush"></a>Cブラシ::Cブラシ

`CBrush` オブジェクトを構築します。

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>パラメーター

*Crcolor*<br/>
ブラシの前景色を RGB カラーとして指定します。 ブラシがハッチングされている場合、このパラメータはハッチングの色を指定します。

*nIndex*<br/>
ブラシのハッチ スタイルを指定します。 次のいずれかの値を指定できます。

- HS_BDIAGONAL 下向きのハッチ(左から右)を45度で

- HS_CROSS水平および垂直ハッチング

- HS_DIAGCROSS45度のハッチング

- HS_FDIAGONAL 上向きハッチ(左から右)を45度で

- HS_HORIZONTAL水平ハッチ

- HS_VERTICAL垂直ハッチ

*ビットマップ*<br/>
ブラシの`CBitmap`描画に使用するビットマップを指定するオブジェクトへのポイント。

### <a name="remarks"></a>解説

`CBrush`は、4 つのオーバーロードされたコンストラクターを持ちます。引数を持たないコンストラクターは、初期化`CBrush`されていないオブジェクトを作成します。

引数を指定しないコンストラクターを使用する場合は、結果の`CBrush`オブジェクトを[初期化](#createsolidbrush)する必要[があります](#createdibpatternbrush)。 [CreateHatchBrush](#createhatchbrush) [CreateBrushIndirect](#createbrushindirect) [CreatePatternBrush](#createpatternbrush) 引数を受け取るコンストラクターのいずれかを使用する場合は、それ以上の初期化は必要ありません。 引数を持つコンストラクターはエラーが発生した場合に例外をスローできますが、引数を持たないコンストラクターは常に成功します。

[単一の COLORREF](/windows/win32/gdi/colorref)パラメーターを持つコンストラクターは、指定した色でソリッド ブラシを構築します。 色は RGB 値を指定し、WINDOWS の RGB マクロを使用して構築できます。H。

2 つのパラメーターを持つコンストラクターは、ハッチ ブラシを構築します。 *nIndex*パラメーターは、ハッチング パターンのインデックスを指定します。 *crColor*パラメーターは、色を指定します。

パラメーターを`CBitmap`持つコンストラクターは、パターン化されたブラシを構築します。 パラメーターは、ビットマップを識別します。 ビットマップは[、CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap) [、CBitmap::CreateBitmapIndirect、CBitmap::](../../mfc/reference/cbitmap-class.md#createbitmapindirect)[ロードビットマップ](../../mfc/reference/cbitmap-class.md#loadbitmap)、または[CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)を使用して作成されたと仮定します。 塗りつぶしパターンで使用するビットマップの最小サイズは 8 ピクセル x 8 ピクセルです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

## <a name="cbrushcreatebrushindirect"></a><a name="createbrushindirect"></a>Cブラシ::ブラシ間接的な作成

[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush)構造体で指定されたスタイル、色、およびパターンを使用してブラシを初期化します。

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>パラメーター

*lpLog ブラシ*<br/>
ブラシに関する情報を含む[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush)構造体へのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ブラシは、その後、任意のデバイス コンテキストの現在のブラシとして選択できます。

モノクロ (1 面、1 ビット/ピクセル) ビットマップを使用して作成されたブラシは、現在のテキストと背景色を使用して描画されます。 0 に設定されたビットで表されるピクセルは、現在のテキストカラーで描画されます。 1 に設定されたビットで表されるピクセルは、現在の背景色で描画されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

## <a name="cbrushcreatedibpatternbrush"></a><a name="createdibpatternbrush"></a>Cブラシ::作成DIBパターンブラシ

デバイスに依存しないビットマップ (DIB) で指定されたパターンでブラシを初期化します。

```
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,
    UINT nUsage);

BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,
    UINT nUsage);
```

### <a name="parameters"></a>パラメーター

*hパックドディブ*<br/>
パックされたデバイスに依存しないビットマップ (DIB) を含むグローバル メモリ オブジェクトを識別します。

*n使用法*<br/>
[BITMAPINFO](/windows/win32/api/wingdi/ns-wingdi-bitmapinfo) `bmiColors[]`データ構造体 ("パック DIB" の一部) のフィールドに、現在実現されている論理パレットに明示的な RGB 値またはインデックスが含まれているかどうかを指定します。 パラメーターは、次のいずれかの値である必要があります。

- DIB_PAL_COLORS カラー テーブルは、16 ビット インデックスの配列で構成されます。

- DIB_RGB_COLORS カラー テーブルに RGB のリテラル値が含まれています。

*プパックドジブ*<br/>
構造体の直後にビットマップのピクセルを`BITMAPINFO`定義するバイト配列で構成されるパックされた DIB へのポインタ。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ブラシは、ラスター操作をサポートするデバイス コンテキストに対して選択できます。

DIB の処理方法は、2 つのバージョンによって異なります。

- 最初のバージョンでは、DIB へのハンドルを取得するには、Windows`GlobalAlloc`関数を呼び出してグローバル メモリのブロックを割り当て、パックされた DIB をメモリに充て込みます。

- 2 番目のバージョンでは、パックされた DIB にメモリを割り当てる呼び出し`GlobalAlloc`は必要ありません。

パックされた DIB は`BITMAPINFO`、データ構造の直後に、ビットマップのピクセルを定義するバイト配列で構成されます。 塗りつぶしパターンとして使用されるビットマップは、8 ピクセル x 8 ピクセルにする必要があります。 ビットマップが大きい場合、ビットマップの左上隅にある最初の 8 行と 8 列のピクセルに対応するビットのみを使用して塗りつぶしパターンが作成されます。

アプリケーションがモノクロデバイス コンテキストに 2 色の DIB パターン ブラシを選択すると、Windows は DIB で指定された色を無視し、代わりにデバイス コンテキストの現在のテキストと背景色を使用してパターン ブラシを表示します。 DIB の最初のカラー(DIB カラーテーブルのオフセット 0)にマッピングされたピクセルは、テキストカラーを使用して表示されます。 2 番目の色にマップされたピクセル (カラー テーブルのオフセット 1) は背景色を使用して表示されます。

次の Windows 関数の使用方法については、Windows SDK を参照してください。

- [CreateDIBPatternBrush](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrush) (この関数は、3.0 より前のバージョンの Windows 用に作成されたアプリケーション`CreateDIBPatternBrushPt`との互換性を保つためにのみ提供されます。

- [この](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrushpt)関数は、Win32 ベースのアプリケーションで使用する必要があります。

- [グローバルオロック](/windows/win32/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

## <a name="cbrushcreatehatchbrush"></a><a name="createhatchbrush"></a>Cブラシ::ハッチブラシを作成します。

指定したハッチ パターンと色でブラシを初期化します。

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ブラシのハッチ スタイルを指定します。 次のいずれかの値を指定できます。

- HS_BDIAGONAL 下向きのハッチ(左から右)を45度で

- HS_CROSS水平および垂直ハッチング

- HS_DIAGCROSS45度のハッチング

- HS_FDIAGONAL 上向きハッチ(左から右)を45度で

- HS_HORIZONTAL水平ハッチ

- HS_VERTICAL垂直ハッチ

*Crcolor*<br/>
ブラシの前景色を RGB カラー (ハッチの色) として指定します。 詳細については、Windows SDK の[「カラー参照](/windows/win32/gdi/colorref)」を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ブラシは、その後、任意のデバイス コンテキストの現在のブラシとして選択できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

## <a name="cbrushcreatepatternbrush"></a><a name="createpatternbrush"></a>Cブラシ::パターンブラシの作成

ビットマップで指定されたパターンを使用してブラシを初期化します。

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>パラメーター

*ビットマップ*<br/>
ビットマップを識別します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ブラシは、ラスター操作をサポートするデバイス コンテキストに対して選択できます。 *pBitmap*で識別されるビットマップは、通常[、CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap) [、CBitmap::CreateBitmapIndirect、CBitmap::](../../mfc/reference/cbitmap-class.md#createbitmapindirect)[ロードビットマップ](../../mfc/reference/cbitmap-class.md#loadbitmap)、または[CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)関数を使用して初期化されます。

塗りつぶしパターンとして使用されるビットマップは、8 ピクセル x 8 ピクセルにする必要があります。 ビットマップが大きい場合、Windows はビットマップの左上隅にあるピクセルの最初の 8 行と列に対応するビットのみを使用します。

パターン ブラシは、関連付けられたビットマップに影響を与えずに削除できます。 つまり、ビットマップを使用して任意の数のパターン ブラシを作成できます。

モノクロビットマップ(1色平面、1ビット/ピクセル)を使用して作成されたブラシは、現在のテキストと背景色を使用して描画されます。 0 に設定されたビットで表されるピクセルは、現在のテキストカラーで描画されます。 1 に設定されたビットで表されるピクセルは、現在の背景色で描画されます。

Windows 関数の[使用](/windows/win32/api/wingdi/nf-wingdi-createpatternbrush)の詳細については、Windows SDK を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

## <a name="cbrushcreatesolidbrush"></a><a name="createsolidbrush"></a>Cブラシ::ソリッドブラシを作成します。

指定した純色でブラシを初期化します。

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>パラメーター

*Crcolor*<br/>
ブラシの色を指定する[COLORREF](/windows/win32/gdi/colorref)構造体。 色は RGB 値を指定し、WINDOWS の RGB マクロを使用して構築できます。H。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ブラシは、その後、任意のデバイス コンテキストの現在のブラシとして選択できます。

によって`CreateSolidBrush`作成されたブラシの使用が終了したら、アプリケーションはデバイス コンテキストからブラシを選択する必要があります。

### <a name="example"></a>例

  [Cブラシ::Cブラシ](#cbrush)の例を参照してください。

## <a name="cbrushcreatesyscolorbrush"></a><a name="createsyscolorbrush"></a>Cブラシ::作成シスカラーブラシ

ブラシの色を初期化します。

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
カラー インデックスを指定します。 この値は、21 個のウィンドウ要素の 1 つを描画するために使用される色に対応します。 値の一覧については、Windows SDK の[「GetSysColor」](/windows/win32/api/winuser/nf-winuser-getsyscolor)を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ブラシは、その後、任意のデバイス コンテキストの現在のブラシとして選択できます。

によって`CreateSysColorBrush`作成されたブラシの使用が終了したら、アプリケーションはデバイス コンテキストからブラシを選択する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

## <a name="cbrushfromhandle"></a><a name="fromhandle"></a>Cブラシ::ハンドルから

Windows [HBRUSH](#operator_hbrush) `CBrush`オブジェクトへのハンドルが渡されたときに、オブジェクトへのポインターを返します。

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>パラメーター

*hブラシ*<br/>
ウィンドウズ GDI ブラシへのハンドル。

### <a name="return-value"></a>戻り値

成功した場合は`CBrush`オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

オブジェクトが`CBrush`ハンドルにまだアタッチされていない場合は、一時`CBrush`オブジェクトが作成され、アタッチされます。 この一`CBrush`時オブジェクトは、アプリケーションがイベント ループで次にアイドル時間を持つまで有効です。 この時点で、すべての一時的なグラフィック オブジェクトが削除されます。 つまり、一時オブジェクトは、1 つのウィンドウ メッセージの処理中にのみ有効です。

グラフィックオブジェクトの使用の詳細については、Windows SDK の[グラフィックオブジェクト](/windows/win32/gdi/graphic-objects)を参照してください。

### <a name="example"></a>例

  [Cブラシ::Cブラシ](#cbrush)の例を参照してください。

## <a name="cbrushgetlogbrush"></a><a name="getlogbrush"></a>Cブラシ::ゲットログブラシ

構造体を取得するには、このメンバー`LOGBRUSH`関数を呼び出します。

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ブラシに関する情報を含む[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush)構造体へのポイント。

### <a name="return-value"></a>戻り値

関数が成功し *、pLogBrush*が有効なポインターである場合、戻り値はバッファーに格納されているバイト数です。

関数が成功し *、pLogBrush*が NULL の場合、関数がバッファーに格納する情報を保持するために必要なバイト数が戻り値になります。

関数が失敗した場合、戻り値は 0 です。

### <a name="remarks"></a>解説

構造`LOGBRUSH`は、ブラシのスタイル、色、およびパターンを定義します。

たとえば、ビットマップの`GetLogBrush`特定の色またはパターンに一致するように呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

## <a name="cbrushoperator-hbrush"></a><a name="operator_hbrush"></a>Cブラシ::オペレータHブラシ

この演算子を使用して、オブジェクトの添付された Windows `CBrush` GDI ハンドルを取得します。

```
operator HBRUSH() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトによって表される Windows GDI`CBrush`オブジェクトへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は、HBRUSH オブジェクトの直接使用をサポートするキャスト演算子です。

グラフィックオブジェクトの使用の詳細については、Windows SDK の[グラフィックオブジェクト](/windows/win32/gdi/graphic-objects)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル のプロップル](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cbitmap-class.md)<br/>
[CDCクラス](../../mfc/reference/cdc-class.md)
