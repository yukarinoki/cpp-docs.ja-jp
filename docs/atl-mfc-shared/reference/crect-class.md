---
title: クラスを含む CRect |Microsoft ドキュメント
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
ms.openlocfilehash: a819cfc95588dc9225570a82b8a359d90a8f6b9f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
|[CRect::BottomRight](#bottomright)|右下隅の点を返します`CRect`です。|  
|[CRect::CenterPoint](#centerpoint)|中心点を返します`CRect`です。|  
|[CRect::CopyRect](#copyrect)|コピーを元の四角形の寸法`CRect`です。|  
|[CRect::DeflateRect](#deflaterect)|幅と高さの減少`CRect`です。|  
|[CRect::EqualRect](#equalrect)|指定するかどうか`CRect`が指定された四角形と等しい。|  
|[CRect::Height](#height)|高さを計算`CRect`です。|  
|[CRect::InflateRect](#inflaterect)|幅と高さの増加`CRect`です。|  
|[CRect::IntersectRect](#intersectrect)|セット`CRect`の 2 つの四角形の交差部分に等しい。|  
|[CRect::IsRectEmpty](#isrectempty)|指定するかどうか`CRect`が空です。 `CRect` 空の場合は幅または高さは 0 です。|  
|[CRect::IsRectNull](#isrectnull)|決定するかどうか、**上部**、**下部**、**左**、および**右**メンバー変数が 0 に等しいすべて。|  
|[CRect::MoveToX](#movetox)|移動`CRect`に指定した x 座標を指定します。|  
|[CRect::MoveToXY](#movetoxy)|移動`CRect`を指定した x 座標と y 座標。|  
|[CRect::MoveToY](#movetoy)|移動`CRect`に指定された座標の y 座標。|  
|[CRect::NormalizeRect](#normalizerect)|幅と高さを標準化`CRect`です。|  
|[CRect::OffsetRect](#offsetrect)|移動`CRect`指定されたオフセットします。|  
|[CRect::PtInRect](#ptinrect)|内で指定したポイントがあるかどうかを判断`CRect`です。|  
|[CRect::SetRect](#setrect)|寸法を設定`CRect`です。|  
|[CRect::SetRectEmpty](#setrectempty)|セット`CRect`四角形が空であることを (すべての座標は 0 に等しい) にします。|  
|[CRect::Size](#size)|サイズを計算`CRect`です。|  
|[CRect::SubtractRect](#subtractrect)|別の 1 つの四角形を減算します。|  
|[CRect::TopLeft](#topleft)|左上のポイントを返します`CRect`です。|  
|[CRect::UnionRect](#unionrect)|セット`CRect`2 つの四角形の和集合に等しい。|  
|[CRect::Width](#width)|幅を計算`CRect`です。|  
  
### <a name="public-operators"></a>パブリック演算子    
|名前|説明|  
|----------|-----------------|  
|[CRect::operator-](#operator_-)|指定したオフセットを減算`CRect`を縮小または`CRect`し、その結果を返します`CRect`です。|  
|[CRect::operator LPCRECT](#operator_lpcrect)|変換、`CRect`を**LPCRECT**です。|  
|[CRect::operator LPRECT](#operator_lprect)|`CRect` を `LPRECT` に変換します。|  
|[CRect::operator! =](#operator_neq)|指定するかどうか`CRect`が四角形と等しくないです。|  
|[CRect::operator &amp;](#operator_amp)|交差部分を作成`CRect`四角形は、その結果を返しますと`CRect`です。|  
|[CRect::operator &amp;=](#operator_amp_eq)|セット`CRect`の交差部分に等しい`CRect`と四角形。|  
|[CRect::operator |](#operator_or)|和集合を作成`CRect`四角形は、その結果を返しますと`CRect`です。|  
|[CRect::operator |=](#operator_or_eq)|セット`CRect`の共用体に等しい`CRect`と四角形。|  
|[CRect::operator +](#operator_add)|指定したオフセットを追加`CRect`拡張または`CRect`し、その結果を返します`CRect`です。|  
|[CRect::operator + =](#operator_add_eq)|指定したオフセットへの追加`CRect`拡張または`CRect`です。|  
|[CRect::operator =](#operator_eq)|コピーする四角形の寸法`CRect`です。|  
|[CRect::operator =](#operator_-_eq)|指定したオフセットを減算`CRect`を縮小または`CRect`です。|  
|[CRect::operator = =](#operator_eq_eq)|指定するかどうか`CRect`と等しい四角形をします。|  
  
## <a name="remarks"></a>コメント  
 `CRect` 操作するメンバーの機能も含まれます`CRect`オブジェクトと Windows`RECT`構造体。  
  
 A`CRect`オブジェクトは、関数のパラメーターとして渡すことができます限り、`RECT`構造体、 **LPCRECT**、または`LPRECT`渡すことができます。  
  
> [!NOTE]
>  このクラスから派生、 **tagRECT**構造体。 (名前**tagRECT**の以下のよく使用される名前は、`RECT`構造です)。つまり、このデータ メンバー (**左**、**上部**、**右**、および**下部**) の`RECT`構造がアクセスできるデータメンバー`CRect`です。  
  
 A`CRect`四角形の左上および右下のポイントを定義するメンバー変数が含まれています。  
  
 指定する場合、`CRect`は、正規化を構築するように注意する必要があります: 左座標の値が右側の上端とのより小さいことなどが下部より小さいつまり、します。 たとえば、(10, 10) の左、上と (20, 20) の右下正規化された四角形が (20, 20) の左、上 (10, 10) の右下定義し、正規化されていない四角形。 多く、四角形が正規化されていない場合`CRect`メンバー関数は、正しくない結果を返す可能性があります。 (を参照してください[CRect::NormalizeRect](#normalizerect)これらの関数の一覧についてはします)。正規化された四角形を必要とする関数を呼び出す前に呼び出すことによって正規化されていない四角形を正規化することができます、`NormalizeRect`関数。  
  
 操作するときに警告を使用して、`CRect`で、 [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp)と[CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp)メンバー関数。 かどうかディスプレイ コンテキストのマッピング モードは y 範囲が負の場合と同様になるよう`MM_LOENGLISH`、し`CDC::DPtoLP`を変換する、`CRect`の最上位は最下部より大きいできるようにします。 などの関数**高さ**と**サイズ**、変換後の高さに負の値を返します`CRect`、および四角形は、非正規化されます。  

  
 オーバー ロードを使用するときに`CRect`演算子、最初のオペランドがある必要があります、 `CRect`; 2 つ目は、いずれか、 [RECT](../../mfc/reference/rect-structure1.md)構造体、または`CRect`オブジェクト。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltypes.h  
  
##  <a name="bottomright"></a>  CRect::BottomRight  
 座標はへの参照として返されます、 [CPoint](cpoint-class.md)オブジェクトに含まれている`CRect`です。  
  
```  
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 四角形の右下隅の座標。  
  
### <a name="remarks"></a>コメント  
 この関数は、取得、または四角形の右下隅の設定を使用することができます。 代入演算子の左側にあるこの関数を使用して、コーナーを設定します。  
  
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
 中心点を計算`CRect`左と右の値を追加して、2 つで除算し、上部と下部の値を追加する 2 で除算しています。  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 A`CPoint`の中心点のあるオブジェクトを`CRect`です。  
  
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
 コピー、`lpSrcRect`に四角形`CRect`です。  
  
```  
void CopyRect(LPCRECT lpSrcRect) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSrcRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`がコピーされるオブジェクト。  
  
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
 左位置を示す`CRect`です。  
  
 *t*  
 指定の最上部`CRect`です。  
  
 *r*  
 右の位置を示す`CRect`です。  
  
 *b*  
 指定の下部にある`CRect`です。  
  
 *srcRect*  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)の座標で構造`CRect`です。  
  
 `lpSrcRect`  
 指す、`RECT`の座標で構造`CRect`です。  
  
 `point`  
 構築される四角形の最初の場所を指定します。 左上隅に対応します。  
  
 `size`  
 左上隅から構築される四角形の右下隅までの距離を指定します。  
  
 *左上端*  
 左上の位置を示す`CRect`です。  
  
 *BottomRight*  
 右下の位置を示す`CRect`です。  
  
### <a name="remarks"></a>コメント  
 引数が指定されていない場合**左**、**上部**、**右**、および**下部**メンバーは初期化されていません。  
  
 `CRect`(**Const RECT &**) および`CRect`(**LPCRECT**) コンス トラクターで実行、 [CopyRect](#copyrect)です。 他のコンス トラクターは、直接オブジェクトのメンバー変数を初期化します。  
  
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
 `DeflateRect` 縮小`CRect`中心の方向、両側に移動しています。  
  
```  
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左右左側を圧縮する単位の数を示す`CRect`です。  
  
 *y*  
 上下を圧縮する単位の数を指定`CRect`です。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)または[CSize](csize-class.md)圧縮する単位の数を指定する`CRect`です。 `cx`値左辺と右辺を圧縮する単位の数を指定し、`cy`値上部と下部を圧縮する単位の数を指定します。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`それぞれの側を圧縮する単位の数を指定します。  
  
 *l*  
 左側にあるを圧縮する単位の数を指定`CRect`です。  
  
 *t*  
 一番上を圧縮する単位の数を指定`CRect`です。  
  
 *r*  
 右側にあるを圧縮する単位の数を指定`CRect`です。  
  
 *b*  
 下部を圧縮する単位の数を指定`CRect`です。  
  
### <a name="remarks"></a>コメント  
 これを行う`DeflateRect`左側および上部にユニットを追加し、右および下から単位を減算します。 パラメーター`DeflateRect`は署名値以外の正の値が deflate`CRect`負の値は拡大とします。  
  
 最初の 2 つのオーバー ロードは、両方の反対側の組み合わせを縮小`CRect`2 回の合計幅が減らさように*x* (または`cx`) し、2 回、全体の高さが減らさ*y* (または`cy`)。 その他の 2 つのオーバー ロードの各辺の縮小`CRect`他のユーザーとは無関係にします。  
  
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
 指定するかどうか`CRect`が指定された四角形と等しい。  
  
```  
BOOL EqualRect(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`四角形の左上隅および右下隅の座標を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つの四角形は、同じ上、左、下、および右の値がある場合は 0 以外。それ以外の場合 0 を返します。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 高さを計算`CRect`下の値から最上位の値を減算します。  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 高さ`CRect`です。  
  
### <a name="remarks"></a>コメント  
 結果として得られる値は、負の値で指定できます。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 `InflateRect` 拡張`CRect`中心から離れて、両側を移動することによってです。  
  
```  
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左右を左に拡大するためのユニットの数を示す`CRect`です。  
  
 *y*  
 上下に拡大するためのユニットの数を指定`CRect`です。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)または[CSize](csize-class.md)を拡大するためのユニットの数を指定する`CRect`です。 `cx`値は、左辺と右辺を拡大するためのユニットの数を指定し、`cy`値は、上部と下部を拡大するためのユニットの数を指定します。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`各辺を拡大する単位の数を指定します。  
  
 *l*  
 左側にあるを拡大するためのユニットの数を指定`CRect`です。  
  
 *t*  
 一番上を拡大するためのユニットの数を指定`CRect`です。  
  
 *r*  
 右側にあるを拡大するためのユニットの数を指定`CRect`です。  
  
 *b*  
 下部を拡大するためのユニットの数を指定`CRect`です。  
  
### <a name="remarks"></a>コメント  
 これを行う`InflateRect`から左、上の単位を減算し、右および下にユニットを追加します。 パラメーターの`InflateRect`サインインしている値です。 正の値は拡大`CRect`と負の値は縮小します。  
  
 最初の 2 つのオーバー ロードは、両方の反対側の組み合わせを拡大`CRect`、全体の幅は 2 回ずつ増加できるように*x* (または`cx`)、全体の高さを 2 倍に増やす*y* (または`cy`)。 その他の 2 つのオーバー ロードの各辺の拡大`CRect`他のユーザーとは無関係にします。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(0, 0, 300, 300);
 rect.InflateRect(50, 200);

 // rect is now (-50, -200, 350, 500)
 ASSERT(rect == CRect(-50, -200, 350, 500));  
```
  
##  <a name="intersectrect"></a>  CRect::IntersectRect  
 により、 `CRect` 2 つの既存の四角形の交差部分に等しい。  
  
```  
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect1`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`元の四角形を格納しているオブジェクト。  
  
 `lpRect2`  
 指す、`RECT`構造または`CRect`元の四角形を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 積集合が空です。 ない場合は 0 以外。積集合が空の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 積集合は、両方の既存の四角形に含まれている最も大きな四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 指定するかどうか`CRect`が空です。  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`CRect`が空である 0 場合`CRect`空ではありません。  
  
### <a name="remarks"></a>コメント  
 四角形は、空の場合は幅または高さは 0 または負の値です。 異なる`IsRectNull`、四角形のすべての座標は、0 であるかどうかを決定します。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 上、左、下かどうかを判断し、右の値`CRect`すべてが 0 です。  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`CRect`左、上の下し、右の値はすべて 0 に等しいそれ以外の 0 です。  
  
### <a name="remarks"></a>コメント  
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
 指定された絶対 x 座標を四角形を移動するには、この関数を呼び出す*x*です。  
  
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
 この関数では、四角形を移動するを絶対 x 座標と y 座標を指定します。  
  
```  
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 四角形の左上隅の絶対 x 座標。  
  
 *y*  
 四角形の左上隅の絶対 y 座標。  
  
 `point`  
 A**ポイント**四角形の絶対の左上隅を指定する構造体。  
  
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
 絶対座標の y 座標で指定された四角形を移動するには、この関数を呼び出す*y*です。  
  
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
 正規化`CRect`高さと幅の両方に正の値ができるようにします。  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>コメント  
 四角形は正規化の第 4 象限配置に、座標の Windows を通常使用されます。 `NormalizeRect` 上位および下位の値を比較し、最上位は最下部より大きい場合は、それらをスワップします。 同様に、左が右側のより大きい場合、左と右の値を交換します。 この関数は、別のマッピング モードで処理する場合に便利ですし、反転された四角形。  
  
> [!NOTE]
>  次`CRect`メンバー関数が正常に動作するために正規化された四角形を必要とします[高さ](#height)、[幅](#width)、[サイズ](#size)、 [ 。IsRectEmpty](#isrectempty)、 [PtInRect](#ptinrect)、 [EqualRect](#equalrect)、 [UnionRect](#unionrect)、[示します](#intersectrect)、 [SubtractRect](#subtractrect)、[演算子 = =](#operator_eq_eq)、[演算子! =](#operator_neq)、[演算子&#124; ](#operator_or)、[演算子&#124;=](#operator_or_eq)、[演算子 (& a)](#operator_amp)、および[演算子 (& a) =](#operator_amp_eq)です。  
  
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
 移動`CRect`指定されたオフセットします。  
  
```  
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左に移動する量を指定します。 左に移動する負の値がある場合があります。  
  
 *y*  
 上下に移動する量を指定します。 上に移動する負の値がある場合があります。  
  
 `point`  
 含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)移動に使用する寸法の両方を指定するオブジェクト。  
  
 `size`  
 含まれています、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)移動に使用する寸法の両方を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 移動`CRect` *x* x 軸に単位と*y* y 軸に沿って単位です。 *X*と*y*パラメーターが符号付きの値のためは`CRect`およびが切り上げまたは切り捨てまたは右左に移動することができます。  
  
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

  
##  <a name="operator_lpcrect"></a>  CRect::operator LPCRECT 変換、`CRect`を[LPCRECT](../../mfc/reference/data-types-mfc.md)です。  

  
```  
operator LPCRECT() const throw();
```  
  
### <a name="remarks"></a>コメント  
 この関数を使用する場合のアドレスが必要ありません (**&**) 演算子。 この演算子は渡す際に自動的に使用する`CRect`オブジェクトを要求する関数を**LPCRECT**です。  
  

##  <a name="operator_lprect"></a>  CRect::operator LPRECT  
 変換、`CRect`を[LPRECT](../../mfc/reference/data-types-mfc.md)です。  

  
```
operator LPRECT() throw();
```  
  
### <a name="remarks"></a>コメント  
 この関数を使用する場合のアドレスが必要ありません (**&**) 演算子。 この演算子は渡す際に自動的に使用する`CRect`オブジェクトを要求する関数を`LPRECT`です。  
  
### <a name="example"></a>例  
 例を参照して[CRect::operator LPCRECT](#operator_lpcrect)です。  
  
##  <a name="operator_eq"></a>  CRect::operator =  
 割り当てます*srcRect*に`CRect`です。  
  
```  
void operator=(const RECT& srcRect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *srcRect*  
 元の四角形を指します。 指定できます、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`です。  
  
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
 決定するかどうか`rect`と等しい`CRect`左と右下隅の座標を比較することによってです。  
  
```  
BOOL operator==(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 元の四角形を指します。 指定できます、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`です。  
  
### <a name="return-value"></a>戻り値  
 等しい場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 決定するかどうか`rect`は等しくありません`CRect`左と右下隅の座標を比較することによってです。  
  
```  
BOOL operator!=(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 元の四角形を指します。 指定できます、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`です。  
  
### <a name="return-value"></a>戻り値  
 等しくない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 最初の 2 つのオーバー ロードは、移動`CRect`指定されたオフセットします。  
  
```  
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)四角形を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)四角形を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`のそれぞれの側を拡大するためのユニットの数を格納しているオブジェクト`CRect`です。  
  
### <a name="remarks"></a>コメント  
 パラメーターの*x*と*y* (または`cx`と`cy`) 値に追加する`CRect`です。  
  
 3 番目のオーバー ロードは、拡張`CRect`によって、パラメーターの各メンバーで指定された単位の数。  
  
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
 最初の 2 つのオーバー ロードは、移動`CRect`指定されたオフセットします。  
  
```  
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)四角形を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)四角形を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`のそれぞれの側を圧縮する単位の数を格納しているオブジェクト`CRect`です。  
  
### <a name="remarks"></a>コメント  
 パラメーターの*x*と*y* (または`cx`と`cy`) から値を減算する`CRect`です。  
  
 3 番目のオーバー ロードを縮小`CRect`によって、パラメーターの各メンバーで指定された単位の数。 このオーバー ロードの機能を[DeflateRect](#deflaterect)です。  
  
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
 セット`CRect`の交差部分に等しい`CRect`と`rect`です。  
  
```  
void operator&=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 含まれています、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`です。  
  
### <a name="remarks"></a>コメント  
 積集合は、両方の四角形に含まれている最も大きな四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 例を参照して[CRect::IntersectRect](#intersectrect)です。  
  
##  <a name="operator_or_eq"></a>  CRect::operator &#124;=  
 セット`CRect`の共用体に等しい`CRect`と`rect`です。  
  
```  
void operator|=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 含まれています、`CRect`または[RECT](../../mfc/reference/rect-structure1.md)です。  
  
### <a name="remarks"></a>コメント  
 共用体は、両方の四角形を含む最小の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 最初の 2 つのオーバー ロードを返す、`CRect`と等しいオブジェクト`CRect`指定したオフセット位置によって転置。  
  
```  
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)戻り値を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)戻り値を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`戻り値のそれぞれの側を拡大するためのユニットの数を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `CRect`移動または膨張させる`CRect`パラメーターで指定された単位数でします。  
  
### <a name="remarks"></a>コメント  
 パラメーターの*x*と*y* (または`cx`と`cy`) パラメーターに追加されます`CRect`の位置します。  
  
 3 番目のオーバー ロードを返します、新しい`CRect`と同じである`CRect`単位で指定された数のパラメーターの各メンバーによって値が大ききます。  
  
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
 最初の 2 つのオーバー ロードを返す、`CRect`と等しいオブジェクト`CRect`指定したオフセット位置によって転置。  
  
```  
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`戻り値を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または`CSize`戻り値を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`戻り値のそれぞれの側を圧縮する単位の数を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `CRect`から移動または縮小された結果として得られる`CRect`パラメーターで指定された単位数でします。  
  
### <a name="remarks"></a>コメント  
 パラメーターの*x*と*y* (または`cx`と`cy`) からのパラメーターが差し引かれます`CRect`の位置します。  
  
 3 番目のオーバー ロードを返します、新しい`CRect`と同じである`CRect`パラメーターの各メンバーで指定された単位数で縮小されました。 このオーバー ロードの機能を[DeflateRect](#deflaterect)ではなく、 [SubtractRect](#subtractrect)です。  
  
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
 返します、`CRect`の積集合は`CRect`と*rect2*です。  
  
```  
CRect operator&(const RECT& rect2) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *rect2*  
 含まれています、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`です。  
  
### <a name="return-value"></a>戻り値  
 A`CRect`の積集合は`CRect`と*rect2*です。  
  
### <a name="remarks"></a>コメント  
 積集合は、両方の四角形に含まれている最も大きな四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 返します、`CRect`の和集合である`CRect`と*rect2*です。  
  
```   
CRect operator|(const RECT& 
rect2) const throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 *rect2*  
 含まれています、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`です。  
  
### <a name="return-value"></a>戻り値  
 A`CRect`の和集合である`CRect`と*rect2*です。  
  
### <a name="remarks"></a>コメント  
 共用体は、両方の四角形を含む最小の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 内で指定したポイントがあるかどうかを判断`CRect`です。  
  
```   
BOOL PtInRect(POINT point) const throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 内のポイントにある場合は 0 以外`CRect`。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 内では、ポイント`CRect`側、左端または上端にあるまたは 4 辺すべて内にあるかどうか。 右端または下端にあるポイントは外側`CRect`です。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 `x1`  
 左上隅の x 座標を指定します。  
  
 `y1`  
 左上隅の y 座標を指定します。  
  
 `x2`  
 右下隅の x 座標を指定します。  
  
 `y2`  
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
 により、 `CRect` null 四角形によってすべての座標をゼロに設定します。  
  
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
 `cx`と`cy`の幅と高さに戻り値のメンバーが含まれて`CRect`です。  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 A [CSize](csize-class.md)オブジェクトのサイズを含む`CRect`です。  
  
### <a name="remarks"></a>コメント  
 高さまたは幅に負の値を使用することができます。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(10, 10, 50, 50);
 CSize sz = rect.Size();
 ASSERT(sz.cx == 40 && sz.cy == 40);  
```

##  <a name="subtractrect"></a>  CRect::SubtractRect  
 ディメンションは、 **CRect**の減算に等しい`lpRectSrc2`から`lpRectSrc1`です。  
  
```  
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRectSrc1`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`四角形が減算元となるオブジェクト。  
  
 `lpRectSrc2`  
 指す、`RECT`構造または`CRect`四角形から減算するオブジェクトを指す、`lpRectSrc1`パラメーター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 減算が最小の四角形内の地点のすべてを含む`lpRectScr1`の交差部分に含まれていない`lpRectScr1`と*lpRectScr2*です。  
  
 によって指定される四角形`lpRectSrc1`を変更しないことで、四角形が指定された場合`lpRectSrc2`によって指定される四角形を完全に重なっていない*lpRectSrc1*少なくとも 1 つの x 方向または y 方向です。  
  
 たとえば場合、`lpRectSrc1`された (10,10、100,100) および`lpRectSrc2`された (50,50、150,150)、四角形を指す`lpRectSrc1`は変更されず、関数が返されるときにします。 場合`lpRectSrc1`されました (10,10、100,100) と`lpRectSrc2`された (50,10、150,150)、ただし、四角形によって示される`lpRectSrc1`座標 (10, 10, 50,100) が含まれます関数が返されます。  
  
 `SubtractRect` 同じではありません[演算子 -](#operator_-)も[演算子-=](#operator_-_eq)です。 これまでに呼び出してこれらの演算子のどちらも`SubtractRect`します。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 座標はへの参照として返されます、 [CPoint](cpoint-class.md)オブジェクトに含まれている`CRect`です。  
  
```  
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 四角形の左上隅の座標。  
  
### <a name="remarks"></a>コメント  
 この関数は、取得、または四角形の左上隅の設定を使用することができます。 代入演算子の左側にあるこの関数を使用して、コーナーを設定します。  
  
### <a name="example"></a>例  
 例を参照して[CRect::CenterPoint](#centerpoint)です。  
  
##  <a name="unionrect"></a>  CRect::UnionRect  
 ディメンションは、 `CRect` 2 つのソース四角形の和集合に等しい。  
  
```  
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect1`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`元の四角形を格納しています。  
  
 `lpRect2`  
 指す、`RECT`または`CRect`元の四角形を格納しています。  
  
### <a name="return-value"></a>戻り値  
 和集合が空です。 ない場合は 0 以外。和集合が空の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 共用体は、両方の四角形を含む最小の四角形です。  
  
 Windows; 空の四角形の寸法は無視されます。つまり、四角形の高さを持たず、幅がないか。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
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
 幅を計算`CRect`右の値から左の値を減算します。  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 幅`CRect`です。  
  
### <a name="remarks"></a>コメント  
 幅は負の値にすることはできます。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  

```cpp  
   CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
   // nWid is now 60
   ASSERT(nWid == 60);   
```
## <a name="see-also"></a>関連項目  
 [CPoint クラス](cpoint-class.md)   
 [CSize クラス](csize-class.md)   
 [RECT](../../mfc/reference/rect-structure1.md)


