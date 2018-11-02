---
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
ms.openlocfilehash: 6f4e6db693a5839fd3add503bfb9697679a98dd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635407"
---
# <a name="multilinkregistry-class"></a>multi_link_registry クラス

`multi_link_registry` オブジェクトは、複数のソース ブロックまたは複数のターゲット ブロックを管理する `network_link_registry` です。

## <a name="syntax"></a>構文

```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

#### <a name="parameters"></a>パラメーター

*(_B)*<br/>
ブロックのデータ型に格納されている、`multi_link_registry`オブジェクト。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[multi_link_registry](#ctor)|`multi_link_registry` オブジェクトを構築します。|
|[~ multi_link_registry デストラクター](#dtor)|`multi_link_registry` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[add](#add)|リンクを追加、`multi_link_registry`オブジェクト。 (上書き[network_link_registry::add](network-link-registry-class.md#add))。|
|[begin](#begin)|最初の要素に反復子を返します、`multi_link_registry`オブジェクト。 (上書き[network_link_registry::begin](network-link-registry-class.md#begin))。|
|[contains](#contains)|検索、`multi_link_registry`の指定されたブロックのオブジェクト。 (上書き[network_link_registry::contains](network-link-registry-class.md#contains))。|
|[count](#count)|内の項目の数をカウント、`multi_link_registry`オブジェクト。 (上書き[network_link_registry::count](network-link-registry-class.md#count))。|
|[remove](#remove)|リンクを削除、`multi_link_registry`オブジェクト。 (上書き[network_link_registry::remove](network-link-registry-class.md#remove))。|
|[set_bound](#set_bound)|リンクの数に上限を設定、`multi_link_registry`オブジェクトを保持できます。|

## <a name="inheritance-hierarchy"></a>継承階層

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="add"></a> 追加します。

リンクを追加、`multi_link_registry`オブジェクト。

```
virtual void add(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*リンク (_l)*<br/>
追加するブロックへのポインター。

### <a name="remarks"></a>Remarks

メソッドはスロー、 [invalid_link_target](invalid-link-target-class.md)例外のリンクが既にレジストリに存在する場合、または場合、バインドが既にで設定された、`set_bound`関数とのリンクが削除されたためです。

##  <a name="begin"></a> 開始

最初の要素に反復子を返します、`multi_link_registry`オブジェクト。

```
virtual iterator begin();
```

### <a name="return-value"></a>戻り値

最初の要素を示す反復子、`multi_link_registry`オブジェクト。

### <a name="remarks"></a>Remarks

最終の状態が付いて、`NULL`リンク。

##  <a name="contains"></a> 含まれています

検索、`multi_link_registry`の指定されたブロックのオブジェクト。

```
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*リンク (_l)*<br/>
内で検索するのには、ブロックへのポインター、`multi_link_registry`オブジェクト。

### <a name="return-value"></a>戻り値

**true**指定されたブロックが見つかった場合**false**それ以外の場合。

##  <a name="count"></a> カウント

内の項目の数をカウント、`multi_link_registry`オブジェクト。

```
virtual size_t count();
```

### <a name="return-value"></a>戻り値

内の項目の数、`multi_link_registry`オブジェクト。

##  <a name="ctor"></a> multi_link_registry

`multi_link_registry` オブジェクトを構築します。

```
multi_link_registry();
```

##  <a name="dtor"></a> ~multi_link_registry

`multi_link_registry` オブジェクトを破棄します。

```
virtual ~multi_link_registry();
```

### <a name="remarks"></a>Remarks

メソッドはスロー、 [invalid_operation](invalid-operation-class.md)すべてのリンクを削除する前に呼び出す場合は例外です。

##  <a name="remove"></a> 削除します。

リンクを削除、`multi_link_registry`オブジェクト。

```
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>パラメーター

*リンク (_l)*<br/>
削除する場合、ブロックへのポインターが見つかりました。

### <a name="return-value"></a>戻り値

**true**場合は、リンクが見つかり、削除、 **false**それ以外の場合。

##  <a name="set_bound"></a> set_bound

リンクの数に上限を設定、`multi_link_registry`オブジェクトを保持できます。

```
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>パラメーター

*_MaxLinks*<br/>
最大数をリンクする、`multi_link_registry`オブジェクトを保持できます。

### <a name="remarks"></a>Remarks

エントリのリンクを解除が発生する、バインドを設定すると後、`multi_link_registry`不変の状態を入力するオブジェクトへの呼び出しをさらに、`add`がスローされます、`invalid_link_target`例外。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[single_link_registry クラス](single-link-registry-class.md)
