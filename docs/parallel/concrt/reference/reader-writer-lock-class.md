---
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
ms.openlocfilehash: 13b44387f3e9489090ec31345fe4347ff5f205ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376243"
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
|[reader_writer_lock::scoped_lock クラス](#scoped_lock_class)|ロック オブジェクトをライターとして取得`reader_writer_lock`するために使用できる例外セーフ RAII ラッパー。|
|[reader_writer_lock::scoped_lock_read クラス](#scoped_lock_read_class)|ロック オブジェクトをリーダーとして取得`reader_writer_lock`するために使用できる例外セーフ RAII ラッパー。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[reader_writer_lock](#ctor)|新しい `reader_writer_lock` オブジェクトを構築します。|
|[~reader_writer_lockデストラクタ](#dtor)|`reader_writer_lock` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ロック](#lock)|リーダー ライター ロックをライターとして取得します。|
|[lock_read](#lock_read)|リーダー ライター ロックをリーダーとして取得します。 ライターが存在する場合、アクティブなリーダーは完了するまで待たなければなりません。 リーダーは、ロックへの関心を登録し、ライターがそれを解放するのを待ちます。|
|[try_lock](#try_lock)|ブロックせずに、リーダー ライター ロックをライターとして取得しようとします。|
|[try_lock_read](#try_lock_read)|ブロックせずにリーダー ライター ロックをリーダーとして取得しようとします。|
|[ロック 解除](#unlock)|ロックしたユーザー、リーダー、ライターに基づいて、リーダー ライター ロックのロックを解除します。|

## <a name="remarks"></a>解説

詳細については、「[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`reader_writer_lock`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** 同時実行

## <a name="lock"></a><a name="lock"></a>ロック

リーダー ライター ロックをライターとして取得します。

```cpp
void lock();
```

### <a name="remarks"></a>解説

多くの場合[、scoped_lock](#scoped_lock_class)構成を利用して`reader_writer_lock`、オブジェクトを安全な方法でライターとして取得および解放する方が安全です。

ライターがロックを取得しようとすると、その後の読み取りプログラムは、そのロックを正常に取得して解放するまでブロックされます。 このロックは作家に偏っており、作家の継続的な負荷の下で読者を飢えさせることができます。

ライターは、ロックを終了するライターが次のライターを行内で解放するようにチェーン化されます。

ロックが呼び出し元のコンテキストによって既に保持されている場合は[、improper_lock](improper-lock-class.md)例外がスローされます。

## <a name="lock_read"></a><a name="lock_read"></a>lock_read

リーダー ライター ロックをリーダーとして取得します。 ライターが存在する場合、アクティブなリーダーは完了するまで待たなければなりません。 リーダーは、ロックへの関心を登録し、ライターがそれを解放するのを待ちます。

```cpp
void lock_read();
```

### <a name="remarks"></a>解説

多くの場合[、scoped_lock_read](#scoped_lock_read_class)構造を利用して`reader_writer_lock`、オブジェクトを安全な方法でリーダーとして取得および解放する方が安全です。

ロックを待機しているライターが存在する場合、リーダーは、行内のすべてのライターがロックを取得して解放するまで待機します。 このロックは作家に偏っており、作家の継続的な負荷の下で読者を飢えさせることができます。

## <a name="reader_writer_lock"></a><a name="ctor"></a>reader_writer_lock

新しい `reader_writer_lock` オブジェクトを構築します。

```cpp
reader_writer_lock();
```

## <a name="reader_writer_lock"></a><a name="dtor"></a>~reader_writer_lock

`reader_writer_lock` オブジェクトを破棄します。

```cpp
~reader_writer_lock();
```

### <a name="remarks"></a>解説

デストラクターの実行時にロックが保持されなくなることが予想されます。 ロックを保持したままリーダー ライター ロックを破棄すると、未定義の動作が発生します。

## <a name="reader_writer_lockscoped_lock-class"></a><a name="scoped_lock_class"></a>reader_writer_lock::scoped_lockクラス

ロック オブジェクトをライターとして取得`reader_writer_lock`するために使用できる例外セーフ RAII ラッパー。

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_ctor"></a>scoped_lock::scoped_lock

オブジェクトを`scoped_lock`構築し、パラメーターで渡`reader_writer_lock`されたオブジェクトを`_Reader_writer_lock`ライターとして取得します。 ロックが別のスレッドによって保持されている場合、この呼び出しはブロックされます。

```cpp
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>パラメーター

*_Reader_writer_lock*<br/>
ライター`reader_writer_lock`として取得するオブジェクト。

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_dtor"></a>scoped_lock::~scoped_lock

オブジェクトを`reader_writer_lock`破棄し、コンストラクターで指定されたロックを解放します。

```cpp
~scoped_lock();
```

## <a name="reader_writer_lockscoped_lock_read-class"></a><a name="scoped_lock_read_class"></a>reader_writer_lock::scoped_lock_readクラス

ロック オブジェクトをリーダーとして取得`reader_writer_lock`するために使用できる例外セーフ RAII ラッパー。

```cpp
class scoped_lock_read;
```

## <a name="scoped_lock_readscoped_lock_read"></a><a name="scoped_lock_read_ctor"></a>scoped_lock_read::scoped_lock_read

オブジェクトを`scoped_lock_read`構築し、パラメーターで渡`reader_writer_lock`されたオブジェクトを`_Reader_writer_lock`リーダーとして取得します。 ロックがライターとして別のスレッドによって保持されている場合、または保留中のライターがある場合、この呼び出しはブロックされます。

```cpp
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>パラメーター

*_Reader_writer_lock*<br/>
リーダー`reader_writer_lock`として取得するオブジェクト。

## <a name="a-namescoped_lock_read_dtor--reader_writer_lockscoped_lock_readscoped_lock_read-destructor"></a><a name="scoped_lock_read_dtor">reader_writer_lock::scoped_lock_read::~scoped_lock_readデストラクタ

オブジェクトを`scoped_lock_read`破棄し、コンストラクターで指定されたロックを解放します。

```cpp
~scoped_lock_read();
```

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

ブロックせずに、リーダー ライター ロックをライターとして取得しようとします。

### <a name="syntax"></a>構文

```cpp
bool try_lock();
```

### <a name="return-value"></a>戻り値

ロックが取得された場合は、値**true、** それ以外の場合は、値**false。**

## <a name="try_lock_read"></a><a name="try_lock_read"></a>try_lock_read

ブロックせずにリーダー ライター ロックをリーダーとして取得しようとします。

```cpp
bool try_lock_read();
```

### <a name="return-value"></a>戻り値

ロックが取得された場合は、値**true、** それ以外の場合は、値**false。**

## <a name="unlock"></a><a name="unlock"></a>ロック 解除

ロックしたユーザー、リーダー、ライターに基づいて、リーダー ライター ロックのロックを解除します。

```cpp
void unlock();
```

### <a name="remarks"></a>解説

ロックを待機しているライターが存在する場合、ロックの解放は常に FIFO 順で次のライターに移動します。 このロックは作家に偏っており、作家の継続的な負荷の下で読者を飢えさせることができます。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[critical_section クラス](critical-section-class.md)
