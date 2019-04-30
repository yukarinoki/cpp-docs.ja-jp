---
title: '方法: コンテキスト クラスを使用して協調セマフォを実装するには'
ms.date: 11/04/2016
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
ms.openlocfilehash: 92f77fade972bff1528bc9a22416670354c70f34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366707"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>方法: コンテキスト クラスを使用して協調セマフォを実装するには

このトピックでは、concurrency::context クラスを使用して協調セマフォ クラスを実装する方法を示します。

`Context` クラスを使用すると、現在の実行コンテキストをブロックまたは生成できます。 現在のコンテキストをブロックまたは生成する機能は、リソースを使用できないことが原因で現在のコンテキストを続行できない場合に有用です。 A*セマフォ*使用可能になるリソースの現在の実行コンテキストを待つ必要があります、状況の 1 つの例を示します。 セマフォは、クリティカル セクション オブジェクトと同様に、1 つのコンテキストのコードがリソースに対して排他的にアクセスすることを可能にする同期オブジェクトです。 ただし、クリティカル セクション オブジェクトとは異なり、セマフォは、複数のコンテキストが並列的にリソースにアクセスできるようにします。 コンテキストの数が最大数に達してセマフォがロックされた場合、追加のコンテキストは、別のコンテキストがロックを解放するのを待機する必要があります。

### <a name="to-implement-the-semaphore-class"></a>semaphore クラスを実装するには

1. `semaphore` という名前のクラスを宣言します。 このクラスに `public` セクションと `private` セクションを追加します。

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. `private`のセクション、`semaphore`クラスを宣言、 [std::atomic](../../standard-library/atomic-structure.md)セマフォのカウントを保持する変数と[concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)コンテキストを保持するオブジェクトセマフォを取得するを待機する必要があります。

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. `public` クラスの `semaphore` セクションで、コンストラクターを実装します。 このコンストラクターは、ロックを同時に保持できるコンテキストの最大数を指定する `long long` 値を受け取ります。

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. `public` クラスの `semaphore` セクションで、`acquire` メソッドを実装します。 このメソッドは、分割不可能な操作として、セマフォのカウントをデクリメントします。 セマフォのカウントが負になった場合は、呼び出し、待機キューの末尾に、現在のコンテキストを追加、 [concurrency::Context::Block](reference/context-class.md#block)メソッドを現在のコンテキストをブロックします。

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. `public` クラスの `semaphore` セクションで、`release` メソッドを実装します。 このメソッドは、分割不可能な操作として、セマフォのカウントをインクリメントします。 インクリメント操作の前にセマフォのカウントが負になる場合は、ロックを待機しているコンテキストが 1 つ以上存在することを示します。 この場合は、待機キューの先頭にあるコンテキストのブロックを解除します。

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>例

この例の `semaphore` クラスは協調的に動作します。それは、`Context::Block` メソッドと `Context::Yield` メソッドによって実行が生成され、ランタイムが他のタスクを実行できるらめです。

`acquire` メソッドはカウンターをデクリメントしますが、別のコンテキストが `release` メソッドを呼び出す前にコンテキストを待機キューに追加できない可能性があります。 これは、対応するため、`release`メソッドを呼び出すスピン ループを使用して、 [:yield](reference/context-class.md#yield)メソッドを待機する、`acquire`メソッド コンテキストの追加を完了します。

`release` メソッドは、`Context::Unblock` メソッドが `acquire` メソッドを呼び出す前に、`Context::Block` メソッドを呼び出すことができます。 ランタイムではこれらのメソッドが任意の順序で呼び出されることが考慮されているため、この競合状態に対する対策は必要ありません。 `release` メソッドが `Context::Unblock` を呼び出す前に同じコンテキストに対して `acquire` メソッドが `Context::Block` を呼び出した場合、このコンテキストは非ブロック状態のままになります。 ランタイムでは、`Context::Block` の各呼び出しが対応する `Context::Unblock` の呼び出しと一致することのみが求められます。

次の例は、完全な `semaphore` クラスを示しています。 `wmain` 関数に、このクラスの基本的な使用法が示されています。 `wmain`関数は、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムをセマフォへのアクセスを必要とするいくつかのタスクを作成します。 3 つのスレッドがいつでもロックを保持できるため、いくつかのタスクは、別のタスクが完了してロックを解除するのを待機する必要があります。

[!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
In loop iteration 5...
In loop iteration 0...
In loop iteration 6...
In loop iteration 1...
In loop iteration 2...
In loop iteration 7...
In loop iteration 3...
In loop iteration 8...
In loop iteration 9...
In loop iteration 4...
```

詳細については、`concurrent_queue`クラスを参照してください[並列コンテナーとオブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)します。 詳細については、`parallel_for`アルゴリズムを参照してください[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)します。

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`cooperative-semaphore.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe /EHsc cooperative-semaphore.cpp**

## <a name="robust-programming"></a>信頼性の高いプログラミング

使用することができます、 *Resource Acquisition Is Initialization*へのアクセスを制限する (RAII) パターンを`semaphore`スコープを指定するオブジェクト。 RAII パターンでは、データ構造はスタック上に割り当てられます。 データ構造は、作成されたときにリソースを初期化または取得し、破棄されたときにそのリソースを破棄または解放します。 RAII パターンでは、外側のスコープが終了する前に、常にデストラクターが呼び出されます。 したがって、例外がスローされた場合や、関数に複数の `return` ステートメントが含まれている場合でも、リソースは適切に管理されます。

次の例では、`scoped_lock` クラスの `public` セクションに定義されている、`semaphore` という名前のクラスを定義しています。 `scoped_lock`クラスに似ています、 [concurrency::critical_section::scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class)と[concurrency::reader_writer_lock::scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class)クラス。 `semaphore::scoped_lock` クラスのコンストラクターは特定の `semaphore` オブジェクトへのアクセスを取得し、デストラクターはこのオブジェクトへのアクセスを解放します。

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
次の例では、RAII を使用して関数から制御が返される前にセマフォが確実に解放されるようにするために、`parallel_for` アルゴリズムに渡される処理関数の本体に変更を加えています。 これにより、処理関数は例外セーフとなります。

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>関連項目

[コンテキスト](../../parallel/concrt/contexts.md)<br/>
[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)
