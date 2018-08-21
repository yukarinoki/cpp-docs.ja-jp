---
title: Platform::Collections::VectorIterator クラス |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
dev_langs:
- C++
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68198edb54c79d0872b3181d4ffe36df21a8cf02
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208472"
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform::Collections::VectorIterator クラス
Windows ランタイム IVector インターフェイスから派生したオブジェクトの標準テンプレート ライブラリ反復子を提供します。  
  
 VectorIterator の型 VectorProxy 要素を格納するプロキシ反復子は、\<T >。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename T>  
class VectorIterator;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 VectorIterator テンプレート クラスの型名。  
  
### <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`difference_type`|ポインターの相違点 (ptrdiff_t)。|  
|`iterator_category`|ランダム アクセス反復子 (::std::random_access_iterator_tag) のカテゴリ。|  
|`pointer`|Platform::Collections::Details::VectorProxy 内部型へのポインター\<T > は、VectorIterator の実装に必要な。|  
|`reference`|Platform::Collections::Details::VectorProxy 内部型への参照を\<T >、つまり、VectorIterator の実装に必要な。|  
|`value_type`|`T` 型名。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[VectorIterator::VectorIterator](#ctor)|VectorIterator クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[VectorIterator::operator- 演算子](#operator-minus)|現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。|  
|[VectorIterator::operator-- 演算子](#operator-decrement)|現在の VectorIterator をデクリメントします。|  
|[VectorIterator::operator!= 演算子](#operator-inequality)|現在の VectorIterator が、指定された VectorIterator と等しくないかどうかを示します。|  
|[VectorIterator::operator* 演算子](#operator-dereference)|現在の VectorIterator により指定された要素への参照を取得します。|  
|[VectorIterator::operator\[\]](#operator-at)|現在の VectorIterator から指定された転置にある要素への参照を取得します。|  
|[VectorIterator::operator+ 演算子](#operator-plus)|指定された VectorIterator から指定された転置にある要素を参照する VectorIterator を返します。|  
|[VectorIterator::operator++ 演算子](#operator-increment)|現在の VectorIterator をインクリメントします。|  
|[VectorIterator::operator+= 演算子](#operator-plus-assign)|指定されたディスプレイスメントだけ現在の VectorIterator をインクリメントします。|  
|[VectorIterator::operator< 演算子](#operator-less-than)|現在の VectorIterator が、指定された VectorIterator より小さいかどうかを示します。|  
|[Vectoriterator::operator\<= 演算子](#operator-less-than-or-equals)|現在の VectorIterator が、指定された VectorIterator 以下かどうかを示します。|  
|[VectorIterator::operator-= 演算子](#operator-subtract-assign)|指定されたディスプレイスメントだけ現在の VectorIterator をデクリメントします。|  
|[VectorIterator::operator== 演算子](#operator-equality)|現在の VectorIterator が、指定された VectorIterator と等しいかどうかを示します。|  
|[VectorIterator::operator> 演算子](#operator-greater-than)|現在の VectorIterator が、指定された VectorIterator より大きいかどうかを示します。|  
|[VectorIterator::operator-> 演算子](#operator-arrow)|現在の VectorIterator により参照される要素のアドレスを取得します。|  
|[VectorIterator::operator>= 演算子](#operator-greater-than-or-equal)|現在の VectorIterator が、指定された VectorIterator 以上であるかどうかを示します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `VectorIterator`  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  

## <a name="operator-arrow"></a>  Vectoriterator::operator-&gt;演算子
現在の VectorIterator により参照される要素のアドレスを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の VectorIterator により参照される要素の値。  
  
 戻り値の型は、この演算子の実装に必要な、指定されていない内部型です。  
  


## <a name="operator-decrement"></a>  Vectoriterator::operator - 演算子
現在の VectorIterator をデクリメントします。  
  
### <a name="syntax"></a>構文  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(int);  
```  
  
### <a name="return-value"></a>戻り値  
 最初の構文は、現在の VectorIterator をデクリメントしてから返します。 2 番目の構文は、現在の VectorIterator のコピーを返し、現在の VectorIterator をデクリメントします。  
  
### <a name="remarks"></a>Remarks  
 最初の VectorIterator 構文は、現在の VectorIterator の前置デクリメントを実行します。  
  
 2 番目の構文は、現在の VectorIterator に後置デクリメントを実行します。 `int` 2 番目の構文で型を後置デクリメント演算、実際の整数オペランドではなくを示します。  
  


## <a name="operator-dereference"></a>  Vectoriterator::operator\*演算子
現在の VectorIterator により指定される要素のアドレスを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の VectorIterator により指定される要素。  
  


## <a name="operator-equality"></a>  Vectoriterator::operator = 演算子
現在の VectorIterator が、指定された VectorIterator と等しいかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```  
bool operator==(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 別の VectorIterator。  
  
### <a name="return-value"></a>戻り値  
 現在の VectorIterator が `true` と等しい場合は `other`。それ以外の場合は `false`。  
  


## <a name="operator-greater-than"></a>  Vectoriterator::operator&gt;演算子
現在の VectorIterator が、指定された VectorIterator より大きいかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
  
bool operator>(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 別の VectorIterator。  
  
### <a name="return-value"></a>戻り値  
 `true` 現在の VectorIterator がより大きい場合`other`、それ以外の`false`します。  
  


## <a name="operator-greater-than-or-equals"></a>  Vectoriterator::operator&gt;= 演算子
現在の VectorIterator が、指定された VectorIterator 以上であるかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
  
bool operator>=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 別の VectorIterator。  
  
### <a name="return-value"></a>戻り値  
 現在の VectorIterator が `true` 以上の場合は `other`。それ以外の場合は `false`。    


## <a name="operator-increment"></a>  Vectoriterator::operator++ 演算子
現在の VectorIterator をインクリメントします。  
  
### <a name="syntax"></a>構文  
  
```    
VectorIterator& operator++();  
VectorIterator operator++(int);  
```  
  
### <a name="return-value"></a>戻り値  
 最初の構文は、現在の VectorIterator をインクリメントしてから返します。 2 番目の構文は、現在の VectorIterator のコピーを返し、現在の VectorIterator をインクリメントします。  
  
### <a name="remarks"></a>Remarks  
 最初の VectorIterator 構文は、現在の VectorIterator の前置インクリメントを実行します。  
  
 2 番目の構文は、現在の VectorIterator に後置インクリメントを実行します。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置インクリメント演算を示します。  
  


## <a name="operator-inequality"></a>  Vectoriterator::operator! = 演算子
現在の VectorIterator が、指定された VectorIterator と等しくないかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```  
bool operator!=(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 別の VectorIterator。  
  
### <a name="return-value"></a>戻り値  
 `true` 現在の VectorIterator が等しくない場合`other`、それ以外の`false`します。  
  


## <a name="operator-less-than"></a>  Vectoriterator::operator&lt;演算子
現在の VectorIterator が、指定された VectorIterator より小さいかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
  
bool operator<(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 別の VectorIterator。  
  
### <a name="return-value"></a>戻り値  
 現在の VectorIterator が `true` より小さい場合は `other`。それ以外の場合は `false`。  
  


## <a name="operator-less-than-or-equals"></a>  Vectoriterator::operator&lt;= 演算子
現在の VectorIterator が、指定された VectorIterator 以下かどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
  
bool operator<=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 別の VectorIterator。  
  
### <a name="return-value"></a>戻り値  
 `true` 現在の VectorIterator と等しいまたはそれよりも小さいかどうか`other`、それ以外の`false`します。  
  


## <a name="operator-minus"></a>  Vectoriterator::operator-演算子
現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。  
  
### <a name="syntax"></a>構文  
  
```  
  
VectorIterator operator-(difference_type n) const;  
  
difference_type operator-(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `n`  
 要素の数。  
  
 `other`  
 別の VectorIterator。  
  
### <a name="return-value"></a>戻り値  
 最初の演算子構文は、VectorIterator オブジェクトを取得する`n`要素が現在の VectorIterator より小さい。 2 番目の演算子構文は、現在の要素の数を返します、 `other` VectorIterator。  
  


## <a name="operator-plus-assign"></a>  Vectoriterator::operator + = 演算子
指定されたディスプレイスメントだけ現在の VectorIterator をインクリメントします。  
  
### <a name="syntax"></a>構文  
  
```  
VectorIterator& operator+=(difference_type n);  
```  
  
### <a name="parameters"></a>パラメーター  
 `n`  
 整数の転置。  
  
### <a name="return-value"></a>戻り値  
 更新された VectorIterator。  
  


## <a name="operator-plus"></a>  ectorIterator::operator + 演算子
指定された VectorIterator から指定された転置にある要素を参照する VectorIterator を返します。  
  
### <a name="syntax"></a>構文  
  
```  
  
VectorIterator operator+(difference_type n);  
  
template <typename T>  
inline VectorIterator<T> operator+(
  ptrdiff_t n, 
  const VectorIterator<T>& i);  
  
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 2 番目の構文では、VectorIterator の型名。  
  
 `n`  
 整数のディスプレイスメント。  
  
 `i`  
 2 番目の構文では、VectorIterator。  
  
### <a name="return-value"></a>戻り値  
 最初の構文では、現在の VectorIterator から指定された転置にある要素を参照する VectorIterator。  
  
 2 番目の構文では、`i` パラメーターの先頭から指定された転置にある要素を参照する VectorIterator。  
  
### <a name="remarks"></a>Remarks  
 最初の構文例  
  


## <a name="operator-minus-equals"></a>  Vectoriterator::operator-= 演算子
指定されたディスプレイスメントだけ現在の VectorIterator をデクリメントします。  
  
### <a name="syntax"></a>構文  
  
```  
VectorIterator& operator-=(difference_type n);  
```  
  
### <a name="parameters"></a>パラメーター  
 `n`  
 整数のディスプレイスメント。  
  
### <a name="return-value"></a>戻り値  
 更新された VectorIterator。  
  


## <a name="operator-at"></a>  VectorIterator::operator\[\]
現在の VectorIterator から指定された転置にある要素への参照を取得します。  
  
### <a name="syntax"></a>構文  
  
```    
reference operator[](difference_type n) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `n`  
 整数のディスプレイスメント。  
  
### <a name="return-value"></a>戻り値  
 現在の VectorIterator からの `n` 個の要素によって転置される要素。  
  


## <a name="ctor"></a>  Vectoriterator::vectoriterator コンス トラクター
VectorIterator クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```    
VectorIterator();  
  
explicit VectorIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
### <a name="parameters"></a>パラメーター  
 `v`  
 IVector\<T > オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 最初の構文例は既定のコンストラクターです。 2 番目の構文例は、IVector から VectorIterator を構築するために使用する明示的なコンス トラクター\<T > オブジェクト。  
  


  
## <a name="see-also"></a>関連項目  
 [プラットフォーム Namespace](platform-namespace-c-cx.md)