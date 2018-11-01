---
title: location クラス
ms.date: 11/04/2016
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
ms.openlocfilehash: ffb469ec5f5542b5037d31bfdb5fd1eaab47ed38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596537"
---
# <a name="location-class"></a>location クラス

ハードウェアの物理位置の抽象化です。

## <a name="syntax"></a>構文

```
class location;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[location](#ctor)|オーバーロードされます。 `location` オブジェクトを構築します。|
|[~ location デストラクター](#dtor)|`location` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[current](#current)|返します、`location`呼び出し元のスレッドが実行中の最も特定の場所を表すオブジェクト。|
|[from_numa_node](#from_numa_node)|返します、`location`を指定した NUMA ノードを表すオブジェクト。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator!=](#operator_neq)|2 つかどうかを判断します`location`オブジェクトが別の場所を表します。|
|[operator=](#operator_eq)|別の内容を割り当てます`location`オブジェクトをこのオブジェクト。|
|[operator==](#operator_eq_eq)|2 つかどうかを判断します`location`オブジェクトが同じ場所を表します。|

## <a name="inheritance-hierarchy"></a>継承階層

`location`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="dtor"></a> ~ の場所

`location` オブジェクトを破棄します。

```
~location();
```

##  <a name="current"></a> 現在の

返します、`location`呼び出し元のスレッドが実行中の最も特定の場所を表すオブジェクト。

```
static location __cdecl current();
```

### <a name="return-value"></a>戻り値

最も固有の場所を表す場所、呼び出し元のスレッドが実行しています。

##  <a name="from_numa_node"></a> from_numa_node

返します、`location`を指定した NUMA ノードを表すオブジェクト。

```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>パラメーター

*_NumaNodeNumber*<br/>
場所を構築する NUMA ノードの数。

### <a name="return-value"></a>戻り値

によって指定された NUMA ノードを表す場所、`_NumaNodeNumber`パラメーター。

##  <a name="ctor"></a> 場所

`location` オブジェクトを構築します。

```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```

### <a name="parameters"></a>パラメーター

*_Src*<br/>

*_LocationType*<br/>

*Id (_i)*<br/>

*_BindingId*<br/>

*_PBinding*<br/>
(省略可能)バインドのポインター。

### <a name="remarks"></a>Remarks

既定で構築される場所は、全体として、システムを表します。

##  <a name="operator_neq"></a> operator!=

2 つかどうかを判断します`location`オブジェクトが別の場所を表します。

```
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>パラメーター

*_Rhs*<br/>
オペランド`location`します。

### <a name="return-value"></a>戻り値

**true** 2 つの場所が異なる場合、 **false**それ以外の場合。

##  <a name="operator_eq"></a> 演算子 =

別の内容を割り当てます`location`オブジェクトをこのオブジェクト。

```
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>パラメーター

*_Rhs*<br/>
ソース `location` オブジェクト。

### <a name="return-value"></a>戻り値

##  <a name="operator_eq_eq"></a> 演算子 = =

2 つかどうかを判断します`location`オブジェクトが同じ場所を表します。

```
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>パラメーター

*_Rhs*<br/>
オペランド`location`します。

### <a name="return-value"></a>戻り値

**true**場合は、2 つの場所が同じで、 **false**それ以外の場合。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
