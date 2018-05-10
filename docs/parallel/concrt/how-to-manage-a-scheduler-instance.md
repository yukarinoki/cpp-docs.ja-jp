---
title: '方法: スケジューラ インスタンスを管理 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 699abcbc75dc4f0df40d07d26c0e6987d4711fe3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-manage-a-scheduler-instance"></a>方法: スケジューラ インスタンスを管理する
スケジューラ インスタンスにより、特定のスケジューリング ポリシーと各種の作業負荷を関連付けることができます。 このトピックには、スケジューラ インスタンスを作成および管理する方法を示す 2 つの基本的な例が含まれています。  
  
 例では、既定のスケジューラ ポリシーを使用するスケジューラを作成します。 スケジューラを作成する例は、カスタム ポリシーを使用して、参照してください[する方法: 特定のスケジューラ ポリシーの指定](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)です。  
  
### <a name="to-manage-a-scheduler-instance-in-your-application"></a>アプリケーションのスケジューラ インスタンスを管理するには  
  
1.  作成、 [concurrency::schedulerpolicy](../../parallel/concrt/reference/schedulerpolicy-class.md)スケジューラを使用するポリシーを含んでいるオブジェクトの値します。  
  

2.  呼び出す、 [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create)メソッドまたは[:create](reference/scheduler-class.md#create)スケジューラ インスタンスを作成するメソッド。  
  
     使用する場合、`Scheduler::Create`メソッドを呼び出し、 [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach)メソッドは、現在のコンテキストにスケジューラを関連付ける必要があるとします。  
  
3.  呼び出す、 [CreateEvent](http://msdn.microsoft.com/library/windows/desktop/ms682396)を非シグナルの自動リセット イベント オブジェクトへのハンドルを作成する関数。  
  
4.  先ほど作成したイベント オブジェクトへのハンドルを渡す、 [concurrency::CurrentScheduler::RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)メソッドまたは[concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)メソッドです。 これにより、スケジューラが破棄されるときに設定されるイベントが登録されます。  
  
5.  現在のスケジューラでスケジュールするタスクを実行します。  
  
6.  呼び出す、 [::detach](reference/currentscheduler-class.md#detach)メソッドを現在のスケジューラをデタッチして、現在と以前のスケジューラを復元します。  
  
     使用する場合、`Scheduler::Create`メソッドを呼び出し、 [concurrency::Scheduler::Release](reference/scheduler-class.md#release)の参照カウントをデクリメントするためのメソッド、`Scheduler`オブジェクト。  
  
7.  イベントにハンドルを渡す、 [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032)スケジューラをシャット ダウンするまで待機する関数。  
  
8.  呼び出す、 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211)イベント オブジェクトへのハンドルを閉じます。  
  
## <a name="example"></a>例  
 次のコードに、スケジューラ インスタンスを管理するための 2 つの方法を示します。 どちらの例でも、最初に既定のスケジューラを使用して、現在のスケジューラの一意の識別子を印刷するタスクを実行します。 次に、スケジューラ インスタンスを使用して同じタスクを再び実行します。 最後に、既定のスケジューラを現在のスケジューラとして復元した後、もう一度同じタスクを実行します。  
  
 最初の例では、 [concurrency::currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md)スケジューラ インスタンスを作成し、現在のコンテキストに関連付けるクラスです。 2 番目の例では、 [concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)を同じタスクを実行するクラス。 通常は、現在のスケジューラを操作するのに `CurrentScheduler` クラスを使用します。 `Scheduler` クラスを使用する 2 つ目の例は、スケジューラを現在のコンテキストに関連付けるタイミングを制御したり、特定のスケジューラを特定のタスクに関連付けたりする場合に有用です。  
  
 [!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
Using CurrentScheduler class...  
 
Current scheduler id: 0  
Creating and attaching scheduler...  
Current scheduler id: 1  
Detaching scheduler...  
Current scheduler id: 0  
 
Using Scheduler class...  
 
Current scheduler id: 0  
Creating scheduler...  
Attaching scheduler...  
Current scheduler id: 2  
Detaching scheduler...  
Current scheduler id: 0  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`scheduler-instance.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc scheduler-instance.cpp**  
  
## <a name="see-also"></a>関連項目  
 [スケジューラ インスタンス](../../parallel/concrt/scheduler-instances.md)   
 [方法: 特定のスケジューラ ポリシーを指定する](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)

