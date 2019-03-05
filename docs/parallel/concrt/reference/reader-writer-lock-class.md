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
ms.openlocfilehash: 111d48b9c4a575078f2342bfaa944871bbd628f5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268656"
---
# <a name="readerwriterlock-class"></a>reader_writer_lock クラス

ローカルのみのスピンを行う、ライター優先キュー ベースのリーダー ライター ロックです。 ロックはライターに先入れ先出し (FIFO: First In First Out) アクセスを許可し、ライターに連続的な負荷がかかる状況ではリーダーが処理を実行できなくします。

## <a name="syntax"></a>構文

```
class reader_writer_lock;
```

## <a name="members"></a>メンバー

### <a name="public-classes"></a>パブリック クラス

|名前|説明|
|----------|-----------------|
|[reader_writer_lock::scoped_lock クラス](#scoped_lock_class)|取得に使用できる例外安全な RAII ラッパー`reader_writer_lock`ライター オブジェクトをロックします。|
|[reader_writer_lock::scoped_lock_read クラス](#scoped_lock_read_class)|取得に使用できる例外安全な RAII ラッパー`reader_writer_lock`をリーダーとしてのオブジェクトをロックします。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[reader_writer_lock](#ctor)|新しい `reader_writer_lock` オブジェクトを構築します。|
|[~ reader_writer_lock デストラクター](#dtor)|
  `reader_writer_lock` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[lock](#lock)|ライターには、リーダー/ライター ロックを取得します。|
|[lock_read](#lock_read)|リーダーとして、リーダー/ライター ロックを取得します。 ライターがある場合は、アクティブなリーダーは、終了するまで待機するがあります。 リーダーは単に、ロックに関心を登録し、ライターによって解放されるまで待機します。|
|[try_lock](#try_lock)|ブロックすることがなく、ライターとしてリーダー/ライター ロックを取得しようとしています。|
|[try_lock_read](#try_lock_read)|ブロックすることがなく、リーダーとしてリーダー/ライター ロックを取得しようとしています。|
|[unlock](#unlock)|リーダーまたはライターがロックされているユーザーに基づいて、リーダー/ライター ロックを解除します。|

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`reader_writer_lock`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="lock"></a> ロック

ライターには、リーダー/ライター ロックを取得します。

```
void lock();
```

### <a name="remarks"></a>Remarks

利用する方が安全では多くの場合、 [scoped_lock](#scoped_lock_class)コンストラクトを取得および解放、`reader_writer_lock`オブジェクトを例外のライターとして安全な方法です。

ライターがロックを取得しようとすると、後に後続のリーダーはライターを正常に取得およびロックを解放するまでブロックされます。 このロックはライターが増えます、ライターの負荷が継続的なリーダーの処理を続行できなくできます。

ライターは、ライター ロックを終了する行の次のライターを解放するために連結されます。

ロックは既に呼び出し元のコンテキストによって保持されている場合、 [improper_lock](improper-lock-class.md)例外がスローされます。

##  <a name="lock_read"></a> lock_read

リーダーとして、リーダー/ライター ロックを取得します。 ライターがある場合は、アクティブなリーダーは、終了するまで待機するがあります。 リーダーは単に、ロックに関心を登録し、ライターによって解放されるまで待機します。

```
void lock_read();
```

### <a name="remarks"></a>Remarks

利用する方が安全では多くの場合、 [scoped_lock_read](#scoped_lock_read_class)コンストラクトを取得および解放を`reader_writer_lock`オブジェクト、例外がリーダーとして安全な方法です。

ライター ロックを待機している場合は、リーダーはすべてのライターを取得およびロックが解放されるまで待機します。 このロックはライターが増えます、ライターの負荷が継続的なリーダーの処理を続行できなくできます。

##  <a name="ctor"></a> reader_writer_lock

新しい `reader_writer_lock` オブジェクトを構築します。

```
reader_writer_lock();
```

##  <a name="dtor"></a> ~reader_writer_lock


  `reader_writer_lock` オブジェクトを破棄します。

```
~reader_writer_lock();
```

### <a name="remarks"></a>Remarks

デストラクターが実行されるときに、ロックが保持されないと想定されます。 未定義の動作、結果の保持をされているロックを消滅させるためにリーダー ライター ロックを許可します。

##  <a name="scoped_lock_class"></a>  reader_writer_lock::scoped_lock クラス

取得に使用できる例外安全な RAII ラッパー`reader_writer_lock`ライター オブジェクトをロックします。

```
class scoped_lock;
```

## <a name="scoped_lock_ctor"></a> scoped_lock::scoped_lock

構築します、`scoped_lock`オブジェクトし、取得、`reader_writer_lock`で渡されるオブジェクト、`_Reader_writer_lock`パラメーター ライター。 別のスレッドによってロックは、この呼び出しはブロックされます。

```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

#### <a name="parameters"></a>パラメーター

*_Reader_writer_lock*<br/>
`reader_writer_lock`ライターを取得するオブジェクト。

## <a name="scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock

破棄、`reader_writer_lock`オブジェクトし、そのコンス トラクターでロックを解放します。

```
~scoped_lock();
```

##  <a name="scoped_lock_read_class"></a>  reader_writer_lock::scoped_lock_read クラス

取得に使用できる例外安全な RAII ラッパー`reader_writer_lock`をリーダーとしてのオブジェクトをロックします。

```
class scoped_lock_read;
```

##  <a name="try_lock"></a> try_lock

ブロックすることがなく、ライターとしてリーダー/ライター ロックを取得しようとしています。

## <a name="scoped_lock_read_ctor"></a> scoped_lock_read::scoped_lock_read

構築、`scoped_lock_read`オブジェクトし、取得、`reader_writer_lock`で渡されるオブジェクト、`_Reader_writer_lock`をリーダーとしてパラメーター。 ライターとして別のスレッドによってロックが保持されているか、保留中のライターが、この呼び出しはブロックされます。

```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

#### <a name="parameters"></a>パラメーター

*_Reader_writer_lock*<br/>
`reader_writer_lock`をリーダーとして取得するオブジェクト。

## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">  reader_writer_lock::scoped_lock_read:: ~ scoped_lock_read デストラクター

破棄、`scoped_lock_read`オブジェクトし、そのコンス トラクターでロックを解放します。

```
~scoped_lock_read();
```

## <a name="try_lock"></a> try_lock

```
bool try_lock();
```

### <a name="return-value"></a>戻り値

ロックが取得された場合、値**true**、それ以外の値**false**します。

##  <a name="try_lock_read"></a> try_lock_read

ブロックすることがなく、リーダーとしてリーダー/ライター ロックを取得しようとしています。

```
bool try_lock_read();
```

### <a name="return-value"></a>戻り値

ロックが取得された場合、値**true**、それ以外の値**false**します。

##  <a name="unlock"></a> ロックを解除します。

リーダーまたはライターがロックされているユーザーに基づいて、リーダー/ライター ロックを解除します。

```
void unlock();
```

### <a name="remarks"></a>Remarks

ライター ロックを待機している場合は、FIFO の順序で次のライターに、ロックのリリースが常にします。 このロックはライターが増えます、ライターの負荷が継続的なリーダーの処理を続行できなくできます。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[critical_section クラス](critical-section-class.md)
