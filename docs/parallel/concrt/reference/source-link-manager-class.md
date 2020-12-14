---
description: '詳細情報: source_link_manager クラス'
title: source_link_manager クラス
ms.date: 11/04/2016
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
ms.openlocfilehash: 132dc2db07a1c9abeeb04672f97e262761764feb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188509"
---
# <a name="source_link_manager-class"></a>source_link_manager クラス

`source_link_manager` オブジェクトは、`ISource` ブロックへのメッセージング ブロック ネットワーク リンクを管理します。

## <a name="syntax"></a>構文

```cpp
template<class _LinkRegistry>
class source_link_manager;
```

### <a name="parameters"></a>パラメーター

*_LinkRegistry*<br/>
ネットワークリンクレジストリ。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`const_pointer`|**`const`** オブジェクト内の要素へのポインターを提供する型 `source_link_manager` 。|
|`const_reference`|**`const`** `source_link_manager` 読み取りと const 操作の実行のために、オブジェクトに格納されている要素への参照を提供する型。|
|`iterator`|オブジェクト内の任意の要素の読み取りまたは変更ができる反復子を提供する型 `source_link_manager` 。|
|`type`|オブジェクトによって管理されているリンクレジストリの種類 `source_link_manager` 。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[source_link_manager](#ctor)|`source_link_manager` オブジェクトを構築します。|
|[~ source_link_manager デストラクター](#dtor)|`source_link_manager` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[add](#add)|オブジェクトにソースリンクを追加し `source_link_manager` ます。|
|[初め](#begin)|オブジェクト内の最初の要素を指す反復子を返し `source_link_manager` ます。|
|[contains](#contains)|`network_link_registry`このオブジェクト内で、指定したブロックを検索し `source_link_manager` ます。|
|[count](#count)|オブジェクト内のリンクされたブロックの数をカウントし `source_link_manager` ます。|
|[reference](#reference)|オブジェクトの参照を取得 `source_link_manager` します。|
|[register_target_block](#register_target_block)|このオブジェクトを保持するターゲットブロックを登録 `source_link_manager` します。|
|[解除](#release)|オブジェクトの参照を解放し `source_link_manager` ます。|
|[remove](#remove)|オブジェクトからリンクを削除 `source_link_manager` します。|
|[set_bound](#set_bound)|このオブジェクトに追加できるソースリンクの最大数を設定し `source_link_manager` ます。|

## <a name="remarks"></a>解説

現在、ソースブロックは参照カウントされています。 これは `network_link_registry` 、リンクへの同時アクセスを可能にし、コールバックを介してリンクを参照する機能を提供するオブジェクトのラッパーです。 メッセージブロックは `target_block` `propagator_block` 、ソースリンクにこのクラスを使用する必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

`source_link_manager`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="add"></a><a name="add"></a> アドイン

オブジェクトにソースリンクを追加し `source_link_manager` ます。

```cpp
void add(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
追加するブロックへのポインター。

## <a name="begin"></a><a name="begin"></a> begin

オブジェクト内の最初の要素を指す反復子を返し `source_link_manager` ます。

```cpp
iterator begin();
```

### <a name="return-value"></a>戻り値

オブジェクト内の最初の要素を指す反復子 `source_link_manager` 。

### <a name="remarks"></a>解説

反復子の終了状態は、リンクによって示され `NULL` ます。

## <a name="contains"></a><a name="contains"></a> は

`network_link_registry`このオブジェクト内で、指定したブロックを検索し `source_link_manager` ます。

```cpp
bool contains(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
オブジェクト内で検索されるブロックへのポインター `source_link_manager` 。

### <a name="return-value"></a>戻り値

**`true`** 指定されたブロックが見つかった場合は **`false`** 。それ以外の場合は。

## <a name="count"></a><a name="count"></a> 数

オブジェクト内のリンクされたブロックの数をカウントし `source_link_manager` ます。

```cpp
size_t count();
```

### <a name="return-value"></a>戻り値

オブジェクト内のリンクされたブロックの数 `source_link_manager` 。

## <a name="reference"></a><a name="reference"></a> 「

オブジェクトの参照を取得 `source_link_manager` します。

```cpp
void reference();
```

## <a name="register_target_block"></a><a name="register_target_block"></a> register_target_block

このオブジェクトを保持するターゲットブロックを登録 `source_link_manager` します。

```cpp
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このオブジェクトを保持しているターゲットブロック `source_link_manager` 。

## <a name="release"></a><a name="release"></a> 解除

オブジェクトの参照を解放し `source_link_manager` ます。

```cpp
void release();
```

## <a name="remove"></a><a name="remove"></a> から

オブジェクトからリンクを削除 `source_link_manager` します。

```cpp
bool remove(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*_Link*<br/>
削除するブロックへのポインター (見つかった場合)。

### <a name="return-value"></a>戻り値

**`true`** リンクが見つかり、削除された場合は **`false`** 。それ以外の場合は。

## <a name="set_bound"></a><a name="set_bound"></a> set_bound

このオブジェクトに追加できるソースリンクの最大数を設定し `source_link_manager` ます。

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>パラメーター

*_MaxLinks*<br/>
リンクの最大数。

## <a name="source_link_manager"></a><a name="ctor"></a> source_link_manager

`source_link_manager` オブジェクトを構築します。

```cpp
source_link_manager();
```

## <a name="source_link_manager"></a><a name="dtor"></a> ~ source_link_manager

`source_link_manager` オブジェクトを破棄します。

```cpp
~source_link_manager();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[single_link_registry クラス](single-link-registry-class.md)<br/>
[multi_link_registry クラス](multi-link-registry-class.md)
