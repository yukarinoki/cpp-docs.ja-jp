---
title: 'チュートリアル: フューチャの実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12f2bd5897945dec0045019462c2faeb665a19e4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-implementing-futures"></a>チュートリアル: フューチャの実装
このトピックでは、アプリケーションにフューチャを実装する方法について説明します。 このトピックでは、同時実行ランタイムの既存の機能を組み合わせて、より効果的に使用する方法を示します。  
  
> [!IMPORTANT]
>  このトピックでは、デモンストレーションのために、将来の概念について説明します。 使用することをお勧め[std::future](../../standard-library/future-class.md)または[concurrency::task](../../parallel/concrt/reference/task-class.md)後で使用できる値を計算する非同期タスクを必要とする場合。  
  
 A*タスク*は追加より細かい計算に分解することができますを計算します。 A*将来*後で使用できる値を計算する非同期タスクです。  
  
 フューチャを実装するために、このトピックでは `async_future` クラスを定義します。 `async_future`クラスは、同時実行ランタイムのこれらのコンポーネントを使用して: [concurrency::task_group](reference/task-group-class.md)クラスおよび[concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md)クラスです。 `async_future` クラスは、`task_group` クラスを使用して非同期的に値を計算し、`single_assignment` クラスを使用して計算結果を格納します。 `async_future` クラスのコンストラクターは、結果を計算する処理関数を受け取り、`get` メソッドが結果を取得します。  
  
### <a name="to-implement-the-asyncfuture-class"></a>async_future クラスを実装するには  
  
1.  計算結果の型でパラメーター化された `async_future` という名前のテンプレート クラスを宣言します。 このクラスに `public` セクションと `private` セクションを追加します。  
  
 [!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]  
  
2.  `private` クラスの `async_future` セクションで、`task_group` と `single_assignment` データ メンバーを宣言します。  
  
 [!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]  
  

3.  `public` クラスの `async_future` セクションで、コンストラクターを実装します。 コンストラクターは、結果を計算する処理関数でパラメーター化されたテンプレートです。 コンス トラクター内で、作業関数を非同期に実行する、`task_group`データ メンバーを使用して、 [concurrency::send](reference/concurrency-namespace-functions.md#send)関数を結果の書き込み、`single_assignment`データ メンバーです。  
  
 [!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]  
  
4.  `public` クラスの `async_future` セクションで、デストラクターを実装します。 デストラクターはタスクが完了するまで待機します。  
  
 [!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]  
  

5.  `public` クラスの `async_future` セクションで、`get` メソッドを実装します。 このメソッドを使用して、 [concurrency::receive](reference/concurrency-namespace-functions.md#receive)処理関数の結果を取得します。  

  
 [!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 完全な `async_future` クラスとその使用例を次に示します。 `wmain`関数を作成する std::[ベクター](../../standard-library/vector-class.md) 10,000 のランダムな整数値を含むオブジェクト。 次に `async_future` オブジェクトを使用して、`vector` オブジェクト内の最小値と最大値を見つけます。  
  
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


 拡張する、`async_future`変更、処理関数によってスローされる例外を処理するクラス、`async_future::get`メソッドを呼び出す、 [concurrency::task_group::wait](reference/task-group-class.md#wait)メソッドです。 `task_group::wait` メソッドは、処理関数によって生成されたすべての例外をスローします。  


  
 `async_future` クラスを変更した例を次に示します。 `wmain`関数は、 `try` - `catch`ブロックの結果を印刷する、`async_future`オブジェクトまたは処理関数によって生成される例外の値を出力します。  
  
 [!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
caught exception: error  
```  
  
 同時実行ランタイムで例外処理モデルの詳細については、次を参照してください。[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)です。  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`futures.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc futures.cpp**  
  
## <a name="see-also"></a>関連項目  
 [同時実行ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [task_group クラス](reference/task-group-class.md)   
 [single_assignment クラス](../../parallel/concrt/reference/single-assignment-class.md)
