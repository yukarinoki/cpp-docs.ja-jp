---
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
ms.openlocfilehash: a806cfa18119df9beef3e070a65bc238a12580a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317717"
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
|[CPoint::オフセット](#offset)|のメンバーと`x``y`に値を追加`CPoint`します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CPoint::演算子 -](#operator_-)|a`CPoint`と 1 つのサイズの差、ポイントの否定、2 点のサイズの差、または負のサイズによるオフセットを返します。|
|[CPoint::演算子!=](#operator_neq)|2 点間の不等式をチェックします。|
|[CPoint::演算子 +](#operator_add)|の合計`CPoint`とサイズまたはポイント、またはサイズによるオフセットを`CRect`返します。|
|[CPoint::演算子 +=](#operator_add_eq)|サイズまたは`CPoint`ポイントを追加してオフセットします。|
|[CPoint::演算子 -=](#operator_-_eq)|サイズまたは`CPoint`ポイントを減算してオフセットします。|
|[CPoint::演算子 ==](#operator_eq_eq)|2 つのポイント間の等値をチェックします。|

## <a name="remarks"></a>解説

また、操作`CPoint`するメンバー関数と[POINT](/windows/win32/api/windef/ns-windef-point)構造体も含まれています。

オブジェクト`CPoint`は、構造を使用する`POINT`場所であればどこでも使用できます。 "size" と対話するこのクラスの演算子は、2 つのオブジェクトが交換可能であるため[、CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトまたは[SIZE](/windows/win32/api/windef/ns-windef-size)構造体のいずれかを受け入れます。

> [!NOTE]
> このクラスは、構造体から`tagPOINT`派生します。 (この名前`tagPOINT`は、`POINT`構造体ではあまり使用されません。つまり、`POINT`構造体のデータ メンバ、`x`および`y`は`CPoint`のアクセス可能なデータ メンバーです。

> [!NOTE]
> 共有ユーティリティ クラスの詳細については、「`CPoint`[共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`tagPOINT`

`CPoint`

## <a name="requirements"></a>必要条件

**ヘッダー:** atltypes.h

## <a name="cpointcpoint"></a><a name="cpoint"></a>CPoint::CPoint

`CPoint` オブジェクトを構築します。

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>パラメーター

*イニットX*<br/>
`x` の `CPoint` メンバーの値を指定します。

*イニティ*<br/>
`y` の `CPoint` メンバーの値を指定します。

*イニトプト*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体`CPoint`または初期化`CPoint`に使用する値を指定します。

*イニトサイズ*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size)`CPoint`構造体または初期化に使用する値を指定する[CSize。](../../atl-mfc-shared/reference/csize-class.md)

*ドウポイント*<br/>
メンバを`x` *dwPoint*の下位ワードに設定し、メンバ`y`を*dwPoint*の上位ワードに設定します。

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

## <a name="cpointoffset"></a><a name="offset"></a>CPoint::オフセット

のメンバーと`x``y`に値を追加`CPoint`します。

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>パラメーター

*x オフセット*<br/>
のメンバーをオフセットする`x`量を指定します`CPoint`。

*yオフセット*<br/>
のメンバーをオフセットする`y`量を指定します`CPoint`。

*ポイント*<br/>
オフセットする量[POINT](/windows/win32/api/windef/ns-windef-point)( `CPoint`POINT または`CPoint`) を指定します。

*サイズ*<br/>
オフセットする量 ( [SIZE](/windows/win32/api/windef/ns-windef-size)または[CSize](../../atl-mfc-shared/reference/csize-class.md)) を指定します`CPoint`。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

## <a name="cpointoperator-"></a><a name="operator_eq_eq"></a>CPoint::演算子 ==

2 つのポイント間の等値をチェックします。

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または`CPoint`オブジェクトを格納します。

### <a name="return-value"></a>戻り値

ポイントが等しい場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

## <a name="cpointoperator-"></a><a name="operator_neq"></a>CPoint::演算子!=

2 点間の不等式をチェックします。

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または`CPoint`オブジェクトを格納します。

### <a name="return-value"></a>戻り値

ポイントが等しくない場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add_eq"></a>CPoint::演算子 +=

最初のオーバーロードは、 にサイズ`CPoint`を追加します。

```
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトを格納します。

*ポイント*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトを格納します。

### <a name="remarks"></a>解説

2 番目のオーバーロードは、ポイント`CPoint`を .

どちらの`x`場合も、右側のオペランドの ( または`cx`) メンバーを の`x`メンバーに追加`CPoint`し、 のメンバーに`y`右側の`cy`オペランドの ( または ) メンバー`y`を追加することで`CPoint`、追加を行います。

たとえば、変数を`CPoint(5, -7)`含む`CPoint(30, 40)`変数に追加すると、変数が`CPoint(35, 33)`に変更されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-_eq"></a>CPoint::演算子 -=

最初のオーバーロードでは、 からサイズが`CPoint`減算されます。

```
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトを格納します。

*ポイント*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトを格納します。

### <a name="remarks"></a>解説

2 番目のオーバーロードでは、 から`CPoint`ポイントが減算されます。

どちらの場合も`x`、右オペランドの ( または`cx`) メンバーをの`x`メンバーから減算`CPoint`し、 のメンバーから右側のオペランドの`y`(`cy`または ) メンバーを減算することによって`y`減算が`CPoint`行われます。

たとえば、変数を`CPoint(5, -7)`含む`CPoint(30, 40)`変数からを減算すると、変数`CPoint(25, 47)`が に変更されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add"></a>CPoint::演算子 +

この演算子は、`CPoint``CPoint`または`CSize`オブジェクトでオフセットするか、 によって`CRect`オフセット`CPoint`を行う場合に使用します。

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトを格納します。

*ポイント*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクトを格納します。

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインターを格納します。

### <a name="return-value"></a>戻り値

サイズ`CPoint`によってオフセットされる、ポイントによってオフセットされる`CPoint`、または点による`CRect`オフセット。

### <a name="remarks"></a>解説

たとえば、最初の 2 つのオーバーロードのいずれかを使用してポイントまたはサイズ`CPoint(25, -19)``CPoint(15, 5)``CSize(15, 5)`でポイントをオフセットすると、値`CPoint(40, -14)`が返されます。

ポイントに四角形を追加すると、ポイントで指定された`x`値とによって`y`オフセットされた後の四角形が返されます。 たとえば、最後のオーバーロードを使用して、ポイント`CRect(125, 219, 325, 419)``CPoint(25, -19)`によって四角形をオフセット`CRect(150, 200, 350, 400)`すると、 は返されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-"></a>CPoint::演算子 -

から a`CPoint`または`CSize`オブジェクトを減算するには、最初の`CPoint`2 つのオーバーロードのいずれかを使用します。

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。

*サイズ*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

A`CSize`は 2 つのポイントの差`CPoint`、サイズの否定によってオフセットされる、`CRect`ポイントの否定によってオフセットされる、またはポイントの否定である。 `CPoint`

### <a name="remarks"></a>解説

3 番目のオーバーロードは`CRect`、 の否定によって`CPoint`a をオフセットします。 最後に、単項演算子を使用して否定`CPoint`します。

たとえば、最初のオーバーロードを使用して 2 つの点と`CPoint(25, -19)`戻`CPoint(15, 5)`り`CSize(10, -24)`値の差を見つけるとします。

`CSize`から`CPoint`を減算すると、上記と同じ計算が行`CPoint`われますが、オブジェクト`CSize`ではなくオブジェクトを返します。 たとえば、2 番目のオーバーロードを使用して、ポイント`CPoint(25, -19)`とサイズ`CSize(15, 5)`の差を見`CPoint(10, -24)`つけると、返されます。

ポイントから四角形を引いた場合、そのポイントで指定された値`x`と`y`の負の値によって四角形がオフセットされます。 たとえば、最後のオーバーロードを使用して、ポイント`CRect(125, 200, 325, 400)``CPoint(25, -19)`によって四角形をオフセット`CRect(100, 219, 300, 419)`すると、 は返されます。

単項演算子を使用して、ポイントを否定します。 たとえば、単項演算子を使用してポイント`CPoint(25, -19)`を返`CPoint(-25, 19)`すなどです。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>関連項目

[MDI のサンプル](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ポイント構造](/windows/win32/api/windef/ns-windef-point)<br/>
[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize クラス](../../atl-mfc-shared/reference/csize-class.md)
