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
ms.openlocfilehash: 9c08b679f1423b499a5b95b260fd0fac9ddeaf9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467981"
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
|[CRgn::CombineRgn](#combinergn)|セットを`CRgn`オブジェクトの指定した 2 つの共用体に対応できるように`CRgn`オブジェクト。|
|[CRgn::CopyRgn](#copyrgn)|セットを`CRgn`オブジェクトは、指定したコピーされるよう`CRgn`オブジェクト。|
|[CRgn::CreateEllipticRgn](#createellipticrgn)|初期化します、`CRgn`楕円の領域を持つオブジェクト。|
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|初期化します、`CRgn`によって定義される楕円の領域を持つオブジェクトを[RECT](../../mfc/reference/rect-structure1.md)構造体。|
|[CRgn::CreateFromData](#createfromdata)|指定された領域と変換データからの領域を作成します。|
|[CRgn::CreateFromPath](#createfrompath)|特定のデバイス コンテキストに選択されているパスからの領域を作成します。|
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|初期化します、`CRgn`多角形の領域を持つオブジェクト。 システム、多角形自動的に閉じます、必要に応じて、最後の頂点から最初の行を描画することで。|
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|初期化します、`CRgn`一連の閉じた多角形で構成される領域を持つオブジェクト。 多角形が不整合のある、または重なる可能性があります。|
|[CRgn::CreateRectRgn](#createrectrgn)|初期化します、`CRgn`四角形の領域を持つオブジェクト。|
|[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)|初期化します、`CRgn`によって定義される四角形の領域を持つオブジェクトを[RECT](../../mfc/reference/rect-structure1.md)構造体。|
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|初期化します、`CRgn`角の丸い四角形の領域を持つオブジェクト。|
|[CRgn::EqualRgn](#equalrgn)|2 つ`CRgn`等しいかどうかを判断するオブジェクト。|
|[CRgn::FromHandle](#fromhandle)|ポインターを返します、 `CRgn` Windows リージョンへのハンドルが指定されるとします。|
|[CRgn::GetRegionData](#getregiondata)|特定のリージョンを記述するデータを指定したバッファーに設定します。|
|[CRgn::GetRgnBox](#getrgnbox)|外接する四角形の座標を取得、`CRgn`オブジェクト。|
|[CRgn::OffsetRgn](#offsetrgn)|移動、`CRgn`指定されたオフセットでのオブジェクト。|
|[CRgn::PtInRegion](#ptinregion)|指定したポイントは、リージョンでかどうかを判断します。|
|[CRgn::RectInRegion](#rectinregion)|領域の境界内で指定した四角形の一部であるかどうかを判断します。|
|[CRgn::SetRectRgn](#setrectrgn)|セット、`CRgn`オブジェクトを指定した四角形領域。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CRgn::operator HRGN](#operator_hrgn)|含まれる Windows ハンドルを返します、`CRgn`オブジェクト。|

## <a name="remarks"></a>Remarks

リージョンは、ウィンドウ内の楕円形または多角形の領域です。 クラスのメンバー関数を使用するリージョンを使用する`CRgn`クラスのメンバーとして定義されたクリッピング関数で`CDC`します。

メンバー関数は、`CRgn`作成、変更、および呼び出される領域オブジェクトに関する情報を取得します。

使用しての詳細については`CRgn`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CRgn`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="combinergn"></a>  CRgn::CombineRgn

既存の 2 つの領域を組み合わせることで、新しい GDI の領域を作成します。

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

*nCombineMode*<br/>
2 つの領域を結合するときに実行する操作を指定します。 次の値のいずれかを指定できます。

- RGN_AND 重なり合っている (共通集合) の両方のリージョンの範囲を使用します。

- RGN_COPY リージョン 1 のコピーを作成します (で識別される*pRgn1*)。

- RGN_DIFF リージョン 1 の部分で構成される領域を作成します (で識別される*pRgn1*) リージョン 2 の一部ではない (で識別される*pRgn2*)。

- RGN_OR 全体 (union) の両方のリージョンを結合します。

- RGN_XOR は両方のリージョンの結合が、重複する領域を削除します。

### <a name="return-value"></a>戻り値

結果として得られる領域の種類を指定します。 次の値のいずれかを指定できます。

- COMPLEXREGION 新しいリージョンには、重なり合った境界線。

- 新しい領域が作成されませんとしてエラーが発生しました。

- NULLREGION 新しい領域が空です。

- SIMPLEREGION 新しい領域には、重複する境界がありません。

### <a name="remarks"></a>Remarks

領域のうちの指定に従って変換された*nCombineMode*します。

2 つのリージョンは組み合わされ、結果として得られる領域ハンドルに格納されている、`CRgn`オブジェクト。 任意のリージョンに格納されるため、`CRgn`オブジェクトは、結合された領域で置き換えられます。

領域のサイズは 32,767 で 32,767 の論理ユニットまたはメモリの 64 K に制限されていますが、小さい方です。

使用[CopyRgn](#copyrgn)単に 1 つのリージョンを別のリージョンにコピーします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]

##  <a name="copyrgn"></a>  CRgn::CopyRgn

によって定義される領域をコピー *pRgnSrc*に、`CRgn`オブジェクト。

```
int CopyRgn(CRgn* pRgnSrc);
```

### <a name="parameters"></a>パラメーター

*pRgnSrc*<br/>
既存の領域を識別します。

### <a name="return-value"></a>戻り値

結果として得られる領域の種類を指定します。 次の値のいずれかを指定できます。

- COMPLEXREGION 新しいリージョンには、重なり合った境界線。

- 新しい領域が作成されませんとしてエラーが発生しました。

- NULLREGION 新しい領域が空です。

- SIMPLEREGION 新しい領域には、重複する境界がありません。

### <a name="remarks"></a>Remarks

新しいリージョンに格納されていたリージョンの置換、`CRgn`オブジェクト。 この関数の特殊なケースは、 [CombineRgn](#combinergn)メンバー関数。

### <a name="example"></a>例

  例をご覧ください[CRgn::CreateEllipticRgn](#createellipticrgn)します。

##  <a name="createellipticrgn"></a>  CRgn::CreateEllipticRgn

楕円の領域を作成します。

```
BOOL CreateEllipticRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>パラメーター

*x1*<br/>
楕円の外接する四角形の左上隅の x の論理座標を指定します。

*y1*<br/>
楕円の外接する四角形の左上隅の y の論理座標を指定します。

*x2*<br/>
楕円の外接する四角形の右上隅の x の論理座標を指定します。

*y2*<br/>
楕円の外接する四角形の右上隅の y の論理座標を指定します。

### <a name="return-value"></a>戻り値

操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

リージョンがで指定された外接する四角形によって定義されている*x1*、 *y1*、 *x2*、および*y2*します。 リージョンが格納されている、`CRgn`オブジェクト。

領域のサイズは 32,767 で 32,767 の論理ユニットまたはメモリの 64 K に制限されていますが、小さい方です。

作成された領域の使用の終了時、`CreateEllipticRgn`関数の場合、アプリケーションは、デバイス コンテキストと使用のアウト リージョンを選択する必要があります、`DeleteObject`関数を削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]

##  <a name="createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect

楕円の領域を作成します。

```
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
指す、`RECT`構造または`CRect`楕円の外接する四角形の左上隅および右下コーナーの論理座標を格納しているオブジェクト。

### <a name="return-value"></a>戻り値

操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

構造体またはオブジェクトが指すによって領域が定義されている*lpRect*に格納されて、`CRgn`オブジェクト。

領域のサイズは 32,767 で 32,767 の論理ユニットまたはメモリの 64 K に制限されていますが、小さい方です。

作成された領域の使用の終了時、`CreateEllipticRgnIndirect`関数の場合、アプリケーションは、デバイス コンテキストと使用のアウト リージョンを選択する必要があります、`DeleteObject`関数を削除します。

### <a name="example"></a>例

  例をご覧ください[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)します。

##  <a name="createfromdata"></a>  CRgn::CreateFromData

指定された領域と変換データからの領域を作成します。

```
BOOL CreateFromData(
    const XFORM* lpXForm,
    int nCount,
    const RGNDATA* pRgnData);
```

### <a name="parameters"></a>パラメーター

*lpXForm*<br/>
指す、 [XFORM](../../mfc/reference/xform-structure.md)リージョンで実行する変換を定義するデータ構造。 このポインターが NULL の場合は、恒等変換が使用されます。

*nCount*<br/>
によって示されるバイト数を指定*pRgnData*します。

*pRgnData*<br/>
指す、 [RGNDATA](../../mfc/reference/rgndata-structure.md)地域のデータを含むデータ構造です。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションが呼び出すことによって、リージョンのデータを取得できます、`CRgn::GetRegionData`関数。

##  <a name="createfrompath"></a>  CRgn::CreateFromPath

特定のデバイス コンテキストに選択されているパスからの領域を作成します。

```
BOOL CreateFromPath(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
閉じたパスを格納しているデバイス コンテキストを識別します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

識別されるデバイス コンテキスト、 *pDC*パラメーターは、閉じたパスを含める必要があります。 後`CreateFromPath`領域、Windows をパスに変換は、デバイス コンテキストから閉じたパスを破棄します。

##  <a name="createpolygonrgn"></a>  CRgn::CreatePolygonRgn

多角形の領域を作成します。

```
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,
    int nCount,
    int nMode);
```

### <a name="parameters"></a>パラメーター

*lpPoints*<br/>
配列を指す`POINT`構造体や配列の`CPoint`オブジェクト。 各構造体には、x 座標と y 座標、多角形の頂点を 1 つの値を指定します。 `POINT`構造体は、次の形式。

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*nCount*<br/>
数を指定`POINT`構造体または`CPoint`が配列内のオブジェクトが指す*lpPoints*します。

*nMode*<br/>
領域の塗りつぶしモードを指定します。 このパラメーターには、代替またはワインディングのいずれかを指定できます。

### <a name="return-value"></a>戻り値

操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

システム、多角形自動的に閉じます、必要に応じて、最後の頂点から最初の行を描画することで。 結果として得られる領域は、`CRgn`オブジェクト。

領域のサイズは 32,767 で 32,767 の論理ユニットまたはメモリの 64 K に制限されていますが、小さい方です。

多角形の塗りつぶしモードは、代替は、システムは、各スキャン ラインに奇数し、偶数の多角形の辺の間の領域を塗りつぶします。 つまり、システムは、最初と 2 番目の側の間で、3 番目と 4 番目の側との間の領域を塗りつぶします。

多角形の塗りつぶしモードの頂点を結ぶときに、システムは、図が描いた領域を入力するかどうかを決定する方向を使用します。 多角形の場合は、各直線セグメントは、時計回りまたは反時計回りの方向で描画されます。 閉じた領域から、図の外側に描画される線が時計回りに直線セグメントを通過するたびにカウントがインクリメントされます。 行は、反時計回りの直線セグメントを通過して、ときに、カウントは減少します。 図形の外側の行に達したら、カウントが 0 以外の場合は、領域が入力されます。

アプリケーションがいつ終了したで作成されたリージョンを使用して、`CreatePolygonRgn`関数を使用して、デバイス コンテキストの領域選択されます、`DeleteObject`関数を削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]

##  <a name="createpolypolygonrgn"></a>  CRgn::CreatePolyPolygonRgn

一連の閉じた多角形で構成される領域を作成します。

```
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,
    LPINT lpPolyCounts,
    int nCount,
    int nPolyFillMode);
```

### <a name="parameters"></a>パラメーター

*lpPoints*<br/>
配列を指す`POINT`構造体や配列の`CPoint`多角形の頂点を定義するオブジェクト。 システムが閉じないに自動的にあるために、各多角形を明示的に閉じる必要があります。 多角形は連続して指定します。 `POINT`構造体は、次の形式。

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*lpPolyCounts*<br/>
整数の配列を指します。 最初の整数の最初の多角形の頂点の数を指定します、 *lpPoints* 、2 番目の整数の配列で 2 つ目の多角形の頂点の数を指定します。

*nCount*<br/>
内の整数の合計数を指定します、 *lpPolyCounts*配列。

*nPolyFillMode*<br/>
多角形の塗りつぶしモードを指定します。 この値は、代替またはワインディングのいずれかにあります。

### <a name="return-value"></a>戻り値

操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

結果として得られる領域は、`CRgn`オブジェクト。

多角形が不整合のある、または重なる可能性があります。

領域のサイズは 32,767 で 32,767 の論理ユニットまたはメモリの 64 K に制限されていますが、小さい方です。

多角形の塗りつぶしモードは、代替は、システムは、各スキャン ラインに奇数し、偶数の多角形の辺の間の領域を塗りつぶします。 つまり、システムは、最初と 2 番目の側の間で、3 番目と 4 番目の側との間の領域を塗りつぶします。

多角形の塗りつぶしモードの頂点を結ぶときに、システムは、図が描いた領域を入力するかどうかを決定する方向を使用します。 多角形の場合は、各直線セグメントは、時計回りまたは反時計回りの方向で描画されます。 閉じた領域から、図の外側に描画される線が時計回りに直線セグメントを通過するたびにカウントがインクリメントされます。 行は、反時計回りの直線セグメントを通過して、ときに、カウントは減少します。 図形の外側の行に達したら、カウントが 0 以外の場合は、領域が入力されます。

アプリケーションがいつ終了したで作成されたリージョンを使用して、`CreatePolyPolygonRgn`関数を使用して、デバイス コンテキストの領域選択されます、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数を削除します。

##  <a name="createrectrgn"></a>  CRgn::CreateRectRgn

格納されている四角形の領域を作成、`CRgn`オブジェクト。

```
BOOL CreateRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>パラメーター

*x1*<br/>
領域の左上隅の x の論理座標を指定します。

*y1*<br/>
領域の左上隅の y の論理座標を指定します。

*x2*<br/>
論理で、領域の右上隅の x 座標を指定します。

*y2*<br/>
論理で、領域の右上隅の y 座標を指定します。

### <a name="return-value"></a>戻り値

操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

領域のサイズは 32,767 で 32,767 の論理ユニットまたはメモリの 64 K に制限されていますが、小さい方です。

によって作成された領域の使用の終了時`CreateRectRgn`、アプリケーションで使用する、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)領域を削除するメンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]

たとえば、次を参照してください。 [CRgn::CombineRgn](#combinergn)します。

##  <a name="createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect

格納されている四角形の領域を作成、`CRgn`オブジェクト。

```
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
指す、`RECT`構造または`CRect`領域の左上隅および右下コーナーの論理座標を格納しているオブジェクト。 `RECT`構造体は、次の形式。

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>戻り値

操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

領域のサイズは 32,767 で 32,767 の論理ユニットまたはメモリの 64 K に制限されていますが、小さい方です。

によって作成された領域の使用の終了時`CreateRectRgnIndirect`、アプリケーションで使用する、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)領域を削除するメンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]

##  <a name="createroundrectrgn"></a>  CRgn::CreateRoundRectRgn

格納されている角の丸い四角形の領域を作成、`CRgn`オブジェクト。

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
領域の左上隅の x の論理座標を指定します。

*y1*<br/>
領域の左上隅の y の論理座標を指定します。

*x2*<br/>
論理で、領域の右上隅の x 座標を指定します。

*y2*<br/>
論理で、領域の右上隅の y 座標を指定します。

*x3*<br/>
丸い角の作成に使用される楕円の幅を指定します。

*y3*<br/>
丸い角の作成に使用される楕円の高さを指定します。

### <a name="return-value"></a>戻り値

操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

領域のサイズは 32,767 で 32,767 の論理ユニットまたはメモリの 64 K に制限されていますが、小さい方です。

アプリケーションがいつ終了したで作成されたリージョンを使用して、`CreateRoundRectRgn`関数を使用して、デバイス コンテキストの領域選択されます、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数を削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]

##  <a name="crgn"></a>  CRgn::CRgn

`CRgn` オブジェクトを構築します。

```
CRgn();
```

### <a name="remarks"></a>Remarks

`m_hObject`と他の 1 つ以上のオブジェクトが初期化されるまでデータ メンバーは、有効な Windows GDI 地域を含まない`CRgn`メンバー関数。

### <a name="example"></a>例

  例をご覧ください[CRgn::CreateRoundRectRgn](#createroundrectrgn)します。

##  <a name="equalrgn"></a>  CRgn::EqualRgn

特定のリージョンに格納されているリージョンと同じかどうか、`CRgn`オブジェクト。

```
BOOL EqualRgn(CRgn* pRgn) const;
```

### <a name="parameters"></a>パラメーター

*pRgn*<br/>
領域を識別します。

### <a name="return-value"></a>戻り値

2 つのリージョンが等しい場合は 0 以外。それ以外の場合 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]

##  <a name="fromhandle"></a>  CRgn::FromHandle

ポインターを返します、 `CRgn` Windows リージョンへのハンドルが指定されるとします。

```
static CRgn* PASCAL FromHandle(HRGN hRgn);
```

### <a name="parameters"></a>パラメーター

*hRgn*<br/>
Windows のリージョンを識別するハンドルを指定します。

### <a name="return-value"></a>戻り値

`CRgn` オブジェクトへのポインター。 関数が成功しなかった場合、戻り値は NULL です。

### <a name="remarks"></a>Remarks

場合、`CRgn`ハンドル、一時的にオブジェクトが既にアタッチされていない`CRgn`オブジェクトを作成し、接続されています。 この一時`CRgn`すべて一時的なグラフィックを時間があるオブジェクトは削除まで、次回、アプリケーションは、イベント ループでのアイドル時間は、専用、オブジェクトが無効です。 言い換えると、別の方法は、1 つのウィンドウ メッセージを処理中に一時オブジェクトが有効でのみことです。

##  <a name="getregiondata"></a>  CRgn::GetRegionData

指定されたバッファー領域を記述するデータを設定します。

```
int GetRegionData(
    LPRGNDATA lpRgnData,
    int nCount) const;
```

### <a name="parameters"></a>パラメーター

*lpRgnData*<br/>
指す、 [RGNDATA](../../mfc/reference/rgndata-structure.md)情報を受信するデータ構造体。 このパラメーターが NULL の場合、戻り値には、地域のデータに必要なバイト数が含まれています。

*nCount*<br/>
サイズ (バイト単位) を指定します、 *lpRgnData*バッファー。

### <a name="return-value"></a>戻り値

関数が成功した場合と*nCount*十分な数を指定します (バイト単位) の戻り値は常に、 *nCount*します。 関数が失敗した場合、または場合*nCount*以下を指定します (バイト) の適切な数よりも、戻り値には 0 (エラー)。

### <a name="remarks"></a>Remarks

このデータには、リージョンを構成する四角形の大きさが含まれています。 この関数は組み合わせて使用、`CRgn::CreateFromData`関数。

##  <a name="getrgnbox"></a>  CRgn::GetRgnBox

外接する四角形の座標を取得、`CRgn`オブジェクト。

```
int GetRgnBox(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
指す、`RECT`構造または`CRect`外接する四角形の座標を受け取るオブジェクト。 `RECT`構造体は、次の形式。

`typedef struct tagRECT {`

`int left;`

`int top;`

`int right;`

`int bottom;`

`} RECT;`

### <a name="return-value"></a>戻り値

領域の種類を指定します。 次の値のいずれかを指定できます。

- COMPLEXREGION リージョンは、重なり合った境界線。

- NULLREGION リージョンが空です。

- エラー`CRgn`オブジェクトが有効なリージョンを指定しません。

- SIMPLEREGION 領域には、重複する境界がありません。

### <a name="example"></a>例

  例をご覧ください[CRgn::CreatePolygonRgn](#createpolygonrgn)します。

##  <a name="offsetrgn"></a>  CRgn::OffsetRgn

格納されているリージョンを移動、`CRgn`指定されたオフセットでのオブジェクト。

```
int OffsetRgn(
    int x,
    int y);

int OffsetRgn(POINT point);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
左に移動する単位数を指定します。

*y*<br/>
上下に移動するユニット数を指定します。

*ポイント*<br/>
X 座標*ポイント*左に移動する単位数を指定します。 Y 座標*ポイント*を上下に移動する単位の数を指定します。 *ポイント*パラメーターには、いずれかを指定できます、`POINT`構造または`CPoint`オブジェクト。

### <a name="return-value"></a>戻り値

新しい領域の種類。 次の値のいずれかを指定できます。

- COMPLEXREGION リージョンは、重なり合った境界線。

- エラー領域ハンドルが無効です。

- NULLREGION リージョンが空です。

- SIMPLEREGION 領域には、重複する境界がありません。

### <a name="remarks"></a>Remarks

関数は、リージョンを移動*x* x 軸に沿った単位と*y* y 軸に沿った単位。

領域の座標の値は、32,767 を超えるや-32,768 と等しく以下である必要があります。 *X*と*y*パラメーターは無効な領域の座標値を防ぐために慎重に選択する必要があります。

### <a name="example"></a>例

  例をご覧ください[CRgn::CreateEllipticRgn](#createellipticrgn)します。

##  <a name="operator_hrgn"></a>  CRgn::operator HRGN

接続されている Windows GDI ハンドルを取得するこの演算子を使用して、`CRgn`オブジェクト。

```
operator HRGN() const;
```

### <a name="return-value"></a>戻り値

かどうかは成功すると、Windows GDI オブジェクトを識別するハンドルで表される、`CRgn`オブジェクト。 それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

この演算子は、キャスト演算子です。

グラフィック オブジェクトの使用に関する詳細については、記事を参照してください。[グラフィック オブジェクト](/windows/desktop/gdi/graphic-objects)Windows SDK に含まれています。

##  <a name="ptinregion"></a>  CRgn::PtInRegion

チェックかどうかで指定したポイント*x*と*y*に格納されているリージョンでは、`CRgn`オブジェクト。

```
BOOL PtInRegion(
    int x,
    int y) const;

BOOL PtInRegion(POINT point) const;
```

### <a name="parameters"></a>パラメーター

*x*<br/>
論理でテストする点の x 座標を指定します。

*y*<br/>
論理でテストする点の y 座標を指定します。

*ポイント*<br/>
X 座標と y 座標*ポイント*の値をテストする点の x 座標と y 座標を指定します。 *ポイント*パラメーターにすることができますか、`POINT`構造または`CPoint`オブジェクト。

### <a name="return-value"></a>戻り値

0 以外の場合、リージョンとは、ポイントがある場合それ以外の場合 0 を返します。

##  <a name="rectinregion"></a>  CRgn::RectInRegion

四角形の一部がで指定されたかどうかを判断します*lpRect*に格納されている領域の境界内では、`CRgn`オブジェクト。

```
BOOL RectInRegion(LPCRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
指す、`RECT`構造または`CRect`オブジェクト。 `RECT`構造体は、次の形式。

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>戻り値

指定した四角形の任意の部分は、領域の境界内にある場合、0 以外。それ以外の場合 0 を返します。

##  <a name="setrectrgn"></a>  CRgn::SetRectRgn

四角形の領域を作成します。

```
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
四角形領域の右上隅の x 座標を指定します。

*y2*<br/>
四角形領域の右上隅の y 座標を指定します。

*lpRect*<br/>
四角形の領域を指定します。 ポインターにすることができます、`RECT`構造または`CRect`オブジェクト。

### <a name="remarks"></a>Remarks

異なり[CreateRectRgn](#createrectrgn)、ただし、これはメモリの割り当て追加、ローカルの Windows アプリケーションのヒープからです。 格納されているリージョンに割り当てられた領域を使用して、代わりに、`CRgn`オブジェクト。 つまり、`CRgn`オブジェクト既に初期化されていなければなりませんを呼び出す前に有効な Windows 領域`SetRectRgn`します。 指定されたポイント*x1*、 *y1*、 *x2*、および*y2*に割り当てられた領域の最小サイズを指定します。

代わりに、この関数を使用して、`CreateRectRgn`メンバー関数は、ローカル メモリ マネージャーへの呼び出しを回避するためにします。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)

