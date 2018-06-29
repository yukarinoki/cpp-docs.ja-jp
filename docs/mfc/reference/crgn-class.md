---
title: CRgn クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1d61049c4c5af0285d728685776b2f285f69ba4
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079604"
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
|[CRgn::CombineRgn](#combinergn)|セット、`CRgn`オブジェクトの指定した 2 つの和集合と等価であるように`CRgn`オブジェクト。|  
|[CRgn::CopyRgn](#copyrgn)|セット、`CRgn`オブジェクトは、指定されたのコピーを`CRgn`オブジェクト。|  
|[CRgn::CreateEllipticRgn](#createellipticrgn)|初期化、`CRgn`楕円の領域を持つオブジェクト。|  
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|初期化、`CRgn`によって定義される楕円の領域を持つオブジェクト、 [RECT](../../mfc/reference/rect-structure1.md)構造体。|  
|[CRgn::CreateFromData](#createfromdata)|指定された領域と変換のデータから領域を作成します。|  
|[CRgn::CreateFromPath](#createfrompath)|指定されたデバイス コンテキストに選択されているパスからの領域を作成します。|  
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|初期化、`CRgn`多角形の領域を持つオブジェクト。 システム多角形が自動的に終了、必要に応じて、最初最後の頂点から線が描画します。|  
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|初期化、`CRgn`閉じた多角形の系列で構成される領域を持つオブジェクト。 多角形、不整合のあるか、重なる可能性があります。|  
|[CRgn::CreateRectRgn](#createrectrgn)|初期化、`CRgn`四角形の領域を持つオブジェクト。|  
|[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)|初期化、`CRgn`で定義された四角形の領域を持つオブジェクト、 [RECT](../../mfc/reference/rect-structure1.md)構造体。|  
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|初期化、`CRgn`角の丸い四角形の領域を持つオブジェクト。|  
|[CRgn::EqualRgn](#equalrgn)|2 つ`CRgn`それらが等しいかどうかを決定するオブジェクト。|  
|[CRgn::FromHandle](#fromhandle)|ポインターを返します、 `CRgn` Windows 領域へのハンドルが指定されるとします。|  
|[CRgn::GetRegionData](#getregiondata)|指定された領域を記述するデータを指定したバッファーに設定します。|  
|[CRgn::GetRgnBox](#getrgnbox)|外接する四角形の座標を取得、`CRgn`オブジェクト。|  
|[CRgn::OffsetRgn](#offsetrgn)|移動、`CRgn`指定されたオフセットでのオブジェクト。|  
|[CRgn::PtInRegion](#ptinregion)|指定したポイントが領域内にあるかどうかを判断します。|  
|[CRgn::RectInRegion](#rectinregion)|指定した四角形の任意の部分が領域の境界内にあるかどうかを判断します。|  
|[CRgn::SetRectRgn](#setrectrgn)|セット、`CRgn`オブジェクトを指定した四角形領域です。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CRgn::operator HRGN](#operator_hrgn)|含まれる Windows ハンドルを返します、`CRgn`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 領域は、ウィンドウ内で楕円形または多角形領域です。 クラスのメンバー関数を使用する領域を使用する`CRgn`クラスのメンバーとして定義されているクリッピング関数と`CDC`です。  
  
 メンバー関数は、`CRgn`作成、変更、およびが呼び出された対象の領域オブジェクトに関する情報を取得します。  
  
 使用する方法についての`CRgn`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CRgn`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="combinergn"></a>  CRgn::CombineRgn  
 既存の 2 つの領域を組み合わせることによって、新しい GDI 領域を作成します。  
  
```  
int CombineRgn(
    CRgn* pRgn1,  
    CRgn* pRgn2,  
    int nCombineMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRgn1*  
 既存の領域を識別します。  
  
 *pRgn2*  
 既存の領域を識別します。  
  
 *nCombineMode*  
 2 つの領域を結合するときに実行する操作を指定します。 次の値のいずれかを指定できます。  
  
- **RGN_AND** (共通集合) の両方の地域の重なり合う領域を使用します。  
  
- **RGN_COPY**地域 1 のコピーを作成 (で識別される*pRgn1*)。  
  
- **RGN_DIFF**領域 1 の部分から成る領域を作成する (で識別される*pRgn1*) 領域 2 の一部ではないこと (で識別される*pRgn2*)。  
  
- **RGN_OR**全体 (union) の両方の領域を結合します。  
  
- **RGN_XOR**両方の地域の結合が、重なり合う領域を削除します。  
  
### <a name="return-value"></a>戻り値  
 結果として得られる領域の種類を指定します。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**新しい領域が重なり合う境界線です。  
  
- **エラー**新しい領域は作成します。  
  
- **NULLREGION**新しい領域が空です。  
  
- **SIMPLEREGION**新しい領域には、重複する境界がありません。  
  
### <a name="remarks"></a>Remarks  
 領域を結合の指定に従って*nCombineMode*です。  
  
 2 つの指定された領域は結合に結果として得られる領域ハンドルが格納されている、`CRgn`オブジェクト。 どのような領域が格納されるため、`CRgn`オブジェクトは、結合された領域に置換します。  
  
 領域のサイズは、32,767 で 32,767 の論理ユニットまたは 64 K のメモリに制限されます、小さい方です。  
  
 使用して[CopyRgn](#copyrgn)単に 1 つの領域を別の領域にコピーします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]  
  
##  <a name="copyrgn"></a>  CRgn::CopyRgn  
 によって定義される領域をコピー *pRgnSrc*に、`CRgn`オブジェクト。  
  
```  
int CopyRgn(CRgn* pRgnSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRgnSrc*  
 既存の領域を識別します。  
  
### <a name="return-value"></a>戻り値  
 結果として得られる領域の種類を指定します。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**新しい領域が重なり合う境界線です。  
  
- **エラー**新しい領域は作成します。  
  
- **NULLREGION**新しい領域が空です。  
  
- **SIMPLEREGION**新しい領域には、重複する境界がありません。  
  
### <a name="remarks"></a>Remarks  
 新しい領域が以前に格納されている領域を置き換えます、`CRgn`オブジェクト。 この関数は、の特殊なケース、 [CombineRgn](#combinergn)メンバー関数。  
  
### <a name="example"></a>例  
  例を参照して[CRgn::CreateEllipticRgn](#createellipticrgn)です。  
  
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
 *x1*  
 論理で楕円の外接する四角形の左上隅の x 座標を指定します。  
  
 *y1*  
 論理で楕円の外接する四角形の左上隅の y 座標を指定します。  
  
 *x2*  
 論理で楕円の外接する四角形の右下隅の x 座標を指定します。  
  
 *y2*  
 論理で楕円の外接する四角形の右下隅の y 座標を指定します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 領域がで指定された外接する四角形によって定義された*x1*、 *y1*、 *x2*、および*y2*です。 地域が格納されている、`CRgn`オブジェクト。  
  
 領域のサイズは、32,767 で 32,767 の論理ユニットまたは 64 K のメモリに制限されます、小さい方です。  
  
 これが終了した場合に作成された領域を使用して、`CreateEllipticRgn`関数、アプリケーションはデバイス コンテキストおよび使用のアウト地域を選択する必要があります、`DeleteObject`関数を削除します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]  
  
##  <a name="createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect  
 楕円の領域を作成します。  
  
```  
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRect*  
 指す、`RECT`構造体、または`CRect`楕円の外接する四角形の左上隅および右下コーナーの論理座標を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 地域が構造体またはによって指されるオブジェクトによって定義された*lpRect*に格納されて、`CRgn`オブジェクト。  
  
 領域のサイズは、32,767 で 32,767 の論理ユニットまたは 64 K のメモリに制限されます、小さい方です。  
  
 これが終了した場合に作成された領域を使用して、`CreateEllipticRgnIndirect`関数、アプリケーションはデバイス コンテキストおよび使用のアウト地域を選択する必要があります、`DeleteObject`関数を削除します。  
  
### <a name="example"></a>例  
  例を参照して[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)です。  
  
##  <a name="createfromdata"></a>  CRgn::CreateFromData  
 指定された領域と変換のデータから領域を作成します。  
  
```  
BOOL CreateFromData(
    const XFORM* lpXForm,  
    int nCount,  
    const RGNDATA* pRgnData);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpXForm*  
 指す、 [XFORM](../../mfc/reference/xform-structure.md)領域上で実行される変換を定義するデータ構造体。 このポインターがある場合**NULL**、identity 変換を使用します。  
  
 *nCount*  
 によって示されるバイト数を指定*pRgnData*です。  
  
 *pRgnData*  
 指す、 [RGNDATA](../../mfc/reference/rgndata-structure.md)地域のデータを格納するデータ構造です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションが呼び出すことによって、地域のデータを取得できます、`CRgn::GetRegionData`関数。  
  
##  <a name="createfrompath"></a>  CRgn::CreateFromPath  
 指定されたデバイス コンテキストに選択されているパスからの領域を作成します。  
  
```  
BOOL CreateFromPath(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDC*  
 閉じられたパスを格納しているデバイス コンテキストを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 デバイス コンテキストで識別される、 *pDC*パラメーターが閉じられたパスを含める必要があります。 後に`CreateFromPath`領域、Windows をパスに変換は、デバイス コンテキストから閉じたパスを破棄します。  
  
##  <a name="createpolygonrgn"></a>  CRgn::CreatePolygonRgn  
 多角形の領域を作成します。  
  
```  
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,  
    int nCount,  
    int nMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpPoints*  
 配列を指す**ポイント**構造体や配列の`CPoint`オブジェクト。 X 座標と y 座標の多角形の 1 つの頂点の各構造体を指定します。 **ポイント**構造体には、次の形式。  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 *nCount*  
 数を指定**ポイント**構造体または`CPoint`配列内のオブジェクトを指す*lpPoints*です。  
  
 *nMode*  
 領域の塗りつぶしモードを指定します。 このパラメーターには、いずれかを指定できます**代替**または**ワインディング**です。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 システム多角形が自動的に終了、必要に応じて、最初最後の頂点から線が描画します。 作成された領域が格納されている、`CRgn`オブジェクト。  
  
 領域のサイズは、32,767 で 32,767 の論理ユニットまたは 64 K のメモリに制限されます、小さい方です。  
  
 多角形の塗りつぶしモードのときは**代替**システムが各スキャン ラインに奇数し、偶数の多角形の辺の間の領域を塗りつぶします。 つまり、システムは、最初と 2 番目の側の間で、3 番目と 4 番目の側との間の領域を塗りつぶします。  
  
 多角形の塗りつぶしモードのときは**ワインディング**システムは、図が描いた領域を入力するかどうかを決定する方向を使用します。 多角形の場合は、各直線セグメントは、時計回りまたは反時計回りに描画されます。 囲まれた領域から、図の外側に描画虚数部の行が時計回りに直線セグメントを通過するたびに、カウントが増加します。 行は、反時計回りの線分を通過、ときに、カウントがデクリメントします。 行が、図の外側に達すると、カウントが 0 でない場合、領域を塗りつぶします。  
  
 アプリケーションが終了した場合に作成された領域を使用して、`CreatePolygonRgn`関数を使用して、デバイス コンテキストのアウト リージョンを選択にする必要があります、`DeleteObject`関数を削除します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]  
  
##  <a name="createpolypolygonrgn"></a>  CRgn::CreatePolyPolygonRgn  
 閉じた多角形の系列で構成される領域を作成します。  
  
```  
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,  
    LPINT lpPolyCounts,  
    int nCount,  
    int nPolyFillMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpPoints*  
 配列を指す**ポイント**構造体や配列の`CPoint`多角形の頂点を定義するオブジェクト。 システムは閉じませんに自動的にあるために、各多角形を明示的に閉じる必要があります。 多角形が連続的に指定します。 **ポイント**構造体には、次の形式。  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 *lpPolyCounts*  
 整数の配列を指します。 最初の整数は、最初の多角形の頂点の数を指定、 *lpPoints* 2 番目の整数の配列が 2 番目の多角形で頂点の数を指定します。  
  
 *nCount*  
 で整数の合計数を指定、 *lpPolyCounts*配列。  
  
 *nPolyFillMode*  
 多角形の塗りつぶしモードを指定します。 この値は、いずれかの**代替**または**ワインディング**です。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 作成された領域が格納されている、`CRgn`オブジェクト。  
  
 多角形、不整合のあるか、重なる可能性があります。  
  
 領域のサイズは、32,767 で 32,767 の論理ユニットまたは 64 K のメモリに制限されます、小さい方です。  
  
 多角形の塗りつぶしモードのときは**代替**システムが各スキャン ラインに奇数し、偶数の多角形の辺の間の領域を塗りつぶします。 つまり、システムは、最初と 2 番目の側の間で、3 番目と 4 番目の側との間の領域を塗りつぶします。  
  
 多角形の塗りつぶしモードのときは**ワインディング**システムは、図が描いた領域を入力するかどうかを決定する方向を使用します。 多角形の場合は、各直線セグメントは、時計回りまたは反時計回りに描画されます。 囲まれた領域から、図の外側に描画虚数部の行が時計回りに直線セグメントを通過するたびに、カウントが増加します。 行は、反時計回りの線分を通過、ときに、カウントがデクリメントします。 行が、図の外側に達すると、カウントが 0 でない場合、領域を塗りつぶします。  
  
 アプリケーションが終了した場合に作成された領域を使用して、`CreatePolyPolygonRgn`関数を使用して、デバイス コンテキストのアウト リージョンを選択にする必要があります、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数を削除します。  
  
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
 *x1*  
 論理で領域の左上隅の x 座標を指定します。  
  
 *y1*  
 論理で領域の左上隅の y 座標を指定します。  
  
 *x2*  
 論理で領域の右下隅の x 座標を指定します。  
  
 *y2*  
 論理で領域の右下隅の y 座標を指定します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 領域のサイズは、32,767 で 32,767 の論理ユニットまたは 64 K のメモリに制限されます、小さい方です。  
  
 によって作成された領域の使用の終了時`CreateRectRgn`、アプリケーションを使用する必要があります、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)領域を削除するメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]  
  
 たとえば、次を参照してください。 [CRgn::CombineRgn](#combinergn)です。  
  
##  <a name="createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect  
 格納されている四角形の領域を作成、`CRgn`オブジェクト。  
  
```  
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRect*  
 指す、`RECT`構造または`CRect`領域の左上隅および右下コーナーの論理座標を格納しているオブジェクト。 `RECT`構造体には、次の形式。  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 領域のサイズは、32,767 で 32,767 の論理ユニットまたは 64 K のメモリに制限されます、小さい方です。  
  
 によって作成された領域の使用の終了時`CreateRectRgnIndirect`、アプリケーションを使用する必要があります、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)領域を削除するメンバー関数。  
  
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
 *x1*  
 論理で領域の左上隅の x 座標を指定します。  
  
 *y1*  
 論理で領域の左上隅の y 座標を指定します。  
  
 *x2*  
 論理で領域の右下隅の x 座標を指定します。  
  
 *y2*  
 論理で領域の右下隅の y 座標を指定します。  
  
 *x3*  
 丸い角を作成するために使用する省略記号の幅を指定します。  
  
 *y3*  
 丸い角を作成するために使用する省略記号の高さを指定します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 領域のサイズは、32,767 で 32,767 の論理ユニットまたは 64 K のメモリに制限されます、小さい方です。  
  
 アプリケーションが終了した場合に作成された領域を使用して、`CreateRoundRectRgn`関数を使用して、デバイス コンテキストのアウト リージョンを選択にする必要があります、 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数を削除します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]  
  
##  <a name="crgn"></a>  CRgn::CRgn  
 `CRgn` オブジェクトを構築します。  
  
```  
CRgn();
```  
  
### <a name="remarks"></a>Remarks  
 `m_hObject`データ メンバーを含まない有効な Windows GDI 領域とその他の 1 つ以上のオブジェクトが初期化されるまで`CRgn`メンバー関数。  
  
### <a name="example"></a>例  
  例を参照して[CRgn::CreateRoundRectRgn](#createroundrectrgn)です。  
  
##  <a name="equalrgn"></a>  CRgn::EqualRgn  
 指定された領域に格納されている領域に相当するかどうかを判断、`CRgn`オブジェクト。  
  
```  
BOOL EqualRgn(CRgn* pRgn) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pRgn*  
 領域を識別します。  
  
### <a name="return-value"></a>戻り値  
 2 つの領域が等しい場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]  
  
##  <a name="fromhandle"></a>  CRgn::FromHandle  
 ポインターを返します、 `CRgn` Windows 領域へのハンドルが指定されるとします。  
  
```  
static CRgn* PASCAL FromHandle(HRGN hRgn);
```  
  
### <a name="parameters"></a>パラメーター  
 *hRgn*  
 Windows の領域へのハンドルを指定します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CRgn`オブジェクト。 関数が成功しなかった場合、戻り値は**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 場合、`CRgn`オブジェクトが、一時的なハンドルに既にアタッチされていない`CRgn`オブジェクトが作成され、接続されています。 この一時`CRgn`オブジェクトが有効では、次回アプリケーションがある移動するまでのアイドル時間イベント ループで、すべて一時的なグラフィックを時間でオブジェクトが削除専用です。 言い換えると、別の方法は、1 つのウィンドウ メッセージを処理中に、一時オブジェクトが有効でのみことです。  
  
##  <a name="getregiondata"></a>  CRgn::GetRegionData  
 領域を記述するデータを指定したバッファーに設定します。  
  
```  
int GetRegionData(
    LPRGNDATA lpRgnData,  
    int nCount) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRgnData*  
 指す、 [RGNDATA](../../mfc/reference/rgndata-structure.md)情報を受信するデータ構造です。 このパラメーターが場合**NULL**、戻り値には地域のデータに必要なバイト数が含まれています。  
  
 *nCount*  
 サイズ (バイト単位) を指定、 *lpRgnData*バッファー。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合と*nCount*十分な数を指定します (バイト単位) の戻り値は常に*nCount*です。 関数が失敗した場合、または場合*nCount*未満を示すバイトの十分な数よりも、戻り値は 0 (エラー)。  
  
### <a name="remarks"></a>Remarks  
 このデータには、領域を構成する四角形のディメンションが含まれています。 この関数を組み合わせて使用、`CRgn::CreateFromData`関数。  
  
##  <a name="getrgnbox"></a>  CRgn::GetRgnBox  
 外接する四角形の座標を取得、`CRgn`オブジェクト。  
  
```  
int GetRgnBox(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRect*  
 指す、`RECT`構造または`CRect`外接する四角形の座標を受け取るオブジェクト。 `RECT`構造体には、次の形式。  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>戻り値  
 領域の種類を指定します。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**境界が重複領域には、します。  
  
- **NULLREGION**領域が空です。  
  
- **エラー** `CRgn`オブジェクトが有効な領域が指定されていません。  
  
- **SIMPLEREGION**領域に重複する境界がありません。  
  
### <a name="example"></a>例  
  例を参照して[CRgn::CreatePolygonRgn](#createpolygonrgn)です。  
  
##  <a name="offsetrgn"></a>  CRgn::OffsetRgn  
 格納されている領域を移動、`CRgn`指定されたオフセットでのオブジェクト。  
  
```  
int OffsetRgn(
    int x,  
    int y);  
  
int OffsetRgn(POINT point);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左に移動する単位数を指定します。  
  
 *y*  
 上下に移動する単位の数を指定します。  
  
 *ポイント*  
 X 座標*ポイント*左に移動する単位の数を指定します。 Y 座標*ポイント*を上下に移動する単位の数を指定します。 *ポイント*パラメーターには、いずれかを指定できます、**ポイント**構造体、または`CPoint`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 新しい領域の種類。 次の値のいずれかを指定できます。  
  
- **COMPLEXREGION**境界が重複領域には、します。  
  
- **エラー**領域ハンドルは無効です。  
  
- **NULLREGION**領域が空です。  
  
- **SIMPLEREGION**領域に重複する境界がありません。  
  
### <a name="remarks"></a>Remarks  
 関数は、領域を移動*x* x 軸に単位と*y* y 軸に沿って単位です。  
  
 領域の座標の値は、32,767 および以上-32,768 を以下にする必要があります。 *X*と*y*パラメーターが無効な領域の座標値を防ぐために慎重に選択する必要があります。  
  
### <a name="example"></a>例  
  例を参照して[CRgn::CreateEllipticRgn](#createellipticrgn)です。  
  
##  <a name="operator_hrgn"></a>  CRgn::operator HRGN  
 この演算子のアタッチされた Windows GDI ハンドルの取得を使用して、`CRgn`オブジェクト。  
  
```  
operator HRGN() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、Windows GDI オブジェクトへのハンドルによって表される、`CRgn`オブジェクト。 それ以外の場合**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 この演算子はキャスト演算子の**HRGN**オブジェクト。  
  
 グラフィック オブジェクトの使用に関する詳細については、記事を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)Windows SDK に含まれています。  
  
##  <a name="ptinregion"></a>  CRgn::PtInRegion  
 チェックするかどうかで指定したポイント*x*と*y*に格納されている地域では、`CRgn`オブジェクト。  
  
```  
BOOL PtInRegion(
    int x,  
    int y) const;  
  
BOOL PtInRegion(POINT point) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 論理でテストする点の x 座標を指定します。  
  
 *y*  
 論理でテストする点の y 座標を指定します。  
  
 *ポイント*  
 X 座標と y 座標*ポイント*の値をテストする点の x 座標と y 座標を指定します。 *ポイント*パラメーターを指定できますか、**ポイント**構造体、または`CPoint`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポイントが、領域の場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="rectinregion"></a>  CRgn::RectInRegion  
 四角形の任意の部分が指定したかどうかを判定*lpRect*に格納されている領域の境界内にある、`CRgn`オブジェクト。  
  
```  
BOOL RectInRegion(LPCRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRect*  
 指す、`RECT`構造または`CRect`オブジェクト。 `RECT`構造体には、次の形式。  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>戻り値  
 指定した四角形の任意の部分が、領域の境界内に存在する場合は 0 以外。それ以外の場合 0 を返します。  
  
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
 *x1*  
 四角形領域の左上隅の x 座標を指定します。  
  
 *y1*  
 四角形領域の左上隅の y 座標を指定します。  
  
 *x2*  
 四角形領域の右下隅の x 座標を指定します。  
  
 *y2*  
 四角形領域の右下隅の y 座標を指定します。  
  
 *lpRect*  
 四角形の領域を指定します。 ポインターにすることができます、`RECT`構造体、または`CRect`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 異なり[CreateRectRgn](#createrectrgn)、ただし、これは割り当てません追加のメモリが、ローカルの Windows アプリケーション ヒープからです。 代わりに格納されている領域に割り当てられた領域を使用して、`CRgn`オブジェクト。 つまり、`CRgn`オブジェクト既に初期化されていなければなりませんを呼び出す前に有効な Windows 領域`SetRectRgn`です。 によって指定されたポイント*x1*、 *y1*、 *x2*、および*y2*割り当てられた領域の最小サイズを指定します。  
  
 代わりにこの関数を使用して、`CreateRectRgn`ローカル メモリ マネージャーへの呼び出しを避けるためにメンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



