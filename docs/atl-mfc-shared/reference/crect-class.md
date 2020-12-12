---
description: '詳細: CRect クラス'
title: CRect クラス
ms.date: 11/06/2018
f1_keywords:
- CRect
- ATLTYPES/ATL::CRect
- ATLTYPES/ATL::CRect::CRect
- ATLTYPES/ATL::CRect::BottomRight
- ATLTYPES/ATL::CRect::CenterPoint
- ATLTYPES/ATL::CRect::CopyRect
- ATLTYPES/ATL::CRect::DeflateRect
- ATLTYPES/ATL::CRect::EqualRect
- ATLTYPES/ATL::CRect::Height
- ATLTYPES/ATL::CRect::InflateRect
- ATLTYPES/ATL::CRect::IntersectRect
- ATLTYPES/ATL::CRect::IsRectEmpty
- ATLTYPES/ATL::CRect::IsRectNull
- ATLTYPES/ATL::CRect::MoveToX
- ATLTYPES/ATL::CRect::MoveToXY
- ATLTYPES/ATL::CRect::MoveToY
- ATLTYPES/ATL::CRect::NormalizeRect
- ATLTYPES/ATL::CRect::OffsetRect
- ATLTYPES/ATL::CRect::PtInRect
- ATLTYPES/ATL::CRect::SetRect
- ATLTYPES/ATL::CRect::SetRectEmpty
- ATLTYPES/ATL::CRect::Size
- ATLTYPES/ATL::CRect::SubtractRect
- ATLTYPES/ATL::CRect::TopLeft
- ATLTYPES/ATL::CRect::UnionRect
- ATLTYPES/ATL::CRect::Width
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
ms.openlocfilehash: 229ec3b54f1b128641034bc763d2a62c0a6fe0a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166682"
---
# <a name="crect-class"></a>CRect クラス

Windows の [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体に似ています。

## <a name="syntax"></a>構文

```
class CRect : public tagRECT
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRect:: CRect](#crect)|`CRect` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRect:: 右下](#bottomright)|の右下の点を返し `CRect` ます。|
|[CRect:: 小惑星](#centerpoint)|の小惑星を返し `CRect` ます。|
|[CRect:: CopyRect](#copyrect)|変換元の四角形の寸法をにコピー `CRect` します。|
|[CRect::D eflateRect](#deflaterect)|の幅と高さを小さくし `CRect` ます。|
|[CRect:: EqualRect](#equalrect)|が、指定された四角形と等しいかどうかを判断し `CRect` ます。|
|[CRect:: Height](#height)|の高さを計算 `CRect` します。|
|[CRect:: InflateRect](#inflaterect)|の幅と高さを大きくし `CRect` ます。|
|[CRect:: IntersectRect](#intersectrect)|`CRect`2 つの四角形の交差部分に等しいを設定します。|
|[CRect:: IsRectEmpty](#isrectempty)|が空かどうかを判断し `CRect` ます。 `CRect` 幅と高さのどちらかまたは両方が0の場合、は空になります。|
|[CRect:: IsRectNull](#isrectnull)|`top`、、 `bottom` 、およびの各 `left` `right` メンバー変数がすべて0に等しいかどうかを判断します。|
|[CRect:: MoveToX](#movetox)|`CRect`指定した x 座標に移動します。|
|[CRect:: MoveToXY](#movetoxy)|`CRect`指定した x 座標と y 座標に移動します。|
|[CRect:: MoveToY](#movetoy)|`CRect`指定した y 座標に移動します。|
|[CRect:: NormalizeRect](#normalizerect)|の高さと幅を標準化 `CRect` します。|
|[CRect:: OffsetRect](#offsetrect)|`CRect`指定したオフセットだけ移動します。|
|[CRect::P の実行](#ptinrect)|指定した点が内にあるかどうかを判断し `CRect` ます。|
|[CRect:: SetRect](#setrect)|の大きさを設定 `CRect` します。|
|[CRect:: SetRectEmpty](#setrectempty)|`CRect`は空の四角形 (すべての座標が0に等しい) に設定されます。|
|[CRect:: Size](#size)|のサイズを計算 `CRect` します。|
|[CRect:: SubtractRect](#subtractrect)|ある四角形を別の四角形から減算します。|
|[CRect:: TopLeft](#topleft)|の左上の点を返し `CRect` ます。|
|[CRect:: UnionRect](#unionrect)|`CRect`2 つの四角形の和集合に等しいを設定します。|
|[CRect:: Width](#width)|の幅を計算 `CRect` します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CRect:: operator-](#operator_-)|指定したオフセットを `CRect` または縮小から減算 `CRect` し、結果として得られるを返し `CRect` ます。|
|[CRect:: operator LPCRECT](#operator_lpcrect)|`CRect` を `LPCRECT` に変換します。|
|[CRect:: operator LPRECT](#operator_lprect)|`CRect` を `LPRECT` に変換します。|
|[CRect:: operator! =](#operator_neq)|が四角形と等しくないかどうかを判断し `CRect` ます。|
|[CRect:: operator &amp;](#operator_amp)|と四角形の交差部分を作成し、結果とし `CRect` て得られるを返し `CRect` ます。|
|[CRect:: operator &amp;=](#operator_amp_eq)|`CRect`と四角形の交差部分に等しいを設定し `CRect` ます。|
|[CRect:: operator &#124;](#operator_or)|と四角形の和集合を作成 `CRect` し、その結果のを返し `CRect` ます。|
|[CRect:: operator &#124;=](#operator_or_eq)|`CRect`と四角形の和集合に等しいを設定し `CRect` ます。|
|[CRect:: operator +](#operator_add)|指定されたオフセットを `CRect` または増えに追加 `CRect` し、結果として得られるを返し `CRect` ます。|
|[CRect:: operator + =](#operator_add_eq)|指定したオフセットを `CRect` または増えに追加し `CRect` ます。|
|[CRect:: operator =](#operator_eq)|四角形の寸法をにコピー `CRect` します。|
|[CRect:: operator-=](#operator_-_eq)|指定したオフセットを `CRect` または縮小から減算し `CRect` ます。|
|[CRect:: operator = =](#operator_eq_eq)|が四角形と等しいかどうかを判断し `CRect` ます。|

## <a name="remarks"></a>解説

`CRect` には `CRect` 、オブジェクトと Windows 構造体を操作するためのメンバー関数も含まれてい `RECT` ます。

オブジェクトは、 `CRect` `RECT` 構造体、、またはを任意の場所に渡すことができる関数パラメーターとして渡すことができ `LPCRECT` `LPRECT` ます。

> [!NOTE]
> このクラスは、 `tagRECT` 構造体から派生します。 (名前は、 `tagRECT` 構造体の使用頻度が低い名前です `RECT` )。これは、 `left` 構造体のデータメンバー (、、 `top` `right` 、および `bottom` ) `RECT` が、のアクセス可能なデータメンバーであることを意味 `CRect` します。

には、 `CRect` 四角形の左上および右下の点を定義するメンバー変数が含まれています。

を指定する場合は、これを `CRect` 正規化するように注意する必要があります。つまり、左の座標の値が右側より小さく、上の値が下部よりも小さくなるようにします。 たとえば、の左上 (10, 10) と右下 (20, 20) は正規化された四角形を定義しますが、(10, 10) の左上 (20, 20) と右下 (10, 10) は正規化されていない四角形を定義します。 四角形が正規化されていない場合、多くの `CRect` メンバー関数が正しくない結果を返す可能性があります。 (これらの関数の一覧については、「 [CRect:: NormalizeRect](#normalizerect) 」を参照してください)。正規化された四角形を必要とする関数を呼び出す前に、関数を呼び出すことにより、正規化されていない四角形を正規化でき `NormalizeRect` ます。

`CRect` [Cdc::D PtoLP](../../mfc/reference/cdc-class.md#dptolp)および[Cdc:: lptodp](../../mfc/reference/cdc-class.md#lptodp)メンバー関数を使用してを操作する場合は注意が必要です。 表示コンテキストのマッピングモードが、のように y エクステントが負の値になるような場合、はを変換して `MM_LOENGLISH` `CDC::DPtoLP` 、その `CRect` 上辺が一番下よりも大きくなるようにします。 やなどの `Height` 関数 `Size` は、変換されたの高さに対して負の値を返し、 `CRect` 四角形は正規化されません。

オーバーロードされた演算子を使用する場合 `CRect` 、最初のオペランドはである必要があります `CRect` 。2番目のオペランドは、 [RECT](/windows/win32/api/windef/ns-windef-rect)構造体またはオブジェクトのいずれかになります。 `CRect`

## <a name="inheritance-hierarchy"></a>継承階層

`tagRECT`

`CRect`

## <a name="requirements"></a>要件

**ヘッダー:** atltypes. h

## <a name="crectbottomright"></a><a name="bottomright"></a> CRect:: 右下

座標は、に格納されている [CPoint](cpoint-class.md) オブジェクトへの参照として返され `CRect` ます。

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>戻り値

四角形の右下隅の座標です。

### <a name="remarks"></a>解説

この関数を使用すると、四角形の右下隅を取得または設定できます。 代入演算子の左側にあるこの関数を使用して、コーナーを設定します。

### <a name="example"></a>例

```cpp
// use BottomRight() to retrieve the bottom
// right POINT
CRect rect(210, 150, 350, 900);
CPoint ptDown;

ptDown = rect.BottomRight();

// ptDown is now set to (350, 900)
ASSERT(ptDown == CPoint(350, 900));

// or, use BottomRight() to set the bottom
// right POINT
CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);

CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

// rect2 is now (10, 10, 180, 180)
ASSERT(rect2 == CRect(10, 10, 180, 180));
```

## <a name="crectcenterpoint"></a><a name="centerpoint"></a> CRect:: 小惑星

左辺と右辺の `CRect` 値を加算して2で割ることによって、の小惑星を計算します。また、上と下の値を加算し、2で除算します。

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>戻り値

`CPoint`の小惑星であるオブジェクト `CRect` 。

### <a name="example"></a>例

```cpp
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog.
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);

    // device context for painting

    // get the size and position of the client area of
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT
    // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```

## <a name="crectcopyrect"></a><a name="copyrect"></a> CRect:: CopyRect

四角形を `lpSrcRect` にコピー `CRect` します。

```cpp
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>パラメーター

*lpSrcRect*<br/>
コピーされる [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体またはオブジェクトを指し `CRect` ます。

### <a name="example"></a>例

```cpp
CRect rectSource(35, 10, 125, 10);
CRect rectDest;

rectDest.CopyRect(&rectSource);

// rectDest is now set to (35, 10, 125, 10)

RECT rectSource2;
rectSource2.left = 0;
rectSource2.top = 0;
rectSource2.bottom = 480;
rectSource2.right = 640;

rectDest.CopyRect(&rectSource2);

// works against RECT structures, too!
// rectDest is now set to (0, 0, 640, 480)
```

## <a name="crectcrect"></a><a name="crect"></a> CRect:: CRect

`CRect` オブジェクトを構築します。

```
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();
```

### <a name="parameters"></a>パラメーター

*l*<br/>
の左の位置を指定し `CRect` ます。

*t*<br/>
の先頭を指定し `CRect` ます。

*r*<br/>
の適切な位置を指定し `CRect` ます。

*b*<br/>
の下部を指定し `CRect` ます。

*srcRect*<br/>
は、の座標を使用して [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体を参照し `CRect` ます。

*lpSrcRect*<br/>
`RECT`の座標を持つ構造体を指し `CRect` ます。

*視点*<br/>
構築する四角形の始点を指定します。 左上隅に相当します。

*size*<br/>
構築する四角形の左上隅から右下隅までの移動を指定します。

*topLeft*<br/>
の左上の位置を指定し `CRect` ます。

*bottomRight*<br/>
の右下の位置を指定し `CRect` ます。

### <a name="remarks"></a>解説

引数を指定しない場合、、、 `left` `top` 、およびの各 `right` `bottom` メンバーは0に設定されます。

`CRect`( `const RECT&` ) コンストラクターと `CRect` ( `LPCRECT` ) コンストラクターは、 [copyrect](#copyrect)を実行します。 その他のコンストラクターは、オブジェクトのメンバー変数を直接初期化します。

### <a name="example"></a>例

```cpp
// default constructor is equivalent to CRect(0, 0, 0, 0)
CRect emptyRect;

// four-integers are left, top, right, and bottom
CRect rect(0, 0, 100, 50);
ASSERT(rect.Width() == 100);
ASSERT(rect.Height() == 50);

// Initialize from RECT structure
RECT sdkRect;
sdkRect.left = 0;
sdkRect.top = 0;
sdkRect.right = 100;
sdkRect.bottom = 50;

CRect rect2(sdkRect);
// by reference
CRect rect3(&sdkRect);

// by address
ASSERT(rect2 == rect);
ASSERT(rect3 == rect);

// from a point and a size
CPoint pt(0, 0);
CSize sz(100, 50);
CRect rect4(pt, sz);
ASSERT(rect4 == rect2);

// from two points
CPoint ptBottomRight(100, 50);
CRect rect5(pt, ptBottomRight);
ASSERT(rect5 == rect4);
```

## <a name="crectdeflaterect"></a><a name="deflaterect"></a> CRect::D eflateRect

`DeflateRect` 縮小は、 `CRect` 中心に向かって移動します。

```cpp
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
の左側と右側を縮小する単位の数を指定し `CRect` ます。

*y*<br/>
の上下を収縮する単位数を指定し `CRect` ます。

*size*<br/>
Deflate する単位の数を指定する [サイズ](/windows/win32/api/windef/ns-windef-size) または [CSize](csize-class.md) `CRect` 。 値は、左右を縮小 `cx` する単位の数を指定し、値は、 `cy` 上と下を収縮する単位の数を指定します。

*lpRect*<br/>
[](/windows/win32/api/windef/ns-windef-rect) `CRect` 各辺を収縮する単位の数を指定する RECT 構造体またはを指します。

*l*<br/>
の左側を圧縮する単位数を指定し `CRect` ます。

*t*<br/>
の上部を deflate する単位数を指定し `CRect` ます。

*r*<br/>
右側を縮小する単位の数を指定し `CRect` ます。

*b*<br/>
の下部を圧縮する単位数を指定し `CRect` ます。

### <a name="remarks"></a>解説

これを行うには、によって、 `DeflateRect` 左と上に単位が加算され、右と下から単位が減算されます。 のパラメーター `DeflateRect` は符号付きの値です。正の値は deflate と負の値が `CRect` 膨張します。

最初の2つのオーバーロードは、の反対側の両方のペアを圧縮し、 `CRect` 合計幅が *x* (または) の2倍に減少 `cx` し、合計の高さが *y* (または) の2倍に減少し `cy` ます。 他の2つのオーバーロードは、互いに独立してそれぞれの辺を deflate し `CRect` ます。

### <a name="example"></a>例

```cpp
CRect rect(10, 10, 50, 50);
rect.DeflateRect(1, 2);
ASSERT(rect.left == 11 && rect.right == 49);
ASSERT(rect.top == 12 && rect.bottom == 48);

CRect rect2(10, 10, 50, 50);
CRect rectDeflate(1, 2, 3, 4);
rect2.DeflateRect(&rectDeflate);
ASSERT(rect2.left == 11 && rect2.right == 47);
ASSERT(rect2.top == 12 && rect2.bottom == 46);
```

## <a name="crectequalrect"></a><a name="equalrect"></a> CRect:: EqualRect

が、指定された四角形と等しいかどうかを判断し `CRect` ます。

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
[](/windows/win32/api/windef/ns-windef-rect) `CRect` 四角形の左上隅と右下隅の座標を格納している RECT 構造体またはオブジェクトを指します。

### <a name="return-value"></a>戻り値

2つの四角形の上、左、下、および右の値が同じ場合は0以外の値。それ以外の場合は0です。

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
ASSERT(!rect1.EqualRect(rect3));
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1.EqualRect(&test));
```

## <a name="crectheight"></a><a name="height"></a> CRect:: Height

`CRect`下部の値からトップの値を減算することによっての高さを計算します。

```
int Height() const throw();
```

### <a name="return-value"></a>戻り値

の高さ `CRect` 。

### <a name="remarks"></a>解説

結果の値には負の値を指定できます。

> [!NOTE]
> 四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

## <a name="crectinflaterect"></a><a name="inflaterect"></a> CRect:: InflateRect

`InflateRect` 増えは、 `CRect` その側を中央から離れて移動します。

```cpp
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
の左辺と右辺を拡大する単位の数を指定し `CRect` ます。

*y*<br/>
の上と下を拡大する単位の数を指定し `CRect` ます。

*size*<br/>
膨張する単位の数を指定する [サイズ](/windows/win32/api/windef/ns-windef-size) または [CSize](csize-class.md) `CRect` 。 値は、左右に拡大 `cx` する単位の数を指定し、値は、 `cy` 上および下を拡大する単位の数を指定します。

*lpRect*<br/>
[](/windows/win32/api/windef/ns-windef-rect) `CRect` 各辺を膨張する単位の数を指定する RECT 構造体またはを指します。

*l*<br/>
の左側を拡大する単位の数を指定し `CRect` ます。

*t*<br/>
の先頭を拡大する単位の数を指定し `CRect` ます。

*r*<br/>
右側を拡大する単位の数を指定し `CRect` ます。

*b*<br/>
の下部を拡大する単位の数を指定し `CRect` ます。

### <a name="remarks"></a>解説

これを行うには、 `InflateRect` 左と上から単位を減算し、右と下に単位を追加します。 のパラメーター `InflateRect` は符号付きの値です。正の値の膨張と負の値は `CRect` それを deflate します。

最初の2つのオーバーロードは、の反対側の両方のペアを膨張 `CRect` させて、合計幅が *x* (または) の2倍増加し、 `cx` 合計の高さが *y* (または) の2倍増加するようにし `cy` ます。 他の2つのオーバーロードは、の各辺を互いに独立して膨張させ `CRect` ます。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

## <a name="crectintersectrect"></a><a name="intersectrect"></a> CRect:: IntersectRect

は、 `CRect` 既存の2つの四角形の交差部分と等しいことを意味します。

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>パラメーター

*lpRect1*<br/>
ソース四角形を含む [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体またはオブジェクトを指し `CRect` ます。

*lpRect2*<br/>
`RECT`ソース四角形を含む構造体またはオブジェクトを指し `CRect` ます。

### <a name="return-value"></a>戻り値

積集合が空でない場合は0以外の。積集合が空の場合は0。

### <a name="remarks"></a>解説

共通部分は、両方の既存の四角形に含まれる最大の四角形です。

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect rectOne(125,  0, 150, 200);
CRect rectTwo(0, 75, 350, 95);
CRect rectInter;

rectInter.IntersectRect(rectOne, rectTwo);
ASSERT(rectInter == CRect(125, 75, 150, 95));
// operator &= can do the same task:

CRect rectInter2 = rectOne;
rectInter2 &= rectTwo;
ASSERT(rectInter2 == CRect(125, 75, 150, 95));
```

## <a name="crectisrectempty"></a><a name="isrectempty"></a> CRect:: IsRectEmpty

が空かどうかを判断し `CRect` ます。

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>戻り値

が空の場合は0以外の `CRect` `CRect` 。が空でない場合は0。

### <a name="remarks"></a>解説

幅と高さのどちらかまたは両方が0または負の場合、四角形は空になります。 はとは異なり `IsRectNull` 、四角形のすべての座標がゼロであるかどうかを判断します。

> [!NOTE]
> 四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

## <a name="crectisrectnull"></a><a name="isrectnull"></a> CRect:: IsRectNull

の top、left、bottom、および right の各値 `CRect` がすべて0に等しいかどうかを判断します。

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>戻り値

`CRect`が top、left、bottom、および right の各値がすべて0の場合は0以外の値。それ以外の場合は0。

### <a name="remarks"></a>解説

はとは異なり `IsRectEmpty` 、四角形が空であるかどうかを判断します。

### <a name="example"></a>例

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());
```

## <a name="crectmovetox"></a><a name="movetox"></a> CRect:: MoveToX

四角形を *x* で指定された絶対 x 座標に移動します。

```cpp
void MoveToX(int x) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
四角形の左上隅の絶対値の x 座標。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

// rect is now (10, 0, 110, 100);
ASSERT(rect == CRect(10, 0, 110, 100));
```

## <a name="crectmovetoxy"></a><a name="movetoxy"></a> CRect:: MoveToXY

この関数を呼び出して、指定した絶対値の x 座標と y 座標に四角形を移動します。

```cpp
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
四角形の左上隅の絶対値の x 座標。

*y*<br/>
四角形の左上隅の絶対値の y 座標。

*視点*<br/>
`POINT`四角形の左上隅を指定する構造体。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

## <a name="crectmovetoy"></a><a name="movetoy"></a> CRect:: MoveToY

四角形を *y* によって指定された絶対 y 座標に移動するには、この関数を呼び出します。

```cpp
void MoveToY(int y) throw();
```

### <a name="parameters"></a>パラメーター

*y*<br/>
四角形の左上隅の絶対値の y 座標。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
ASSERT(rect == CRect(0, 10, 100, 110));
```

## <a name="crectnormalizerect"></a><a name="normalizerect"></a> CRect:: NormalizeRect

`CRect`高さと幅の両方が正であるように、を正規化します。

```cpp
void NormalizeRect() throw();
```

### <a name="remarks"></a>解説

四角形は、Windows が座標に通常使用する4番目のクアドラントの配置に対して正規化されます。 `NormalizeRect` 上と下の値を比較し、top が下端より大きい場合はそれらを交換します。 同様に、左側の値が右側よりも大きい場合は、左辺と右辺の値が入れ替えられます。 この関数は、さまざまなマッピングモードおよび反転された四角形を処理する場合に便利です。

> [!NOTE]
> 次の `CRect` メンバー関数は、適切に機能するために正規化された四角形を必要とします: [Height](#height)、 [Width](#width)、 [Size](#size)、 [isrectempty](#isrectempty)、 [ptinrect](#ptinrect)、 [EqualRect](#equalrect)、 [UnionRect](#unionrect)、 [IntersectRect](#intersectrect)、 [SubtractRect](#subtractrect)、 [operator = =](#operator_eq_eq)、 [operator! =](#operator_neq)、 [operator &#124;](#operator_or)、 [operator &#124;=](#operator_or_eq)、operator [&](#operator_amp)、operator [&=](#operator_amp_eq)。

### <a name="example"></a>例

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

## <a name="crectoffsetrect"></a><a name="offsetrect"></a> CRect:: OffsetRect

`CRect`指定したオフセットだけ移動します。

```cpp
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
左または右に移動する量を指定します。 左に移動するには、負の値にする必要があります。

*y*<br/>
上または下に移動する量を指定します。 上に移動するには、負の値である必要があります。

*視点*<br/>
移動する次元の両方を指定する [POINT](/windows/win32/api/windef/ns-windef-point) 構造体または [CPoint](cpoint-class.md) オブジェクトを格納します。

*size*<br/>
移動する次元の両方を指定する [サイズ](/windows/win32/api/windef/ns-windef-size) 構造体または [CSize](csize-class.md) オブジェクトを格納します。

### <a name="remarks"></a>解説

X `CRect` 単位を x 軸と *y* 単位の y 軸に沿っ *て移動* します。 *X* および *y* パラメーターは符号付きの値なので、左または右に移動したり、上下に `CRect` 移動したりできます。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

## <a name="crectoperator-lpcrect-converts-a-crect-to-an-lpcrect"></a><a name="operator_lpcrect"></a> CRect:: operator LPCRECT を `CRect` [Lpcrect](../../mfc/reference/data-types-mfc.md)に変換します。

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>解説

この関数を使用する場合、address of () 演算子は必要ありません **&** 。 この演算子は、を必要とする関数にオブジェクトを渡すときに自動的に使用され `CRect` `LPCRECT` ます。

## <a name="crectoperator-lprect"></a><a name="operator_lprect"></a> CRect:: operator LPRECT

を `CRect` [LPRECT](../../mfc/reference/data-types-mfc.md)に変換します。

```
operator LPRECT() throw();
```

### <a name="remarks"></a>解説

この関数を使用する場合、address of () 演算子は必要ありません **&** 。 この演算子は、を必要とする関数にオブジェクトを渡すときに自動的に使用され `CRect` `LPRECT` ます。

### <a name="example"></a>例

「 [CRect:: operator LPCRECT](#operator_lpcrect)」の例を参照してください。

## <a name="crectoperator-"></a><a name="operator_eq"></a> CRect:: operator =

*Srcrect* をに割り当て `CRect` ます。

```cpp
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>パラメーター

*srcRect*<br/>
ソースの四角形を参照します。 には、 [RECT](/windows/win32/api/windef/ns-windef-rect) またはを指定でき `CRect` ます。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

## <a name="crectoperator-"></a><a name="operator_eq_eq"></a> CRect:: operator = =

`rect` `CRect` 左上隅と右下隅の座標を比較することによって、がと等しいかどうかを判断します。

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
ソースの四角形を参照します。 には、 [RECT](/windows/win32/api/windef/ns-windef-rect) またはを指定でき `CRect` ます。

### <a name="return-value"></a>戻り値

等しい場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1 == test);
```

## <a name="crectoperator-"></a><a name="operator_neq"></a> CRect:: operator! =

 `CRect` 左上隅と右下隅の座標を比較することによって、rect がと等しくないかどうかを判断します。

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
ソースの四角形を参照します。 には、 [RECT](/windows/win32/api/windef/ns-windef-rect) またはを指定でき `CRect` ます。

### <a name="return-value"></a>戻り値

等しくない場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999,  6,  3);
ASSERT(rect1 != rect3);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect3 != test);
```

## <a name="crectoperator-"></a><a name="operator_add_eq"></a> CRect:: operator + =

最初の2つのオーバーロードは、 `CRect` 指定されたオフセットによって移動します。

```cpp
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
四角形を移動する単位の数を指定する [ポイント](/windows/win32/api/windef/ns-windef-point) 構造体または [CPoint](cpoint-class.md) オブジェクト。

*size*<br/>
四角形を移動する単位の数を指定する [サイズ](/windows/win32/api/windef/ns-windef-size) 構造体または [CSize](csize-class.md) オブジェクト。

*lpRect*<br/>
[](/windows/win32/api/windef/ns-windef-rect) `CRect` 各辺を拡大する単位の数を含む RECT 構造体またはオブジェクトを指し `CRect` ます。

### <a name="remarks"></a>解説

パラメーターの *x* 値と *y* 値 (または `cx` と `cy` ) がに追加され `CRect` ます。

3番目のオーバーロードは、 `CRect` パラメーターの各メンバーで指定された単位数で増えます。

### <a name="example"></a>例

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-_eq"></a> CRect:: operator-=

最初の2つのオーバーロードは、 `CRect` 指定されたオフセットによって移動します。

```cpp
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
四角形を移動する単位の数を指定する [ポイント](/windows/win32/api/windef/ns-windef-point) 構造体または [CPoint](cpoint-class.md) オブジェクト。

*size*<br/>
四角形を移動する単位の数を指定する [サイズ](/windows/win32/api/windef/ns-windef-size) 構造体または [CSize](csize-class.md) オブジェクト。

*lpRect*<br/>
[](/windows/win32/api/windef/ns-windef-rect) `CRect` 各辺を収縮する単位数を格納している RECT 構造体またはオブジェクトを指し `CRect` ます。

### <a name="remarks"></a>解説

パラメーターの *x* と *y* (または `cx` と `cy` ) の値はから減算され `CRect` ます。

3番目のオーバーロードは、 `CRect` パラメーターの各メンバーで指定された単位数で縮小ます。 このオーバーロードは [DeflateRect](#deflaterect)のように機能することに注意してください。

### <a name="example"></a>例

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp_eq"></a> CRect:: operator &amp;=

`CRect`との積集合に等しいを設定し `CRect` `rect` ます。

```cpp
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
に [RECT](/windows/win32/api/windef/ns-windef-rect) またはが含まれてい `CRect` ます。

### <a name="remarks"></a>解説

交差部分は、両方の四角形に含まれる最大の四角形です。

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

「 [CRect:: IntersectRect](#intersectrect)」の例を参照してください。

## <a name="crectoperator-124"></a><a name="operator_or_eq"></a> CRect:: operator &#124;=

`CRect`との和集合に等しいを設定し `CRect` `rect` ます。

```cpp
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
に、またはの四角形が含まれてい `CRect` ます。 [](/windows/win32/api/windef/ns-windef-rect)

### <a name="remarks"></a>解説

共用体は、両方のソース四角形を含む最小の四角形です。

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

## <a name="crectoperator-"></a><a name="operator_add"></a> CRect:: operator +

最初の2つのオーバーロードは、 `CRect` `CRect` 指定されたオフセットによって置き換えられると等しいオブジェクトを返します。

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
戻り値を移動する単位の数を指定する [ポイント](/windows/win32/api/windef/ns-windef-point) 構造体または [CPoint](cpoint-class.md) オブジェクト。

*size*<br/>
戻り値を移動する単位の数を指定する [サイズ](/windows/win32/api/windef/ns-windef-size) 構造体または [CSize](csize-class.md) オブジェクト。

*lpRect*<br/>
[](/windows/win32/api/windef/ns-windef-rect) `CRect` 戻り値の各辺を膨張させる単位数を格納する RECT 構造体またはオブジェクトを指します。

### <a name="return-value"></a>戻り値

`CRect` `CRect` パラメーターで指定した単位数だけ移動または拡大した結果の。

### <a name="remarks"></a>解説

パラメーターの *x* と *y* (または `cx` 、および `cy` ) パラメーターがの位置に追加され `CRect` ます。

3番目のオーバーロードは、 `CRect` `CRect` パラメーターの各メンバーで指定された単位数によって大きくなると等しい新しいを返します。

### <a name="example"></a>例

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-"></a> CRect:: operator-

最初の2つのオーバーロードは、 `CRect` `CRect` 指定されたオフセットによって置き換えられると等しいオブジェクトを返します。

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
[](/windows/win32/api/windef/ns-windef-point) `CPoint` 戻り値を移動する単位の数を指定するポイント構造またはオブジェクト。

*size*<br/>
[](/windows/win32/api/windef/ns-windef-size) `CSize` 戻り値を移動する単位の数を指定するサイズ構造体またはオブジェクト。

*lpRect*<br/>
[](/windows/win32/api/windef/ns-windef-rect) `CRect` 戻り値の各辺を収縮する単位数を格納している RECT 構造体またはオブジェクトを指します。

### <a name="return-value"></a>戻り値

`CRect` `CRect` パラメーターで指定した単位数だけ移動または deflating した結果の。

### <a name="remarks"></a>解説

パラメーターの *x* および *y* (または `cx` および `cy` ) パラメーターは、の位置から減算され `CRect` ます。

3番目のオーバーロードは、 `CRect` `CRect` パラメーターの各メンバーで指定された単位数によって deflated に等しい新しいを返します。 このオーバーロードは、 [SubtractRect](#subtractrect)ではなく[DeflateRect](#deflaterect)のように機能することに注意してください。

### <a name="example"></a>例

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp"></a> CRect:: operator &amp;

`CRect`と rect2 の積集合であるを返し `CRect` ます。 

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>パラメーター

*rect2*<br/>
に [RECT](/windows/win32/api/windef/ns-windef-rect) またはが含まれてい `CRect` ます。

### <a name="return-value"></a>戻り値

`CRect`と rect2 の積集合で `CRect` ある。

### <a name="remarks"></a>解説

交差部分は、両方の四角形に含まれる最大の四角形です。

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

## <a name="crectoperator-124"></a><a name="operator_or"></a> CRect:: operator &#124;

`CRect`と rect2 の和集合であるを返し `CRect` ます。 

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>パラメーター

*rect2*<br/>
に [RECT](/windows/win32/api/windef/ns-windef-rect) またはが含まれてい `CRect` ます。

### <a name="return-value"></a>戻り値

`CRect`と rect2 の和集合で `CRect` ある。

### <a name="remarks"></a>解説

共用体は、両方の四角形を含む最小の四角形です。

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectptinrect"></a><a name="ptinrect"></a> CRect::P の実行

指定した点が内にあるかどうかを判断し `CRect` ます。

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](cpoint-class.md)オブジェクトが含まれています。

### <a name="return-value"></a>戻り値

ポイントが内にある場合は0以外 `CRect` 。それ以外の場合は0。

### <a name="remarks"></a>解説

位置が `CRect` 左側または上側にある場合、または4辺のいずれかにある場合、ポイントは内にあります。 右または下の点が外側に `CRect` あります。

> [!NOTE]
> 四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect rect(5, 5, 100, 100);
CPoint pt1(35, 50);
CPoint pt2(125, 298);

// this is true, because pt1 is inside the rectangle
ASSERT(rect.PtInRect(pt1));

// this is NOT true, because pt2 is outside the rectangle
ASSERT(!rect.PtInRect(pt2));

// note that the right and the bottom aren't inside
ASSERT(!rect.PtInRect(CPoint(35, 100)));
ASSERT(!rect.PtInRect(CPoint(100, 98)));

// but the top and the left are inside
ASSERT(rect.PtInRect(CPoint(5, 65)));
ASSERT(rect.PtInRect(CPoint(88, 5)));

// and that PtInRect() works against a POINT, too
POINT pt;
pt.x = 35;
pt.y = 50;
ASSERT(rect.PtInRect(pt));
```

## <a name="crectsetrect"></a><a name="setrect"></a> CRect:: SetRect

の次元 `CRect` を指定した座標に設定します。

```cpp
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>パラメーター

*x1*<br/>
左上隅の x 座標を指定します。

*y1*<br/>
左上隅の y 座標を指定します。

*×*<br/>
右下隅の x 座標を指定します。

*y2*<br/>
右下隅の y 座標を指定します。

### <a name="example"></a>例

```cpp
CRect rect;
rect.SetRect(256, 256, 512, 512);
ASSERT(rect == CRect(256, 256, 512, 512));
```

## <a name="crectsetrectempty"></a><a name="setrectempty"></a> CRect:: SetRectEmpty

`CRect`すべての座標を0に設定して、null の四角形を作成します。

```cpp
void SetRectEmpty() throw();
```

### <a name="example"></a>例

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

## <a name="crectsize"></a><a name="size"></a> CRect:: SIZE

`cx` `cy` 戻り値のおよびメンバーには、の高さと幅が含まれ `CRect` ます。

```
CSize Size() const throw();
```

### <a name="return-value"></a>戻り値

のサイズを格納している [CSize](csize-class.md) オブジェクト `CRect` 。

### <a name="remarks"></a>解説

高さまたは幅は負の値にすることができます。

> [!NOTE]
> 四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

## <a name="crectsubtractrect"></a><a name="subtractrect"></a> CRect:: SubtractRect

の次元を `CRect` からのの減算と同じに `lpRectSrc2` し `lpRectSrc1` ます。

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>パラメーター

*lpRectSrc1*<br/>
四角形を減算する [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体またはオブジェクトをポイントし `CRect` ます。

*lpRectSrc2*<br/>
`RECT` `CRect` *LpRectSrc1* パラメーターによって示される四角形から減算される構造体またはオブジェクトを指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

減算は、 *lpRectScr1* と *lpRectScr2* が交差していない、 *lpRectScr1* 内のすべての点を含む最小の四角形です。

*LpRectSrc1* で指定された四角形は、 *lpRectSrc2* によって指定された四角形が、x または y 方向の少なくとも1つの *lpRectSrc1* によって指定された四角形と完全に重ならない場合、変更されません。

たとえば、 *lpRectSrc1* が (10, 10, 100100) で、 *lpRectSrc2* が (50, 50, 150150) であった場合、 *lpRectSrc1* が指す四角形は、関数が返されたときに変更されません。 *LpRectSrc1* が (10, 10, 100100) で、 *lpRectSrc2* が (50, 10, 150150) である場合、 *lpRectSrc1* が指す四角形には、関数が返されたときの座標 (10, 10, 50100) が格納されます。

`SubtractRect` が [演算子](#operator_-) または [演算子-=](#operator_-_eq)と同じではありません。 これらの演算子はいずれもを呼び出しません `SubtractRect` 。

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
RECT   rectOne;
RECT   rectTwo;

rectOne.left = 10;
rectOne.top = 10;
rectOne.bottom = 100;
rectOne.right = 100;

rectTwo.left = 50;
rectTwo.top = 10;
rectTwo.bottom = 150;
rectTwo.right = 150;

CRect   rectDiff;

rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

ASSERT(rectDiff == rectResult);

// works for CRect, too, since there is
// implicit CRect -> LPCRECT conversion

CRect rect1(10, 10, 100, 100);
CRect rect2(50, 10, 150, 150);
CRect rectOut;

rectOut.SubtractRect(rect1, rect2);
ASSERT(rectResult == rectOut);
```

## <a name="crecttopleft"></a><a name="topleft"></a> CRect:: TopLeft

座標は、に格納されている [CPoint](cpoint-class.md) オブジェクトへの参照として返され `CRect` ます。

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>戻り値

四角形の左上隅の座標です。

### <a name="remarks"></a>解説

この関数を使用すると、四角形の左上隅を取得または設定できます。 代入演算子の左側にあるこの関数を使用して、コーナーを設定します。

### <a name="example"></a>例

「 [CRect:: 小惑星](#centerpoint)」の例を参照してください。

## <a name="crectunionrect"></a><a name="unionrect"></a> CRect:: UnionRect

`CRect`2 つのソース四角形の和集合に等しいの大きさを作成します。

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>パラメーター

*lpRect1*<br/>
ソース四角形を格納している [RECT](/windows/win32/api/windef/ns-windef-rect) またはを指し `CRect` ます。

*lpRect2*<br/>
`RECT`変換元の四角形を格納しているまたはを指し `CRect` ます。

### <a name="return-value"></a>戻り値

共用体が空でない場合は0以外の。共用体が空の場合は0。

### <a name="remarks"></a>解説

共用体は、両方のソース四角形を含む最小の四角形です。

空の四角形の大きさは無視されます。つまり、高さのない四角形や幅のない四角形です。

> [!NOTE]
> 両方の四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectwidth"></a><a name="width"></a> CRect:: Width

`CRect`右側の値から左の値を減算することによっての幅を計算します。

```
int Width() const throw();
```

### <a name="return-value"></a>戻り値

の幅 `CRect` 。

### <a name="remarks"></a>解説

幅には負の値を指定できます。

> [!NOTE]
> 四角形が正規化されているか、この関数が失敗する可能性があります。 [NormalizeRect](#normalizerect)を呼び出して、この関数を呼び出す前に四角形を正規化することができます。

### <a name="example"></a>例

```cpp
CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
// nWid is now 60
ASSERT(nWid == 60);
```

## <a name="see-also"></a>関連項目

[CPoint クラス](cpoint-class.md)<br/>
[CSize クラス](csize-class.md)<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)
