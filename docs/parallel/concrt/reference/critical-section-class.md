---
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
ms.openlocfilehash: 24f96282a7728c6db6e0b05d36406f15383913f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372687"
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
|[critical_section::scoped_lock クラス](#critical_section__scoped_lock_class)|`critical_section`オブジェクトの例外セーフ RAII ラッパー。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[critical_section](#ctor)|新しいクリティカル セクションを作成します。|
|[~critical_sectionデストラクタ](#dtor)|クリティカル セクションを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ロック](#lock)|このクリティカル セクションを取得します。|
|[native_handle](#native_handle)|プラットフォーム固有のネイティブ ハンドルが存在する場合は、そのハンドルを返します。|
|[try_lock](#try_lock)|ブロックせずにロックを取得しようとします。|
|[try_lock_for](#try_lock_for)|特定のミリ秒数のブロックを行わずにロックを取得しようとします。|
|[ロック 解除](#unlock)|クリティカル セクションのロックを解除します。|

## <a name="remarks"></a>解説

詳細については、「[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`critical_section`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** 同時実行

## <a name="critical_section"></a><a name="ctor"></a>critical_section

新しいクリティカル セクションを作成します。

```cpp
critical_section();
```

## <a name="critical_section"></a><a name="dtor"></a>~critical_section

クリティカル セクションを破棄します。

```cpp
~critical_section();
```

### <a name="remarks"></a>解説

デストラクターの実行時にロックが保持されなくなることが予想されます。 ロックを保持したままクリティカル セクションを破棄すると、未定義の動作が発生します。

## <a name="lock"></a><a name="lock"></a>ロック

このクリティカル セクションを取得します。

```cpp
void lock();
```

### <a name="remarks"></a>解説

多くの場合[、scoped_lock](#critical_section__scoped_lock_class)の構造を利用して、例外セーフな`critical_section`方法でオブジェクトを取得して解放する方が安全です。

ロックが呼び出し元のコンテキストによって既に保持されている場合は[、improper_lock](improper-lock-class.md)例外がスローされます。

## <a name="native_handle"></a><a name="native_handle"></a>native_handle

プラットフォーム固有のネイティブ ハンドルが存在する場合は、そのハンドルを返します。

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>戻り値

クリティカル セクションへの参照。

### <a name="remarks"></a>解説

`critical_section`オブジェクトは、Windows オペレーティング システムのプラットフォーム固有のネイティブ ハンドルと関連付けされていません。 このメソッドは、オブジェクト自体への参照を返します。

## <a name="critical_sectionscoped_lock-class"></a><a name="critical_section__scoped_lock_class"></a>critical_section::scoped_lockクラス

`critical_section`オブジェクトの例外セーフ RAII ラッパー。

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_ctor"></a>scoped_lock::scoped_lock

オブジェクトを`scoped_lock`構築し、パラメーターで渡`critical_section`されたオブジェクトを`_Critical_section`取得します。 クリティカル セクションが別のスレッドによって保持されている場合、この呼び出しはブロックされます。

```cpp
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>パラメーター

*_Critical_section*<br/>
ロックするクリティカル セクション。

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_dtor"></a>scoped_lock::~scoped_lock

オブジェクトを`scoped_lock`破棄し、コンストラクターで指定されたクリティカル セクションを解放します。

```cpp
~scoped_lock();
```

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

ブロックせずにロックを取得しようとします。

```cpp
bool try_lock();
```

### <a name="return-value"></a>戻り値

ロックが取得された場合は、値**true、** それ以外の場合は、値**false。**

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

特定のミリ秒数のブロックを行わずにロックを取得しようとします。

```cpp
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>パラメーター

*_Timeout*<br/>
タイムアウトするまでの待機時間 (ミリ秒) です。

### <a name="return-value"></a>戻り値

ロックが取得された場合は、値**true、** それ以外の場合は、値**false。**

## <a name="unlock"></a><a name="unlock"></a>ロック 解除

クリティカル セクションのロックを解除します。

```cpp
void unlock();
```

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[reader_writer_lockクラス](reader-writer-lock-class.md)
