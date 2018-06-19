---
title: '方法: 減少変数を使用して、同時実行ランタイムを使用する OpenMP ループを変換 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0191f88eea47d21c730172ddb3594db7655006ca
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692770"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>方法: 減少変数を使用する OpenMP ループを変換し、同時実行ランタイムを使用する
OpenMP を変換する方法を示します[並列](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[の](../../parallel/openmp/reference/for-openmp.md)ループを使用する、[削減](../../parallel/openmp/reference/reduction.md)句の同時実行ランタイムを使用します。  
  
 OpenMP `reduction` 句を使用すると、並列領域の最後にあるリダクション演算の対象となる 1 つ以上のスレッド プライベート変数を指定できます。 OpenMP には、リダクション演算子のセットがあらかじめ定義されています。 各リダクション変数はスカラー (`int`、`long`、`float` など) にする必要があります。 OpenMP には、並列領域でのリダクション変数の使用方法に関する制限事項もいくつか定義されています。  
  
 並列パターン ライブラリ (PPL) は、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)再利用可能なスレッド ローカル ストレージを使用すると、詳細な計算を実行し、その後、その計算を最終にマージを提供するクラス結果。 `combinable` クラスは、スカラー型と複合型の両方に作用するテンプレートです。 使用する、`combinable`クラス、parallel コンストラクトの本体でサブ計算を実行し、呼び出し、 [concurrency::combinable::combine](reference/combinable-class.md#combine)または[:combine_each](reference/combinable-class.md#combine_each)最終的な結果を生成するメソッドです。 `combine`と`combine_each`の各メソッドの実行、*関数を組み合わせる*要素の各ペアを結合する方法を指定します。 したがって、`combinable` クラスは、リダクション演算子の固定セットだけに制限されません。  
  
## <a name="example"></a>例  
 この例では、OpenMP と同時実行ランタイムの両方を使用して、最初の 35 個のフィボナッチ数の合計を計算します。  
  
 [!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
Using OpenMP...  
The sum of the first 35 Fibonacci numbers is 14930351.  
Using the Concurrency Runtime...  
The sum of the first 35 Fibonacci numbers is 14930351.  
```  
  
 詳細については、`combinable`クラスを参照してください[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)です。  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`concrt-omp-fibonacci-reduction.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc/openmp concrt-omp-フィボナッチ-reduction.cpp**  
  
## <a name="see-also"></a>関連項目  
 [OpenMP から同時実行ランタイムへの移行](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)

