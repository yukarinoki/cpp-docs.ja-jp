---
title: CRgn クラス
ms.date: 11/04/2016
f1_keywords:
- CRgn
- AFXWIN/CRgn
- AFXWIN/CRgn::CRgn
- AFXWIN/CRgn::CombineRgn
- AFXWIN/CRgn::CopyRgn
- AFXWIN/CRgn::CreateEllipticRgn
- AFXWIN/CRgn::CreateEllipticRgnIndirect
- AFXWIN/CRgn::CreateFromData
- AFXWIN/CRgn::CreateFromPath
- AFXWIN/CRgn::CreatePolygonRgn
- AFXWIN/CRgn::CreatePolyPolygonRgn
- AFXWIN/CRgn::CreateRectRgn
- AFXWIN/CRgn::CreateRectRgnIndirect
- AFXWIN/CRgn::CreateRoundRectRgn
- AFXWIN/CRgn::EqualRgn
- AFXWIN/CRgn::FromHandle
- AFXWIN/CRgn::GetRegionData
- AFXWIN/CRgn::GetRgnBox
- AFXWIN/CRgn::OffsetRgn
- AFXWIN/CRgn::PtInRegion
- AFXWIN/CRgn::RectInRegion
- AFXWIN/CRgn::SetRectRgn
helpviewer_keywords:
- CRgn [MFC], CRgn
- CRgn [MFC], CombineRgn
- CRgn [MFC], CopyRgn
- CRgn [MFC], CreateEllipticRgn
- CRgn [MFC], CreateEllipticRgnIndirect
- CRgn [MFC], CreateFromData
- CRgn [MFC], CreateFromPath
- CRgn [MFC], CreatePolygonRgn
- CRgn [MFC], CreatePolyPolygonRgn
- CRgn [MFC], CreateRectRgn
- CRgn [MFC], CreateRectRgnIndirect
- CRgn [MFC], CreateRoundRectRgn
- CRgn [MFC], EqualRgn
- CRgn [MFC], FromHandle
- CRgn [MFC], GetRegionData
- CRgn [MFC], GetRgnBox
- CRgn [MFC], OffsetRgn
- CRgn [MFC], PtInRegion
- CRgn [MFC], RectInRegion
- CRgn [MFC], SetRectRgn
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
ms.openlocfilehash: e84526eec8f4fd4b1935fa39bc7f4ed3c4d5dd71
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754478"
---
# <a name="crgn-class"></a>CRgn クラス

Windows のグラフィック デバイス インターフェイス (GDI) の領域をカプセル化したものです。

## <a name="syntax"></a>構文

```
class CRgn : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRgn::CRgn](#crgn)|`CRgn` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRgn::コンバインRgn](#combinergn)|指定した`CRgn``CRgn`2 つのオブジェクトの和集合と等価になるようにオブジェクトを設定します。|
|[CRgn::コピールグン](#copyrgn)|オブジェクトを`CRgn`指定した`CRgn`オブジェクトのコピーに設定します。|
|[CRgn::リエッピティックルグンを作成します。](#createellipticrgn)|オブジェクトを`CRgn`楕円領域で初期化します。|
|[CRgn::インダイレクトを作成します。](#createellipticrgnindirect)|[RECT](/windows/win32/api/windef/ns-windef-rect) `CRgn`構造体で定義された楕円領域を使用してオブジェクトを初期化します。|
|[データを作成します。](#createfromdata)|指定した領域および変換データから領域を作成します。|
|[CRgn::パスを作成します。](#createfrompath)|指定されたデバイス コンテキストに選択されたパスから領域を作成します。|
|[CRgn::ポリゴンRgnの作成](#createpolygonrgn)|ポリゴン領域を`CRgn`使用してオブジェクトを初期化します。 システムは、必要に応じて、最後の頂点から最初の頂点に線を描画することで、ポリゴンを自動的に閉じます。|
|[CRgn::ポリポリゴンRgnを作成します。](#createpolypolygonrgn)|一連の`CRgn`閉じたポリゴンで構成される領域を使用してオブジェクトを初期化します。 ポリゴンが不整合になっているか、重なり合っている可能性があります。|
|[CRgn::CreateRectRgn](#createrectrgn)|四角形の`CRgn`領域を使用してオブジェクトを初期化します。|
|[CRgn::ダイレクト](#createrectrgnindirect)|[RECT](/windows/win32/api/windef/ns-windef-rect)`CRgn`トラクチャによって定義された矩形領域を使用してオブジェクトを初期化します。|
|[CRgn::ラウンドレックルグンを作成します。](#createroundrectrgn)|角が`CRgn`丸い四角形の領域でオブジェクトを初期化します。|
|[CRgn::イコールルグン](#equalrgn)|2`CRgn`つのオブジェクトが等価かどうかを確認します。|
|[CRgn::ハンドルから](#fromhandle)|Windows 領域へのハンドル`CRgn`が与えられた場合、オブジェクトへのポインターを返します。|
|[CRGN::ゲットリージョンデータ](#getregiondata)|指定したバッファーに、指定した領域を記述するデータを格納します。|
|[CRGN::ゲットルグンボックス](#getrgnbox)|オブジェクトの外接する四角形の座標を`CRgn`取得します。|
|[CRgn::オフセットRgn](#offsetrgn)|指定した`CRgn`オフセットでオブジェクトを移動します。|
|[CRGN::PtIn領域](#ptinregion)|指定した点が領域内にあるかどうかを判断します。|
|[CRGN::レクチン地域](#rectinregion)|指定した四角形の一部が領域の境界内にあるかどうかを判断します。|
|[CRgn::セットレクトルグン](#setrectrgn)|オブジェクトを`CRgn`指定された四角形の領域に設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CRGN::オペレーターHRGN](#operator_hrgn)|オブジェクトに含まれる Windows`CRgn`ハンドルを返します。|

## <a name="remarks"></a>解説

領域は、ウィンドウ内の楕円形またはポリゴン領域です。 領域を使用するには、クラス`CRgn`のメンバー関数を使用し、 クラスのメンバーとして定義されたクリッピング`CDC`関数を使用します。

呼び出される`CRgn`領域オブジェクトに関する情報を作成、変更、および取得するメンバー関数。

の使用方法`CRgn`の詳細については、「[グラフィック オブジェクト](../../mfc/graphic-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CRgn`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="crgncombinergn"></a><a name="combinergn"></a>CRgn::コンバインRgn

既存の 2 つの領域を組み合わせて新しい GDI 領域を作成します。

```
int CombineRgn(
    CRgn* pRgn1,
    CRgn* pRgn2,
    int nCombineMode);
```

### <a name="parameters"></a>パラメーター

*pRgn1*<br/>
既存の領域を識別します。

*pRgn2*<br/>
既存の領域を識別します。

*結合モード*<br/>
2 つのソース領域を結合するときに実行される操作を指定します。 次のいずれかの値を指定できます。

- RGN_AND 両方の領域 (交差) の重なり合う領域を使用します。

- RGN_COPY 領域 1 のコピーを作成します *(pRgn1*で識別されます)。

- RGN_DIFF 領域 2 の一部ではない領域 1 *(pRgn1*で識別される) 領域 1 の領域 *(pRgn2*によって識別される) から成る領域を作成します。

- RGN_OR両方の領域を全体 (ユニオン) で結合します。

- RGN_XOR 両方の領域を結合しますが、重なり合う領域は削除されます。

### <a name="return-value"></a>戻り値

結果の領域の種類を指定します。 次のいずれかの値を指定できます。

- 複合領域 新しい領域の境界線が重複しています。

- エラー 新しいリージョンは作成されません。

- 新しい領域が空です。

- シンプルリージョン 新しいリージョンには、重複する境界線はありません。

### <a name="remarks"></a>解説

領域は*nCombineMode*で指定されたとおりに結合されます。

指定した 2 つの領域が結合され、結果の領域ハンドルがオブジェクトに`CRgn`格納されます。 したがって、`CRgn`オブジェクトに格納されている領域は、結合領域に置き換えられます。

領域のサイズは、32,767 の論理ユニットまたは 64K のメモリのうち、小さい方の方が 32,767 に制限されています。

[CopyRgn](#copyrgn)を使用して、あるリージョンを別のリージョンにコピーするだけです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]

## <a name="crgncopyrgn"></a><a name="copyrgn"></a>CRgn::コピールグン

*pRgnSrc*によって定義された領域をオブジェクト`CRgn`にコピーします。

```
int CopyRgn(CRgn* pRgnSrc);
```

### <a name="parameters"></a>パラメーター

*pRgnSrc*<br/>
既存の領域を識別します。

### <a name="return-value"></a>戻り値

結果の領域の種類を指定します。 次のいずれかの値を指定できます。

- 複合領域 新しい領域の境界線が重複しています。

- エラー 新しいリージョンは作成されません。

- 新しい領域が空です。

- シンプルリージョン 新しいリージョンには、重複する境界線はありません。

### <a name="remarks"></a>解説

新しい領域は、オブジェクトに以前格納されていた領域`CRgn`に置き換わります。 この関数は[、CombineRgn](#combinergn)メンバー関数の特殊なケースです。

### <a name="example"></a>例

  [CRgn::CreateEllipticRgn](#createellipticrgn)の例を参照してください。

## <a name="crgncreateellipticrgn"></a><a name="createellipticrgn"></a>CRgn::リエッピティックルグンを作成します。

楕円領域を作成します。

```
BOOL CreateEllipticRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>パラメーター

*x1*<br/>
楕円の外接する四角形の左上隅の論理 x 座標を指定します。

*y1*<br/>
楕円の外接する四角形の左上隅の論理 y 座標を指定します。

*x2*<br/>
楕円の外接する四角形の右下隅の論理 x 座標を指定します。

*y2*<br/>
楕円の外接する四角形の右下隅の論理 y 座標を指定します。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

領域は *、x1*、 *y1 、x2*、および*y2**y2*で指定された外接する四角形によって定義されます。 領域はオブジェクトに`CRgn`格納されます。

領域のサイズは、32,767 の論理ユニットまたは 64K のメモリのうち、小さい方の方が 32,767 に制限されています。

関数で作成された領域の使用が`CreateEllipticRgn`終了したら、アプリケーションはデバイス コンテキストから領域を選択し、その関数を`DeleteObject`使用してその領域を削除する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]

## <a name="crgncreateellipticrgnindirect"></a><a name="createellipticrgnindirect"></a>CRgn::インダイレクトを作成します。

楕円領域を作成します。

```
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
楕円の`RECT`外接する`CRect`四角形の左上隅と右下隅の論理座標を含む構造体またはオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

領域は *、lpRect*によって指される構造体またはオブジェクトによって定義され、オブジェクトに`CRgn`格納されます。

領域のサイズは、32,767 の論理ユニットまたは 64K のメモリのうち、小さい方の方が 32,767 に制限されています。

関数で作成された領域の使用が`CreateEllipticRgnIndirect`終了したら、アプリケーションはデバイス コンテキストから領域を選択し、その関数を`DeleteObject`使用してその領域を削除する必要があります。

### <a name="example"></a>例

  [CRgn::CreateRectRgnインダイレクト](#createrectrgnindirect)の例を参照してください。

## <a name="crgncreatefromdata"></a><a name="createfromdata"></a>データを作成します。

指定した領域および変換データから領域を作成します。

```
BOOL CreateFromData(
    const XFORM* lpXForm,
    int nCount,
    const RGNDATA* pRgnData);
```

### <a name="parameters"></a>パラメーター

*lpX フォーム*<br/>
領域で実行される変換を定義する[XFORM](/windows/win32/api/wingdi/ns-wingdi-xform)ata 構造体へのポイント。 このポインターが NULL の場合、ID 変換が使用されます。

*nカウント*<br/>
*pRgnData*が指すバイト数を指定します。

*を使用します。*<br/>
領域データを含む[RGNDATA](/windows/win32/api/wingdi/ns-wingdi-rgndata)データ構造へのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

アプリケーションは、関数を呼び出すことによって領域の`CRgn::GetRegionData`データを取得できます。

## <a name="crgncreatefrompath"></a><a name="createfrompath"></a>CRgn::パスを作成します。

指定されたデバイス コンテキストに選択されたパスから領域を作成します。

```
BOOL CreateFromPath(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
閉じたパスを含むデバイス コンテキストを識別します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

*pDC*パラメーターによって識別されるデバイス コンテキストには、閉じたパスが含まれている必要があります。 パス`CreateFromPath`を領域に変換すると、Windows はデバイス コンテキストから閉じたパスを破棄します。

## <a name="crgncreatepolygonrgn"></a><a name="createpolygonrgn"></a>CRgn::ポリゴンRgnの作成

ポリゴン領域を作成します。

```
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,
    int nCount,
    int nMode);
```

### <a name="parameters"></a>パラメーター

*Lppoints*<br/>
構造体の配列または`POINT``CPoint`オブジェクトの配列へのポイント。 各構造体は、ポリゴンの 1 つの頂点の x 座標と y 座標を指定します。 構造`POINT`の形式は次のとおりです。

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*nカウント*<br/>
*lpPoints*が`POINT`指す配列`CPoint`内の構造体またはオブジェクトの数を指定します。

*nモード*<br/>
領域の塗りつぶしモードを指定します。 このパラメーターは、代替または巻き取りのいずれかです。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

システムは、必要に応じて、最後の頂点から最初の頂点に線を描画することで、ポリゴンを自動的に閉じます。 結果の領域はオブジェクトに`CRgn`格納されます。

領域のサイズは、32,767 の論理ユニットまたは 64K のメモリのうち、小さい方の方が 32,767 に制限されています。

ポリゴン塗りつぶしモードが ALTERNATE の場合、各スキャン ラインの奇数ポリゴン側と偶数数のポリゴン辺の間の領域が塗りつぶされます。 つまり、システムは、第 1 側と 2 番目の側、3 番目と 4 番目の側の間の領域を塗りつぶします。

ポリゴン充填モードが WINDING の場合、図が描画された方向を使用して、領域を塗りつぶすかどうかを決定します。 ポリゴン内の各線分セグメントは、時計回りまたは反時計回りの方向に描画されます。 囲まれた領域から図形の外側に描画された架空の線が時計回りの線分セグメントを通過すると、カウントが増分されます。 線が反時計回りの線分を通過すると、カウントはデクリメントされます。 線が図の外側に達したときにカウントが 0 以外の場合、領域は塗りつぶされます。

アプリケーションは、関数で作成された領域の使用を`CreatePolygonRgn`終了したら、デバイス コンテキストから領域を選択し、その関数を`DeleteObject`使用して削除する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]

## <a name="crgncreatepolypolygonrgn"></a><a name="createpolypolygonrgn"></a>CRgn::ポリポリゴンRgnを作成します。

一連の閉じたポリゴンで構成される領域を作成します。

```
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,
    LPINT lpPolyCounts,
    int nCount,
    int nPolyFillMode);
```

### <a name="parameters"></a>パラメーター

*Lppoints*<br/>
ポリゴンの頂点を定義`POINT`する構造体の配列またはオブジェクト`CPoint`の配列へのポイント。 各ポリゴンは、システムが自動的に閉じるわけではないので、明示的に閉じる必要があります。 ポリゴンは連続して指定されます。 構造`POINT`の形式は次のとおりです。

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*lpPolyカウント*<br/>
整数の配列へのポイント。 最初の整数は *、lpPoints*配列の最初のポリゴンの頂点の数を指定し、2 番目の整数は 2 番目のポリゴンの頂点の数を指定します。

*nカウント*<br/>
*配列*内の整数の総数を指定します。

*nポリフィルモード*<br/>
ポリゴン塗りつぶしモードを指定します。 この値は、代替または巻き上げのいずれかです。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

結果の領域はオブジェクトに`CRgn`格納されます。

ポリゴンが不整合になっているか、重なり合っている可能性があります。

領域のサイズは、32,767 の論理ユニットまたは 64K のメモリのうち、小さい方の方が 32,767 に制限されています。

ポリゴン塗りつぶしモードが ALTERNATE の場合、各スキャン ラインの奇数ポリゴン側と偶数数のポリゴン辺の間の領域が塗りつぶされます。 つまり、システムは、第 1 側と 2 番目の側、3 番目と 4 番目の側の間の領域を塗りつぶします。

ポリゴン充填モードが WINDING の場合、図が描画された方向を使用して、領域を塗りつぶすかどうかを決定します。 ポリゴン内の各線分セグメントは、時計回りまたは反時計回りの方向に描画されます。 囲まれた領域から図形の外側に描画された架空の線が時計回りの線分セグメントを通過すると、カウントが増分されます。 線が反時計回りの線分を通過すると、カウントはデクリメントされます。 線が図の外側に達したときにカウントが 0 以外の場合、領域は塗りつぶされます。

アプリケーションは、関数で作成された領域の使用を`CreatePolyPolygonRgn`終了したら、デバイス コンテキストから領域を選択し、それを削除する[CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数を使用する必要があります。

## <a name="crgncreaterectrgn"></a><a name="createrectrgn"></a>CRgn::CreateRectRgn

オブジェクトに格納されている四角形の領域を`CRgn`作成します。

```
BOOL CreateRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>パラメーター

*x1*<br/>
領域の左上隅の論理 x 座標を指定します。

*y1*<br/>
領域の左上隅の論理 y 座標を指定します。

*x2*<br/>
領域の右下隅の論理 x 座標を指定します。

*y2*<br/>
領域の右下隅の論理 y 座標を指定します。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

領域のサイズは、32,767 の論理ユニットまたは 64K のメモリのうち、小さい方の方が 32,767 に制限されています。

によって`CreateRectRgn`作成された領域の使用が終了したら、アプリケーションは[CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数を使用して領域を削除する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]

その他の例については[、「CRgn::CombineRgn」](#combinergn)を参照してください。

## <a name="crgncreaterectrgnindirect"></a><a name="createrectrgnindirect"></a>CRgn::ダイレクト

オブジェクトに格納されている四角形の領域を`CRgn`作成します。

```
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
領域の`RECT`左上および`CRect`右下隅の論理座標を含む構造体またはオブジェクトへのポインター。 構造`RECT`の形式は次のとおりです。

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

領域のサイズは、32,767 の論理ユニットまたは 64K のメモリのうち、小さい方の方が 32,767 に制限されています。

によって`CreateRectRgnIndirect`作成された領域の使用が終了したら、アプリケーションは[CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数を使用して領域を削除する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]

## <a name="crgncreateroundrectrgn"></a><a name="createroundrectrgn"></a>CRgn::ラウンドレックルグンを作成します。

オブジェクトに格納されている角が丸い四角形の領域`CRgn`を作成します。

```
BOOL CreateRoundRectRgn(
    int x1,
    int y1,
    int x2,
    int y2,
    int x3,
    int y3);
```

### <a name="parameters"></a>パラメーター

*x1*<br/>
領域の左上隅の論理 x 座標を指定します。

*y1*<br/>
領域の左上隅の論理 y 座標を指定します。

*x2*<br/>
領域の右下隅の論理 x 座標を指定します。

*y2*<br/>
領域の右下隅の論理 y 座標を指定します。

*x3*<br/>
角丸を作成するために使用する楕円の幅を指定します。

*y3*<br/>
丸い角を作成するために使用する楕円の高さを指定します。

### <a name="return-value"></a>戻り値

操作が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

領域のサイズは、32,767 の論理ユニットまたは 64K のメモリのうち、小さい方の方が 32,767 に制限されています。

アプリケーションは、関数で作成された領域の使用を`CreateRoundRectRgn`終了したら、デバイス コンテキストから領域を選択し、それを削除する[CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数を使用する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]

## <a name="crgncrgn"></a><a name="crgn"></a>CRgn::CRgn

`CRgn` オブジェクトを構築します。

```
CRgn();
```

### <a name="remarks"></a>解説

オブジェクト`m_hObject`が他`CRgn`の 1 つ以上のメンバー関数で初期化されるまで、データ メンバーには有効な Windows GDI 領域が含まれません。

### <a name="example"></a>例

  [CRgn::CreateRoundRectRgn](#createroundrectrgn)の例を参照してください。

## <a name="crgnequalrgn"></a><a name="equalrgn"></a>CRgn::イコールルグン

指定した領域が`CRgn`、オブジェクトに格納されている領域と等しいかどうかを判断します。

```
BOOL EqualRgn(CRgn* pRgn) const;
```

### <a name="parameters"></a>パラメーター

*Prgn*<br/>
領域を識別します。

### <a name="return-value"></a>戻り値

2 つの領域が等価の場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]

## <a name="crgnfromhandle"></a><a name="fromhandle"></a>CRgn::ハンドルから

Windows 領域へのハンドル`CRgn`が与えられた場合、オブジェクトへのポインターを返します。

```
static CRgn* PASCAL FromHandle(HRGN hRgn);
```

### <a name="parameters"></a>パラメーター

*hRgn*<br/>
Windows 領域へのハンドルを指定します。

### <a name="return-value"></a>戻り値

`CRgn` オブジェクトを指すポインターです。 関数が正常に終了しなかった場合、戻り値は NULL です。

### <a name="remarks"></a>解説

オブジェクトが`CRgn`ハンドルにまだアタッチされていない場合は、一時`CRgn`オブジェクトが作成され、アタッチされます。 この一`CRgn`時オブジェクトは、アプリケーションがイベント ループで次にアイドル時間を持つまで有効で、その時点ですべての一時グラフィック オブジェクトが削除されます。 もう 1 つの言い方は、一時オブジェクトが 1 つのウィンドウ メッセージの処理中にのみ有効であるというものです。

## <a name="crgngetregiondata"></a><a name="getregiondata"></a>CRGN::ゲットリージョンデータ

指定したバッファーに領域を記述するデータを格納します。

```
int GetRegionData(
    LPRGNDATA lpRgnData,
    int nCount) const;
```

### <a name="parameters"></a>パラメーター

*データ*<br/>
情報を受け取る[RGNDATA](/windows/win32/api/wingdi/ns-wingdi-rgndata)データ構造体へのポイント。 このパラメーターが NULL の場合、戻り値には領域データに必要なバイト数が含まれます。

*nカウント*<br/>
*lpRgnData*バッファーのサイズをバイト単位で指定します。

### <a name="return-value"></a>戻り値

関数が成功し *、nCount*が適切なバイト数を指定する場合、戻り値は常に*nCount です*。 関数が失敗した場合、または*nCount*が指定したバイト数が十分なバイト数より少ない場合、戻り値は 0 (エラー) になります。

### <a name="remarks"></a>解説

このデータには、領域を構成する四角形の寸法が含まれます。 この関数は、関数と組み`CRgn::CreateFromData`合わせて使用されます。

## <a name="crgngetrgnbox"></a><a name="getrgnbox"></a>CRGN::ゲットルグンボックス

オブジェクトの外接する四角形の座標を`CRgn`取得します。

```
int GetRgnBox(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
外接する`RECT`四角形`CRect`の座標を受け取る構造体またはオブジェクトへのポインター。 構造`RECT`の形式は次のとおりです。

`typedef struct tagRECT {`

`int left;`

`int top;`

`int right;`

`int bottom;`

`} RECT;`

### <a name="return-value"></a>戻り値

リージョンの種類を指定します。 次のいずれかの値を指定できます。

- 複合領域領域に重複する境界線があります。

- 領域が空です。

- ERROR`CRgn`オブジェクトは有効な領域を指定していません。

- シンプル領域領域には、重複する境界線はありません。

### <a name="example"></a>例

  [CRgn::CreatePolygonRgn](#createpolygonrgn)の例を参照してください。

## <a name="crgnoffsetrgn"></a><a name="offsetrgn"></a>CRgn::オフセットRgn

オブジェクトに格納されている領域を`CRgn`指定したオフセットで移動します。

```
int OffsetRgn(
    int x,
    int y);

int OffsetRgn(POINT point);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
左または右に移動する単位数を指定します。

*Y*<br/>
上または下に移動する単位数を指定します。

*ポイント*<br/>
x 座標の*点*は、左または右に移動する単位の数を指定します。 y 座標の*点*は、上下に移動する単位の数を指定します。 *ポイント*パラメータは`POINT`、構造体または`CPoint`オブジェクトのいずれかです。

### <a name="return-value"></a>戻り値

新しいリージョンの型。 次のいずれかの値を指定できます。

- 複合領域領域に重複する境界線があります。

- エラー領域ハンドルが無効です。

- 領域が空です。

- シンプル領域領域には、重複する境界線はありません。

### <a name="remarks"></a>解説

この関数は、y 軸に沿って領域*x*単位を x 軸と*y*単位に移動します。

領域の座標値は、32,767 以下で、-32,768 以上である必要があります。 x*および**y*パラメータは、無効な領域座標を避けるために慎重に選択する必要があります。

### <a name="example"></a>例

  [CRgn::CreateEllipticRgn](#createellipticrgn)の例を参照してください。

## <a name="crgnoperator-hrgn"></a><a name="operator_hrgn"></a>CRGN::オペレーターHRGN

この演算子を使用して、オブジェクトの添付された Windows `CRgn` GDI ハンドルを取得します。

```
operator HRGN() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトによって表される Windows GDI`CRgn`オブジェクトへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は、HRGN オブジェクトの直接使用をサポートするキャスティング演算子です。

グラフィック オブジェクトの使用の詳細については、Windows SDK の記事[「グラフィック オブジェクト](/windows/win32/gdi/graphic-objects)」を参照してください。

## <a name="crgnptinregion"></a><a name="ptinregion"></a>CRGN::PtIn領域

*x*と*y*で指定された点が`CRgn`、オブジェクトに格納されている領域にあるかどうかをチェックします。

```
BOOL PtInRegion(
    int x,
    int y) const;

BOOL PtInRegion(POINT point) const;
```

### <a name="parameters"></a>パラメーター

*x*<br/>
テストする点の論理 x 座標を指定します。

*Y*<br/>
テストする点の論理 y 座標を指定します。

*ポイント*<br/>
*ポイント*の x 座標と y 座標は、値をテストする点の x 座標と Y 座標を指定します。 *ポイント*パラメータは`POINT`、構造または`CPoint`オブジェクトのいずれかです。

### <a name="return-value"></a>戻り値

ポイントが領域内にある場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="crgnrectinregion"></a><a name="rectinregion"></a>CRGN::レクチン地域

*lpRect*で指定された四角形の一部が`CRgn`、オブジェクトに格納されている領域の境界内にあるかどうかを判断します。

```
BOOL RectInRegion(LPCRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
構造体または`CRect`オブジェクト`RECT`へのポイント。 構造`RECT`の形式は次のとおりです。

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>戻り値

指定された四角形の一部が領域の境界内にある場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="crgnsetrectrgn"></a><a name="setrectrgn"></a>CRgn::セットレクトルグン

四角形の領域を作成します。

```cpp
void SetRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);

void SetRectRgn(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*x1*<br/>
四角形領域の左上隅の x 座標を指定します。

*y1*<br/>
四角形領域の左上隅の y 座標を指定します。

*x2*<br/>
四角形領域の右下隅の x 座標を指定します。

*y2*<br/>
四角形領域の右下隅の y 座標を指定します。

*Lprect*<br/>
四角形の領域を指定します。 `RECT`構造体またはオブジェクトへのポインターを`CRect`指定できます。

### <a name="remarks"></a>解説

[CreateRectRgn](#createrectrgn)とは異なり、ローカル Windows アプリケーション ヒープから追加のメモリは割り当てません。 代わりに、オブジェクトに格納されている領域に割り当てられた領域`CRgn`を使用します。 つまり、オブジェクトは`CRgn`、 を呼び出す`SetRectRgn`前に有効な Windows 領域で既に初期化されている必要があります。 x1 、 *y1*、 *x2*、*および y2*で指定されるポイントは、割り当てられたスペースの最小サイズを指定します。 *y1*

ローカル メモリ マネージャの`CreateRectRgn`呼び出しを回避するには、メンバー関数の代わりにこの関数を使用します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
