---
title: 'マルチ スレッド: ユーザー インターフェイス スレッドの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 480839316cc8d47b2af4be1cd81c0d02f09fad25
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688870"
---
# <a name="multithreading-creating-user-interface-threads"></a>マルチスレッド : ユーザー インターフェイス スレッドの生成
ユーザー インターフェイス スレッドでは、主にユーザー入力を処理し、ユーザーが生成したイベントに応答します。この処理は、アプリケーションのほかの部分を実行しているスレッドとは無関係に行われます。 `CWinApp` の派生クラスで提供されるメイン アプリケーション スレッドは、既に生成され実行を開始しています。 このトピックでは、ユーザー インターフェイス スレッドを作成するための手順について説明します。  
  
 ユーザー インターフェイス スレッドを作成するときに行う必要がありますはまずからクラスを派生[CWinThread](../mfc/reference/cwinthread-class.md)です。 宣言し、これを実装するクラス、使用、 [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate)と[IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate)マクロです。 このクラスでは、一部の関数をオーバーライドする必要があります。また、他の関数も必要に応じてオーバーライドできます。 次の表に、各関数とその用途を示します。  
  
### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>ユーザー インターフェイス スレッドを作成するためにオーバーライドする関数  
  
|関数|目的|  
|--------------|-------------|  

|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)|スレッドが終了するときは、クリーンアップを実行します。 通常、オーバーライドします |。  
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)|スレッドのインスタンスを初期化を実行します。 オーバーライドする必要があります |。  
|[OnIdle](../mfc/reference/cwinthread-class.md#onidle)|スレッド固有のアイドル処理を実行します。 通常、オーバーライドしません |。  
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)|ディスパッチされる前に、メッセージをフィルター処理**TranslateMessage**と**DispatchMessage**です。 通常、オーバーライドしません |。  
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)|スレッドのメッセージとコマンド ハンドラーによってスローされた未処理の例外を受け取ります。 通常、オーバーライドしません |。  
|[実行](../mfc/reference/cwinthread-class.md#run)|スレッドの制御関数です。 メッセージ ポンプが含まれます。 オーバーライドされることはほとんどありません |。  

  
 MFC は、パラメーターのオーバーロードによって `AfxBeginThread` の 2 つのバージョンを提供します。1 つはワーカー スレッドのみを作成でき、もう 1 つは、ユーザー インターフェイス スレッドまたはワーカー スレッドを作成できます。 2 番目のオーバー ロードを呼び出して、ユーザー インターフェイス スレッドを開始するには、 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)、次の情報を提供します。  
  
-   [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class)から派生したクラスの`CWinThread`します。  
  
-   (省略可) 目的の優先順位。 既定の優先順位は normal です。 使用可能な優先度レベルの詳細については、次を参照してください。 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)で、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
-   (省略可) スレッドのスタック サイズ。 既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。  
  
-   (省略可能)**CREATE_SUSPENDED**する場合は、一時停止状態で作成するスレッド。 既定値 0 では、スレッドを通常どおり起動します。  
  
-   (省略可) セキュリティ属性。 既定では親スレッドと同じ値になります。 このセキュリティ情報の書式設定に関する詳細については、次を参照してください。 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)で、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
 `AfxBeginThread` は、スレッド生成処理の大部分を自動的に行います。 クラスの新しいオブジェクトを作成を指定する情報と呼び出しを使用して初期化[cwinthread::createthread](../mfc/reference/cwinthread-class.md#createthread)スレッドの実行を開始します。 なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [マルチスレッド: スレッドの終了](../parallel/multithreading-terminating-threads.md)  
  
-   [マルチスレッド: ワーカー スレッドの生成](../parallel/multithreading-creating-worker-threads.md)  
  
-   [プロセスとスレッド](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
## <a name="see-also"></a>関連項目  
 [C++ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)