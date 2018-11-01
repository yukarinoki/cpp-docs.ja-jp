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
ms.openlocfilehash: a08cb5049d742a9740361595bd931a2f7a48bd16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498765"
---
# <a name="criticalsection-class"></a>critical_section クラス

同時実行ランタイムを明示的に認識する再入不可能なミューテックスです。

## <a name="syntax"></a>構文

```
class critical_section;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`native_handle_type`|`critical_section` オブジェクトへの参照。|

### <a name="public-classes"></a>パブリック クラス

|名前|説明|
|----------|-----------------|
|[critical_section::scoped_lock クラス](#critical_section__scoped_lock_class)|例外安全な RAII ラッパーを`critical_section`オブジェクト。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[critical_section](#ctor)|新しい重要なセクションを構築します。|
|[~ critical_section デストラクター](#dtor)|クリティカル セクションを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[lock](#lock)|この重要なセクションを取得します。|
|[native_handle](#native_handle)|いずれかが存在する場合は、プラットフォーム固有のネイティブ ハンドルを返します。|
|[try_lock](#try_lock)|ブロックすることがなく、ロックの取得を試みます。|
|[try_lock_for](#try_lock_for)|ミリ秒数を特定のブロックすることがなく、ロックの取得を試みます。|
|[unlock](#unlock)|クリティカル セクションのロックを解除します。|

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`critical_section`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> critical_section

新しい重要なセクションを構築します。

```
critical_section();
```

##  <a name="dtor"></a> ~critical_section

クリティカル セクションを破棄します。

```
~critical_section();
```

### <a name="remarks"></a>Remarks

デストラクターが実行されるときに、ロックが保持されないと想定されます。 未定義の動作で、結果の保持をされている、クリティカル セクションがロックに破棄されることができます。

##  <a name="lock"></a> ロック

この重要なセクションを取得します。

```
void lock();
```

### <a name="remarks"></a>Remarks

利用する方が安全では多くの場合、 [scoped_lock](#critical_section__scoped_lock_class)コンストラクトを取得および解放を`critical_section`オブジェクト、例外が安全な方法です。

ロックは既に呼び出し元のコンテキストによって保持されている場合、 [improper_lock](improper-lock-class.md)例外がスローされます。

##  <a name="native_handle"></a> native_handle

いずれかが存在する場合は、プラットフォーム固有のネイティブ ハンドルを返します。

```
native_handle_type native_handle();
```

### <a name="return-value"></a>戻り値

クリティカル セクションへの参照。

### <a name="remarks"></a>Remarks

A`critical_section`オブジェクトは、Windows オペレーティング システムのプラットフォームの特定ネイティブ ハンドルに関連付けられていません。 メソッドは、単に、オブジェクト自体への参照を返します。

##  <a name="critical_section__scoped_lock_class"></a>  critical_section::scoped_lock クラス

例外安全な RAII ラッパーを`critical_section`オブジェクト。

```
class scoped_lock;
```

##  <a name="critical_section__scoped_lock_ctor"></a> scoped_lock::scoped_lock

構築、`scoped_lock`オブジェクトし、取得、`critical_section`で渡されるオブジェクト、`_Critical_section`パラメーター。 クリティカル セクションは、別のスレッドによって保持されているが、この呼び出しはブロックされます。

```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>パラメーター

*_Critical_section*<br/>
ロックするクリティカル セクション。

##  <a name="critical_section__scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock

破棄、`scoped_lock`オブジェクトし、そのコンス トラクターで重要なセクションを解放します。

```
~scoped_lock();
```

##  <a name="try_lock"></a> try_lock

ブロックすることがなく、ロックの取得を試みます。

```
bool try_lock();
```

### <a name="return-value"></a>戻り値

ロックが取得された場合、値**true**、それ以外の値**false**します。

##  <a name="try_lock_for"></a> try_lock_for

ミリ秒数を特定のブロックすることがなく、ロックの取得を試みます。

```
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>パラメーター

*タイムアウト _t*<br/>
タイムアウトになるまで待機するミリ秒数。

### <a name="return-value"></a>戻り値

ロックが取得された場合、値**true**、それ以外の値**false**します。

##  <a name="unlock"></a> ロックを解除します。

クリティカル セクションのロックを解除します。

```
void unlock();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[reader_writer_lock クラス](reader-writer-lock-class.md)
