---
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
ms.openlocfilehash: d4979eaf9065183be646be72cfdd5a94500edf55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337584"
---
# <a name="sourcelinkmanager-class"></a>source_link_manager クラス

`source_link_manager` オブジェクトは、`ISource` ブロックへのメッセージング ブロック ネットワーク リンクを管理します。

## <a name="syntax"></a>構文

```
template<class _LinkRegistry>
class source_link_manager;
```

#### <a name="parameters"></a>パラメーター

*_LinkRegistry*<br/>
ネットワーク リンクのレジストリ。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`const_pointer`|ポインターを提供する型、`const`内の要素を`source_link_manager`オブジェクト。|
|`const_reference`|参照を提供する型、`const`に要素が格納されている、`source_link_manager`の読み取りと const の操作を実行するオブジェクト。|
|`iterator`|反復子を提供する型の読み取りまたはの任意の要素の変更ができる、`source_link_manager`オブジェクト。|
|`type`|によって管理されているリンクのレジストリの種類、`source_link_manager`オブジェクト。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[source_link_manager](#ctor)|`source_link_manager` オブジェクトを構築します。|
|[~ source_link_manager デストラクター](#dtor)|`source_link_manager` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[add](#add)|ソースへのリンクを追加、`source_link_manager`オブジェクト。|
|[begin](#begin)|最初の要素に反復子を返します、`source_link_manager`オブジェクト。|
|[contains](#contains)|検索、`network_link_registry`この`source_link_manager`の指定されたブロックのオブジェクト。|
|[count](#count)|リンクされたブロックの数をカウント、`source_link_manager`オブジェクト。|
|[reference](#reference)|参照を取得、`source_link_manager`オブジェクト。|
|[register_target_block](#register_target_block)|これを保持するターゲット ブロックを登録します`source_link_manager`オブジェクト。|
|[release](#release)|参照を解放、`source_link_manager`オブジェクト。|
|[remove](#remove)|リンクを削除、`source_link_manager`オブジェクト。|
|[set_bound](#set_bound)|これに追加できる送信元のリンクの最大数を設定`source_link_manager`オブジェクト。|

## <a name="remarks"></a>Remarks

現時点では、ソース ブロックは、カウントされた参照です。 これで、ラッパーを`network_link_registry`オブジェクトをリンクへの同時アクセスを許可し、コールバックをとおしてリンクを参照する機能を提供します。 メッセージ ブロック ( `target_block`s または`propagator_block`s)、送信元のリンクをこのクラスを使用する必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

`source_link_manager`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="add"></a> 追加します。

ソースへのリンクを追加、`source_link_manager`オブジェクト。

```
void add(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*リンク (_l)*<br/>
追加するブロックへのポインター。

##  <a name="begin"></a> 開始

最初の要素に反復子を返します、`source_link_manager`オブジェクト。

```
iterator begin();
```

### <a name="return-value"></a>戻り値

最初の要素を示す反復子、`source_link_manager`オブジェクト。

### <a name="remarks"></a>Remarks

によって、反復子の最終の状態が示される、`NULL`リンク。

##  <a name="contains"></a> 含まれています

検索、`network_link_registry`この`source_link_manager`の指定されたブロックのオブジェクト。

```
bool contains(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*リンク (_l)*<br/>
内で検索するのには、ブロックへのポインター、`source_link_manager`オブジェクト。

### <a name="return-value"></a>戻り値

**true**指定されたブロックが見つかった場合**false**それ以外の場合。

##  <a name="count"></a> カウント

リンクされたブロックの数をカウント、`source_link_manager`オブジェクト。

```
size_t count();
```

### <a name="return-value"></a>戻り値

リンクされたブロックの数、`source_link_manager`オブジェクト。

##  <a name="reference"></a> 参照

参照を取得、`source_link_manager`オブジェクト。

```
void reference();
```

##  <a name="register_target_block"></a> register_target_block

これを保持するターゲット ブロックを登録します`source_link_manager`オブジェクト。

```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
これを保持しているターゲット ブロック`source_link_manager`オブジェクト。

##  <a name="release"></a> リリース

参照を解放、`source_link_manager`オブジェクト。

```
void release();
```

##  <a name="remove"></a> 削除します。

リンクを削除、`source_link_manager`オブジェクト。

```
bool remove(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*リンク (_l)*<br/>
削除する場合、ブロックへのポインターが見つかりました。

### <a name="return-value"></a>戻り値

**true**場合は、リンクが見つかり、削除、 **false**それ以外の場合。

##  <a name="set_bound"></a> set_bound

これに追加できる送信元のリンクの最大数を設定`source_link_manager`オブジェクト。

```
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>パラメーター

*_MaxLinks*<br/>
リンクの最大数。

##  <a name="ctor"></a> source_link_manager

`source_link_manager` オブジェクトを構築します。

```
source_link_manager();
```

##  <a name="dtor"></a> ~source_link_manager

`source_link_manager` オブジェクトを破棄します。

```
~source_link_manager();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[single_link_registry クラス](single-link-registry-class.md)<br/>
[multi_link_registry クラス](multi-link-registry-class.md)
