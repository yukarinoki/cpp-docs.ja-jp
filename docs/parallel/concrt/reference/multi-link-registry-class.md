---
description: '詳細情報: multi_link_registry クラス'
title: multi_link_registry クラス
ms.date: 11/04/2016
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
ms.openlocfilehash: a5d5e6c7e837f76a422c3f2879f74d1af36d64d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202133"
---
# <a name="multi_link_registry-class"></a>multi_link_registry クラス

`multi_link_registry` オブジェクトは、複数のソース ブロックまたは複数のターゲット ブロックを管理する `network_link_registry` です。

## <a name="syntax"></a>構文

```cpp
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>パラメーター

*_Block*<br/>
オブジェクトに格納されているブロックデータ型 `multi_link_registry` 。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[multi_link_registry](#ctor)|`multi_link_registry` オブジェクトを構築します。|
|[~ multi_link_registry デストラクター](#dtor)|`multi_link_registry` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[add](#add)|オブジェクトへのリンクを追加し `multi_link_registry` ます。 ( [Network_link_registry:: add](network-link-registry-class.md#add)をオーバーライドします)。|
|[初め](#begin)|オブジェクト内の最初の要素を指す反復子を返し `multi_link_registry` ます。 ( [Network_link_registry:: begin](network-link-registry-class.md#begin)をオーバーライドします)。|
|[contains](#contains)|`multi_link_registry`指定されたブロックのオブジェクトを検索します。 ( [Network_link_registry:: contains](network-link-registry-class.md#contains)をオーバーライドします)。|
|[count](#count)|オブジェクト内の項目の数をカウントし `multi_link_registry` ます。 ( [Network_link_registry:: count](network-link-registry-class.md#count)をオーバーライドします)。|
|[remove](#remove)|オブジェクトからリンクを削除 `multi_link_registry` します。 ( [Network_link_registry:: remove](network-link-registry-class.md#remove)をオーバーライドします)。|
|[set_bound](#set_bound)|オブジェクトが保持できるリンクの数の上限を設定 `multi_link_registry` します。|

## <a name="inheritance-hierarchy"></a>継承階層

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="add"></a><a name="add"></a> アドイン

オブジェクトへのリンクを追加し `multi_link_registry` ます。

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
追加するブロックへのポインター。

### <a name="remarks"></a>解説

リンクが既に[](invalid-link-target-class.md)レジストリに存在する場合、またはバインドされたが既に関数で設定されていて、 `set_bound` リンクが削除された後である場合、メソッドは invalid_link_target 例外をスローします。

## <a name="begin"></a><a name="begin"></a> begin

オブジェクト内の最初の要素を指す反復子を返し `multi_link_registry` ます。

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>戻り値

オブジェクト内の最初の要素を指す反復子 `multi_link_registry` 。

### <a name="remarks"></a>解説

終了状態はリンクによって示され `NULL` ます。

## <a name="contains"></a><a name="contains"></a> は

`multi_link_registry`指定されたブロックのオブジェクトを検索します。

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
オブジェクト内で検索されるブロックへのポインター `multi_link_registry` 。

### <a name="return-value"></a>戻り値

**`true`** 指定されたブロックが見つかった場合は **`false`** 。それ以外の場合は。

## <a name="count"></a><a name="count"></a> 数

オブジェクト内の項目の数をカウントし `multi_link_registry` ます。

```cpp
virtual size_t count();
```

### <a name="return-value"></a>戻り値

`multi_link_registry` オブジェクト内の項目の数。

## <a name="multi_link_registry"></a><a name="ctor"></a> multi_link_registry

`multi_link_registry` オブジェクトを構築します。

```cpp
multi_link_registry();
```

## <a name="multi_link_registry"></a><a name="dtor"></a> ~ multi_link_registry

`multi_link_registry` オブジェクトを破棄します。

```cpp
virtual ~multi_link_registry();
```

### <a name="remarks"></a>解説

メソッドは、すべてのリンクが削除される前に呼び出された場合、 [invalid_operation](invalid-operation-class.md) 例外をスローします。

## <a name="remove"></a><a name="remove"></a> から

オブジェクトからリンクを削除 `multi_link_registry` します。

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
削除するブロックへのポインター (見つかった場合)。

### <a name="return-value"></a>戻り値

**`true`** リンクが見つかり、削除された場合は **`false`** 。それ以外の場合は。

## <a name="set_bound"></a><a name="set_bound"></a> set_bound

オブジェクトが保持できるリンクの数の上限を設定 `multi_link_registry` します。

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>パラメーター

*_MaxLinks*<br/>
オブジェクトが保持できるリンクの最大数 `multi_link_registry` 。

### <a name="remarks"></a>解説

バインドされたが設定されると、エントリのリンクを解除すると、オブジェクトは、 `multi_link_registry` さらにを呼び出して例外をスローする、変更できない状態になり `add` `invalid_link_target` ます。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[single_link_registry クラス](single-link-registry-class.md)
