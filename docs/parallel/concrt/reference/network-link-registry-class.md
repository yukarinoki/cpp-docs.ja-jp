---
title: network_link_registry クラス
ms.date: 11/04/2016
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
ms.openlocfilehash: 18fabd0e741c144201f299271cdd01eb9ac55fac
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222681"
---
# <a name="network_link_registry-class"></a>network_link_registry クラス

`network_link_registry` 抽象基底クラスによって、ソース ブロックとターゲット ブロック間のリンクを管理します。

## <a name="syntax"></a>構文

```cpp
template<class _Block>
class network_link_registry;
```

### <a name="parameters"></a>パラメーター

*_Block*<br/>
に格納されているブロックデータ型 `network_link_registry` 。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`const_pointer`|**`const`** オブジェクト内の要素へのポインターを提供する型 `network_link_registry` 。|
|`const_reference`|**`const`** `network_link_registry` 読み取りと const 操作の実行のために、オブジェクトに格納されている要素への参照を提供する型。|
|`iterator`|オブジェクト内の任意の要素の読み取りまたは変更ができる反復子を提供する型 `network_link_registry` 。|
|`type`|オブジェクトに格納されているブロック型を表す型 `network_link_registry` 。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[add](#add)|派生クラスでオーバーライドされると、オブジェクトへのリンクを追加し `network_link_registry` ます。|
|[初め](#begin)|派生クラスでオーバーライドされた場合、オブジェクト内の最初の要素を指す反復子を返し `network_link_registry` ます。|
|[contains](#contains)|派生クラスでオーバーライドされると、 `network_link_registry` 指定したブロックのオブジェクトを検索します。|
|[count](#count)|派生クラスでオーバーライドされた場合、オブジェクト内の項目の数を返し `network_link_registry` ます。|
|[remove](#remove)|派生クラスでオーバーライドされると、指定したブロックをオブジェクトから削除し `network_link_registry` ます。|

## <a name="remarks"></a>解説

は、 `network link registry` 同時アクセスには安全ではありません。

## <a name="inheritance-hierarchy"></a>継承階層

`network_link_registry`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="add"></a><a name="add"></a>アドイン

派生クラスでオーバーライドされると、オブジェクトへのリンクを追加し `network_link_registry` ます。

```cpp
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
追加するブロックへのポインター。

## <a name="begin"></a><a name="begin"></a>初め

派生クラスでオーバーライドされた場合、オブジェクト内の最初の要素を指す反復子を返し `network_link_registry` ます。

```cpp
virtual iterator begin() = 0;
```

### <a name="return-value"></a>戻り値

オブジェクト内の最初の要素を指す反復子 `network_link_registry` 。

### <a name="remarks"></a>解説

反復子の終了状態は、リンクによって示され `NULL` ます。

## <a name="contains"></a><a name="contains"></a>は

派生クラスでオーバーライドされると、 `network_link_registry` 指定したブロックのオブジェクトを検索します。

```cpp
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
オブジェクト内で検索されているブロックへのポインター `network_link_registry` 。

### <a name="return-value"></a>戻り値

**`true`** ブロックが見つかった場合は **`false`** 。それ以外の場合は。

## <a name="count"></a><a name="count"></a>数

派生クラスでオーバーライドされた場合、オブジェクト内の項目の数を返し `network_link_registry` ます。

```cpp
virtual size_t count() = 0;
```

### <a name="return-value"></a>戻り値

`network_link_registry` オブジェクト内の項目の数。

## <a name="remove"></a><a name="remove"></a>から

派生クラスでオーバーライドされると、指定したブロックをオブジェクトから削除し `network_link_registry` ます。

```cpp
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
削除するブロックへのポインター (見つかった場合)。

### <a name="return-value"></a>戻り値

**`true`** リンクが見つかり、削除された場合は **`false`** 。それ以外の場合は。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[single_link_registry クラス](single-link-registry-class.md)<br/>
[multi_link_registry クラス](multi-link-registry-class.md)
