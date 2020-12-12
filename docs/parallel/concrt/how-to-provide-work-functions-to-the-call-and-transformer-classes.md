---
description: '詳細については、「方法: 呼び出しクラスおよびトランスフォーマークラスに処理関数を提供する」を参照してください。'
title: '方法: call クラスおよび transformer クラスに処理関数を提供する'
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: 05def4dcc8357e73a8606fbc4ce741eebb647d37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197362"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>方法: call クラスおよび transformer クラスに処理関数を提供する

このトピックでは、 [concurrency:: call](../../parallel/concrt/reference/call-class.md) クラスおよび [concurrency:: トランスフォーマー](../../parallel/concrt/reference/transformer-class.md) クラスに処理関数を提供するいくつかの方法について説明します。

最初の例では、ラムダ式を `call` オブジェクトに渡す方法を示します。 2 番目の例では、関数オブジェクトを `call` オブジェクトに渡す方法を示します。 3 番目の例では、クラス メソッドを `call` オブジェクトにバインドする方法を示します。

このトピックの説明では、すべての例で `call` クラスを使用します。 クラスを使用する例につい `transformer` ては、「 [方法: データパイプラインでトランスフォーマーを使用](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)する」を参照してください。

## <a name="example-call-class"></a>例: call クラス

次の例は、`call` クラスを使用する一般的な方法を示しています。 この例は、ラムダ関数を `call` コンストラクターに渡します。

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
13 squared is 169.
```

## <a name="example-call-class-with-function-object"></a>例: function オブジェクトを使用したクラスの呼び出し

次の例は前の例に似ていますが、関数オブジェクト (ファンクタ) と共に `call` クラスを使用する点が異なります。

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example-functions-to-bind-call-object"></a>例: 呼び出しオブジェクトをバインドする関数

次の例は前の例と似ていますが、 [std:: bind1st](../../standard-library/functional-functions.md#bind1st) 関数と [std:: mem_fun](../../standard-library/functional-functions.md#mem_fun) 関数を使用してオブジェクトをクラスメソッドにバインドする点が異なり `call` ます。

この方法は、関数呼び出し演算子 `call` ではなく、特定のクラス メソッドに `transformer` オブジェクトまたは `operator()` オブジェクトをバインドする必要がある場合に使用します。

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

`bind1st`次の例に示すように、関数の結果を [std:: function](../../standard-library/function-class.md)オブジェクトに割り当てるか、キーワードを使用することもでき **`auto`** ます。

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `call.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

> **cl.exe/EHsc は .cpp を呼び出します**

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[方法: データパイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[call クラス](../../parallel/concrt/reference/call-class.md)<br/>
[トランスフォーマークラス](../../parallel/concrt/reference/transformer-class.md)
