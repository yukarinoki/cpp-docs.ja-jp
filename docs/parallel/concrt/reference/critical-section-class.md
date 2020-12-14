---
description: '詳細情報: critical_section クラス'
title: critical_section クラス
ms.date: 11/04/2016
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
ms.openlocfilehash: d781ce467123197521bf92dd4d932a665e55c6a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188938"
---
# <a name="critical_section-class"></a>critical_section クラス

コンカレンシー ランタイムを明示的に認識する再入不可能なミューテックスです。

## <a name="syntax"></a>構文

```cpp
class critical_section;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`native_handle_type`|`critical_section` オブジェクトへの参照です。|

### <a name="public-classes"></a>パブリック クラス

|名前|説明|
|----------|-----------------|
|[critical_section::scoped_lock クラス](#critical_section__scoped_lock_class)|オブジェクトの例外セーフ RAII ラッパー `critical_section` 。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[critical_section](#ctor)|新しいクリティカルセクションを構築します。|
|[~ critical_section デストラクター](#dtor)|クリティカルセクションを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[lock](#lock)|このクリティカルセクションを取得します。|
|[native_handle](#native_handle)|プラットフォーム固有のネイティブハンドル (存在する場合) を返します。|
|[try_lock](#try_lock)|ブロックせずにロックを取得しようとします。|
|[try_lock_for](#try_lock_for)|特定のミリ秒数の間、ブロックせずにロックを取得しようとします。|
|[ロック](#unlock)|クリティカルセクションのロックを解除します。|

## <a name="remarks"></a>解説

詳細については、「 [同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`critical_section`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="critical_section"></a><a name="ctor"></a> critical_section

新しいクリティカルセクションを構築します。

```cpp
critical_section();
```

## <a name="critical_section"></a><a name="dtor"></a> ~ critical_section

クリティカルセクションを破棄します。

```cpp
~critical_section();
```

### <a name="remarks"></a>解説

デストラクターの実行時にロックが保持されないことが想定されています。 ロックが保持されている状態でクリティカルセクションを破棄できるようにすると、未定義の動作が発生します。

## <a name="lock"></a><a name="lock"></a> 制限

このクリティカルセクションを取得します。

```cpp
void lock();
```

### <a name="remarks"></a>解説

多くの場合、 [scoped_lock](#critical_section__scoped_lock_class) コンストラクトを使用して、 `critical_section` 例外セーフな方法でオブジェクトを取得および解放する方が安全です。

ロックが呼び出し元のコンテキストによって既に保持されている場合は、 [improper_lock](improper-lock-class.md) 例外がスローされます。

## <a name="native_handle"></a><a name="native_handle"></a> native_handle

プラットフォーム固有のネイティブハンドル (存在する場合) を返します。

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>戻り値

クリティカルセクションへの参照。

### <a name="remarks"></a>解説

`critical_section`オブジェクトは、Windows オペレーティングシステムのプラットフォーム固有のネイティブハンドルに関連付けられていません。 メソッドは、単にオブジェクト自体への参照を返します。

## <a name="critical_sectionscoped_lock-class"></a><a name="critical_section__scoped_lock_class"></a> critical_section:: scoped_lock クラス

オブジェクトの例外セーフ RAII ラッパー `critical_section` 。

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_ctor"></a> scoped_lock:: scoped_lock

オブジェクトを構築 `scoped_lock` し、パラメーターで渡されるオブジェクトを取得し `critical_section` `_Critical_section` ます。 クリティカルセクションが別のスレッドによって保持されている場合、この呼び出しはブロックされます。

```cpp
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>パラメーター

*_Critical_section*<br/>
ロックするクリティカルセクション。

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock

オブジェクトを破棄 `scoped_lock` し、コンストラクターで指定されたクリティカルセクションを解放します。

```cpp
~scoped_lock();
```

## <a name="try_lock"></a><a name="try_lock"></a> try_lock

ブロックせずにロックを取得しようとします。

```cpp
bool try_lock();
```

### <a name="return-value"></a>戻り値

ロックが取得された場合は値。 **`true`** それ以外の場合は値 **`false`** 。

## <a name="try_lock_for"></a><a name="try_lock_for"></a> try_lock_for

特定のミリ秒数の間、ブロックせずにロックを取得しようとします。

```cpp
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>パラメーター

*_Timeout*<br/>
タイムアウトするまでのミリ秒単位の待機時間。

### <a name="return-value"></a>戻り値

ロックが取得された場合は値。 **`true`** それ以外の場合は値 **`false`** 。

## <a name="unlock"></a><a name="unlock"></a> ロック

クリティカルセクションのロックを解除します。

```cpp
void unlock();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[reader_writer_lock クラス](reader-writer-lock-class.md)
