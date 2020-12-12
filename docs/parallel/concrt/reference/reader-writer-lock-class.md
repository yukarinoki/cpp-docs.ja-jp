---
description: '詳細情報: reader_writer_lock クラス'
title: reader_writer_lock クラス
ms.date: 11/04/2016
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
ms.openlocfilehash: 68f42fbce607f05ceb489967d2b13cd08068d0cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115223"
---
# <a name="reader_writer_lock-class"></a>reader_writer_lock クラス

ローカルのみのスピンを行う、ライター優先キュー ベースのリーダー ライター ロックです。 ロックはライターに先入れ先出し (FIFO: First In First Out) アクセスを許可し、ライターに連続的な負荷がかかる状況ではリーダーが処理を実行できなくします。

## <a name="syntax"></a>構文

```cpp
class reader_writer_lock;
```

## <a name="members"></a>メンバー

### <a name="public-classes"></a>パブリック クラス

|名前|説明|
|----------|-----------------|
|[reader_writer_lock::scoped_lock クラス](#scoped_lock_class)|`reader_writer_lock`ロックオブジェクトをライターとして取得するために使用できる、例外セーフ RAII ラッパー。|
|[reader_writer_lock::scoped_lock_read クラス](#scoped_lock_read_class)|`reader_writer_lock`ロックオブジェクトをリーダーとして取得するために使用できる、例外セーフ RAII ラッパー。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[reader_writer_lock](#ctor)|新しい `reader_writer_lock` オブジェクトを構築します。|
|[~ reader_writer_lock デストラクター](#dtor)|`reader_writer_lock` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[lock](#lock)|リーダーライターロックをライターとして取得します。|
|[lock_read](#lock_read)|リーダーライターロックをリーダーとして取得します。 ライターがある場合、アクティブなリーダーは、完了するまで待機する必要があります。 リーダーは単に、ロックの対象を登録し、ライターが解放するまで待機します。|
|[try_lock](#try_lock)|ブロックせずにリーダーライターロックをライターとして取得しようとします。|
|[try_lock_read](#try_lock_read)|ブロックせずにリーダーとしてリーダーライターロックを取得しようとします。|
|[ロック](#unlock)|ロックを解除したユーザー、リーダー、またはライターに基づいて、読み取り/書き込みロックを解除します。|

## <a name="remarks"></a>解説

詳細については、「 [同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`reader_writer_lock`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="lock"></a><a name="lock"></a> 制限

リーダーライターロックをライターとして取得します。

```cpp
void lock();
```

### <a name="remarks"></a>解説

多くの場合、 [scoped_lock](#scoped_lock_class) コンストラクトを使用し `reader_writer_lock` て、例外セーフな方法でオブジェクトをライターとして取得し、解放する方が安全です。

ライターがロックを取得しようとすると、ライターが正常にロックを取得して解放するまで、今後のリーダーはブロックされます。 このロックは、ライターに対してバイアスをかけ、ライターの連続読み込みでリーダーを使用しないようにすることができます。

ライターは、ロックを終了するライターが行の次のライターを解放するようにチェーン化されます。

ロックが呼び出し元のコンテキストによって既に保持されている場合は、 [improper_lock](improper-lock-class.md) 例外がスローされます。

## <a name="lock_read"></a><a name="lock_read"></a> lock_read

リーダーライターロックをリーダーとして取得します。 ライターがある場合、アクティブなリーダーは、完了するまで待機する必要があります。 リーダーは単に、ロックの対象を登録し、ライターが解放するまで待機します。

```cpp
void lock_read();
```

### <a name="remarks"></a>解説

多くの場合、 [scoped_lock_read](#scoped_lock_read_class) コンストラクトを使用し `reader_writer_lock` て、例外セーフな方法でオブジェクトをリーダーとして取得および解放する方が安全です。

ロックを待機しているライターがある場合、リーダーは、行のすべてのライターがロックを取得し解放するまで待機します。 このロックは、ライターに対してバイアスをかけ、ライターの連続読み込みでリーダーを使用しないようにすることができます。

## <a name="reader_writer_lock"></a><a name="ctor"></a> reader_writer_lock

新しい `reader_writer_lock` オブジェクトを構築します。

```cpp
reader_writer_lock();
```

## <a name="reader_writer_lock"></a><a name="dtor"></a> ~ reader_writer_lock

`reader_writer_lock` オブジェクトを破棄します。

```cpp
~reader_writer_lock();
```

### <a name="remarks"></a>解説

デストラクターの実行時にロックが保持されないことが想定されています。 ロックが保持された状態でリーダーライターロックを破棄できるようにすると、未定義の動作が発生します。

## <a name="reader_writer_lockscoped_lock-class"></a><a name="scoped_lock_class"></a> reader_writer_lock:: scoped_lock クラス

`reader_writer_lock`ロックオブジェクトをライターとして取得するために使用できる、例外セーフ RAII ラッパー。

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_ctor"></a> scoped_lock:: scoped_lock

オブジェクトを構築 `scoped_lock` し、 `reader_writer_lock` パラメーターで `_Reader_writer_lock` ライターとして渡されたオブジェクトを取得します。 ロックが別のスレッドによって保持されている場合、この呼び出しはブロックされます。

```cpp
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>パラメーター

*_Reader_writer_lock*<br/>
`reader_writer_lock`ライターとして取得するオブジェクト。

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock

オブジェクトを破棄 `reader_writer_lock` し、コンストラクターで指定されたロックを解放します。

```cpp
~scoped_lock();
```

## <a name="reader_writer_lockscoped_lock_read-class"></a><a name="scoped_lock_read_class"></a> reader_writer_lock:: scoped_lock_read クラス

`reader_writer_lock`ロックオブジェクトをリーダーとして取得するために使用できる、例外セーフ RAII ラッパー。

```cpp
class scoped_lock_read;
```

## <a name="scoped_lock_readscoped_lock_read"></a><a name="scoped_lock_read_ctor"></a> scoped_lock_read:: scoped_lock_read

オブジェクトを構築 `scoped_lock_read` し、 `reader_writer_lock` パラメーターで `_Reader_writer_lock` リーダーとして渡されたオブジェクトを取得します。 ロックがライターとして別のスレッドによって保持されている場合、または保留中のライターがある場合、この呼び出しはブロックされます。

```cpp
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>パラメーター

*_Reader_writer_lock*<br/>
`reader_writer_lock`リーダーとして取得するオブジェクト。

## <a name="a-namescoped_lock_read_dtor--reader_writer_lockscoped_lock_readscoped_lock_read-destructor"></a><a name="scoped_lock_read_dtor">  reader_writer_lock:: scoped_lock_read:: ~ scoped_lock_read デストラクター

オブジェクトを破棄 `scoped_lock_read` し、コンストラクターで指定されたロックを解放します。

```cpp
~scoped_lock_read();
```

## <a name="try_lock"></a><a name="try_lock"></a> try_lock

ブロックせずにリーダーライターロックをライターとして取得しようとします。

### <a name="syntax"></a>構文

```cpp
bool try_lock();
```

### <a name="return-value"></a>戻り値

ロックが取得された場合は値。 **`true`** それ以外の場合は値 **`false`** 。

## <a name="try_lock_read"></a><a name="try_lock_read"></a> try_lock_read

ブロックせずにリーダーとしてリーダーライターロックを取得しようとします。

```cpp
bool try_lock_read();
```

### <a name="return-value"></a>戻り値

ロックが取得された場合は値。 **`true`** それ以外の場合は値 **`false`** 。

## <a name="unlock"></a><a name="unlock"></a> ロック

ロックを解除したユーザー、リーダー、またはライターに基づいて、読み取り/書き込みロックを解除します。

```cpp
void unlock();
```

### <a name="remarks"></a>解説

ロックを待機しているライターがある場合、ロックのリリースは常に FIFO の順序で次のライターに移ります。 このロックは、ライターに対してバイアスをかけ、ライターの連続読み込みでリーダーを使用しないようにすることができます。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[critical_section クラス](critical-section-class.md)
