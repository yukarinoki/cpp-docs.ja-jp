---
title: CPoint クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 36dc82c03f13b4708d705d9fd66eff26870c8346
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365394"
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
|[CPoint::Offset](#offset)|値を追加、 **x**と**y**のメンバー、`CPoint`です。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CPoint::operator-](#operator_-)|差を返します、`CPoint`とサイズ、またはポイント、またはサイズの差 2 つのポイント、または負のサイズのオフセットの符号を反転します。|  
|[CPoint::operator! =](#operator_neq)|2 つのポイント間の不等性を確認します。|  
|[CPoint::operator +](#operator_add)|合計を返して、`CPoint`とサイズ、またはポイント、または`CRect`サイズによって相殺します。|  
|[CPoint::operator + =](#operator_add_eq)|オフセット`CPoint`サイズまたはポイントを追加しています。|  
|[CPoint::operator =](#operator_-_eq)|オフセット`CPoint`サイズまたはポイントを差し引くことで。|  
|[CPoint::operator = =](#operator_eq_eq)|2 つのポイント間の等価性を確認します。|  
  
## <a name="remarks"></a>コメント  
 操作するメンバー関数も含まれています。`CPoint`と[ポイント](../../mfc/reference/point-structure1.md)構造体。  
  
 A`CPoint`オブジェクトには任意の場所に使用される、`POINT`構造体を使用します。 「サイズ」と対話するこのクラスの演算子は、両方を受け付ける[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトまたは[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)、構造体のため、2 つは互換性があります。  
  
> [!NOTE]
>  このクラスから派生します`tagPOINT`構造体。 (名前`tagPOINT`の名前を使用頻度の低い、`POINT`構造です)。つまり、このデータ メンバーの`POINT`構造体、`x`と`y`のアクセス可能なデータ メンバーである`CPoint`です。  
  
> [!NOTE]
>  詳細については、ユーティリティ クラスを共有 (と同様に`CPoint`) を参照してください[共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)です。  
  
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
 `initX`  
 `x` の `CPoint` メンバーの値を指定します。  
  
 `initY`  
 `y` の `CPoint` メンバーの値を指定します。  
  
 `initPt`  
 [ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`初期化するために使用される値を指定する`CPoint`です。  
  
 `initSize`  
 [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)初期化するために使用される値を指定する`CPoint`です。  
  
 `dwPoint`  
 `x` の下位ワードに `dwPoint` メンバー、`y` の上位ワードに `dwPoint` メンバーを設定します。  
  
### <a name="remarks"></a>コメント  
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
 値を追加、 **x**と**y**のメンバー、`CPoint`です。  
  
```  
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x オフセット*  
 オフセットの量を指定します、 **x**のメンバー、`CPoint`です。  
  
 *y オフセット*  
 オフセットの量を指定します、 **y**のメンバー、`CPoint`です。  
  
 `point`  
 量を指定します ([ポイント](../../mfc/reference/point-structure1.md)または`CPoint`) のオフセット、`CPoint`です。  
  
 `size`  
 量を指定します ([サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)または[CSize](../../atl-mfc-shared/reference/csize-class.md)) のオフセット、`CPoint`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>  CPoint::operator = =  
 2 つのポイント間の等価性を確認します。  
  
```  
BOOL operator==(POINT point) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
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
 `point`  
 含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポイントが等しくない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>  CPoint::operator + =  
 最初のオーバー ロードを追加するサイズ、`CPoint`です。  
  
```  
void operator+=(SIZE size) throw(); 
void operator+=(POINT point) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 含まれています、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。  
  
 `point`  
 含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 2 番目のオーバー ロードするポイントを追加する、`CPoint`です。  
  
 追加することでどちらの場合も、加算が行われます、 **x** (または**cx**) を右辺のオペランドのメンバー、 **x**のメンバー、`CPoint`を追加して、 **y** (または**cy**) を右辺のオペランドのメンバー、 **y**のメンバー、`CPoint`です。  
  
 たとえば、追加する`CPoint(5, -7)`を含む変数を`CPoint(30, 40)`に変数が変更される`CPoint(35, 33)`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>  CPoint::operator =  
 最初のオーバー ロードからサイズを減算し、`CPoint`です。  
  
```  
void operator-=(SIZE size) throw(); 
void operator-=(POINT point) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 含まれています、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。  
  
 `point`  
 含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 2 番目のオーバー ロードは、減算、ポイントから、`CPoint`です。  
  
 どちらの場合は、減算は減算することによって行われます、 **x** (または**cx**) から右のオペランドのメンバー、 **x**のメンバー、 `CPoint` を差し引く**y** (または**cy**) から右のオペランドのメンバー、 **y**のメンバー、`CPoint`です。  
  
 たとえば、減算`CPoint(5, -7)`を含む変数から`CPoint(30, 40)`に変数が変更される`CPoint(25, 47)`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]  
  
##  <a name="operator_add"></a>  CPoint::operator +  
 この演算子のオフセットを使用して`CPoint`によって、`CPoint`または`CSize`オブジェクト、またはオフセット、`CRect`によって、`CPoint`です。  
  
```  
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 含まれています、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。  
  
 `point`  
 含まれています、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。  
  
 `lpRect`  
 ポインターが含まれています、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 A `CPoint` 、サイズをオフセットする、 **CPoint** 、点をオフセットする、または**CRect**点をオフセットします。  
  
### <a name="remarks"></a>コメント  
 たとえば、最初の 2 つのオーバー ロードのいずれかの点をオフセットするを使用して`CPoint(25, -19)`ポイントによって`CPoint(15, 5)`またはサイズ`CSize(15, 5)`値を返します`CPoint(40, -14)`です。  
  
 後でオフセットされている四角形を返します、ポイントに四角形を追加する、 **x**と**y**ポイントで指定された値。 たとえば、四角形をオフセットする最後のオーバー ロードを使用して`CRect(125, 219, 325, 419)`ポイントによって`CPoint(25, -19)`返します`CRect(150, 200, 350, 400)`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]  
  
##  <a name="operator_-"></a>  CPoint::operator-  
 減算する最初の 2 つのオーバー ロードのいずれかを使用して、`CPoint`または`CSize`オブジェクトから`CPoint`です。  
  
```  
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)オブジェクト。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。  
  
 `lpRect`  
 ポインター、 [RECT](../../mfc/reference/rect-structure1.md)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 A `CSize` 2 つのポイント間の違いは、 `CPoint` 、サイズの否定をオフセットする、 `CRect` 、ポイントの否定をオフセットするまたは`CPoint`は、ポイントの符号を反転します。  
  
### <a name="remarks"></a>コメント  
 3 番目のオーバー ロードのオフセット、`CRect`の符号を反転して`CPoint`です。 符号反転する単項演算子を使用して最後に、`CPoint`です。  
  
 たとえば、2 つのポイント間の違いを検索する最初のオーバー ロードを使用して`CPoint(25, -19)`と`CPoint(15, 5)`返します`CSize(10, -24)`です。  
  
 減算、`CSize`から`CPoint`上と同じ計算が返されます、`CPoint`オブジェクトは、`CSize`オブジェクト。 たとえば、2 番目のオーバー ロードを使用して、ポイント間の違いを検索する`CPoint(25, -19)`およびサイズ`CSize(15, 5)`返します`CPoint(10, -24)`です。  
  
 符号を反転して四角形のオフセットを返します点から四角形を引いて、 **x**と**y**ポイントで指定された値。 たとえば、四角形をオフセットする最後のオーバー ロードを使用して`CRect(125, 200, 325, 400)`ポイントによって`CPoint(25, -19)`返します`CRect(100, 219, 300, 419)`です。  
  
 ポイントを無効にするのにには、単項演算子を使用します。 たとえば、単項演算子を使用して、ポイントと`CPoint(25, -19)`返します`CPoint(-25, 19)`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [POINT 構造体](../../mfc/reference/point-structure1.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)   
 [CSize クラス](../../atl-mfc-shared/reference/csize-class.md)



