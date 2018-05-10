---
title: reader_writer_lock クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a2f48a80efca0ec6e85a315b355a6482fb2096b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
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
|[reader_writer_lock::scoped_lock クラス](#scoped_lock_class)|取得に使用できる例外セーフ RAII ラッパー`reader_writer_lock`ライターとしてオブジェクトをロックします。|  
|[reader_writer_lock::scoped_lock_read クラス](#scoped_lock_read_class)|取得に使用できる例外セーフ RAII ラッパー`reader_writer_lock`リーダーとしてオブジェクトをロックします。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[reader_writer_lock](#ctor)|新しい `reader_writer_lock` オブジェクトを構築します。|  
|[~ reader_writer_lock デストラクター](#dtor)|`reader_writer_lock` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[lock](#lock)|ライターとしてのリーダー ライター ロックを取得します。|  
|[lock_read](#lock_read)|リーダーとしてのリーダー ライター ロックを取得します。 ライターがある場合は、アクティブなリーダーが終了するまで待機する必要があります。 リーダーは単に、ロックに関心を登録し、ライターによって解放されるを待機します。|  
|[try_lock](#try_lock)|ブロックすることがなく、ライターとしてのリーダー ライター ロックを取得しようとしています。|  
|[try_lock_read](#try_lock_read)|ブロックすることがなくリーダーとしてのリーダー ライター ロックを取得しようとしています。|  
|[unlock](#unlock)|リーダーまたはライターがロックされているユーザーに基づいてリーダー/ライター ロックを解除します。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `reader_writer_lock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="lock"></a> ロック 

 ライターとしてのリーダー ライター ロックを取得します。  
  
```
void lock();
```  
  
### <a name="remarks"></a>コメント  
 利用する方が安全では多くの場合、 [scoped_lock](#scoped_lock_class)コンストラクトを取得し、解放、`reader_writer_lock`オブジェクト ライターを例外として安全な方法です。  
  
 ライターがロックを獲得しようとすると、後に後続のリーダーはライターが正常に取得してロックを解除するまでブロックされます。 このロックはライターにバイアスは、ライターの負荷が継続的なリーダーの余裕ができすぎることができます。  
  
 ライターはライター ロックを終了する行の次のライターを解放するように連結されます。  
  
 ロックが呼び出し元のコンテキストによって既に保持されている場合、 [improper_lock](improper-lock-class.md)例外がスローされます。  
  
##  <a name="lock_read"></a> lock_read 

 リーダーとしてのリーダー ライター ロックを取得します。 ライターがある場合は、アクティブなリーダーが終了するまで待機する必要があります。 リーダーは単に、ロックに関心を登録し、ライターによって解放されるを待機します。  
  
```
void lock_read();
```  
  
### <a name="remarks"></a>コメント  
 利用する方が安全では多くの場合、 [scoped_lock_read](#scoped_lock_read_class)コンストラクトを取得し、解放、`reader_writer_lock`オブジェクト、例外内のリーダーとして安全な方法です。  
  
 ライター ロックで待機している場合は、リーダーはすべてのライターを取得およびロックが解放されるまで待機します。 このロックはライターにバイアスは、ライターの負荷が継続的なリーダーの余裕ができすぎることができます。  
  
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
  
### <a name="remarks"></a>コメント  
 デストラクターが実行されるときに、ロックが保持不要になったことが必要です。 未定義の動作で結果は保持もロックと消滅させるためにリーダー ライター ロックを許可します。  
  
##  <a name="scoped_lock_class"></a>  reader_writer_lock::scoped_lock クラス  
 取得に使用できる例外セーフ RAII ラッパー`reader_writer_lock`ライターとしてオブジェクトをロックします。  
  
```
class scoped_lock;
``` 
## <a name="scoped_lock_ctor"></a> scoped_lock::scoped_lock 

構築、`scoped_lock`オブジェクトを取得し、`reader_writer_lock`に渡されたオブジェクト、`_Reader_writer_lock`ライターとしてパラメーター。 ロックが別のスレッドによって保持されている場合、この呼び出しはブロックされます。  
  
  
```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Reader_writer_lock`  
 `reader_writer_lock`ライターとして取得するオブジェクト。  
  
## <a name="scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock 

破棄、`reader_writer_lock`オブジェクトし、そのコンス トラクターで指定されたロックを解放します。   

```
~scoped_lock();
```  
  
##  <a name="scoped_lock_read_class"></a>  reader_writer_lock::scoped_lock_read クラス  
 取得に使用できる例外セーフ RAII ラッパー`reader_writer_lock`リーダーとしてオブジェクトをロックします。  
  
```
class scoped_lock_read;
```  
  
##  <a name="try_lock"></a> try_lock 

 ブロックすることがなく、ライターとしてのリーダー ライター ロックを取得しようとしています。  

## <a name="scoped_lock_read_ctor"></a> scoped_lock_read::scoped_lock_read 

構築、`scoped_lock_read`オブジェクトを取得し、`reader_writer_lock`に渡されたオブジェクト、`_Reader_writer_lock`リーダーとしてパラメーター。 ライターとして別のスレッドによってロックが保持されているか、保留中のライターが、この呼び出しはブロックされます。  
  
```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Reader_writer_lock`  
 `reader_writer_lock`リーダーとして取得するオブジェクト。  
  
## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">  reader_writer_lock::scoped_lock_read:: ~ scoped_lock_read デストラクター
破棄、`scoped_lock_read`オブジェクトし、そのコンス トラクターで指定されたロックを解放します。  

```
~scoped_lock_read();
```  
  
## <a name="try_lock"></a> try_lock 

```
bool try_lock();
```  
  
### <a name="return-value"></a>戻り値  
 ロックが取得された場合、値`true`、それ以外の値`false`です。  
  
##  <a name="try_lock_read"></a> try_lock_read 

 ブロックすることがなくリーダーとしてのリーダー ライター ロックを取得しようとしています。  
  
```
bool try_lock_read();
```  
  
### <a name="return-value"></a>戻り値  
 ロックが取得された場合、値`true`、それ以外の値`false`です。  
  
##  <a name="unlock"></a> ロックを解除します。 

 リーダーまたはライターがロックされているユーザーに基づいてリーダー/ライター ロックを解除します。  
  
```
void unlock();
```  
  
### <a name="remarks"></a>コメント  
 ライター ロックで待機している場合は、FIFO の順序で次のライターに、ロックの解放が常にします。 このロックはライターにバイアスは、ライターの負荷が継続的なリーダーの余裕ができすぎることができます。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [critical_section クラス](critical-section-class.md)
