---
title: single_link_registry クラス
ms.date: 11/04/2016
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
ms.openlocfilehash: 4f706b4551d71c77e136e4d65d2d6a3183293d8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454497"
---
# <a name="singlelinkregistry-class"></a>single_link_registry クラス

`single_link_registry` オブジェクトは、単一のソース ブロックまたはターゲット ブロックのみを管理する `network_link_registry` です。

## <a name="syntax"></a>構文

```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

#### <a name="parameters"></a>パラメーター

*(_B)*<br/>
ブロックのデータ型に格納されている、`single_link_registry`オブジェクト。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[single_link_registry](#ctor)|`single_link_registry` オブジェクトを構築します。|
|[~ single_link_registry デストラクター](#dtor)|`single_link_registry` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[add](#add)|リンクを追加、`single_link_registry`オブジェクト。 (上書き[network_link_registry::add](network-link-registry-class.md#add))。|
|[begin](#begin)|最初の要素に反復子を返します、`single_link_registry`オブジェクト。 (上書き[network_link_registry::begin](network-link-registry-class.md#begin))。|
|[contains](#contains)|検索、`single_link_registry`の指定されたブロックのオブジェクト。 (上書き[network_link_registry::contains](network-link-registry-class.md#contains))。|
|[count](#count)|内の項目の数をカウント、`single_link_registry`オブジェクト。 (上書き[network_link_registry::count](network-link-registry-class.md#count))。|
|[remove](#remove)|リンクを削除、`single_link_registry`オブジェクト。 (上書き[network_link_registry::remove](network-link-registry-class.md#remove))。|

## <a name="inheritance-hierarchy"></a>継承階層

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="add"></a> 追加します。

リンクを追加、`single_link_registry`オブジェクト。

```
virtual void add(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*リンク (_l)*<br/>
追加するブロックへのポインター。

### <a name="remarks"></a>Remarks

メソッドはスロー、 [invalid_link_target](invalid-link-target-class.md)でこのレジストリが既にリンクがある場合は例外です。

##  <a name="begin"></a> 開始

最初の要素に反復子を返します、`single_link_registry`オブジェクト。

```
virtual iterator begin();
```

### <a name="return-value"></a>戻り値

最初の要素を示す反復子、`single_link_registry`オブジェクト。

### <a name="remarks"></a>Remarks

最終の状態が付いて、`NULL`リンク。

##  <a name="contains"></a> 含まれています

検索、`single_link_registry`の指定されたブロックのオブジェクト。

```
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*リンク (_l)*<br/>
内で検索するのには、ブロックへのポインター、`single_link_registry`オブジェクト。

### <a name="return-value"></a>戻り値

**true**場合は、リンクが検出されましたが、 **false**それ以外の場合。

##  <a name="count"></a> カウント

内の項目の数をカウント、`single_link_registry`オブジェクト。

```
virtual size_t count();
```

### <a name="return-value"></a>戻り値

内の項目の数、`single_link_registry`オブジェクト。

##  <a name="remove"></a> 削除します。

リンクを削除、`single_link_registry`オブジェクト。

```
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*リンク (_l)*<br/>
削除する場合、ブロックへのポインターが見つかりました。

### <a name="return-value"></a>戻り値

**true**場合は、リンクが見つかり、削除、 **false**それ以外の場合。

##  <a name="ctor"></a> single_link_registry

`single_link_registry` オブジェクトを構築します。

```
single_link_registry();
```

##  <a name="dtor"></a> ~single_link_registry

`single_link_registry` オブジェクトを破棄します。

```
virtual ~single_link_registry();
```

### <a name="remarks"></a>Remarks

メソッドはスロー、 [invalid_operation](invalid-operation-class.md)のリンクを削除する前に呼び出された場合は例外です。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[multi_link_registry クラス](multi-link-registry-class.md)
