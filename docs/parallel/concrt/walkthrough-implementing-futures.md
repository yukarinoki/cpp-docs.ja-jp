---
title: 'チュートリアル: フューチャの実装'
ms.date: 11/04/2016
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
ms.openlocfilehash: 4c43719199ef4009433ec65d54fcc238d82ac305
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525659"
---
# <a name="walkthrough-implementing-futures"></a>チュートリアル: フューチャの実装

このトピックでは、アプリケーションにフューチャを実装する方法について説明します。 このトピックでは、コンカレンシー ランタイムの既存の機能を組み合わせて、より効果的に使用する方法を示します。

> [!IMPORTANT]
>  このトピックでは、デモンストレーションのために、将来の概念について説明します。 使用することをお勧めします。 [std::future](../../standard-library/future-class.md)または[concurrency::task](../../parallel/concrt/reference/task-class.md)後で使用できる値を計算する非同期タスクを必要とする場合。

A*タスク*は追加より細かい計算に分解することができますの計算です。 A*将来*は後で使用できる値を計算する非同期タスク。

フューチャを実装するために、このトピックでは `async_future` クラスを定義します。 `async_future`クラスは、同時実行ランタイムのこれらのコンポーネントを使用して: [concurrency::task_group](reference/task-group-class.md)クラスおよび[concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md)クラス。 `async_future` クラスは、`task_group` クラスを使用して非同期的に値を計算し、`single_assignment` クラスを使用して計算結果を格納します。 `async_future` クラスのコンストラクターは、結果を計算する処理関数を受け取り、`get` メソッドが結果を取得します。

### <a name="to-implement-the-asyncfuture-class"></a>async_future クラスを実装するには

1. 計算結果の型でパラメーター化された `async_future` という名前のテンプレート クラスを宣言します。 このクラスに `public` セクションと `private` セクションを追加します。

[!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]

1. `private` クラスの `async_future` セクションで、`task_group` と `single_assignment` データ メンバーを宣言します。

[!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]

1. `public` クラスの `async_future` セクションで、コンストラクターを実装します。 コンストラクターは、結果を計算する処理関数でパラメーター化されたテンプレートです。 コンス トラクターは、処理関数を非同期に実行、`task_group`データ メンバーと、使用して、 [concurrency::send](reference/concurrency-namespace-functions.md#send)関数に結果の書き込み、`single_assignment`データ メンバー。

[!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]

1. `public` クラスの `async_future` セクションで、デストラクターを実装します。 デストラクターはタスクが完了するまで待機します。

[!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]

1. `public` クラスの `async_future` セクションで、`get` メソッドを実装します。 このメソッドを使用して、 [concurrency::receive](reference/concurrency-namespace-functions.md#receive)作業関数の結果を取得します。

[!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]

## <a name="example"></a>例

### <a name="description"></a>説明

完全な `async_future` クラスとその使用例を次に示します。 `wmain`関数の作成、std::[ベクター](../../standard-library/vector-class.md) 10,000 のランダムな整数値を含むオブジェクト。 次に `async_future` オブジェクトを使用して、`vector` オブジェクト内の最小値と最大値を見つけます。

### <a name="code"></a>コード

[!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]

### <a name="comments"></a>コメント

この例を実行すると、次の出力が生成されます。

```Output
smallest: 0
largest:  9999
average:  4981
```

この例では `async_future::get` メソッドを使用して、計算の結果を取得しています。 `async_future::get` メソッドは、計算がアクティブな場合は、計算が完了するまで待機します。

## <a name="robust-programming"></a>信頼性の高いプログラミング

拡張する、`async_future`処理関数によってスローされる例外の処理を変更するにはクラス、`async_future::get`メソッドを呼び出す、 [::task_group::wait](reference/task-group-class.md#wait)メソッド。 `task_group::wait` メソッドは、処理関数によって生成されたすべての例外をスローします。

`async_future` クラスを変更した例を次に示します。 `wmain`関数は、 `try` - `catch`の結果を出力するブロック、`async_future`オブジェクトまたは処理関数によって生成される例外の値を出力します。

[!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
caught exception: error
```

同時実行ランタイムで例外処理モデルの詳細については、次を参照してください。[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)します。

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`futures.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc futures.cpp**

## <a name="see-also"></a>関連項目

[コンカレンシー ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[task_group クラス](reference/task-group-class.md)<br/>
[single_assignment クラス](../../parallel/concrt/reference/single-assignment-class.md)
