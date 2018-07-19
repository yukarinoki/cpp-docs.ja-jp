---
title: critical_section クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0287c74155e7b4fe827bb015b43cfca3384f3b1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693563"
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
|[critical_section::scoped_lock クラス](#critical_section__scoped_lock_class)|例外セーフ RAII ラッパー、`critical_section`オブジェクト。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[critical_section](#ctor)|新しい重要なセクションを構築します。|  
|[~ critical_section デストラクター](#dtor)|クリティカル セクションを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[lock](#lock)|この重要なセクションを取得します。|  
|[native_handle](#native_handle)|1 つが存在する場合は、プラットフォーム固有のネイティブ ハンドルを返します。|  
|[try_lock](#try_lock)|ブロックすることがなく、ロックの取得を試みます。|  
|[try_lock_for](#try_lock_for)|特定のミリ秒数をブロックすることがなく、ロックの取得を試みます。|  
|[unlock](#unlock)|クリティカル セクションのロックを解除します。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `critical_section`  
  
## <a name="requirements"></a>要件  
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
  
### <a name="remarks"></a>コメント  
 デストラクターが実行されるときに、ロックが保持不要になったことが必要です。 未定義の動作で結果は保持もロックと消滅させるために重要なセクションを許可します。  
  
##  <a name="lock"></a> ロック 

 この重要なセクションを取得します。  
  
```
void lock();
```  
  
### <a name="remarks"></a>コメント  
 利用する方が安全では多くの場合、 [scoped_lock](#critical_section__scoped_lock_class)コンストラクトを取得し、解放、`critical_section`例外オブジェクト安全な方法です。  
  
 ロックが呼び出し元のコンテキストによって既に保持されている場合、 [improper_lock](improper-lock-class.md)例外がスローされます。  
  
##  <a name="native_handle"></a> native_handle 

 1 つが存在する場合は、プラットフォーム固有のネイティブ ハンドルを返します。  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>戻り値  
 クリティカル セクションへの参照。  
  
### <a name="remarks"></a>コメント  
 A`critical_section`オブジェクトに関連付けられていない Windows オペレーティング システムのプラットフォームの特定ネイティブ ハンドルです。 このメソッドは、単にオブジェクト自体への参照を返します。  
  
##  <a name="critical_section__scoped_lock_class"></a>  critical_section::scoped_lock クラス  
 例外セーフ RAII ラッパー、`critical_section`オブジェクト。  
  
```
class scoped_lock;
```  
  
##  <a name="critical_section__scoped_lock_ctor"></a> scoped_lock::scoped_lock 

 構築、`scoped_lock`オブジェクトを取得し、`critical_section`に渡されたオブジェクト、`_Critical_section`パラメーター。 クリティカル セクションが別のスレッドによって保持されている場合、この呼び出しはブロックされます。  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Critical_section`  
 ロックには、重要なセクションです。  
  
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
 ロックが取得された場合、値`true`、それ以外の値`false`です。  
  
##  <a name="try_lock_for"></a> try_lock_for 

 特定のミリ秒数をブロックすることがなく、ロックの取得を試みます。  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Timeout`  
 タイムアウトになるまで待機するミリ秒数。  
  
### <a name="return-value"></a>戻り値  
 ロックが取得された場合、値`true`、それ以外の値`false`です。  
  
##  <a name="unlock"></a> ロックを解除します。 

 クリティカル セクションのロックを解除します。  
  
```
void unlock();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [reader_writer_lock クラス](reader-writer-lock-class.md)
