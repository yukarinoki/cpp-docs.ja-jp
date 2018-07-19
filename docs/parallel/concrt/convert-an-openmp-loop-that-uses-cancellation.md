---
title: '方法: 同時実行ランタイムを使用する取り消し処理を使用する OpenMP ループを変換 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, cancellation
- cancellation, converting from OpenMP to the Concurrency Runtime
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9dae22a46d6570d7ef7abbdfc08cb2c6d76d0c08
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693264"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-cancellation-to-use-the-concurrency-runtime"></a>方法: キャンセル処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する
並列ループによっては、すべての反復を必ずしも実行する必要はありません。 たとえば、値を検索するアルゴリズムは、値が見つかれば終了できます。 OpenMP には、並列ループを抜けるための機構は用意されていません。 ただし、ブール値 (フラグ) を使用して、ループの反復処理時に、解決策が見つかったことを通知できます。 同時実行ランタイムの場合、先行のタスクによって、まだ開始されていない他のタスクを取り消すことができます。  
  
 OpenMP を変換する方法を示します[並列](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[の](../../parallel/openmp/reference/for-openmp.md)ループを必要としないすべての反復を実行する同時実行ランタイムのキャンセル メカニズムを使用します。  
  
## <a name="example"></a>例  

 この例の並列バージョンを実装する OpenMP と同時実行ランタイムの両方を使用して、 [std::any_of](../../standard-library/algorithm-functions.md#any_of)アルゴリズムです。 この例に示す OpenMP バージョンでは、フラグを使用して、条件が満たされたときにすべての並列ループ反復で調整が行われるようにしています。 同時実行ランタイムを使用するバージョンを使用して、 [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel)メソッドを条件が満たされたときに、全体的な操作を停止します。  

  
 [!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
Using OpenMP...  
9114046 is in the array.  
Using the Concurrency Runtime...  
9114046 is in the array.  
```  
  
 OpenMP を使用するバージョンでは、フラグが設定されている場合でも、すべてのループ反復が実行されます。 さらに、タスクに子タスクが含まれている場合は、それらの子タスクにもフラグによって取り消しが通知される必要があります。 同時実行ランタイムでは、タスク グループが取り消されると、ランタイムは子タスクを含む全処理ツリーを取り消します。 [Concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズムでは、タスクを使用して、作業を実行します。 そのため、ループの 1 つの反復でルート タスクが取り消されると、計算ツリー全体が取り消されます。 処理ツリーが取り消された場合、ランタイムは新しいタスクを開始しません。 ただし、既に開始されているタスクは終了できます。 したがって、`parallel_for_each` アルゴリズムの場合、アクティブなループ反復によってリソースがクリーンアップされることがあります。  
  
 この例に示すどちらのバージョンでも、配列に検索対象値の複数のコピーが含まれている場合は、複数のループ反復でそれぞれ同時に結果が設定され、操作全体が取り消されることがあります。 条件が満たされたときに 1 つのタスクだけが実行されるようにする必要がある場合は、クリティカル セクションなどの同期プリミティブを使用できます。  
  
 また、例外処理を使用して、PPL を使用するタスクを取り消すこともできます。 取り消し処理の詳細については、次を参照してください。 [PPL における取り消し処理](cancellation-in-the-ppl.md)です。  
  
 詳細については`parallel_for_each`およびその他の並列アルゴリズムは、「[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)です。  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`concrt-omp-parallel-any-of.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc/openmp concrt-omp-並列-任意-of.cpp**  
  
## <a name="see-also"></a>関連項目  
 [OpenMP から同時実行ランタイムへの移行](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [PPL における取り消し処理](cancellation-in-the-ppl.md)   
 [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)

