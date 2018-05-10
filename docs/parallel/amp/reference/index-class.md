---
title: index クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
dev_langs:
- C++
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 594ee94bbbfc19bc6fcceb9ae7f0760d9ec877dc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="index-class"></a>index クラス
定義、 *N*-次元インデックス pographics cpp amp.md です。  
  
## <a name="syntax"></a>構文  
  
```  
template <int _Rank>  
class index;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Rank`  
 ランク (次元数)。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[インデックスのコンス トラクター](#ctor)|`index` クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator--](#operator--)|`index` オブジェクトの各要素をデクリメントします。|  
|[operator(mod)=](#operator_mod_eq)|その要素がある数で除算された場合、`index` オブジェクトの各要素の剰余を計算します。|  
|[operator*=](#operator_star_eq)|`index` オブジェクトの各要素をある数で乗算します。|  
|[operator/=](#operator_div_eq)|`index` オブジェクトの各要素をある数で除算します。|  
|[index::operator\[\]](#operator_at)|指定したインデックス位置にある要素を返します。|  
|[operator++](#operator_add_add)|`index` オブジェクトの各要素をインクリメントします。|  
|[operator+=](#operator_add_eq)|指定した数を `index` オブジェクトの各要素に加算します。|  
|[operator=](#operator_eq)|指定された `index` オブジェクトの内容をこのオブジェクトにコピーします。|  
|[operator-=](#operator_-_eq)|指定した数を `index` オブジェクトの各要素から減算します。|  

  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[rank 定数](#rank)|`index` オブジェクトのランクを格納します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `index`  
  
## <a name="remarks"></a>コメント  
 `index`構造体の座標ベクターを表します*N*で一意の位置を示す整数、 *N*-次元空間です。 ベクターの値は最上位から最下位へ順に並べ替えられます。 使用して、コンポーネントの値を取得する[演算子 =](#operator_eq)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  


## <a name="index_ctor"></a> インデックスのコンス トラクター
Index クラスの新しいインスタンスを初期化します。

```  
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
``` 

### <a name="parameters"></a>パラメーター

_Array  
ランク値を持つ 1 次元配列。  
_I  
1 次元インデックスのインデックス位置。  
_I0  
最上位の次元の長さ。  
_I1  
最上位の次の次元の長さ。  
_I2  
最下位の次元の長さ。  
_Other  
新しいインデックス オブジェクトの基になるインデックス オブジェクトです。  

## <a name="operator--"></a>  operator--
デクリメント インデックス オブジェクトの各要素。  
```  
index<_Rank>& operator--() restrict(amp,cpu);  

index operator--(
   int
) restrict(amp,cpu);
```  
### <a name="return-values"></a>戻り値
前置演算子のインデックス オブジェクト (* この)。 後置演算子は、新しいインデックス オブジェクトです。

## <a name="operator_mod_eq"></a>  operator(mod)=   
その要素が指定された数で除算された場合は、インデックス オブジェクトの各要素の剰余 (余り) を計算します。

```  
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```  
### <a name="parameters"></a>パラメーター
_Rhs 5/3 をで除算する数値。
オブジェクトをインデックス値を返します。

## <a name="operator_star_eq"></a>  operator*=   
指定したインデックス オブジェクト内の各要素を乗算します。
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター
_Rhs 乗算する数値。

## <a name="operator_div_eq"></a>  operator/= 
Index オブジェクト内の各要素を指定された数で除算します。

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>パラメーター
_Rhs で除算する数値。

## <a name="operator_at"></a>  演算子\[\]  
指定した位置にあるインデックスのコンポーネントを返します。

```
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター
_Index 0 からランク-1 までの整数。

### <a name="return-value"></a>戻り値
指定したインデックス位置にある要素。

### <a name="remarks"></a>コメント
次の例では、インデックスのコンポーネント値を表示します。
```  
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>  + + 演算子   
インデックス オブジェクトの各要素をインクリメントします。
```  
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```  
### <a name="return-value"></a>戻り値
前置演算子のインデックス オブジェクト (* この)。 後置演算子は、新しいインデックス オブジェクトです。

## <a name="operator_add_eq"></a>  operator+=   
インデックス オブジェクトの各要素に指定された数を追加します。
```  
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>パラメーター
_Rhs 加算する数。

### <a name="return-value"></a>戻り値
インデックス オブジェクトです。

## <a name="operator_eq"></a>  operator=   
この 1 つに、指定したインデックス オブジェクトの内容をコピーします。
```  
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>パラメーター
_Other からコピーするインデックス オブジェクトです。

### <a name="return-value"></a>戻り値
このインデックス オブジェクトへの参照。

## <a name="operator_-_eq"></a>  operator-=
インデックス オブジェクトの各要素から指定した数値を減算します。
```  
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```  
### <a name="parameters"></a>パラメーター
_Rhs 減算する数。

### <a name="return-value"></a>戻り値
インデックス オブジェクトです。   

## <a name="rank"></a>  ランク  
  インデックス オブジェクトのランクを取得します。
```
static const int rank = _Rank;
``` 
## <a name="see-also"></a>関連項目  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
