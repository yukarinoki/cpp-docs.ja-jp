---
title: '方法: call クラスおよび transformer クラスに処理関数を提供 |Microsoft ドキュメント'
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
ms.openlocfilehash: ca7948a1258ac1b5193d379dd37f426360edc42e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>方法: call クラスおよび transformer クラスに処理関数を提供する
このトピックは、処理関数を提供するいくつかの方法を示しています、 [concurrency::call](../../parallel/concrt/reference/call-class.md)と[concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)クラスです。  
  
 最初の例では、ラムダ式を `call` オブジェクトに渡す方法を示します。 2 番目の例では、関数オブジェクトを `call` オブジェクトに渡す方法を示します。 3 番目の例では、クラス メソッドを `call` オブジェクトにバインドする方法を示します。  
  
 このトピックの説明では、すべての例で `call` クラスを使用します。 使用する例については、`transformer`クラスを参照してください[する方法: データ パイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)です。  
  
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

 次の例に似ていますが、以前を使用する点を除いて、 [std::bind1st](../../standard-library/functional-functions.md#bind1st)と[:mem_fun](../../standard-library/functional-functions.md#mem_fun)をバインドする関数、`call`クラス メソッドにオブジェクト。  

  
 この方法は、関数呼び出し演算子 `call` ではなく、特定のクラス メソッドに `transformer` オブジェクトまたは `operator()` オブジェクトをバインドする必要がある場合に使用します。  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 結果を割り当てることも、`bind1st`関数を[std::function](../../standard-library/function-class.md)オブジェクト、またはを使用して、`auto`キーワード、次の例で示すようにします。  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`call.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc call.cpp**  
  
## <a name="see-also"></a>関連項目  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [方法: データ パイプラインでトランスフォーマーを使用します。](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [クラスを呼び出します。](../../parallel/concrt/reference/call-class.md)   
 [transformer クラス](../../parallel/concrt/reference/transformer-class.md)
