---
title: CSize クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
dev_langs:
- C++
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18c48ccf2d1d7f424ca9b95f9dcbf7a2953a52aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362958"
---
# <a name="csize-class"></a>CSize クラス
Windows の [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) 構造体と同様に、相対座標や位置を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSize : public tagSIZE 
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSize::CSize](#csize)|`CSize` オブジェクトを構築します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSize::operator-](#operator_-)|2 つのサイズを減算します。|  
|[CSize::operator! =](#operator_neq)|非等値の間のチェック`CSize`とサイズ。|  
|[CSize::operator +](#operator_add)|2 つのサイズを追加します。|  
|[CSize::operator + =](#operator_add_eq)|追加するサイズを`CSize`です。|  
|[CSize::operator =](#operator_-_eq)|サイズを減算`CSize`です。|  
|[CSize::operator = =](#operator_eq_eq)|間の等値チェック`CSize`とサイズ。|  
  
## <a name="remarks"></a>コメント  
 このクラスから派生、**サイズ**構造体。 つまり、渡すことができます、`CSize`のパラメーターです、**サイズ**こととのデータ メンバーの**サイズ**構造のアクセス可能なデータ メンバーである`CSize`です。  
  
 **Cx**と**cy**のメンバー**サイズ**(および`CSize`) はパブリックです。 さらに、`CSize`を操作するメンバー関数を実装して、**サイズ**構造体。  
  
> [!NOTE]
>  詳細については、ユーティリティ クラスを共有 (と同様に`CSize`) を参照してください[共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagSIZE`  
  
 `CSize`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltypes.h  
  
##  <a name="csize"></a>  CSize::CSize  
 `CSize` オブジェクトを構築します。  
  
```  
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 *initCX*  
 セット、 **cx**のメンバー、`CSize`です。  
  
 *initCY*  
 セット、 **cy**のメンバー、`CSize`です。  
  
 `initSize`  
 [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または`CSize`初期化するために使用されるオブジェクト`CSize`です。  
  
 `initPt`  
 [ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`初期化するために使用されるオブジェクト`CSize`です。  
  
 `dwSize`  
 `DWORD` 初期化するために使用される`CSize`です。 下位ワードは、 **cx**メンバーであり、高位の単語が、 **cy**メンバー。  
  
### <a name="remarks"></a>コメント  
 引数が指定されていない場合**cx**と**cy**ゼロに初期化されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>  CSize::operator = =  
 2 つのサイズに等しいかどうかを確認します。  
  
```   
BOOL operator==(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>コメント  
 0 は、サイズが等しい場合は 0 以外を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]  
  
##  <a name="operator_neq"></a>  CSize::operator! =  
 2 つのサイズには、非等値を確認します。  
  
```   
BOOL operator!=(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>コメント  
 サイズが等しくない場合は 0 以外を返しますそれ以外の場合に 0 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>  CSize::operator + =  
 このサイズを追加`CSize`です。  
  
```   
void operator+=(SIZE size) throw(); 
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>  CSize::operator =  
 これからサイズを減算`CSize`です。  
  
```   
void operator-=(SIZE size) throw(); 
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]  
  
##  <a name="operator_add"></a>  CSize::operator +  
 これらの演算子は、この追加`CSize`値パラメーターの値にします。  
  
```   
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw(); 
```  
  
### <a name="remarks"></a>コメント  
 次の各演算子の説明を参照してください。  
  
- **演算子 + (** `size` **)** この操作は、2 つ追加`CSize`値。  
  
- **演算子 + (** `point` **)** この操作のオフセット (移動)、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)(または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) この値`CSize`値。 **Cx**と**cy** this のメンバー`CSize`値に追加されます、 **x**と**y**のデータ メンバー、**ポイント**値。 バージョンのと類似している[CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add)を受け取る、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)パラメーター。  
  
- **演算子 + (** `lpRect` **)** この操作のオフセット (移動)、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) (または[CRect](../../atl-mfc-shared/reference/crect-class.md)) この値`CSize`値。 **Cx**と**cy** this のメンバー`CSize`値に追加されます、**左**、**上部**、**右**、および**下部**のデータ メンバー、`RECT`値。 バージョンのと類似している[CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add)を受け取る、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)パラメーター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]  
  
##  <a name="operator_-"></a>  CSize::operator-  
 これらの演算子の最初の 3 つがこれを減算`CSize`値パラメーターの値にします。  
  
```   
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw(); 
```  
  
### <a name="remarks"></a>コメント  
 4 番目の演算子では、単項マイナス、変更の符号、`CSize`値。 次の各演算子の説明を参照してください。  
  
- **-演算子 (** `size` **)** この操作は、2 つを減算`CSize`値。  
  
- **-演算子 (** `point` **)** この操作のオフセット (移動)、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)これの加法に関する逆元での値を`CSize`値。 **Cx**と**cy**この`CSize`値から減算されて、 **x**と**y**のデータ メンバー、**ポイント**値。 バージョンのと類似している[CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-)を受け取る、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)パラメーター。  
  
- **-演算子 (** `lpRect` **)** この操作のオフセット (移動)、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)または[CRect](../../atl-mfc-shared/reference/crect-class.md)これの加法に関する逆元での値を`CSize`値。 **Cx**と**cy** this のメンバー`CSize`値から減算されて、**左**、**上部**、**右**、および**下部**のデータ メンバー、`RECT`値。 バージョンのと類似している[CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-)を受け取る、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)パラメーター。  
  
- **演算子のに関するページ ()** この操作を返しますこれの加法に関する逆元`CSize`値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint クラス](../../atl-mfc-shared/reference/cpoint-class.md)

