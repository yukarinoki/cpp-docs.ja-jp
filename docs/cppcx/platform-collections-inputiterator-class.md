---
title: Platform::Collections::InputIterator クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
dev_langs:
- C++
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7188cba0655e2ca89f82b60ffe9ee4b8ce94633a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089092"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform::Collections::InputIterator クラス
Windows ランタイムから派生したコレクションの標準テンプレート ライブラリ InputIterator を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename X>  
class InputIterator;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `X`  
 InputIterator テンプレート クラスの型名。  
  
### <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`difference_type`|ポインターの相違点 (ptrdiff_t)。|  
|`iterator_category`|入力反復子のカテゴリ (::std::input_iterator_tag)。|  
|`pointer`|ポインター、 `const X`|  
|`reference`|参照を `const X`|  
|`value_type`|`X` 型名。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[InputIterator::InputIterator](#ctor)|InputIterator クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[InputIterator::operator!= 演算子](#operator-inequality)|現在の InputIterator が、指定された InputIterator と等しくないかどうかを示します。|  
|[InputIterator::operator* 演算子](#operator-decrement)|現在の InputIterator により指定された要素への参照を取得します。|  
|[InputIterator::operator++ 演算子](#operator-increment)|現在の InputIterator をインクリメントします。|  
|[InputIterator::operator== 演算子](#operator-equality)|現在の InputIterator が、指定された InputIterator と等しいかどうかを示します。|  
|[InputIterator::operator-> 演算子](#operator-arrow)|現在の InputIterator により参照される要素のアドレスを取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `InputIterator`  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  

## <a name="ctor"></a>  Inputiterator::inputiterator コンス トラクター
InputIterator クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```  
InputIterator();  
explicit InputIterator(Windows::Foundation::Collections<X>^ iter);  
```  
  
### <a name="parameters"></a>パラメーター  
 `iter`  
 反復子オブジェクト。  
  


## <a name="operator-arrow"></a>  Inputiterator::operator-&gt;演算子
現在の InputIterator により指定される要素のアドレスを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
pointer operator->() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の InputIterator により指定される要素のアドレス。  
  


## <a name="operator-dereference"></a>  Inputiterator::operator * 演算子
現在の InputIterator により指定された要素への参照を取得します。  
  
### <a name="syntax"></a>構文  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の InputIterator により指定された要素。  
  


## <a name="operator-equality"></a>  Inputiterator::operator = = 演算子
現在の InputIterator が、指定された InputIterator と等しいかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```  
bool operator== (const InputIterator& other) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 別の InputIterator。  
  
### <a name="return-value"></a>戻り値  
 現在の InputIterator が `true` と等しい場合は `other`。それ以外の場合は `false`。  
  


## <a name="operator-increment"></a>  Inputiterator::operator++ 演算子
現在の InputIterator をインクリメントします。  
  
### <a name="syntax"></a>構文  
  
```    
InputIterator& operator++();   
InputIterator operator++(int);  
```  
  
### <a name="return-value"></a>戻り値  
 最初の構文は、現在の InputIterator をインクリメントしてから返します。 2 番目の構文は、現在の InputIterator のコピーを返し、現在の InputIterator をインクリメントします。  
  
### <a name="remarks"></a>コメント  
 最初の InputIterator 構文は、現在の InputIterator の前置インクリメントを実行します。  
  
 2 番目の構文は、現在の InputIterator の後置インクリメントを実行します。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置インクリメント演算を示します。  
  


## <a name="operator-inequality"></a>  Inputiterator::operator! = 演算子
現在の InputIterator が、指定された InputIterator と等しくないかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```  
bool operator!=(const InputIterator& other) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 別の InputIterator。  
  
### <a name="return-value"></a>戻り値  
 現在の InputIterator が `true` と等しくない場合は `other`。それ以外の場合は `false`。   

  
## <a name="see-also"></a>関連項目  
 [プラットフォーム Namespace](platform-namespace-c-cx.md)