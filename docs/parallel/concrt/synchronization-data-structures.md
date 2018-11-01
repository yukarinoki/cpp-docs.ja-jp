---
title: 同期データ構造
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
ms.openlocfilehash: 8c91de87bb5d579916743051d06c15f6df6921bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495928"
---
# <a name="synchronization-data-structures"></a>同期データ構造

同時実行ランタイムでは、複数のスレッドから共有データへのアクセスを同期できるいくつかのデータ構造を提供します。 これらのデータ構造は、変更頻度の低いデータを共有している場合に便利です。 同期オブジェクトをクリティカル セクションなどは、他のスレッドが共有リソースが利用されるまで待機します。 そのため、頻繁に使用されるデータへのアクセスを同期するようなオブジェクトを使用する場合、アプリケーションでスケーラビリティを失うことができます。 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)提供、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラスは、複数のスレッドや同期を必要としないタスクでリソースを共有することができます。 詳細については、`combinable`クラスを参照してください[並列コンテナーとオブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)します。

##  <a name="top"></a> セクション

このトピックでは、詳細で次の非同期メッセージ ブロックの型について説明します。

- [critical_section](#critical_section)

- [reader_writer_lock](#reader_writer_lock)

- [scoped_lock と scoped_lock_read](#scoped_lock)

- [event](#event)

##  <a name="critical_section"></a> critical_section

[Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md)クラスにプリエンプトではなく、その他のタスクを生成する協調相互排他オブジェクトを表します。 クリティカル セクションは、複数のスレッドは、排他的読み取りと共有データへの書き込みアクセスが必要な場合に便利です。

`critical_section`クラスは、再入不可能な。 [Concurrency::critical_section::lock](reference/critical-section-class.md#lock)メソッド型の例外をスロー [concurrency::improper_lock](../../parallel/concrt/reference/improper-lock-class.md)既にロックを所有するスレッドによって呼び出された場合。

### <a name="methods-and-features"></a>メソッドと機能

次の表に、重要なメソッドで定義されている、`critical_section`クラス。

|メソッド|説明|
|------------|-----------------|
|[lock](reference/critical-section-class.md#lock)|クリティカル セクションを取得します。 呼び出し元のコンテキスト、ロックを取得するまでをブロックします。|
|[try_lock](reference/critical-section-class.md#try_lock)|クリティカル セクションの取得を試みますが、ブロックしません。|
|[unlock](reference/critical-section-class.md#unlock)|クリティカル セクションを解放します。|

[[トップ](#top)]

##  <a name="reader_writer_lock"></a> reader_writer_lock

[:Reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)クラスには、共有データへのスレッド セーフの読み取り/書き込み操作が用意されています。 読み取り/書き込みロックを使用して、複数のスレッドが共有リソースへの同時実行の読み取りアクセスが必要ですが、その共有リソースに書き込むことはほとんどありません。 このクラスは、いつでもオブジェクトを 1 つのスレッドの書き込みアクセスを示します。

`reader_writer_lock`クラスが実行できるよりも優れています、`critical_section`クラスのため、`critical_section`オブジェクトは、同時実行の読み取りアクセスを禁止の共有リソースへの排他アクセスを取得します。

ように、`critical_section`クラス、`reader_writer_lock`クラスにプリエンプトではなく、その他のタスクを生成する協調相互排他オブジェクトを表します。

共有リソースを記述する必要のあるスレッドでは、リーダー/ライター ロックを取得するときに、ライター ロックを解放するまでに、リソースにアクセスする必要がありますも他のスレッドがブロックされます。 `reader_writer_lock`クラスの例に示します、*書き込み優先*ロックで、ロックで待機しているリーダーのブロックを解除する前に待機しているライターのブロックを解除します。

ように、`critical_section`クラス、`reader_writer_lock`クラスは、再入不可能な。 [Concurrency::reader_writer_lock::lock](reference/reader-writer-lock-class.md#lock)と[concurrency::reader_writer_lock::lock_read](reference/reader-writer-lock-class.md#lock_read)メソッド型の例外をスローする`improper_lock`既に所有しているスレッドによって呼び出されると、ロックします。

> [!NOTE]
>  `reader_writer_lock`クラスは、再入不可能な場合、リーダー/ライター ロックに読み取り専用ロックをアップグレードまたは読み取り専用ロックへの読み取り/書き込みロックをダウン グレードすることはできません。 これらの操作のいずれかを実行するには、未定義の動作が生成されます。

### <a name="methods-and-features"></a>メソッドと機能

次の表に、重要なメソッドで定義されている、`reader_writer_lock`クラス。

|メソッド|説明|
|------------|-----------------|
|[lock](reference/reader-writer-lock-class.md#lock)|ロックへの読み取り/書き込みアクセスを取得します。|
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|ロックへの読み取り/書き込みアクセスの取得を試みますが、ブロックされません。|
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|ロックへの読み取り専用アクセスを取得します。|
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|ロックへの読み取り専用アクセスの取得を試みますが、ブロックされません。|
|[unlock](reference/reader-writer-lock-class.md#unlock)|ロックを解放します。|

[[トップ](#top)]

##  <a name="scoped_lock"></a> scoped_lock と scoped_lock_read

`critical_section`と`reader_writer_lock`クラスは、相互排他オブジェクトを操作する方法を簡略化する入れ子になったヘルパー クラスを提供します。 これらのヘルパー クラスと呼ばれます*スコープ ロック*します。

`critical_section`クラスが含まれています、 [concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class)クラス。 コンス トラクターは、提供されたアクセスを取得`critical_section`オブジェクト。 そのオブジェクトへのアクセス権をデストラクター解放します。 `reader_writer_lock`クラスが含まれています、 [concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class)クラスに似た`critical_section::scoped_lock`、提供された書き込みのアクセスを管理する点を除いて、`reader_writer_lock`オブジェクト。 `reader_writer_lock`クラスも含まれています、 [concurrency::reader_writer_lock::scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class)クラス。 このクラスは、指定されたへの読み取りアクセスを管理`reader_writer_lock`オブジェクト。

スコープのロックが使用しているときに、いくつかの利点を提供`critical_section`と`reader_writer_lock`オブジェクトを手動でします。 通常、スタック上のスコープのロックを割り当てます。 スコープのロックを解放相互排除して、そのオブジェクトへのアクセスに自動的に破棄されるときにそのため、操作を行いますない手動でロックを解除する基になるオブジェクト。 これは、関数が複数含まれている場合に役立ちます`return`ステートメント。 スコープのロックは例外セーフ コードを記述できます。 ときに、`throw`ステートメントによってスタック アンワインドが、アクティブなスコープ ロックのデストラクターが呼び出されると、および相互排他オブジェクトが常に正しくにリリースされるためです。

> [!NOTE]
>  使用すると、 `critical_section::scoped_lock`、 `reader_writer_lock::scoped_lock`、および`reader_writer_lock::scoped_lock_read`クラスが基になる相互排他オブジェクトへのアクセスを手動で解放しません。 無効な状態でこのランタイムを配置できます。

##  <a name="event"></a> イベント

[Concurrency::event](../../parallel/concrt/reference/event-class.md)クラス状態をシグナル状態になるか、非シグナルは、同期オブジェクトを表します。 重要なセクションでは、共有データへのアクセスを保護するが目的であるなどの同期オブジェクトとは異なりは、イベントは、実行の流れを同期します。

`event`クラスは、1 つのタスクが別のタスクの作業を完了したときに便利です。 たとえば、1 つのタスク可能性があります通知別のタスクのネットワーク接続またはファイルにデータを読み取られています。

### <a name="methods-and-features"></a>メソッドと機能

次の表にはいくつかの重要なメソッドで定義されている、`event`クラス。

|メソッド|説明|
|------------|-----------------|
|[wait](reference/event-class.md#wait)|イベントがシグナル状態になるのを待機します。|
|[set](reference/event-class.md#set)|イベントをシグナル状態に設定します。|
|[reset](reference/event-class.md#reset)|イベントを非シグナル状態に設定します。|
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|複数のイベントがシグナル状態になるのを待機します。|

### <a name="example"></a>例

使用する方法を示す例については、`event`クラスを参照してください[Windows API への同期データ構造の比較](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)します。

[[トップ](#top)]

## <a name="related-sections"></a>関連項目

[同期データ構造と Windows API の比較](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
Windows API が提供する同期データ構造の動作を比較します。

[コンカレンシー ランタイム](../../parallel/concrt/concurrency-runtime.md)<br/>
並列プログラミングを容易にするコンカレンシー ランタイムについて説明します。また、関連トピックへのリンクを示します。

