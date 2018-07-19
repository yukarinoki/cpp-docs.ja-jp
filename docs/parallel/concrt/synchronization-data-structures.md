---
title: 同期データ構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f64acda5fe11cae3a40e4affc403ebb61d876de
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693807"
---
# <a name="synchronization-data-structures"></a>同期データ構造
同時実行ランタイムでは、複数のスレッドから共有データへのアクセスを同期するために、いくつかのデータ構造体を提供します。 これらのデータ構造は、頻繁に変更するデータを共有している場合に便利です。 たとえば、重要なセクションの同期オブジェクトは、共有リソースが利用するまで待機するには、他のスレッドをによりします。 そのため、このようなオブジェクトを頻繁に使用されるデータへのアクセスを同期するために使用する場合をスケーラビリティ、アプリケーションで失います。 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)提供、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラスは、複数のスレッドまたは同期の必要としないタスクにリソースを共有することができます。 詳細については、`combinable`クラスを参照してください[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)です。  
  
##  <a name="top"></a> セクション  
 このトピックでは、詳細での次の非同期メッセージ ブロックの型について説明します。  
  
-   [critical_section](#critical_section)  
  
-   [reader_writer_lock](#reader_writer_lock)  
  
-   [scoped_lock と scoped_lock_read](#scoped_lock)  
  
-   [event](#event)  
  
##  <a name="critical_section"></a> critical_section  
 [Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md)クラスにプリエンプトではなく、その他のタスクを生成する協調相互排他オブジェクトを表します。 重要なセクションは、複数のスレッドには、排他的な読み取りおよび共有データへの書き込みアクセスが必要とする場合に便利です。  

 `critical_section`クラスは、再入不可能なです。 [Concurrency::critical_section::lock](reference/critical-section-class.md#lock)メソッド型の例外をスロー [concurrency::improper_lock](../../parallel/concrt/reference/improper-lock-class.md)既にロックを所有するスレッドで呼び出された場合。  


  
### <a name="methods-and-features"></a>メソッドと機能  
 次の表に、重要なメソッドで定義されている、`critical_section`クラスです。  
  
|メソッド|説明|  
|------------|-----------------|  
|[lock](reference/critical-section-class.md#lock)|クリティカル セクションを取得します。 呼び出し元コンテキストまで、ブロック、ロックを取得します。|  
|[try_lock](reference/critical-section-class.md#try_lock)|クリティカル セクションの取得を試みますが、ブロックされません。|  
|[unlock](reference/critical-section-class.md#unlock)|クリティカル セクションを解放します。|  
  
 [[トップ](#top)]  
  
##  <a name="reader_writer_lock"></a> reader_writer_lock  
 [:Reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)クラスには、共有データへのスレッド セーフの読み取り/書き込み操作が用意されています。 リーダー/ライター ロックを使用して、複数のスレッドは共有リソースへの同時の読み取りアクセスを必要としますが、その共有リソースに書き込むことはほとんどありません。 このクラスは、オブジェクトを 1 つのスレッドの書き込みアクセスをいつでも、します。  
  
 `reader_writer_lock`クラスが実行できるよりも高く、`critical_section`クラスため、`critical_section`オブジェクトは、同時実行の読み取りアクセスを禁止する共有リソースへの排他アクセスを取得します。  
  
 同様に、`critical_section`クラス、`reader_writer_lock`クラスにプリエンプトではなく、その他のタスクを生成する協調相互排他オブジェクトを表します。  
  
 共有リソースに書き込む必要があります、スレッドは、リーダー/ライター ロックを取得するときに、ライター ロックを解放するまで、リソースにアクセスする必要がありますも他のスレッドはブロックされます。 `reader_writer_lock`クラスの例は、*書き込み優先*ロックで、ロックで待機しているリーダーのブロックを解除する前に待機中のライターのブロックを解除します。  
  
 同様に、`critical_section`クラス、`reader_writer_lock`クラスは、再入不可能なです。 [Concurrency::reader_writer_lock::lock](reference/reader-writer-lock-class.md#lock)と[concurrency::reader_writer_lock::lock_read](reference/reader-writer-lock-class.md#lock_read)メソッドが型の例外をスロー`improper_lock`既に所有しているスレッドで呼び出されると、ロックします。  


  
> [!NOTE]
>  `reader_writer_lock`クラスは、再入不可能なリーダー/ライター ロックに読み取り専用ロックをアップグレードまたは読み取り専用ロックにリーダー/ライター ロックにダウン グレードすることはできません。 これらの操作のいずれかを実行するには、未定義の動作が生成されます。  
  
### <a name="methods-and-features"></a>メソッドと機能  
 次の表に、重要なメソッドで定義されている、`reader_writer_lock`クラスです。  
  
|メソッド|説明|  
|------------|-----------------|  
|[lock](reference/reader-writer-lock-class.md#lock)|ロックへの読み取り/書き込みアクセスを取得します。|  
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|読み取り/書き込みアクセスをロックの取得を試みますが、ブロックされません。|  
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|読み取り専用アクセスをロックを取得します。|  
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|読み取り専用アクセスをロックの取得を試みますが、ブロックされません。|  
|[unlock](reference/reader-writer-lock-class.md#unlock)|ロックを解放します。|  
  
 [[トップ](#top)]  
  
##  <a name="scoped_lock"></a> scoped_lock と scoped_lock_read  
 `critical_section`と`reader_writer_lock`クラスは、相互排他オブジェクトを操作する方法を簡単にする入れ子になったヘルパー クラスを提供します。 これらのヘルパー クラスと呼ばれる*スコープ ロック*です。  
  
 `critical_section`クラスに含まれる、 [concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class)クラスです。 コンス トラクターを指定されたアクセスを取得する`critical_section`オブジェクト以外のオブジェクトへのアクセス権をデストラクター解放します。 `reader_writer_lock`クラスに含まれる、 [concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class)クラスに似た`critical_section::scoped_lock`、提供されたへの書き込みアクセスを管理することを除いて、`reader_writer_lock`オブジェクト。 `reader_writer_lock`クラスも含まれています、 [concurrency::reader_writer_lock::scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class)クラスです。 このクラスは、指定したへの読み取りアクセスを管理`reader_writer_lock`オブジェクト。  

  
 スコープを設定したロックが使用しているときに、いくつかの利点を提供`critical_section`と`reader_writer_lock`オブジェクトを手動でします。 通常は、スタック上のスコープのロックを割り当てます。 スコープのロックの相互排他オブジェクトへのアクセスと自動的に解放が破棄されるとします。したがって、するは手動でロックを解除、基になるオブジェクト。 これは、関数が複数含まれている場合に役立ちます`return`ステートメントです。 また、スコープ ロックは例外セーフなコードを記述することができます。 ときに、`throw`ステートメントによってスタック アンワインドが、アクティブなスコープ ロックのデストラクターが呼び出されると、および相互排他オブジェクトが常に正しくリリースされるためです。  
  
> [!NOTE]
>  使用すると、 `critical_section::scoped_lock`、 `reader_writer_lock::scoped_lock`、および`reader_writer_lock::scoped_lock_read`クラスが、基になる相互排他オブジェクトへのアクセスを手動で解放しません。 ランタイムは、無効な状態にこのことができます。  
  
##  <a name="event"></a> イベント  
 [Concurrency::event](../../parallel/concrt/reference/event-class.md)クラス状態をシグナル状態にしたり非シグナル状態の同期オブジェクトを表します。 を共有データへのアクセスを保護する目的とするには、クリティカル セクションなどの同期オブジェクトとは異なりは、イベントは、実行のフローを同期します。  
  
 `event`クラスは、1 つのタスクが別のタスクの作業を完了したときに便利です。 たとえば、1 つのタスク可能性があります通知別のタスク、ネットワーク接続とは、ファイルからデータを読み取ることができます。  
  
### <a name="methods-and-features"></a>メソッドと機能  
 によって定義されている重要なメソッドのいくつか次の表は、`event`クラスです。  
  
|メソッド|説明|  
|------------|-----------------|  
|[wait](reference/event-class.md#wait)|イベントがシグナル状態になるのを待機します。|  
|[set](reference/event-class.md#set)|イベントをシグナル状態に設定します。|  
|[reset](reference/event-class.md#reset)|イベントを非シグナル状態に設定します。|  
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|複数のイベントがシグナル状態になるのを待機します。|  

  
### <a name="example"></a>例  
 使用する方法を示す例については、`event`クラスを参照してください[を比較する同期データ構造体を Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)です。  
  
 [[トップ](#top)]  
  
## <a name="related-sections"></a>関連項目  
 [同期データ構造と Windows API の比較](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)  
 Windows API が提供する同期データ構造の動作を比較します。  
  
 [同時実行ランタイム](../../parallel/concrt/concurrency-runtime.md)  
 並列プログラミングを容易にする同時実行ランタイムについて説明します。また、関連トピックへのリンクを示します。

