---
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
ms.openlocfilehash: b99eca7fe3a9c84f8b79ef3d694e27b6dd74dcd9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747057"
---
# <a name="crect-class"></a>CRect クラス

Windows の[RECT](/windows/win32/api/windef/ns-windef-rect)構造に似ています。

## <a name="syntax"></a>構文

```
class CRect : public tagRECT
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クレスト::クレスト](#crect)|`CRect` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クレスト::ボトムライト](#bottomright)|の右下の点を`CRect`返します。|
|[クレスト::センターポイント](#centerpoint)|の中心点を`CRect`返します。|
|[クレスト::コピーレック](#copyrect)|ソース四角形の寸法を`CRect`にコピーします。|
|[クレスト::Dレクラテレック](#deflaterect)|の幅と高さを`CRect`小さくします。|
|[クレスト::イコールレック](#equalrect)|指定された`CRect`四角形と等しいかどうかを判断します。|
|[クレスト::高さ](#height)|の`CRect`高さを計算します。|
|[クレスト::インフレレック](#inflaterect)|の幅と高さを`CRect`増やします。|
|[CRect::交差レクト](#intersectrect)|2`CRect`つの四角形の交差部分に等しい値を設定します。|
|[クレスト::IsRectEmpty](#isrectempty)|空かどうかを`CRect`判断します。 `CRect`幅または高さが 0 の場合は空です。|
|[クレスト::イズレクトヌル](#isrectnull)|`top` `bottom`、、、および`left``right`メンバー変数がすべて 0 であるかどうかを判断します。|
|[クレスト::ムーブトックス](#movetox)|指定`CRect`した x 座標に移動します。|
|[クレスト::移動トキシ](#movetoxy)|指定`CRect`した x 座標と y 座標に移動します。|
|[クレスト::移動トイ](#movetoy)|指定`CRect`した y 座標に移動します。|
|[クレスト::ノーマライズレック](#normalizerect)|の高さと幅を標準化します`CRect`。|
|[クレスト::オフセットレック](#offsetrect)|指定`CRect`したオフセットを移動します。|
|[クレスト::PtInRect](#ptinrect)|指定したポイントが`CRect`内にあるかどうかを判断します。|
|[クレスト::セットレック](#setrect)|の寸法を`CRect`設定します。|
|[クレット::セットレクト空](#setrectempty)|空`CRect`の四角形 (すべての座標が 0) に設定されます。|
|[クレスト:サイズ](#size)|のサイズを計算`CRect`します。|
|[クレスト::減算](#subtractrect)|1 つの四角形を別の四角形から減算します。|
|[クレクト::トップレフト](#topleft)|の左上の点を`CRect`返します。|
|[クレスト::ユニオンレック](#unionrect)|2`CRect`つの四角形の和集合に等しい値を設定します。|
|[クレスト::幅](#width)|の幅を計算`CRect`します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CRect::演算子 -](#operator_-)|指定されたオフセットを、から`CRect`減算したり、デ`CRect`フレートしたりして`CRect`、結果の .|
|[クレクト:オペレーター LPCRECT](#operator_lpcrect)|`CRect` を `LPCRECT` に変換します。|
|[クレスト::オペレーターLPRECT](#operator_lprect)|`CRect` を `LPRECT` に変換します。|
|[CRect::演算子 !=](#operator_neq)|四角形`CRect`と等しくないかどうかを判断します。|
|[CRect::演算子&amp;](#operator_amp)|の交差`CRect`と四角形を作成し、結果を`CRect`返します。|
|[CRect::演算子&amp;=](#operator_amp_eq)|四`CRect`角形と`CRect`の交点と等しい値を設定します。|
|[クレスト::演算子&#124;](#operator_or)|の和集合`CRect`と四角形を作成し、結果`CRect`を返します。|
|[&#124;=](#operator_or_eq)|の`CRect`和集合`CRect`と四角形と等しい値を設定します。|
|[CRect::演算子 +](#operator_add)|指定されたオフセットをに追加`CRect`または膨張`CRect`し、結果を`CRect`返します。|
|[CRect::演算子 +=](#operator_add_eq)|指定したオフセットをに追加`CRect`するか、または`CRect`を膨らませる。|
|[CRect::演算子 =](#operator_eq)|四角形のサイズを`CRect`にコピーします。|
|[CRect::演算子 -=](#operator_-_eq)|指定したオフセットをから減`CRect`算するか、または`CRect`をデフレートします。|
|[CRect::演算子 ==](#operator_eq_eq)|四角形`CRect`と等しいかどうかを判断します。|

## <a name="remarks"></a>解説

`CRect`また、オブジェクトや Windows`CRect``RECT`の構造体を操作するメンバー関数も含まれています。

オブジェクト`CRect`は、構造体、または`RECT``LPCRECT``LPRECT`を渡すことができる場所であれば、関数パラメーターとして渡すことができます。

> [!NOTE]
> このクラスは、構造体から`tagRECT`派生します。 (この名前`tagRECT`は、構造体ではあまり使用されないほど使用`RECT`される名前です。つまり`left`、`top``right``bottom``CRect`構造体のデータ メンバ ( 、 、、および ) は、 のデータ メンバにアクセス可能です。 `RECT`

A`CRect`には、四角形の左上および右下の点を定義するメンバー変数が含まれます。

を`CRect`指定する場合、正規化されるように、つまり、左座標の値が右より小さく、上が下辺より小さくなるように、構築に注意する必要があります。 たとえば、左上の (10,10) と右下の (20,20) の場合は正規化された四角形を定義しますが、左上の (20,20) と右下の (10,10) は正規化されていない四角形を定義します。 四角形が正規化されていない場合、多くの`CRect`メンバー関数が正しくない結果を返すことがあります。 (これらの関数の一覧については[、CRect::NormalizeRect](#normalizerect)を参照してください。正規化された四角形を必要とする関数を呼び出す前に、関数を呼び出すことによって正規化されていない`NormalizeRect`四角形を正規化できます。

を操作する`CRect`場合は[、CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp)および[CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp)メンバー関数を使用する場合は注意が必要です。 表示コンテキストのマッピング モードが y 範囲が負の場合は、`MM_LOENGLISH`のように、`CDC::DPtoLP`その上が下より`CRect`大きくなるように変換します。 などの`Height`関数`Size`は、変換後`CRect`の高さの負の値を返し、四角形は正規化されません。

オーバーロードされた`CRect`演算子を使用する場合、最初のオペランドは`CRect`、 ;2 つ目は[、RECT](/windows/win32/api/windef/ns-windef-rect)構造体または`CRect`オブジェクトのいずれかです。

## <a name="inheritance-hierarchy"></a>継承階層

`tagRECT`

`CRect`

## <a name="requirements"></a>必要条件

**ヘッダー:** atltypes.h

## <a name="crectbottomright"></a><a name="bottomright"></a>クレスト::ボトムライト

座標は、 に含まれる[CPoint](cpoint-class.md)オブジェクトへの参照として返`CRect`されます。

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>戻り値

四角形の右下隅の座標。

### <a name="remarks"></a>解説

この関数を使用して、四角形の右下隅を取得または設定できます。 代入演算子の左側にあるこの関数を使用して、コーナーを設定します。

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

## <a name="crectcenterpoint"></a><a name="centerpoint"></a>クレスト::センターポイント

左右の`CRect`値を加算して 2 で除算し、上と下の値を加算して 2 で割ることによって、の中心点を計算します。

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>戻り値

の`CPoint`中心点であるオブジェクト`CRect`。

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

## <a name="crectcopyrect"></a><a name="copyrect"></a>クレスト::コピーレック

四角形`lpSrcRect`を`CRect`にコピーします。

```cpp
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>パラメーター

*lpSrcRect*<br/>
コピーする[RECT](/windows/win32/api/windef/ns-windef-rect)構造体`CRect`またはオブジェクトへのポイント。

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

## <a name="crectcrect"></a><a name="crect"></a>クレスト::クレスト

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

*L*<br/>
の左位置を`CRect`指定します。

*t*<br/>
の先頭を`CRect`指定します。

*r*<br/>
の右の位置を`CRect`指定します。

*B*<br/>
の底部を`CRect`指定します。

*srcRect*<br/>
の座標を持つ[RECT](/windows/win32/api/windef/ns-windef-rect)構造体`CRect`を参照します。

*lpSrcRect*<br/>
の座標を`RECT`持つ構造体への`CRect`ポインター。

*ポイント*<br/>
構築する四角形の原点を指定します。 左上隅に対応します。

*size*<br/>
構築する四角形の左上隅から右下隅までの距離を指定します。

*topLeft*<br/>
の左上の位置を`CRect`指定します。

*bottomRight*<br/>
の右下の位置を`CRect`指定します。

### <a name="remarks"></a>解説

引数を指定しない場合、 `left` `top`、 `right`、`bottom`および メンバーは初期化されません。

( `CRect``const RECT&`)`CRect`および`LPCRECT`( ) のコンストラクターは[CopyRect](#copyrect)を実行します。 他のコンストラクターは、オブジェクトのメンバー変数を直接初期化します。

### <a name="example"></a>例

```cpp
// default constructor doesn't initialize!
CRect rectUnknown;

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

## <a name="crectdeflaterect"></a><a name="deflaterect"></a>クレスト::Dレクラテレック

`DeflateRect`その中心に`CRect`向かって側面を移動することによって膨張します。

```cpp
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
の左右を収縮させる単位数を`CRect`指定します。

*Y*<br/>
の上部と下部を収縮させる単位の`CRect`数を指定します。

*size*<br/>
縮小する単位の数を指定する[SIZE](/windows/win32/api/windef/ns-windef-size)または[CSize](csize-class.md) `CRect`です。 値`cx`は、左右の辺を収縮させる単位の数を指定し、値`cy`は、上部と下部を収縮させる単位の数を指定します。

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポイント、`CRect`または各辺を収縮させる単位数を指定します。

*L*<br/>
の左側を収縮させる単位数を指定`CRect`します。

*t*<br/>
の上部を収縮させる単位数を指定`CRect`します。

*r*<br/>
の右側を収縮させる単位数を指定`CRect`します。

*B*<br/>
の底部を収縮させる単位の数を指定`CRect`します。

### <a name="remarks"></a>解説

これを行うには、`DeflateRect`左と上に単位を追加し、右と下から単位を減算します。 のパラメータ`DeflateRect`は符号付きの値です。正の値は`CRect`収縮し、負の値はそれを膨らませる。

最初の 2 つのオーバーロードは、反対側の両方の`CRect`ペアを縮小して、その合計幅が*x* (`cx`または ) の 2 倍減少し、その`cy`合計高さが*y* (または) の 2 倍減少します。 他の 2 つのオーバーロードは、他`CRect`のオーバーロードとは独立してそれぞれの側を収縮させる。

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

## <a name="crectequalrect"></a><a name="equalrect"></a>クレスト::イコールレック

指定された`CRect`四角形と等しいかどうかを判断します。

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
四角形の左上隅と右下`CRect`隅の座標を含む[RECT](/windows/win32/api/windef/ns-windef-rect)構造体またはオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

2 つの四角形の上、左、下、右の値が同じ場合は 0 以外の値を返します。それ以外の場合は 0。

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

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

## <a name="crectheight"></a><a name="height"></a>クレスト::高さ

下の値から上`CRect`の値を減算しての高さを計算します。

```
int Height() const throw();
```

### <a name="return-value"></a>戻り値

の高さ`CRect`。

### <a name="remarks"></a>解説

結果の値は負の値になります。

> [!NOTE]
> 四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

### <a name="example"></a>例

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

## <a name="crectinflaterect"></a><a name="inflaterect"></a>クレスト::インフレレック

`InflateRect`その側面`CRect`をその中心から離れて移動することによって膨張します。

```cpp
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
の左右を膨らませる単位数を`CRect`指定します。

*Y*<br/>
の上部と下部を拡大する単位数を`CRect`指定します。

*size*<br/>
膨張`CRect`する単位の数を指定する[SIZE](/windows/win32/api/windef/ns-windef-size)または[CSize](csize-class.md)です。 この`cx`値は、左右の辺を膨らませる単位数を指定し`cy`、値は上部と下部を膨らませる単位数を指定します。

*Lprect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポイント、`CRect`または各側を膨張させる単位数を指定します。

*L*<br/>
の左側を拡大する単位数を指定`CRect`します。

*t*<br/>
の上部を拡大する単位数を指定`CRect`します。

*r*<br/>
の右側を拡大する単位数を指定`CRect`します。

*B*<br/>
の底部を膨らませる単位数を`CRect`指定します。

### <a name="remarks"></a>解説

これを行うには、`InflateRect`左と上から単位を減算し、右と下に単位を追加します。 のパラメータ`InflateRect`は符号付きの値です。正の値`CRect`は膨らみ、負の値はそれを膨らませる。

最初の 2 つのオーバーロードは、両方の対`CRect`の反対側のペアを膨らませて、その合計幅`cx`が*x* (または ) の 2`cy`倍に増加し、その合計高さが*y* (または) の 2 倍増加します。 他の 2 つのオーバーロードは、`CRect`他のオーバーロードとは独立してそれぞれの側を膨らませる。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

## <a name="crectintersectrect"></a><a name="intersectrect"></a>CRect::交差レクト

既存の`CRect`2 つの四角形の交差部分に等しくなります。

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ソースの四角形を含む`CRect` [RECT](/windows/win32/api/windef/ns-windef-rect)構造体またはオブジェクトへのポインター。

*2*<br/>
ソースの四`RECT`角形を`CRect`含む構造体またはオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

交差が空でない場合は 0 以外の値を返します。交差が空の場合は 0。

### <a name="remarks"></a>解説

交差は、両方の既存の四角形に含まれる最大の四角形です。

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

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

## <a name="crectisrectempty"></a><a name="isrectempty"></a>クレスト::IsRectEmpty

空かどうかを`CRect`判断します。

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>戻り値

空の場合`CRect`は 0 以外の値を返します。空でない`CRect`場合は 0。

### <a name="remarks"></a>解説

幅や高さ、または負の値の場合、四角形は空になります。 は、四`IsRectNull`角形のすべての座標が 0 かどうかを決定する のとは異なります。

> [!NOTE]
> 四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

### <a name="example"></a>例

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
ASSERT(rectEmpty.IsRectEmpty());
```

## <a name="crectisrectnull"></a><a name="isrectnull"></a>クレスト::イズレクトヌル

上、左、下、右の`CRect`値がすべて 0 かどうかを判断します。

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>戻り値

上、左`CRect`、下、右の値がすべて 0 の場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

は、四`IsRectEmpty`角形が空かどうかを決定する のとは異なります。

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

## <a name="crectmovetox"></a><a name="movetox"></a>クレスト::ムーブトックス

この関数は、x*で指定*された絶対 x 座標に四角形を移動します。

```cpp
void MoveToX(int x) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
四角形の左上隅の絶対 x 座標。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

// rect is now (10, 0, 110, 100);
ASSERT(rect == CRect(10, 0, 110, 100));
```

## <a name="crectmovetoxy"></a><a name="movetoxy"></a>クレスト::移動トキシ

指定した x 座標と y 座標に四角形を移動します。

```cpp
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
四角形の左上隅の絶対 x 座標。

*Y*<br/>
四角形の左上隅の絶対 y 座標。

*ポイント*<br/>
四`POINT`角形の絶対左上隅を指定する構造体。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
ASSERT(rect == CRect(10, 10, 110, 110));
```

## <a name="crectmovetoy"></a><a name="movetoy"></a>クレスト::移動トイ

この関数は、四角形を*y*で指定された絶対 y 座標に移動します。

```cpp
void MoveToY(int y) throw();
```

### <a name="parameters"></a>パラメーター

*Y*<br/>
四角形の左上隅の絶対 y 座標。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
ASSERT(rect == CRect(0, 10, 100, 110));
```

## <a name="crectnormalizerect"></a><a name="normalizerect"></a>クレスト::ノーマライズレック

高さと`CRect`幅の両方が正になるように正規化します。

```cpp
void NormalizeRect() throw();
```

### <a name="remarks"></a>解説

四角形は、Windows が座標に通常使用する 4 番目の四分領域の位置に対して正規化されます。 `NormalizeRect`は、上と下の値を比較し、上が下より大きい場合は、それらを入れ替えます。 同様に、左と右の値が右より大きい場合は、左右の値を交換します。 この関数は、さまざまなマッピング モードや反転矩形を扱う場合に便利です。

> [!NOTE]
> 次の`CRect`メンバー関数は[&](#operator_amp_eq) [Width](#width) [EqualRect](#equalrect) [UnionRect](#unionrect) [SubtractRect](#subtractrect) [PtInRect](#ptinrect) [&](#operator_amp) [IntersectRect](#intersectrect) [IsRectEmpty](#isrectempty) [&#124;](#operator_or_eq) [&#124;、](#operator_or)正しく動作するために正規化[Size](#size)された四角形を必要と[します。](#height) [operator ==](#operator_eq_eq) [operator !=](#operator_neq)

### <a name="example"></a>例

```cpp
CRect rect1(110, 100, 250, 310);
CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
rect2.NormalizeRect();
ASSERT(rect1 == rect2);
```

## <a name="crectoffsetrect"></a><a name="offsetrect"></a>クレスト::オフセットレック

指定`CRect`したオフセットを移動します。

```cpp
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
左または右に移動する量を指定します。 左に移動するには負の値にする必要があります。

*Y*<br/>
上下に移動する量を指定します。 上に移動するには負の値にする必要があります。

*ポイント*<br/>
移動の際に使用する両方の寸法を指定する[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](cpoint-class.md)オブジェクトを含みます。

*size*<br/>
移動の際に使用する両方の寸法を指定する[SIZE](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](csize-class.md)オブジェクトを格納します。

### <a name="remarks"></a>解説

x`CRect`軸に沿って*x*単位を移動し *、y*単位を y 軸に沿って移動します。 *x*および*y*パラメーターは符号付`CRect`きの値なので、左右に移動したり上下に移動したりできます。

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 35, 35);
rect.OffsetRect(230, 230);

// rect is now (230, 230, 265, 265)
ASSERT(rect == CRect(230, 230, 265, 265));
```

## <a name="crectoperator-lpcrect-converts-a-crect-to-an-lpcrect"></a><a name="operator_lpcrect"></a>CRect::演算子 LPCRECT は`CRect`[、LPCRECT](../../mfc/reference/data-types-mfc.md)に変換します。

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>解説

この関数を使用する場合は、アドレス演算子 (**&**) は必要ありません。 この演算子は、オブジェクトををを必要とする`CRect`関数に渡すときに自動的に`LPCRECT`使用されます。

## <a name="crectoperator-lprect"></a><a name="operator_lprect"></a>クレスト::オペレーターLPRECT

を`CRect` [LPRECT](../../mfc/reference/data-types-mfc.md)に変換します。

```
operator LPRECT() throw();
```

### <a name="remarks"></a>解説

この関数を使用する場合は、アドレス演算子 (**&**) は必要ありません。 この演算子は、オブジェクトををを必要とする`CRect`関数に渡すときに自動的に`LPRECT`使用されます。

### <a name="example"></a>例

[例](#operator_lpcrect)を参照してください。

## <a name="crectoperator-"></a><a name="operator_eq"></a>CRect::演算子 =

に*srcRect* `CRect`を割り当てます。

```cpp
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>パラメーター

*srcRect*<br/>
ソースの四角形を参照します。 [RECT](/windows/win32/api/windef/ns-windef-rect)または`CRect`.

### <a name="example"></a>例

```cpp
CRect rect(0, 0, 127, 168);
CRect rect2;

rect2 = rect;
ASSERT(rect2 == CRect(0, 0, 127, 168));
```

## <a name="crectoperator-"></a><a name="operator_eq_eq"></a>CRect::演算子 ==

左上隅と`rect`右下隅`CRect`の座標を比較して、等しいかどうかを判断します。

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
ソースの四角形を参照します。 [RECT](/windows/win32/api/windef/ns-windef-rect)または`CRect`.

### <a name="return-value"></a>戻り値

等しい場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

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

## <a name="crectoperator-"></a><a name="operator_neq"></a>CRect::演算子 !=

*rect*が、左上隅と右`CRect`下隅の座標を比較して等しくないかどうかを判断します。

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
ソースの四角形を参照します。 [RECT](/windows/win32/api/windef/ns-windef-rect)または`CRect`.

### <a name="return-value"></a>戻り値

等しくない場合は 0 以外の値。それ以外の場合は 0。

### <a name="remarks"></a>解説

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

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

## <a name="crectoperator-"></a><a name="operator_add_eq"></a>CRect::演算子 +=

最初の 2 つの`CRect`オーバーロードは、指定されたオフセットによって移動します。

```cpp
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
四角形を移動する単位数を指定する[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](cpoint-class.md)オブジェクト。

*size*<br/>
四角形を移動する単位数を指定する[SIZE](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](csize-class.md)オブジェクト。

*Lprect*<br/>
の各辺を膨張させる単位`CRect`の数を含む[RECT](/windows/win32/api/windef/ns-windef-rect)構造体またはオブジェクト`CRect`を指します。

### <a name="remarks"></a>解説

パラメーターの*x*および*y* `cx` (`cy`または) の値`CRect`が に追加されます。

3 番目のオーバーロード`CRect`は、パラメーターの各メンバーで指定された単位数によって膨らみます。

### <a name="example"></a>例

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint  pt(35, 65);
CRect   rect2(135, 300, 235, 400);

rect1 += pt;
ASSERT(rect1 == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-_eq"></a>CRect::演算子 -=

最初の 2 つの`CRect`オーバーロードは、指定されたオフセットによって移動します。

```cpp
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
四角形を移動する単位数を指定する[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](cpoint-class.md)オブジェクト。

*size*<br/>
四角形を移動する単位数を指定する[SIZE](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](csize-class.md)オブジェクト。

*Lprect*<br/>
の各辺を収縮させる単位`CRect`の数を含む[RECT](/windows/win32/api/windef/ns-windef-rect)構造体またはオブジェクトを`CRect`指します。

### <a name="remarks"></a>解説

パラメーターの*x*および*y* `cx` (`cy`または) の値は`CRect`から減算されます。

3 番目のオーバーロードは`CRect`、パラメーターの各メンバーで指定された単位数だけ値が減少します。 このオーバーロードは[DeflateRect](#deflaterect)のような機能を持ちます。

### <a name="example"></a>例

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);

rect1 -= pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect1 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp_eq"></a>CRect::演算子&amp;=

と`CRect`の交点と`CRect`等`rect`しい値を設定します。

```cpp
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)または`CRect`.

### <a name="remarks"></a>解説

交差は、両方の四角形に含まれる最大の四角形です。

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

### <a name="example"></a>例

[「CRect::交差レック](#intersectrect)」の例を参照してください。

## <a name="crectoperator-124"></a><a name="operator_or_eq"></a>&#124;=

と`CRect`の`CRect`和集合と等`rect`しい値を設定します。

```cpp
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
または`CRect`[RECT](/windows/win32/api/windef/ns-windef-rect)を含みます。

### <a name="remarks"></a>解説

結合は、両方のソース四角形を含む最小の四角形です。

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

### <a name="example"></a>例

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);

rect1 |= rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect1);
```

## <a name="crectoperator-"></a><a name="operator_add"></a>CRect::演算子 +

最初の 2 つのオーバーロード`CRect`は、指定されたオフセット`CRect`によって変位されるオブジェクトを返します。

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
戻り値を移動する単位数を指定する[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](cpoint-class.md)オブジェクト。

*size*<br/>
戻り値を移動する単位数を指定する[SIZE](/windows/win32/api/windef/ns-windef-size)構造体または[CSize](csize-class.md)オブジェクト。

*Lprect*<br/>
戻り値の各辺を`CRect`膨らませる単位数を含む[RECT](/windows/win32/api/windef/ns-windef-rect)構造体またはオブジェクトを指します。

### <a name="return-value"></a>戻り値

パラメータ`CRect`で指定された単位数`CRect`で移動または膨張した結果。

### <a name="remarks"></a>解説

パラメータの*x*と*y* `cx` (`cy`または) のパラメータ`CRect`が 's の位置に追加されます。

3 番目のオーバーロードは`CRect`、パラメーターの各`CRect`メンバーで指定された単位数によって膨らむのと等しい新しい値を返します。

### <a name="example"></a>例

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 + pt;
CRect   rectResult(135, 300, 235, 400);
ASSERT(rectResult == rect2);
```

## <a name="crectoperator--"></a><a name="operator_-"></a>CRect::演算子 -

最初の 2 つのオーバーロード`CRect`は、指定されたオフセット`CRect`によって変位されるオブジェクトを返します。

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
戻[POINT](/windows/win32/api/windef/ns-windef-point)り値を`CPoint`移動する単位数を指定する POINT 構造体またはオブジェクト。

*size*<br/>
戻[SIZE](/windows/win32/api/windef/ns-windef-size)り値を`CSize`移動する単位数を指定する SIZE 構造体またはオブジェクト。

*Lprect*<br/>
戻り値の各辺を`CRect`収縮させる単位数を含む[RECT](/windows/win32/api/windef/ns-windef-rect)構造体またはオブジェクトへのポイント。

### <a name="return-value"></a>戻り値

パラメータ`CRect`で指定された単位数`CRect`で移動または膨張した結果。

### <a name="remarks"></a>解説

パラメータの*x*と*y* `cx` (`cy`または) のパラメータは`CRect`'s 位置から減算されます。

3 番目のオーバーロードは`CRect`、パラメーターの各`CRect`メンバーで指定された単位数によって縮小された新しい値を返します。 このオーバーロード関数は[、SubtractRect](#subtractrect)ではなく[DeflateRect](#deflaterect)のように機能します。

### <a name="example"></a>例

```cpp
CRect   rect1(100, 235, 200, 335);
CPoint pt(35, 65);
CRect   rect2;

rect2 = rect1 - pt;
CRect   rectResult(65, 170, 165, 270);
ASSERT(rect2 == rectResult);
```

## <a name="crectoperator-amp"></a><a name="operator_amp"></a>CRect::演算子&amp;

`CRect`と*rect2*の`CRect`交差を返します。

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>パラメーター

*rect2*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)または`CRect`.

### <a name="return-value"></a>戻り値

と`CRect` *rect2*`CRect`の交点である A .

### <a name="remarks"></a>解説

交差は、両方の四角形に含まれる最大の四角形です。

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

### <a name="example"></a>例

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 & rect2;
CRect   rectResult(100, 100, 200, 200);
ASSERT(rectResult == rect3);
```

## <a name="crectoperator-124"></a><a name="operator_or"></a>&#124;

`CRect`の和`CRect`集合であるを返し *、rect2*を返します。

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>パラメーター

*rect2*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)または`CRect`.

### <a name="return-value"></a>戻り値

A`CRect`と`CRect`*rect2*の和集合です。

### <a name="remarks"></a>解説

結合は、両方の四角形を含む最小の四角形です。

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

### <a name="example"></a>例

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3 = rect1 | rect2;
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectptinrect"></a><a name="ptinrect"></a>クレスト::PtInRect

指定したポイントが`CRect`内にあるかどうかを判断します。

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)構造体または[CPoint](cpoint-class.md)オブジェクトを格納します。

### <a name="return-value"></a>戻り値

ポイントが内`CRect`にある場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

ポイントは、左側`CRect`または上側にあるか、4 辺の内側にある場合に入ります。 右側または下側の点が外側`CRect`にあります。

> [!NOTE]
> 四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

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

## <a name="crectsetrect"></a><a name="setrect"></a>クレスト::セットレック

の寸法`CRect`を指定した座標に設定します。

```cpp
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>パラメーター

*x1*<br/>
左上隅の x 座標を指定します。

*y1*<br/>
左上隅の y 座標を指定します。

*x2*<br/>
右下隅の x 座標を指定します。

*y2*<br/>
右下隅の y 座標を指定します。

### <a name="example"></a>例

```cpp
CRect rect;
rect.SetRect(256, 256, 512, 512);
ASSERT(rect == CRect(256, 256, 512, 512));
```

## <a name="crectsetrectempty"></a><a name="setrectempty"></a>クレット::セットレクト空

すべての`CRect`座標をゼロに設定して、null の四角形を作成します。

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

## <a name="crectsize"></a><a name="size"></a>クレスト:サイズ

戻`cx`り`cy`値の と の メンバーには、`CRect`の高さと幅が含まれます。

```
CSize Size() const throw();
```

### <a name="return-value"></a>戻り値

のサイズを格納する[CSize](csize-class.md) `CRect`オブジェクト。

### <a name="remarks"></a>解説

高さまたは幅は負の値にできます。

> [!NOTE]
> 四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

### <a name="example"></a>例

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

## <a name="crectsubtractrect"></a><a name="subtractrect"></a>クレスト::減算

の減算`CRect``lpRectSrc2`に等しいの寸法を作成`lpRectSrc1`します。

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>パラメーター

*lpRectSrc1*<br/>
四角形を減算する`CRect`[RECT](/windows/win32/api/windef/ns-windef-rect)構造体またはオブジェクトへのポインター。

*2*<br/>
`RECT` *lpRectSrc1*パラメーターが指す四角形から減算される構造体または`CRect`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

減算は *、lpRectScr1 と lpRectScr2*の交差部分に含まれていない *、lpRectScr1* *lpRectScr2*のすべてのポイントを含む最小の四角形です。

*lpRectSrc2*で指定された四角形が *、lpRectSrc1*で指定された四角形と x 方向または y 方向の少なくとも 1 つで指定された四角形と完全に重なり合わない場合 *、lpRectSrc1*で指定された四角形は変更されません。

例えば *、lpRectSrc1*が (10,10, 100,100) で *、lpRectSrc2*が (50,50, 150,150) であった場合、関数が戻ったときに*lpRectSrc1*が指す矩形は変更されません。 *ただし、lpRectSrc1*が (10,10, 100,100) で *、lpRectSrc2*が (50,10, 150,150) であった場合、関数が戻ったときに*lpRectSrc1*が指す四角形には座標 (10,10, 50,100) が含まれます。

`SubtractRect`演算子と同じではありません[-](#operator_-)また[演算子 -=](#operator_-_eq)。 これらの演算子のどちらもを呼`SubtractRect`び出すことはありません。

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

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

## <a name="crecttopleft"></a><a name="topleft"></a>クレクト::トップレフト

座標は、 に含まれる[CPoint](cpoint-class.md)オブジェクトへの参照として返`CRect`されます。

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>戻り値

四角形の左上隅の座標。

### <a name="remarks"></a>解説

この関数を使用して、四角形の左上隅を取得または設定できます。 代入演算子の左側にあるこの関数を使用して、コーナーを設定します。

### <a name="example"></a>例

[「CRect::センターポイント](#centerpoint)」の例を参照してください。

## <a name="crectunionrect"></a><a name="unionrect"></a>クレスト::ユニオンレック

2 つのソース`CRect`四角形の和集合と等しい寸法を作成します。

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)へのポインター、`CRect`またはソースの四角形を含むポインター。

*2*<br/>
ソース四角形`RECT`を`CRect`含む または を指します。

### <a name="return-value"></a>戻り値

共用体が空でない場合は 0 以外。共用体が空の場合は 0。

### <a name="remarks"></a>解説

結合は、両方のソース四角形を含む最小の四角形です。

空の四角形のサイズは無視されます。つまり、高さがない四角形、または幅のない四角形です。

> [!NOTE]
> 両方の四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

### <a name="example"></a>例

```cpp
CRect   rect1(100,  0, 200, 300);
CRect   rect2(0, 100, 300, 200);
CRect   rect3;

rect3.UnionRect(&rect1, &rect2);
CRect   rectResult(0, 0, 300, 300);
ASSERT(rectResult == rect3);
```

## <a name="crectwidth"></a><a name="width"></a>クレスト::幅

右の値から左`CRect`の値を減算しての幅を計算します。

```
int Width() const throw();
```

### <a name="return-value"></a>戻り値

の幅`CRect`。

### <a name="remarks"></a>解説

幅は負の値にできます。

> [!NOTE]
> 四角形を正規化する必要があります。 この関数を呼び出す前に[、NormalizeRect](#normalizerect)を呼び出して四角形を正規化できます。

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
[Rect](/windows/win32/api/windef/ns-windef-rect)
