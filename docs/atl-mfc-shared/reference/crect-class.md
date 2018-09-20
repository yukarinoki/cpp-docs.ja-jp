---
title: CRect クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0abe16bc12052601f86cb18677b52af9b40ad15
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428500"
---
# <a name="crect-class"></a>CRect クラス

Windows のような[RECT](../../mfc/reference/rect-structure1.md)構造体。

## <a name="syntax"></a>構文

```
class CRect : public tagRECT  
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRect::CRect](#crect)|`CRect` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRect::BottomRight](#bottomright)|右下の点を返します`CRect`します。|
|[CRect::CenterPoint](#centerpoint)|中心点を返します`CRect`します。|
|[CRect::CopyRect](#copyrect)|コピーするソース四角形の寸法`CRect`します。|
|[CRect::DeflateRect](#deflaterect)|幅と高さの減少`CRect`します。|
|[CRect::EqualRect](#equalrect)|決定かどうか`CRect`が指定された四角形と等しい。|
|[CRect::Height](#height)|高さを計算`CRect`します。|
|[CRect::InflateRect](#inflaterect)|幅と高さの増加`CRect`します。|
|[CRect::IntersectRect](#intersectrect)|セット`CRect`の 2 つの四角形の交差部分を等しくします。|
|[CRect::IsRectEmpty](#isrectempty)|決定かどうか`CRect`が空です。 `CRect` 幅や高さが 0 の場合は空です。|
|[CRect::IsRectNull](#isrectnull)|決定かどうか、 `top`、 `bottom`、 `left`、および`right`メンバー変数が 0 に等しい。|
|[CRect::MoveToX](#movetox)|移動`CRect`に指定された x 座標。|
|[CRect::MoveToXY](#movetoxy)|移動`CRect`を指定した x 座標と y 座標。|
|[CRect::MoveToY](#movetoy)|移動`CRect`に指定された y 座標。|
|[CRect::NormalizeRect](#normalizerect)|幅と高さを標準化`CRect`します。|
|[CRect::OffsetRect](#offsetrect)|移動`CRect`指定されたオフセット。|
|[CRect::PtInRect](#ptinrect)|内で指定したポイントがあるかどうかを判断します`CRect`します。|
|[CRect::SetRect](#setrect)|寸法を設定`CRect`します。|
|[CRect::SetRectEmpty](#setrectempty)|セット`CRect`四角形が空であることを (すべての座標は 0 に等しい) にします。|
|[CRect::Size](#size)|サイズを計算`CRect`します。|
|[CRect::SubtractRect](#subtractrect)|別の 1 つの四角形を減算します。|
|[CRect::TopLeft](#topleft)|左上の点を返します`CRect`します。|
|[CRect::UnionRect](#unionrect)|セット`CRect`の 2 つの四角形の共用体に等しい。|
|[CRect::Width](#width)|幅を計算`CRect`します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CRect::operator-](#operator_-)|指定したオフセットを減算`CRect`を縮小または`CRect`し、その結果を返します`CRect`します。|
|[CRect::operator LPCRECT](#operator_lpcrect)|`CRect` を `LPCRECT` に変換します。|
|[CRect::operator LPRECT](#operator_lprect)|`CRect` を `LPRECT` に変換します。|
|[CRect::operator! =](#operator_neq)|決定かどうか`CRect`四角形と等しくないです。|
|[CRect::operator &amp;](#operator_amp)|交差部分を作成します。`CRect`と四角形を、その結果を返します`CRect`します。|
|[CRect::operator &amp;=](#operator_amp_eq)|セット`CRect`の交差部分に等しい`CRect`と四角形。|
|[CRect::operator |](#operator_or)|和集合を作成します。`CRect`と四角形を、その結果を返します`CRect`します。|
|[CRect::operator |=](#operator_or_eq)|セット`CRect`の共用体に等しい`CRect`と四角形。|
|[CRect::operator +](#operator_add)|指定したオフセットを追加します。`CRect`拡張または`CRect`し、その結果を返します`CRect`します。|
|[CRect::operator + =](#operator_add_eq)|指定したオフセットを追加します。`CRect`拡張または`CRect`します。|
|[CRect::operator =](#operator_eq)|コピーする四角形の寸法`CRect`します。|
|[CRect::operator =](#operator_-_eq)|指定したオフセットを減算`CRect`を縮小または`CRect`します。|
|[CRect::operator = =](#operator_eq_eq)|決定かどうか`CRect`が四角形と等しい。|

## <a name="remarks"></a>Remarks

`CRect` 操作するメンバーの機能も含まれます`CRect`オブジェクトと Windows`RECT`構造体。

A`CRect`オブジェクトは、関数のパラメーターとして渡すことがどこにも、`RECT`構造、 `LPCRECT`、または`LPRECT`渡すことができます。

> [!NOTE]
>  このクラスから派生、`tagRECT`構造体。 (名前`tagRECT`のない、一般的に使用される名前は、`RECT`構造です)。つまり、データ メンバー (`left`、 `top`、 `right`、および`bottom`) の`RECT`構造体のアクセス可能なデータ メンバーである`CRect`します。

A`CRect`四角形の左と右下隅の点を定義するメンバー変数が含まれています。

指定するとき、 `CRect`、構築は、正規化ように注意する必要があります: つまり、左の座標の値が右最上部より小さいした結果が下部にあるより小さい。 たとえば、(10, 10) の左 (20, 20) の右下には、正規化された四角形が定義されていますが (20, 20) の左、上と (10, 10) の右下が正規化されていないの四角形を定義します。 多く、四角形が正規化されていない場合`CRect`メンバー関数は、正しくない結果を返す可能性があります。 (を参照してください[CRect::NormalizeRect](#normalizerect)のこれらの関数の一覧です)。正規化された四角形を必要とする関数を呼び出す前に呼び出すことで四角形の正規化されていないを正規化することができます、`NormalizeRect`関数。

操作するときに注意を使用して、`CRect`で、 [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp)と[CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp)メンバー関数。 かどうかのディスプレイ コンテキスト マッピング モードは y 範囲が負の場合と`MM_LOENGLISH`、し`CDC::DPtoLP`は、変換、`CRect`上が下部にあるより大きいようにします。 などの関数`Height`と`Size`は、変換後の高さの負の値を返します、 `CRect`、正規化されていない、四角形になります。  


オーバー ロードを使用すると`CRect`演算子では、最初のオペランドがある必要があります、 `CRect`; 2 つ目は、いずれかを[RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`オブジェクト。

## <a name="inheritance-hierarchy"></a>継承階層

`tagRECT`

`CRect`

## <a name="requirements"></a>要件

**ヘッダー:** atltypes.h

##  <a name="bottomright"></a>  CRect::BottomRight

座標がへの参照として返される、 [CPoint](cpoint-class.md)オブジェクトに含まれている`CRect`します。

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>戻り値

四角形の右下隅の座標。

### <a name="remarks"></a>Remarks

この関数は、取得、または四角形の右下隅の設定を使用できます。 代入演算子の左側にあるこの関数を使用して、角を設定します。

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

##  <a name="centerpoint"></a>  CRect::CenterPoint

中心点を計算`CRect`左辺と右辺値を追加して 2 で上部と下部の値を追加して 2 で除算しています。

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>戻り値

A`CPoint`の中心点であるオブジェクトを`CRect`します。

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

##  <a name="copyrect"></a>  CRect::CopyRect

コピー、`lpSrcRect`に四角形`CRect`します。

```
void CopyRect(LPCRECT lpSrcRect) throw(); 
```

### <a name="parameters"></a>パラメーター

*lpSrcRect*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`オブジェクトのコピーです。

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


##  <a name="crect"></a>  CRect::CRect

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

*l*  
左側の位置を示す`CRect`します。

*t*  
先頭を指定します`CRect`します。

*r*  
適切な位置を示す`CRect`します。

*b*  
指定の下部にある`CRect`します。

*srcRect*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造体の座標で`CRect`します。

*lpSrcRect*  
指す、`RECT`構造体の座標で`CRect`します。

*ポイント*  
構築される四角形の原点を指定します。 左上隅に対応します。

*size*  
左上隅から構築される四角形の右下隅までの距離を指定します。

*左上端*  
左上の位置を示す`CRect`します。

*bottomRight*  
右下の位置を示す`CRect`します。

### <a name="remarks"></a>Remarks

引数を指定しない場合`left`、 `top`、 `right`、および`bottom`メンバーが初期化されていません。

`CRect`(`const RECT&`) と`CRect`(`LPCRECT`) コンス トラクターの実行、 [CopyRect](#copyrect)します。 他のコンス トラクターは、直接のオブジェクトのメンバー変数を初期化します。

### <a name="example"></a>例

```cpp  
// default constructor doesn't initialize!
CRect rectUnknown;

// four-integers are left, top, right, and bottom
CRect rect(0, 0, 100, 50);
ASSERT(rect.Width() == 100);
ASSERT(rect.Height() == 50);

// Initialize from RECT stucture
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

##  <a name="deflaterect"></a>  CRect::DeflateRect

`DeflateRect` 縮小します`CRect`によってその辺を中心に向かっています。

```
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();  
```

### <a name="parameters"></a>パラメーター

*x*  
左右に左側を deflate ユニットの数を指定します`CRect`します。

*y*  
Deflate 上部と下部にユニットの数を指定します`CRect`します。

*size*  
A[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)または[CSize](csize-class.md) deflate をユニットの数を指定する`CRect`します。 `cx`値が左辺と右辺を圧縮する単位数を指定します、 `cy` deflate 上部と下部にユニットの数を指定します。

*lpRect*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`各辺を縮小するユニット数を指定します。

*l*  
左側にあるを圧縮する単位の数を指定します`CRect`します。

*t*  
上部を圧縮する単位の数を指定します`CRect`します。

*r*  
右側にあるを圧縮する単位の数を指定します`CRect`します。

*b*  
Deflate の下部にユニットの数を指定します`CRect`します。

### <a name="remarks"></a>Remarks

これを行う`DeflateRect`left および top にユニットを追加し、右や下から単位を減算します。 パラメーター`DeflateRect`が署名値は正の値が deflate`CRect`負の値は拡大とします。

最初の 2 つのオーバー ロードは、両方の反対側の組み合わせを deflate `CRect` 2 倍、全体の幅が減少するため*x* (または`cx`) と、全体の高さが 2 回減らさ*y* (または`cy`)。 その他の 2 つのオーバー ロードの各辺の縮小`CRect`とは無関係に、他のユーザー。

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

##  <a name="equalrect"></a>  CRect::EqualRect

決定かどうか`CRect`が指定された四角形と等しい。

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>パラメーター

*lpRect*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`四角形の左上隅および右下隅の座標を格納しているオブジェクト。

### <a name="return-value"></a>戻り値

2 つの四角形は、同じ上、左、下、および適切な値がある場合は 0 以外それ以外の場合 0 を返します。

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

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

##  <a name="height"></a>  CRect::Height

高さを計算`CRect`下部にある値から最上位の値を減算します。

```
int Height() const throw();
```

### <a name="return-value"></a>戻り値

高さ`CRect`します。

### <a name="remarks"></a>Remarks

結果の値を負にすることができます。

> [!NOTE]
>  四角形を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

```cpp  
   CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

   // nHt is now 40
   ASSERT(nHt == 40);   
```


##  <a name="inflaterect"></a>  CRect::InflateRect

`InflateRect` 拡張`CRect`中心から離れて、両側を移動します。

```
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();  
```

### <a name="parameters"></a>パラメーター

*x*  
左右を左に拡大するためのユニットの数を指定します`CRect`します。

*y*  
上部と下部の膨張ユニットの数を指定します`CRect`します。

*size*  
A[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)または[CSize](csize-class.md)膨張ユニットの数を指定する`CRect`します。 `cx`値が左辺と右辺を拡大するためのユニットの数を指定します、`cy`上部と下部の膨張ユニットの数を指定します。

*lpRect*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`各辺を拡大するユニット数を指定します。

*l*  
左側にあるを拡大するためのユニットの数を指定します`CRect`します。

*t*  
先頭を拡大するためのユニットの数を指定します`CRect`します。

*r*  
右側にあるを拡大するためのユニットの数を指定します`CRect`します。

*b*  
一番下に拡大するためのユニットの数を指定します`CRect`します。

### <a name="remarks"></a>Remarks

これを行う`InflateRect`から左、上の単位を減算し、右、下の単位を追加します。 パラメーター`InflateRect`署名された値は正の値は拡大`CRect`と負の値は縮小します。

最初の 2 つのオーバー ロードの反対側の両方のペアの膨張`CRect`2 倍、全体の幅を増やすように*x* (または`cx`) を 2 回ことで、全体の高さ*y* (または`cy`)。 その他の 2 つのオーバー ロードの各辺を拡大する`CRect`とは無関係に、他のユーザー。

### <a name="example"></a>例

```cpp  
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));  
```

##  <a name="intersectrect"></a>  CRect::IntersectRect

により、`CRect`既存の 2 つの四角形の交差部分を等しくします。

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();  
```

### <a name="parameters"></a>パラメーター

*lpRect1*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`ソース四角形を格納しているオブジェクト。

*lpRect2*  
指す、`RECT`構造または`CRect`ソース四角形を格納しているオブジェクト。

### <a name="return-value"></a>戻り値

積集合が空です。 ない場合、0 以外の場合積集合が空の場合は 0 を返します。

### <a name="remarks"></a>Remarks

積集合は、両方の既存の四角形に含まれている最も大きな四角形です。

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
CRect rectOne(125, 0, 150, 200);
CRect rectTwo(0, 75, 350,  95);
CRect rectInter;

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

##  <a name="isrectempty"></a>  CRect::IsRectEmpty

決定かどうか`CRect`が空です。

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>戻り値

0 以外の値`CRect`空; 0 は、場合`CRect`空ではありません。

### <a name="remarks"></a>Remarks

四角形は、空の幅または高さが 0 または負の値は。 異なる`IsRectNull`、四角形のすべての座標が 0 でかどうかを決定します。

> [!NOTE]
>  四角形を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
   ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
   ASSERT(rectEmpty.IsRectEmpty());   
```


##  <a name="isrectnull"></a>  CRect::IsRectNull

上、左、下かどうかを決定します。 右の値と`CRect`が 0 に等しいか。

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>戻り値

0 以外の値`CRect`の上、左、下、および適切な値は 0。 それ以外の場合 0。

### <a name="remarks"></a>Remarks

異なる`IsRectEmpty`、四角形が空かどうかを決定します。

### <a name="example"></a>例

```cpp  
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
   ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());  
```

##  <a name="movetox"></a>  CRect::MoveToX

指定された絶対 x 座標を四角形を移動するには、この関数を呼び出す*x*します。

```
void MoveToX(int x) throw();  
```

### <a name="parameters"></a>パラメーター

*x*  
四角形の左上隅の絶対 x 座標。

### <a name="example"></a>例

```cpp  
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

```cpp  
   CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

   // rect is now (10, 0, 110, 100);
   ASSERT(rect == CRect(10, 0, 110, 100));   
```

##  <a name="movetoxy"></a>  CRect::MoveToXY

絶対 x 座標と y 座標を指定した四角形を移動するには、この関数を呼び出します。

```
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();  
```

### <a name="parameters"></a>パラメーター

*x*  
四角形の左上隅の絶対 x 座標。

*y*  
四角形の左上隅の絶対 y 座標。

*ポイント*  
A`POINT`四角形の絶対の左上隅を指定する構造体。

### <a name="example"></a>例

```cpp  
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
   ASSERT(rect == CRect(10, 10, 110, 110));   
```


##  <a name="movetoy"></a>  CRect::MoveToY

絶対座標の y 座標で指定された四角形に移動するには、この関数を呼び出す*y*します。

```
void MoveToY(int y) throw();  
```

### <a name="parameters"></a>パラメーター

*y*  
四角形の左上隅の絶対 y 座標。

### <a name="example"></a>例

```cpp  
CRect rect(0, 0, 100, 100);
rect.MoveToY(10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
   ASSERT(rect == CRect(0, 10, 100, 110));   
```


##  <a name="normalizerect"></a>  CRect::NormalizeRect

正規化`CRect`高さと幅の両方が正の値になるようです。

```
void NormalizeRect() throw();
```

### <a name="remarks"></a>Remarks

四角形を正規化第 4 象限は、次の配置、Windows は、通常の座標を使用します。 `NormalizeRect` 上端と下端の値を比較し、上部、下部にあるより大きい場合は、それらをスワップします。 同様に、左が右より大きい場合、左および右の値を交換します。 この関数は、別のマッピング モードを扱う場合に便利ですし、四角形を反転します。

> [!NOTE]
>  次`CRect`メンバー関数は、適切に機能するために正規化された四角形が必要です:[高さ](#height)、[幅](#width)、[サイズ](#size)、 [IsRectEmpty](#isrectempty)、 [PtInRect](#ptinrect)、 [EqualRect](#equalrect)、 [UnionRect](#unionrect)、[示します](#intersectrect)、 [SubtractRect](#subtractrect)、[演算子 = =](#operator_eq_eq)、[演算子! =](#operator_neq)、[演算子&#124; ](#operator_or)、[演算子&#124;=](#operator_or_eq)、[演算子 (& a)](#operator_amp)、および[演算子 (& a) =](#operator_amp_eq)します。

### <a name="example"></a>例

```cpp  
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);

```cpp  
   CRect rect1(110, 100, 250, 310);
   CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
   rect2.NormalizeRect();
ASSERT(rect1 == rect2);  
```

##  <a name="offsetrect"></a>  CRect::OffsetRect

移動`CRect`指定されたオフセット。

```
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();  
```

### <a name="parameters"></a>パラメーター

*x*  
左に移動する量を指定します。 負の値を左に移動する場合があります。

*y*  
上下に移動する量を指定します。 負の値を上へ移動する場合があります。

*ポイント*  
含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)に移動する寸法の両方を指定するオブジェクト。

*size*  
含まれています、[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)に移動する寸法の両方を指定するオブジェクト。

### <a name="remarks"></a>Remarks

移動`CRect` *x* x 軸に沿った単位と*y* y 軸に沿った単位。 *X*と*y*パラメーターは、符号付きの値であるため`CRect`とが上または下または右左に移動することができます。

### <a name="example"></a>例

```cpp  
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

```cpp  
   CRect rect(0, 0, 35, 35);
   rect.OffsetRect(230, 230);

   // rect is now (230, 230, 265, 265)
   ASSERT(rect == CRect(230, 230, 265, 265));   
```


##  <a name="operator_lpcrect"></a>  CRect::operator LPCRECT 変換、`CRect`を[LPCRECT](../../mfc/reference/data-types-mfc.md)します。  


```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Remarks

この関数を使用する場合は、アドレスの必要はありません (**&**) 演算子。 この演算子は渡すときに自動的に使用、`CRect`が予期される関数オブジェクト、`LPCRECT`します。

##  <a name="operator_lprect"></a>  CRect::operator LPRECT

変換を`CRect`を[LPRECT](../../mfc/reference/data-types-mfc.md)します。  


```
operator LPRECT() throw();
```

### <a name="remarks"></a>Remarks

この関数を使用する場合は、アドレスの必要はありません (**&**) 演算子。 この演算子は渡すときに自動的に使用、`CRect`が予期される関数オブジェクト、`LPRECT`します。

### <a name="example"></a>例

例をご覧ください[CRect::operator LPCRECT](#operator_lpcrect)します。

##  <a name="operator_eq"></a>  CRect::operator =

割り当てます*srcRect*に`CRect`します。

```
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>パラメーター

*srcRect*  
元の四角形を指します。 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`します。

### <a name="example"></a>例

```cpp  
CRect rect(0, 0, 127, 168);
CRect rect2;

```cpp  
   CRect rect(0, 0, 127, 168);
   CRect rect2;

   rect2 = rect;
   ASSERT(rect2 == CRect(0, 0, 127, 168));   
```


##  <a name="operator_eq_eq"></a>  CRect::operator = =

決定かどうか`rect`と等しい`CRect`左および右下隅の座標を比較することで。

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>パラメーター

*rect*  
元の四角形を指します。 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`します。

### <a name="return-value"></a>戻り値

等しい場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999,  6,  3);

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


##  <a name="operator_neq"></a>  CRect::operator! =

決定かどうか*rect*が等しくない`CRect`左および右下隅の座標を比較することで。

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>パラメーター

*rect*  
元の四角形を指します。 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`します。

### <a name="return-value"></a>戻り値

等しくない場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999,  6,  3);

```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1 != rect3);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect3 != test);  
```

##  <a name="operator_add_eq"></a>  CRect::operator + =

最初の 2 つのオーバー ロードは、移動`CRect`指定されたオフセット。

```
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*  
A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)四角形を移動する単位の数を指定するオブジェクト。

*size*  
A[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)四角形を移動する単位の数を指定するオブジェクト。

*lpRect*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`のそれぞれの側を拡大するためのユニットの数を格納しているオブジェクト`CRect`します。

### <a name="remarks"></a>Remarks

パラメーターの*x*と*y* (または`cx`と`cy`) に値を追加`CRect`します。

3 番目のオーバー ロードは、拡張`CRect`の各メンバーのパラメーターで指定された単位数。

### <a name="example"></a>例

```cpp  
CRect rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect rect2(135, 300, 235, 400);

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2(135, 300, 235, 400);

   rect1 += pt;
   ASSERT(rect1 == rect2);   
```

##  <a name="operator_-_eq"></a>  CRect::operator =

最初の 2 つのオーバー ロードは、移動`CRect`指定されたオフセット。

```
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*  
A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)四角形を移動する単位の数を指定するオブジェクト。

*size*  
A[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)四角形を移動する単位の数を指定するオブジェクト。

*lpRect*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`の各辺を縮小するユニット数を格納しているオブジェクト`CRect`します。

### <a name="remarks"></a>Remarks

パラメーターの*x*と*y* (または`cx`と`cy`) から値を減算する`CRect`します。

3 番目のオーバー ロードを縮小します`CRect`の各メンバーのパラメーターで指定された単位数。 このオーバー ロードの機能に注意してください[DeflateRect](#deflaterect)します。

### <a name="example"></a>例

```cpp  
CRect rect1(100, 235, 200, 335);
CPoint pt(35, 65);
rect1 -= pt;

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);

   rect1 -= pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect1 == rectResult);   
```

##  <a name="operator_amp_eq"></a>  CRect::operator &amp;=

セット`CRect`の交差部分に等しい`CRect`と`rect`します。

```
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>パラメーター

*rect*  
含まれています、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`します。

### <a name="remarks"></a>Remarks

積集合は、両方の四角形に含まれている最も大きな四角形です。

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

例をご覧ください[CRect::IntersectRect](#intersectrect)します。

##  <a name="operator_or_eq"></a>  CRect::operator &#124;=

セット`CRect`の共用体に等しい`CRect`と`rect`します。

```
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>パラメーター

*rect*  
含まれています、`CRect`または[RECT](../../mfc/reference/rect-structure1.md)します。

### <a name="remarks"></a>Remarks

共用体が、両方の四角形を含む最小の四角形です。

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
CRect rect1(100,   0, 200, 300);
CRect rect2( 0, 100, 300, 200);
rect1 |= rect2;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);

   rect1 |= rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect1);   
```


##  <a name="operator_add"></a>  CRect::operator +

最初の 2 つのオーバー ロードを返す、`CRect`オブジェクトと等しい`CRect`によって指定されたオフセット転置。

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*  
A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)戻り値を移動する単位の数を指定するオブジェクト。

*size*  
A[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)戻り値を移動する単位の数を指定するオブジェクト。

*lpRect*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`戻り値のそれぞれの側を拡大するためのユニットの数を格納しているオブジェクト。

### <a name="return-value"></a>戻り値

`CRect`移動または膨張させることに起因`CRect`パラメーターで指定された単位数。

### <a name="remarks"></a>Remarks

パラメーターの*x*と*y* (または`cx`と`cy`) パラメーターに追加されます`CRect`の位置します。

新しい 3 つ目のオーバー ロードを返します`CRect`と等しい`CRect`膨らませると各メンバーのパラメーターで指定された単位の数。

### <a name="example"></a>例

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 + pt;
   CRect   rectResult(135, 300, 235, 400);
   ASSERT(rectResult == rect2);   
```


##  <a name="operator_-"></a>  CRect::operator-

最初の 2 つのオーバー ロードを返す、`CRect`オブジェクトと等しい`CRect`によって指定されたオフセット転置。

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*  
A[ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`戻り値を移動する単位の数を指定するオブジェクト。

*size*  
A[サイズ](https://msdn.microsoft.com/library/windows/desktop/dd145106)構造または`CSize`戻り値を移動する単位の数を指定するオブジェクト。

*lpRect*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`戻り値の各辺を縮小するユニット数を格納しているオブジェクト。

### <a name="return-value"></a>戻り値

`CRect`移動または縮小された`CRect`パラメーターで指定された単位数。

### <a name="remarks"></a>Remarks

パラメーターの*x*と*y* (または`cx`と`cy`) パラメーターが減算`CRect`の位置します。

新しい 3 つ目のオーバー ロードを返します`CRect`と等しい`CRect`倍率の各メンバーのパラメーターで指定された単位数。 このオーバー ロードの機能に注意してください[DeflateRect](#deflaterect)ではなく、 [SubtractRect](#subtractrect)します。

### <a name="example"></a>例

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 - pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect2 == rectResult);   
```


##  <a name="operator_amp"></a>  CRect::operator &amp;

返します、`CRect`の積集合である`CRect`と*rect2*します。

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>パラメーター

*rect2*  
含まれています、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`します。

### <a name="return-value"></a>戻り値

A`CRect`の積集合である`CRect`と*rect2*します。

### <a name="remarks"></a>Remarks

積集合は、両方の四角形に含まれている最も大きな四角形です。

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 & rect2;
   CRect   rectResult(100, 100, 200, 200);
   ASSERT(rectResult == rect3);   
```


##  <a name="operator_or"></a>  CRect::operator&#124;

返します、`CRect`の和集合である`CRect`と*rect2*します。

``` 
CRect operator|(const RECT& 
rect2) const throw(); 
```

### <a name="parameters"></a>パラメーター

*rect2*  
含まれています、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`します。

### <a name="return-value"></a>戻り値

A`CRect`の和集合である`CRect`と*rect2*します。

### <a name="remarks"></a>Remarks

共用体が、両方の四角形を含む最小の四角形です。

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
CRect rect1(100,   0, 200, 300);
CRect rect2( 0, 100, 300, 200);
CRect rect3;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 | rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```


##  <a name="ptinrect"></a>  CRect::PtInRect

内で指定したポイントがあるかどうかを判断します`CRect`します。

``` 
BOOL PtInRect(POINT point) const throw(); 
```

### <a name="parameters"></a>パラメーター

*ポイント*  
含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

内のポイントにある場合は 0 以外`CRect`。 それ以外の場合に 0 です。

### <a name="remarks"></a>Remarks

内にポイントが`CRect`左端または上端側上にある、4 辺すべてにつき内にあるかどうか。 右端または下端にある点が範囲外です`CRect`します。

> [!NOTE]
>  四角形を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

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

##  <a name="setrect"></a>  CRect::SetRect

寸法を設定`CRect`指定された座標。

``` 
void SetRect(int x1, int y1, int x2, int y2) throw(); 
```

### <a name="parameters"></a>パラメーター

*x1*  
左上隅の x 座標を指定します。

*y1*  
左上隅の y 座標を指定します。

*x2*  
右下隅の x 座標を指定します。

*y2*  
右下隅の y 座標を指定します。

### <a name="example"></a>例

```cpp  
CRect rect;
rect.SetRect(256, 256, 512, 512);

```cpp  
   CRect rect;
   rect.SetRect(256, 256, 512, 512);
   ASSERT(rect == CRect(256, 256, 512, 512));   
```


##  <a name="setrectempty"></a>  CRect::SetRectEmpty

`CRect`すべての座標を 0 に設定して空の四角形。

```
void SetRectEmpty() throw();
```

### <a name="example"></a>例

```cpp  
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());  
```

##  <a name="size"></a>  CRect::SIZE

`cx`と`cy`高さと幅の戻り値のメンバーが含まれて`CRect`します。

```
CSize Size() const throw();
```

### <a name="return-value"></a>戻り値

A [CSize](csize-class.md)オブジェクトのサイズを含む`CRect`します。

### <a name="remarks"></a>Remarks

高さまたは幅を負にすることができます。

> [!NOTE]
>  四角形を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);  
```

##  <a name="subtractrect"></a>  CRect::SubtractRect

寸法を作成、`CRect`の減算に等しい`lpRectSrc2`から`lpRectSrc1`します。

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>パラメーター

*lpRectSrc1*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`四角形の減算する元のオブジェクト。

*lpRectSrc2*  
指す、`RECT`構造または`CRect`指す四角形から減算するオブジェクト、 *lpRectSrc1*パラメーター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

減算が最小の四角形内のポイントのすべてを含む*lpRectScr1*の交差部分ではない*lpRectScr1*と*lpRectScr2*します。

指定された四角形*lpRectSrc1*は変更されず、四角形を指定して場合*lpRectSrc2*で指定された四角形を完全に重ならない*lpRectSrc1*で少なくとも 1 つの x 方向または y 方向。

たとえば場合、 *lpRectSrc1*された (10,10、100,100) と*lpRectSrc2*された (50,50、150,150) によって示される四角形*lpRectSrc1*ときに変更は、関数が返されます。 場合*lpRectSrc1*されました (10,10、100,100) と*lpRectSrc2*されました (50,10、150,150)、ただし、四角形によって示される*lpRectSrc1* (10, 10、座標が含まれます50,100) 関数によって返されるときにします。

`SubtractRect` 同じ[演算子 -](#operator_-)も[:operator-= 演算子](#operator_-_eq)します。 これらの演算子のどちらでもないことを呼び出す`SubtractRect`します。

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

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

##  <a name="topleft"></a>  CRect::TopLeft

座標がへの参照として返される、 [CPoint](cpoint-class.md)オブジェクトに含まれている`CRect`します。

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw(); 
```

### <a name="return-value"></a>戻り値

四角形の左上隅の座標。

### <a name="remarks"></a>Remarks

この関数は、取得、または四角形の左上隅の設定を使用できます。 代入演算子の左側にあるこの関数を使用して、角を設定します。

### <a name="example"></a>例

例をご覧ください[CRect::CenterPoint](#centerpoint)します。

##  <a name="unionrect"></a>  CRect::UnionRect

ディメンションは、`CRect`の 2 つのソースの四角形の共用体に等しい。

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>パラメーター

*lpRect1*  
指す、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`ソース四角形を格納しています。

*lpRect2*  
指す、`RECT`または`CRect`ソース四角形を格納しています。

### <a name="return-value"></a>戻り値

和集合が空でない場合、0 以外の場合和集合が空の場合は 0 を返します。

### <a name="remarks"></a>Remarks

共用体が、両方の四角形を含む最小の四角形です。

Windows は、空の四角形の大きさを無視します高さがない場合や幅を持たない四角形は、します。

> [!NOTE]
>  四角形の両方を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

### <a name="example"></a>例

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3.UnionRect(&rect1, &rect2);
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```

##  <a name="width"></a>  CRect::Width

幅を計算`CRect`適切な値からの左側の値を減算します。

```
int Width() const throw();
```

### <a name="return-value"></a>戻り値

幅`CRect`します。

### <a name="remarks"></a>Remarks

幅を負にすることができます。

> [!NOTE]
>  四角形を正規化する必要があります。 またはこの関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。

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
[RECT](../../mfc/reference/rect-structure1.md)

