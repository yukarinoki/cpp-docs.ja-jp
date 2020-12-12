---
description: '詳細: CPoint クラス'
title: CPoint クラス
ms.date: 11/04/2016
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
ms.openlocfilehash: 9d1c6ecb628e4d47d80503bb7a441efc4deb1252
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166760"
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
|[CPoint:: CPoint](#cpoint)|`CPoint` を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPoint:: Offset](#offset)|のメンバーとメンバーに値を追加し `x` `y` `CPoint` ます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CPoint:: operator-](#operator_-)|`CPoint`とのサイズ、または点の否定、または2つの点のサイズの差、または負のサイズによるオフセットの差を返します。|
|[CPoint:: operator! =](#operator_neq)|2つの点が等しくないかどうかをチェックします。|
|[CPoint:: operator +](#operator_add)|`CPoint`とサイズまたはポイントの合計、または `CRect` サイズによるオフセットを返します。|
|[CPoint:: operator + =](#operator_add_eq)|`CPoint`サイズまたはポイントを追加してオフセットします。|
|[CPoint:: operator-=](#operator_-_eq)|`CPoint`サイズまたはポイントを減算してオフセットします。|
|[CPoint:: operator = =](#operator_eq_eq)|2つの点が等しいかどうかをチェックします。|

## <a name="remarks"></a>解説

また、構造体を操作するためのメンバー関数も含まれてい `CPoint` ます。 [](/windows/win32/api/windef/ns-windef-point)

オブジェクトは、 `CPoint` 構造体が使用されているすべての場所で使用でき `POINT` ます。 "サイズ" と対話するこのクラスの演算子は、2つの型が交換可能であるため、 [CSize](../../atl-mfc-shared/reference/csize-class.md) オブジェクトまたは [サイズ](/windows/win32/api/windef/ns-windef-size) 構造体のいずれかを受け入れます。

> [!NOTE]
> このクラスは、 `tagPOINT` 構造体から派生します。 (この名前 `tagPOINT` は、構造体で使用頻度の低い名前です `POINT` )。これは、構造体のデータメンバー、およびは、 `POINT` `x` `y` のアクセス可能なデータメンバーであることを意味し `CPoint` ます。

> [!NOTE]
> 共有ユーティリティクラス (など) の詳細につい `CPoint` ては、「 [共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`tagPOINT`

`CPoint`

## <a name="requirements"></a>要件

**ヘッダー:** atltypes. h

## <a name="cpointcpoint"></a><a name="cpoint"></a> CPoint:: CPoint

`CPoint` オブジェクトを構築します。

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>パラメーター

*initX*<br/>
`x` の `CPoint` メンバーの値を指定します。

*initY*<br/>
`y` の `CPoint` メンバーの値を指定します。

*initPt*<br/>
[](/windows/win32/api/windef/ns-windef-point) `CPoint` 初期化に使用する値を指定する POINT 構造体または `CPoint` 。

*initSize*<br/>
初期化に使用する値を指定する[サイズ](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](../../atl-mfc-shared/reference/csize-class.md) `CPoint` 。

*dwPoint*<br/>
メンバーを `x` *dwpoint* の下位ワードに設定し、 `y` メンバーを *dwpoint* の上位ワードに設定します。

### <a name="remarks"></a>解説

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

## <a name="cpointoffset"></a><a name="offset"></a> CPoint:: Offset

のメンバーとメンバーに値を追加し `x` `y` `CPoint` ます。

```cpp
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>パラメーター

*xOffset*<br/>
のメンバーをオフセットする量を指定し `x` `CPoint` ます。

*yOffset*<br/>
のメンバーをオフセットする量を指定し `y` `CPoint` ます。

*視点*<br/>
をオフセットする量 ( [ポイント](/windows/win32/api/windef/ns-windef-point) または) を指定し `CPoint` `CPoint` ます。

*size*<br/>
をオフセットする量 ( [サイズ](/windows/win32/api/windef/ns-windef-size) または [CSize](../../atl-mfc-shared/reference/csize-class.md)) を指定し `CPoint` ます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

## <a name="cpointoperator-"></a><a name="operator_eq_eq"></a> CPoint:: operator = =

2つの点が等しいかどうかをチェックします。

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体またはオブジェクトが含まれてい `CPoint` ます。

### <a name="return-value"></a>戻り値

点が等しい場合は0以外の値。それ以外の場合は0です。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

## <a name="cpointoperator-"></a><a name="operator_neq"></a> CPoint:: operator! =

2つの点が等しくないかどうかをチェックします。

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体またはオブジェクトが含まれてい `CPoint` ます。

### <a name="return-value"></a>戻り値

点が等しくない場合は0以外の値。それ以外の場合は0です。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add_eq"></a> CPoint:: operator + =

最初のオーバーロードは、にサイズを追加し `CPoint` ます。

```cpp
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>パラメーター

*size*<br/>
[サイズ](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトを格納します。

*視点*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトが含まれています。

### <a name="remarks"></a>解説

2番目のオーバーロードは、に点を追加し `CPoint` ます。

どちらの場合も、 `x` `cx` 右側のオペランドの (または) メンバーをのメンバーに追加 `x` し、右側の `CPoint` `y` オペランドの (または) メンバー `cy` をのメンバーに追加 `y` `CPoint` することによって、加算が行われます。

たとえば、を含む変数にを追加すると、 `CPoint(5, -7)` `CPoint(30, 40)` 変数がに変更され `CPoint(35, 33)` ます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-_eq"></a> CPoint:: operator-=

最初のオーバーロードは、からサイズを減算し `CPoint` ます。

```cpp
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>パラメーター

*size*<br/>
[サイズ](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトを格納します。

*視点*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトが含まれています。

### <a name="remarks"></a>解説

2番目のオーバーロードは、から点を減算し `CPoint` ます。

どちらの場合も、減算を行うには `x` 、の `cx` メンバーから右側のオペランドの (または) メンバーを減算し、の `x` `CPoint` `y` `cy` メンバーから右側のオペランドの (または) メンバーを減算し `y` `CPoint` ます。

たとえば、 `CPoint(5, -7)` を含む変数からを減算すると、 `CPoint(30, 40)` 変数がに変更され `CPoint(25, 47)` ます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add"></a> CPoint:: operator +

この演算子は、 `CPoint` `CPoint` オブジェクトまたはオブジェクトによるオフセット `CSize` 、またはによるのオフセットに使用し `CRect` `CPoint` ます。

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>パラメーター

*size*<br/>
[サイズ](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトを格納します。

*視点*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトが含まれています。

*lpRect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインターを格納します。

### <a name="return-value"></a>戻り値

`CPoint`サイズでオフセットされる、 `CPoint` ポイントでオフセットされる、または `CRect` 点によるオフセットを表す。

### <a name="remarks"></a>解説

たとえば、最初の2つのオーバーロードのいずれかを使用してポイントを `CPoint(25, -19)` ポイントまたはサイズでオフセットすると、 `CPoint(15, 5)` `CSize(15, 5)` 値が返さ `CPoint(40, -14)` れます。

点に四角形を追加する `x` と、 `y` ポイントに指定されたおよびの値によってオフセットされた後、四角形が返されます。 たとえば、最後のオーバーロードを使用して、ある点によって四角形をオフセットすると、が `CRect(125, 219, 325, 419)` `CPoint(25, -19)` 返さ `CRect(150, 200, 350, 400)` れます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-"></a> CPoint:: operator-

最初の2つのオーバーロードのいずれかを使用して、 `CPoint` またはオブジェクトをから減算し `CSize` `CPoint` ます。

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

*size*<br/>
[サイズ](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

*lpRect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

2つの点の差である、 `CSize` `CPoint` サイズの否定によってオフセットされる、 `CRect` 点の否定によってオフセットされる、または `CPoint` 点の否定である。

### <a name="remarks"></a>解説

3番目のオーバーロードは、 `CRect` の否定によってをオフセットし `CPoint` ます。 最後に、単項演算子を使用してを否定 `CPoint` します。

たとえば、最初のオーバーロードを使用して2つの点の差を検出し、 `CPoint(25, -19)` `CPoint(15, 5)` を返し `CSize(10, -24)` ます。

からを減算する `CSize` `CPoint` と、上記と同じ計算が行われますが、オブジェクトではなくオブジェクトが返され `CPoint` `CSize` ます。 たとえば、2番目のオーバーロードを使用して、ポイント `CPoint(25, -19)` とサイズの差を求め `CSize(15, 5)` `CPoint(10, -24)` ます。

点から四角形を減算する `x` と、 `y` ポイントで指定された値と値の否定によって四角形のオフセットが返されます。 たとえば、最後のオーバーロードを使用して、四角形をポイントでオフセットすると、が `CRect(125, 200, 325, 400)` `CPoint(25, -19)` 返さ `CRect(100, 219, 300, 419)` れます。

単項演算子を使用して、点を否定します。 たとえば、単項演算子をポイントと共に使用すると、が `CPoint(25, -19)` 返さ `CPoint(-25, 19)` れます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>関連項目

[MFC のサンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[POINT 構造体](/windows/win32/api/windef/ns-windef-point)<br/>
[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize クラス](../../atl-mfc-shared/reference/csize-class.md)
