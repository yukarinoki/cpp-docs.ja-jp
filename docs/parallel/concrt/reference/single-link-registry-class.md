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
ms.openlocfilehash: 24f89a6b2fb998ba5e5a82dbb470accb45d0fd9f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219548"
---
# <a name="single_link_registry-class"></a>single_link_registry クラス

`single_link_registry` オブジェクトは、単一のソース ブロックまたはターゲット ブロックのみを管理する `network_link_registry` です。

## <a name="syntax"></a>構文

```cpp
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>パラメーター

*_Block*<br/>
オブジェクトに格納されているブロックデータ型 `single_link_registry` 。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[single_link_registry](#ctor)|`single_link_registry` オブジェクトを構築します。|
|[~ single_link_registry デストラクター](#dtor)|`single_link_registry` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[add](#add)|オブジェクトへのリンクを追加し `single_link_registry` ます。 ( [Network_link_registry:: add](network-link-registry-class.md#add)をオーバーライドします)。|
|[初め](#begin)|オブジェクト内の最初の要素を指す反復子を返し `single_link_registry` ます。 ( [Network_link_registry:: begin](network-link-registry-class.md#begin)をオーバーライドします)。|
|[contains](#contains)|`single_link_registry`指定されたブロックのオブジェクトを検索します。 ( [Network_link_registry:: contains](network-link-registry-class.md#contains)をオーバーライドします)。|
|[count](#count)|オブジェクト内の項目の数をカウントし `single_link_registry` ます。 ( [Network_link_registry:: count](network-link-registry-class.md#count)をオーバーライドします)。|
|[remove](#remove)|オブジェクトからリンクを削除 `single_link_registry` します。 ( [Network_link_registry:: remove](network-link-registry-class.md#remove)をオーバーライドします)。|

## <a name="inheritance-hierarchy"></a>継承階層

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="add"></a><a name="add"></a>アドイン

オブジェクトへのリンクを追加し `single_link_registry` ます。

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
追加するブロックへのポインター。

### <a name="remarks"></a>解説

このレジストリにリンクが既に存在する場合、メソッドは[invalid_link_target](invalid-link-target-class.md)例外をスローします。

## <a name="begin"></a><a name="begin"></a>初め

オブジェクト内の最初の要素を指す反復子を返し `single_link_registry` ます。

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>戻り値

オブジェクト内の最初の要素を指す反復子 `single_link_registry` 。

### <a name="remarks"></a>解説

終了状態はリンクによって示され `NULL` ます。

## <a name="contains"></a><a name="contains"></a>は

`single_link_registry`指定されたブロックのオブジェクトを検索します。

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
オブジェクト内で検索されるブロックへのポインター `single_link_registry` 。

### <a name="return-value"></a>戻り値

**`true`** リンクが見つかった場合は **`false`** 。それ以外の場合は。

## <a name="count"></a><a name="count"></a>数

オブジェクト内の項目の数をカウントし `single_link_registry` ます。

```cpp
virtual size_t count();
```

### <a name="return-value"></a>戻り値

`single_link_registry` オブジェクト内の項目の数。

## <a name="remove"></a><a name="remove"></a>から

オブジェクトからリンクを削除 `single_link_registry` します。

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
削除するブロックへのポインター (見つかった場合)。

### <a name="return-value"></a>戻り値

**`true`** リンクが見つかり、削除された場合は **`false`** 。それ以外の場合は。

## <a name="single_link_registry"></a><a name="ctor"></a>single_link_registry

`single_link_registry` オブジェクトを構築します。

```cpp
single_link_registry();
```

## <a name="single_link_registry"></a><a name="dtor"></a>~ single_link_registry

`single_link_registry` オブジェクトを破棄します。

```cpp
virtual ~single_link_registry();
```

### <a name="remarks"></a>解説

このメソッドは、リンクが削除される前に呼び出された場合、 [invalid_operation](invalid-operation-class.md)例外をスローします。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[multi_link_registry クラス](multi-link-registry-class.md)
