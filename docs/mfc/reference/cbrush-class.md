---
title: CBrush クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17e422147da931aee1877e7be54b7032e7bc8712
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077999"
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
|[CBrush::CBrush](#cbrush)|`CBrush` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CBrush::CreateBrushIndirect](#createbrushindirect)|スタイル、色、および指定されたパターンでブラシを初期化する[LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush)構造体。|
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|デバイスに依存しないビットマップ (DIB) で指定されたパターンでは、ブラシを初期化します。|
|[CBrush::CreateHatchBrush](#createhatchbrush)|指定したハッシュ パターンおよび色のブラシを初期化します。|
|[CBrush::CreatePatternBrush](#createpatternbrush)|ビットマップで指定されたパターンでは、ブラシを初期化します。|
|[CBrush::CreateSolidBrush](#createsolidbrush)|指定の純色ブラシを初期化します。|
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|既定のシステム カラーであるブラシを作成します。|
|[CBrush::FromHandle](#fromhandle)|ポインターを返します、`CBrush`を Windows にハンドルが指定されると`HBRUSH`オブジェクト。|
|[CBrush::GetLogBrush](#getlogbrush)|取得、 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush)構造体。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CBrush::operator HBRUSH](#operator_hbrush)|アタッチされている Windows ハンドルを返します、`CBrush`オブジェクト。|

## <a name="remarks"></a>Remarks

使用する、`CBrush`オブジェクト、構築、`CBrush`オブジェクトし、いずれかに渡す`CDC`ブラシを必要とするメンバー関数。

ハッチ、およびパターン、ブラシは、solid できます。

詳細については`CBrush`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cbrush"></a>  CBrush::CBrush

`CBrush` オブジェクトを構築します。

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>パラメーター

*crColor*<br/>
RGB 色としてブラシの前景色を指定します。 ブラシがハッチが、このパラメーターは、陰影の色を指定します。

*nIndex*<br/>
ブラシの陰影のスタイルを指定します。 次の値のいずれかを指定できます。

- 45 度 HS_BDIAGONAL 下向きハッチ (左右から)

- HS_CROSS 水平と垂直方向のハッチング

- HS_DIAGCROSS が 45 度のクロスハッチ

- 上方向 HS_FDIAGONAL ハッチ (左右から) を 45 度

- 水平 HS_HORIZONTAL ハッチ

- HS_VERTICAL 垂直ハッチ

*pBitmap*<br/>
指す、`CBitmap`ブラシを描画するビットマップを指定するオブジェクト。

### <a name="remarks"></a>Remarks

`CBrush` コンス トラクターが 4 つオーバー ロードします。引数なしのコンス トラクターを作成、初期化されていない`CBrush`オブジェクトを使用する初期化する必要があります。

引数なしのコンス トラクターを使用する場合、その結果を初期化する必要があります`CBrush`オブジェクト[CreateSolidBrush](#createsolidbrush)、 [CreateHatchBrush](#createhatchbrush)、 [CreateBrushIndirect](#createbrushindirect)、[とき](#createpatternbrush)、または[構築](#createdibpatternbrush)します。 引数を受け取るコンス トラクターのいずれかを使用する場合、それ以上初期化必要があります。 引数を持つコンス トラクターは、引数なしのコンス トラクターは常に成功しますが、エラーが発生した場合、例外をスローできます。

1 つのコンス トラクター [COLORREF](/windows/desktop/gdi/colorref)パラメーターが指定した色を純色ブラシを作成します。 色は、RGB 値を指定しますおよび RGB マクロを WINDOWS で使用して構築できます。H.

2 つのパラメーターを持つコンス トラクターは、ハッチ ブラシを構築します。 *NIndex*ハッチ パターンのインデックスを指定します。 *CrColor*パラメーターは、色を指定します。

使用するコンス トラクター、`CBitmap`パラメーター パターンのブラシを作成します。 パラメーターは、ビットマップを識別します。 ビットマップを使用して作成されたものと見なされます[CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap)、 [cbitmap::createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)、 [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)、または[CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)します。 塗りつぶしのパターンで使用されるビットマップの最小サイズは、8 ピクセルの 8 ピクセルです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

##  <a name="createbrushindirect"></a>  CBrush::CreateBrushIndirect

スタイル、色、および指定されたパターンでブラシを初期化する[LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush)構造体。

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>パラメーター

*lpLogBrush*<br/>
指す、 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush)ブラシに関する情報を含む構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ブラシは、現在の任意のデバイス コンテキスト ブラシとして後で選択できます。

(1 プレーン、ピクセルあたり 1 ビット) のモノクロ ビットマップを使用して作成されたブラシは、現在のテキストと背景色を使用して描画されます。 0 に設定されたビットで表されるピクセルは、現在のテキスト色で描画されます。 1 に設定されたビットで表されるピクセルは、現在の背景色で描画されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

##  <a name="createdibpatternbrush"></a>  CBrush::CreateDIBPatternBrush

デバイスに依存しないビットマップ (DIB) で指定されたパターンでは、ブラシを初期化します。

```
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,
    UINT nUsage);

BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,
    UINT nUsage);
```

### <a name="parameters"></a>パラメーター

*hPackedDIB*<br/>
パックされたデバイスに依存しないビットマップ (DIB) を格納するグローバル メモリ オブジェクトを識別します。

*n 使用法*<br/>
指定するかどうか、`bmiColors[]`のフィールド、 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md)データ構造 (「パック DIB」の一部) が実現された現在の論理パレットに明示的な RGB 値またはインデックスを含めることができます。 パラメーターは、次の値のいずれかである必要があります。

- DIB_PAL_COLORS カラー テーブルは、16 ビットのインデックスの配列で構成されます。

- DIB_RGB_COLORS カラー テーブルには、リテラルの RGB 値が含まれています。

*lpPackedDIB*<br/>
成るパックされた DIB を指す、`BITMAPINFO`構造体の直後に、ビットマップのピクセルを定義するバイト配列。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ブラシは、ラスター オペレーションをサポートする任意のデバイス コンテキストを選択できます。

2 つのバージョンの DIB を処理する方法が異なります。

- 最初のバージョンでの DIB を識別するハンドルを取得するを呼び出す、Windows`GlobalAlloc`関数をグローバル メモリのブロックを割り当てたり、パックされた DIB でメモリを入力します。

- 2 番目のバージョンで必要はありませんを呼び出す`GlobalAlloc`パックされた DIB のメモリを割り当てられません。

パックされた DIB から成る、`BITMAPINFO`直後に、ビットマップのピクセルを定義するバイト配列データ構造体。 塗りつぶしのパターンとして使用されるビットマップ ピクセル、8 8 ピクセルがあります。 ビットマップが大きい場合は、Windows は、最初の 8 行と左上隅にあるビットマップのピクセルの 8 つの列に対応するビットだけを使用して塗りつぶしパターンを作成します。

アプリケーションでは、モノクロ デバイス コンテキストに、2 色の DIB パターンのブラシを選択すると、Windows は DIB で指定された色を無視し、代わりに、デバイス コンテキストの現在のテキストと背景色を使用してブラシ パターンが表示されます。 ピクセルの DIB (DIB のカラー テーブル内のオフセット 0) にある最初の色にマップは、テキストの色で表示されます。 ピクセル (カラー テーブル内のオフセット 1) にある 2 番目の色にマップの背景色を使用してが表示されます。

次の Windows 機能の使用方法の詳細については、Windows SDK を参照してください。

- [構築](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrush)(3.0 より前のバージョンの Windows 用に記述されたアプリケーションとの互換性のためだけに用意されているこの関数は、使用して、`CreateDIBPatternBrushPt`関数です)。

- [されている](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrushpt)(この関数は Win32 ベースのアプリケーションを使用する必要があります)。

- [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

##  <a name="createhatchbrush"></a>  CBrush::CreateHatchBrush

指定したハッシュ パターンおよび色のブラシを初期化します。

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ブラシの陰影のスタイルを指定します。 次の値のいずれかを指定できます。

- 45 度 HS_BDIAGONAL 下向きハッチ (左右から)

- HS_CROSS 水平と垂直方向のハッチング

- HS_DIAGCROSS が 45 度のクロスハッチ

- 上方向 HS_FDIAGONAL ハッチ (左右から) を 45 度

- 水平 HS_HORIZONTAL ハッチ

- HS_VERTICAL 垂直ハッチ

*crColor*<br/>
RGB 色 (の陰影の色) として、ブラシの前景色を指定します。 参照してください[COLORREF](/windows/desktop/gdi/colorref)詳細については、Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ブラシは、現在の任意のデバイス コンテキスト ブラシとして後で選択できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

##  <a name="createpatternbrush"></a>  CBrush::CreatePatternBrush

ビットマップで指定されたパターンでは、ブラシを初期化します。

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>パラメーター

*pBitmap*<br/>
ビットマップを識別します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ブラシは、ラスター オペレーションをサポートする任意のデバイス コンテキストを選択できます。 識別されるビットマップ*pBitmap*を使用して初期化は通常、 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap)、 [cbitmap::createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)、 [CBitmap:。LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)、または[CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)関数。

塗りつぶしのパターンとして使用されるビットマップ ピクセル、8 8 ピクセルがあります。 ビットマップが大きい場合は、Windows は、最初の 8 行と列の左上隅にあるビットマップのピクセルに対応するビットだけ使用します。

ブラシのパターンは、関連するビットマップの影響を与えずに削除できます。 つまり、任意の数のパターンのブラシを作成する、ビットマップを使用できます。

モノクロ ビットマップ (1 ピクセルあたり 1 ビット、色が 1 色プレーン) を使用して作成されたブラシは、現在のテキストと背景色を使用して描画されます。 0 に設定されたビットで表されるピクセルは、現在のテキストの色で描画されます。 1 に設定されたビットで表されるピクセルは、現在の背景色で描画されます。

使用方法について[とき](/windows/desktop/api/wingdi/nf-wingdi-createpatternbrush)、Windows 機能、Windows SDK を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

##  <a name="createsolidbrush"></a>  CBrush::CreateSolidBrush

指定の純色ブラシを初期化します。

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>パラメーター

*crColor*<br/>
A [COLORREF](/windows/desktop/gdi/colorref)構造、ブラシの色を指定します。 色は、RGB 値を指定しますおよび RGB マクロを WINDOWS で使用して構築できます。H.

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ブラシは、現在の任意のデバイス コンテキスト ブラシとして後で選択できます。

アプリケーションがいつ終了したによって作成されたブラシを使用して`CreateSolidBrush`、デバイス コンテキスト外のブラシを選択する必要があります。

### <a name="example"></a>例

  例をご覧ください[CBrush::CBrush](#cbrush)します。

##  <a name="createsyscolorbrush"></a>  CBrush::CreateSysColorBrush

ブラシの色を初期化します。

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
色のインデックスを指定します。 この値は、ウィンドウ要素のいずれかの描画に使用する色に対応します。 参照してください[GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor)値の一覧については、Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ブラシは、現在の任意のデバイス コンテキスト ブラシとして後で選択できます。

アプリケーションがいつ終了したによって作成されたブラシを使用して`CreateSysColorBrush`、デバイス コンテキスト外のブラシを選択する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

##  <a name="fromhandle"></a>  CBrush::FromHandle

ポインターを返します、`CBrush`を Windows にハンドルが指定されると[HBRUSH](#operator_hbrush)オブジェクト。

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>パラメーター

*hBrush*<br/>
Windows GDI ブラシへのハンドルします。

### <a name="return-value"></a>戻り値

ポインター、`CBrush`成功。 それ以外の場合に NULL の場合は、オブジェクト。

### <a name="remarks"></a>Remarks

場合、`CBrush`ハンドル、一時的にオブジェクトが既にアタッチされていない`CBrush`オブジェクトを作成し、接続されています。 この一時`CBrush`オブジェクトが次回アプリケーションがあるイベント ループでのアイドル時間までに限り有効です。 この時点では、すべての一時的なグラフィック オブジェクトが削除されます。 つまり、一時オブジェクトは 1 つのウィンドウ メッセージを処理中にのみ有効です。

グラフィック オブジェクトの使用に関する詳細については、次を参照してください。[グラフィック オブジェクト](/windows/desktop/gdi/graphic-objects)Windows SDK に含まれています。

### <a name="example"></a>例

  例をご覧ください[CBrush::CBrush](#cbrush)します。

##  <a name="getlogbrush"></a>  CBrush::GetLogBrush

取得するには、このメンバー関数を呼び出す、`LOGBRUSH`構造体。

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>パラメーター

*終了*<br/>
指す、 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush)ブラシに関する情報を含む構造体。

### <a name="return-value"></a>戻り値

関数が成功した場合と*終了*有効なポインターが、戻り値は、バッファーに格納されているバイト数。

関数が成功した場合と*終了*が null の場合、戻り値は、関数の情報を保持するために必要なバイト数にはバッファーに保存します。

関数が失敗した場合、戻り値は 0 です。

### <a name="remarks"></a>Remarks

`LOGBRUSH`構造体、スタイル、色、およびブラシのパターンを定義します。

たとえば、呼び出す`GetLogBrush`特定の色またはビットマップのパターンに一致するようにします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

##  <a name="operator_hbrush"></a>  CBrush::operator HBRUSH

接続されている Windows GDI ハンドルを取得するこの演算子を使用して、`CBrush`オブジェクト。

```
operator HBRUSH() const;
```

### <a name="return-value"></a>戻り値

かどうかは成功すると、Windows GDI オブジェクトを識別するハンドルで表される、`CBrush`オブジェクト。 それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

この演算子は、キャスト演算子です。

グラフィック オブジェクトの使用に関する詳細については、次を参照してください。[グラフィック オブジェクト](/windows/desktop/gdi/graphic-objects)Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル PROPDLG](../../visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CBitmap クラス](../../mfc/reference/cbitmap-class.md)<br/>
[CDC クラス](../../mfc/reference/cdc-class.md)
