---
title: CPoint クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29f487f77fac6c3f6def51b69715d1d47257dd7c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374224"
---
# <a name="cpoint-class"></a>CPoint クラス

Windows の `POINT` 構造体と同様のものです。

## <a name="syntax"></a>構文

```
class CPoint : public tagPOINT 
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CPoint::CPoint](#cpoint)|`CPoint` を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPoint::Offset](#offset)|値が追加され、`x`と`y`のメンバー、`CPoint`します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CPoint::operator-](#operator_-)|差を返します、`CPoint`とサイズ、またはポイント、または 2 つのポイント、または負のサイズのオフセットの差をサイズの符号を反転します。|
|[CPoint::operator! =](#operator_neq)|2 つのポイント間の不等性を確認します。|
|[CPoint::operator +](#operator_add)|合計を返して、`CPoint`とサイズ、またはポイント、または`CRect`サイズでオフセットします。|
|[CPoint::operator + =](#operator_add_eq)|オフセット`CPoint`サイズまたはポイントを追加します。|
|[CPoint::operator =](#operator_-_eq)|オフセット`CPoint`サイズまたはポイントを差し引くことで。|
|[CPoint::operator = =](#operator_eq_eq)|2 つのポイント間で等しいかどうかを確認します。|

## <a name="remarks"></a>Remarks

操作するメンバー関数も含まれています。`CPoint`と[ポイント](../../mfc/reference/point-structure1.md)構造体。

A`CPoint`オブジェクトは任意の場所を使用、`POINT`構造体を使用します。 「サイズ」と対話するこのクラスの演算子は、両方を受け付ける[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトまたは[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)、構造体の 2 つは交換可能であるためです。

> [!NOTE]
>  このクラスから派生、`tagPOINT`構造体。 (名前`tagPOINT`の使用頻度の低い名には、`POINT`構造です)。つまりのデータ メンバー、`POINT`構造体、`x`と`y`のアクセス可能なデータ メンバーである`CPoint`します。

> [!NOTE]
>  詳細については、共有ユーティリティ クラス (など`CPoint`) を参照してください[共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`tagPOINT`

`CPoint`

## <a name="requirements"></a>要件

**ヘッダー:** atltypes.h

##  <a name="cpoint"></a>  CPoint::CPoint

`CPoint` オブジェクトを構築します。

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>パラメーター

*initX*  
`x` の `CPoint` メンバーの値を指定します。

*initY*  
`y` の `CPoint` メンバーの値を指定します。

*initPt*  
[ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`初期化するために使用される値を指定する`CPoint`します。

*initSize*  
[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)初期化するために使用される値を指定する`CPoint`します。

*dwPoint*  
セット、`x`メンバーの下位ワードを*dwPoint*と`y`メンバーの上位ワードを*dwPoint*します。

### <a name="remarks"></a>Remarks

引数を指定しない場合、`x` メンバーおよび `y` メンバーは 0 に設定されます。

### <a name="example"></a>例

```cpp   
CPoint   ptTopLeft(0, 0); 
// works from a POINT, too

POINT   ptHere;  
ptHere.x = 35;  
ptHere.y = 95;

CPoint   ptMFCHere(ptHere);

// works from a SIZE 
SIZE   sHowBig;  
sHowBig.cx = 300;  
sHowBig.cy = 10;

CPoint ptMFCBig(sHowBig); 
// or from a DWORD

DWORD   dwSize;  
dwSize = MAKELONG(35, 95);

CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```

##  <a name="offset"></a>  CPoint::Offset

値が追加され、`x`と`y`のメンバー、`CPoint`します。

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>パラメーター

*x オフセット*  
オフセットする量を指定します、`x`のメンバー、`CPoint`します。

*y オフセット*  
オフセットする量を指定します、`y`のメンバー、`CPoint`します。

*ポイント*  
量を指定します ([ポイント](../../mfc/reference/point-structure1.md)または`CPoint`) オフセット、`CPoint`します。

*size*  
量を指定します ([サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)または[CSize](../../atl-mfc-shared/reference/csize-class.md)) オフセット、`CPoint`します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

##  <a name="operator_eq_eq"></a>  CPoint::operator = =

2 つのポイント間で等しいかどうかを確認します。

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*  
含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`オブジェクト。

### <a name="return-value"></a>戻り値

ポイントが等しい場合は 0 以外。それ以外の場合 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

##  <a name="operator_neq"></a>  CPoint::operator! =

2 つのポイント間の不等性を確認します。

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*  
含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`オブジェクト。

### <a name="return-value"></a>戻り値

点が等しくない場合は 0 以外それ以外の場合 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

##  <a name="operator_add_eq"></a>  CPoint::operator + =

最初のオーバー ロードを追加するサイズ、`CPoint`します。

```
void operator+=(SIZE size) throw(); 
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>パラメーター

*size*  
含まれています、[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

*ポイント*  
含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

2 番目のオーバー ロードするポイントを追加します、`CPoint`します。

どちらの場合も、追加することで加算を実行、 `x` (または`cx`) 右側のオペランドのメンバー、`x`のメンバー、`CPoint`を追加して、 `y` (または`cy`) 右側のオペランドのメンバー、`y`のメンバー、`CPoint`します。

たとえば、追加`CPoint(5, -7)`を含む変数を`CPoint(30, 40)`に変数を変更`CPoint(35, 33)`。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

##  <a name="operator_-_eq"></a>  CPoint::operator =

最初のオーバー ロードからサイズを減算する、`CPoint`します。

```
void operator-=(SIZE size) throw(); 
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>パラメーター

*size*  
含まれています、[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

*ポイント*  
含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

2 番目のオーバー ロードからポイントを減算する、`CPoint`します。

どちらの場合も、減算することで減算を実行、 `x` (または`cx`) から右のオペランドのメンバー、`x`のメンバー、`CPoint`引いて、 `y` (または`cy`)、右側のメンバーオペランド、`y`のメンバー、`CPoint`します。

たとえば、減算`CPoint(5, -7)`を含む変数から`CPoint(30, 40)`に変数を変更`CPoint(25, 47)`します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

##  <a name="operator_add"></a>  CPoint::operator +

この演算子を使用して、短縮する`CPoint`によって、`CPoint`または`CSize`オブジェクト、またはオフセット、`CRect`によって、 `CPoint`。

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>パラメーター

*size*  
含まれています、[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

*ポイント*  
含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

*lpRect*  
ポインターが含まれています、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

A`CPoint`サイズでのオフセットを`CPoint`段階では、オフセットまたは`CRect`ポイントによってオフセットします。

### <a name="remarks"></a>Remarks

たとえば、最初の 2 つのオーバー ロードのいずれかの点をオフセットするを使用して`CPoint(25, -19)`ポイントによって`CPoint(15, 5)`サイズまたは`CSize(15, 5)`値を返します`CPoint(40, -14)`します。

後で相殺される四角形を返しますポイントに四角形の追加、`x`と`y`ポイントで指定された値。 たとえば、四角形をオフセットする最後のオーバー ロードを使用して`CRect(125, 219, 325, 419)`ポイントによって`CPoint(25, -19)`返します`CRect(150, 200, 350, 400)`します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

##  <a name="operator_-"></a>  CPoint::operator-

減算する最初の 2 つのオーバー ロードのいずれかを使用して、`CPoint`または`CSize`オブジェクトから`CPoint`します。

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*  
A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

*size*  
A[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

*lpRect*  
ポインターを[RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

A `CSize` 2 つのポイント間の違いは、`CPoint`オフセット、サイズの符号を反転して、 `CRect` 、ポイントの否定でのオフセットまたは`CPoint`ポイントの否定は。

### <a name="remarks"></a>Remarks

3 番目のオーバー ロードのオフセットを`CRect`の否定で`CPoint`します。 最後に、否定する単項演算子を使用して`CPoint`します。

たとえば、最初のオーバー ロードを使用して、2 つの点の差を求める`CPoint(25, -19)`と`CPoint(15, 5)`返します`CSize(10, -24)`します。

減算、`CSize`から`CPoint`は上記と同じ計算が返されます、`CPoint`オブジェクトは、`CSize`オブジェクト。 たとえば、2 番目のオーバー ロードを使用して、ポイント間の差を検索する`CPoint(25, -19)`とサイズ`CSize(15, 5)`返します`CPoint(10, -24)`します。

符号を反転して四角形のオフセットを返しますポイントから四角形を引いて、`x`と`y`ポイントで指定された値。 たとえば、四角形をオフセットする最後のオーバー ロードを使用して`CRect(125, 200, 325, 400)`ポイントによって`CPoint(25, -19)`返します`CRect(100, 219, 300, 419)`します。

ポイントを否定するのに単項演算子を使用します。 たとえば、ポイントと単項演算子を使用して`CPoint(25, -19)`返します`CPoint(-25, 19)`します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル MDI](../../visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[POINT 構造体](../../mfc/reference/point-structure1.md)<br/>
[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize クラス](../../atl-mfc-shared/reference/csize-class.md)

