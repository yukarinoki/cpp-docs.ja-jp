---
description: 詳細については、「同期データ構造」を参照してください。
title: 同期データ構造
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
ms.openlocfilehash: d5e2e9e6d79f1e71a8f18f98d69fb794597d0ccb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169347"
---
# <a name="synchronization-data-structures"></a>同期データ構造

同時実行ランタイムには、複数のスレッドからの共有データへのアクセスを同期できるデータ構造がいくつか用意されています。 これらのデータ構造は、変更する共有データがあまり使用されない場合に役立ちます。 同期オブジェクト (たとえば、クリティカルセクション) は、共有リソースが使用可能になるまで他のスレッドを待機させます。 このため、このようなオブジェクトを使用して頻繁に使用されるデータへのアクセスを同期する場合、アプリケーションのスケーラビリティが失われる可能性があります。 [並列パターンライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)は、 [concurrency:: 組み合わせ](../../parallel/concrt/reference/combinable-class.md)可能クラスを提供します。これにより、同期を必要とすることなく、複数のスレッドまたはタスク間でリソースを共有できます。 クラスの詳細については `combinable` 、「 [並列コンテナーとオブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。

## <a name="sections"></a><a name="top"></a> 各項

このトピックでは、次の非同期メッセージブロックの種類について詳しく説明します。

- [critical_section](#critical_section)

- [reader_writer_lock](#reader_writer_lock)

- [scoped_lock と scoped_lock_read](#scoped_lock)

- [event](#event)

## <a name="critical_section"></a><a name="critical_section"></a> critical_section

[Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md)クラスは、他のタスクを実行するのではなく、その他のタスクを生成する協調相互排他オブジェクトを表します。 重要なセクションは、複数のスレッドが共有データに対する排他的読み取りと書き込みアクセスを必要とする場合に役立ちます。

クラスは再入可能で `critical_section` はありません。 [Concurrency:: critical_section:: lock](reference/critical-section-class.md#lock)メソッドは、既にロックを所有しているスレッドによって呼び出された場合に、 [concurrency:: improper_lock](../../parallel/concrt/reference/improper-lock-class.md)型の例外をスローします。

### <a name="methods-and-features"></a>メソッドと機能

次の表は、クラスによって定義される重要なメソッドを示して `critical_section` います。

|Method|説明|
|------------|-----------------|
|[lock](reference/critical-section-class.md#lock)|クリティカルセクションを取得します。 呼び出しコンテキストは、ロックが取得されるまでブロックされます。|
|[try_lock](reference/critical-section-class.md#try_lock)|クリティカルセクションを取得しようとしますが、ブロックしません。|
|[ロック](reference/critical-section-class.md#unlock)|クリティカルセクションを解放します。|

[[上](#top)]

## <a name="reader_writer_lock"></a><a name="reader_writer_lock"></a> reader_writer_lock

[Concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)クラスは、共有データに対してスレッドセーフな読み取り/書き込み操作を提供します。 複数のスレッドが共有リソースへの同時読み取りアクセスを必要とするが、その共有リソースへの書き込みはほとんど行わない場合は、リーダー/ライターロックを使用します。 このクラスは、オブジェクトに対して常に1つのスレッド書き込みアクセスを提供します。

クラスは、 `reader_writer_lock` クラスよりもパフォーマンスが高くなり `critical_section` `critical_section` ます。これは、オブジェクトが共有リソースへの排他アクセスを取得するため、同時読み取りアクセスができないためです。

クラスと同様に、 `critical_section` `reader_writer_lock` クラスは協調相互排他オブジェクトを表します。このオブジェクトは、その他のタスクによって優先されます。

共有リソースへの書き込みを必要とするスレッドがリーダー/ライターロックを取得すると、そのリソースにもアクセスする必要がある他のスレッドは、ライターがロックを解放するまでブロックされます。 `reader_writer_lock`クラスは *書き込み設定* ロックの例です。これは、待機中のリーダーのブロックを解除する前に、待機中のライターのブロックを解除するロックです。

クラスと同様に、クラスは再 `critical_section` `reader_writer_lock` 入不可です。 [Concurrency:: reader_writer_lock:: lock](reference/reader-writer-lock-class.md#lock)メソッドと[concurrency:: reader_writer_lock:: lock_read](reference/reader-writer-lock-class.md#lock_read)メソッドは、 `improper_lock` 既にロックを所有しているスレッドによって呼び出された場合に、型の例外をスローします。

> [!NOTE]
> クラスは再 `reader_writer_lock` 入可能でないため、読み取り専用ロックをリーダー/ライターロックにアップグレードしたり、読み取り専用ロックにリーダー/ライターロックをダウングレードしたりすることはできません。 これらの操作のいずれかを実行すると、未定義の動作が発生します。

### <a name="methods-and-features"></a>メソッドと機能

次の表は、クラスによって定義される重要なメソッドを示して `reader_writer_lock` います。

|Method|説明|
|------------|-----------------|
|[lock](reference/reader-writer-lock-class.md#lock)|ロックへの読み取り/書き込みアクセス権を取得します。|
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|ロックへの読み取り/書き込みアクセスを取得しようとしますが、ブロックしません。|
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|ロックへの読み取り専用アクセスを取得します。|
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|ロックへの読み取り専用アクセスを取得しようとしますが、ブロックしません。|
|[ロック](reference/reader-writer-lock-class.md#unlock)|ロックを解放します。|

[[上](#top)]

## <a name="scoped_lock-and-scoped_lock_read"></a><a name="scoped_lock"></a> scoped_lock と scoped_lock_read

`critical_section`クラスとクラスには、 `reader_writer_lock` 相互排他オブジェクトの操作方法を簡略化する、入れ子になったヘルパークラスが用意されています。 これらのヘルパークラスは、 *スコープロック* と呼ばれます。

クラスには `critical_section` 、 [concurrency:: critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) クラスが含まれています。 コンストラクターは、指定されたオブジェクトへのアクセスを取得します。 `critical_section` デストラクターは、そのオブジェクトへのアクセスを解放します。 クラスには `reader_writer_lock` 、指定されたオブジェクトへの書き込みアクセスを管理することを除けば、に似た [concurrency:: reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) クラスが含まれてい `critical_section::scoped_lock` `reader_writer_lock` ます。 クラスには `reader_writer_lock` 、 [concurrency:: reader_writer_lock:: scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) クラスも含まれています。 このクラスは、指定されたオブジェクトへの読み取りアクセスを管理 `reader_writer_lock` します。

スコープが指定されたロックは、およびオブジェクトを手動で操作する場合に、いくつかの利点が `critical_section` `reader_writer_lock` あります。 通常は、スコープが指定されたロックをスタックに割り当てます。 スコープが指定されたロックは、その相互排他オブジェクトが破棄されると自動的に解放されます。そのため、基になるオブジェクトのロックを手動で解除する必要はありません。 これは、関数に複数のステートメントが含まれている場合に便利です **`return`** 。 スコープが指定したロックは、例外セーフなコードを記述するのにも役立ちます。 ステートメントに **`throw`** よってスタックがアンワインドされると、アクティブなスコープを持つロックのデストラクターが呼び出されます。そのため、相互排他オブジェクトは常に正しく解放されます。

> [!NOTE]
> 、、およびの各クラスを使用する場合は、 `critical_section::scoped_lock` `reader_writer_lock::scoped_lock` `reader_writer_lock::scoped_lock_read` 基になる相互排他オブジェクトへのアクセスを手動で解放しないでください。 これにより、ランタイムを無効な状態にすることができます。

## <a name="event"></a><a name="event"></a> イベント

[Concurrency:: event](../../parallel/concrt/reference/event-class.md)クラスは、状態がシグナルまたは非シグナルである同期オブジェクトを表します。 重要なセクションなど、共有データへのアクセスを保護することが目的である同期オブジェクトとは異なり、イベントは実行のフローを同期します。

クラスは、 `event` あるタスクが別のタスクに対して作業を完了したときに便利です。 たとえば、あるタスクが、ネットワーク接続またはファイルからデータを読み取ることを別のタスクに通知する場合があります。

### <a name="methods-and-features"></a>メソッドと機能

次の表は、クラスで定義されるいくつかの重要なメソッドを示して `event` います。

|Method|説明|
|------------|-----------------|
|[wait](reference/event-class.md#wait)|イベントがシグナル状態になるのを待機します。|
|[set](reference/event-class.md#set)|イベントをシグナル状態に設定します。|
|[reset](reference/event-class.md#reset)|イベントをシグナル状態以外の状態に設定します。|
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|複数のイベントがシグナル状態になるのを待機します。|

### <a name="example"></a>例

クラスの使用方法を示す例につい `event` ては、「 [同期データ構造と Windows API の比較](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)」を参照してください。

[[上](#top)]

## <a name="related-sections"></a>関連項目

[同期データ構造と Windows API の比較](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
同期データ構造の動作を、Windows API によって提供されるものと比較します。

[コンカレンシー ランタイム](../../parallel/concrt/concurrency-runtime.md)<br/>
並列プログラミングを容易にするコンカレンシー ランタイムについて説明します。また、関連トピックへのリンクを示します。
