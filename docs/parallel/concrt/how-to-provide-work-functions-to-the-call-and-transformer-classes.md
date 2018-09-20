---
title: '方法: 呼び出しおよび transformer クラスに処理関数を提供 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3102947009780f6f4e735b70506c5b2dc02f416b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438965"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>方法: call クラスおよび transformer クラスに処理関数を提供する

このトピックでは、作業関数を提供するいくつかの方法を示しています、 [concurrency::call](../../parallel/concrt/reference/call-class.md)と[concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)クラス。

最初の例では、ラムダ式を `call` オブジェクトに渡す方法を示します。 2 番目の例では、関数オブジェクトを `call` オブジェクトに渡す方法を示します。 3 番目の例では、クラス メソッドを `call` オブジェクトにバインドする方法を示します。

このトピックの説明では、すべての例で `call` クラスを使用します。 使用する例については、`transformer`クラスを参照してください[方法: データ パイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)します。

## <a name="example"></a>例

次の例は、`call` クラスを使用する一般的な方法を示しています。 この例は、ラムダ関数を `call` コンストラクターに渡します。

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
13 squared is 169.
```

## <a name="example"></a>例

次の例は前の例に似ていますが、関数オブジェクト (ファンクタ) と共に `call` クラスを使用する点が異なります。

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example"></a>例

使用する次の例には、前に似ています、 [std::bind1st](../../standard-library/functional-functions.md#bind1st)と[:mem_fun](../../standard-library/functional-functions.md#mem_fun)をバインドする関数を`call`クラス メソッドにオブジェクト。

この方法は、関数呼び出し演算子 `call` ではなく、特定のクラス メソッドに `transformer` オブジェクトまたは `operator()` オブジェクトをバインドする必要がある場合に使用します。

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

結果を割り当てることができます、`bind1st`関数を[std::function](../../standard-library/function-class.md)オブジェクトまたはを使用して、`auto`キーワードは、次の例に示すようにします。

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`call.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc call.cpp**

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[方法: データ パイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[call クラス](../../parallel/concrt/reference/call-class.md)<br/>
[transformer クラス](../../parallel/concrt/reference/transformer-class.md)
