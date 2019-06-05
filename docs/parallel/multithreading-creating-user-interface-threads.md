---
title: マルチ スレッド。MFC ユーザー インターフェイス スレッドの作成
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
ms.openlocfilehash: b2fb23bd502de87aefe01d91e2b0640ee3137b00
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504593"
---
# <a name="multithreading-creating-mfc-user-interface-threads"></a>マルチ スレッド。MFC ユーザー インターフェイス スレッドの作成

ユーザー インターフェイス スレッドでは、主にユーザー入力を処理し、ユーザーが生成したイベントに応答します。この処理は、アプリケーションのほかの部分を実行しているスレッドとは無関係に行われます。 `CWinApp` の派生クラスで提供されるメイン アプリケーション スレッドは、既に生成され実行を開始しています。 このトピックでは、ユーザー インターフェイス スレッドを作成するための手順について説明します。

まず、ユーザー インターフェイス スレッドを作成するときに行う必要がありますからクラスを派生[CWinThread](../mfc/reference/cwinthread-class.md)します。 宣言し、これを実装するクラスを使用して、 [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate)と[IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate)マクロ。 このクラスでは、一部の関数をオーバーライドする必要があります。また、他の関数も必要に応じてオーバーライドできます。 次の表に、各関数とその用途を示します。

### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>ユーザー インターフェイス スレッドを作成するためにオーバーライドする関数

|関数|目的|
|--------------|-------------|
|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)|スレッド終了時の後処理を行います。 通常、オーバーライドします。|
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)|スレッドのインスタンスを初期化します。 必ずオーバーライドします。|
|[OnIdle](../mfc/reference/cwinthread-class.md#onidle)|スレッド固有のアイドル処理ハンドラーを行います。 通常、オーバーライドしません。|
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)|ディスパッチされる前に、メッセージをフィルター処理`TranslateMessage`と`DispatchMessage`します。 通常、オーバーライドしません。|
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)|スレッドのメッセージ ハンドラーおよびコマンド ハンドラーがスローした未処理例外を受け取ります。 通常、オーバーライドしません。|
|[実行](../mfc/reference/cwinthread-class.md#run)|スレッドの制御関数です。 メッセージ ポンプが含まれます。 この関数をオーバーライドすることはほとんどありません。|

MFC は、パラメーターのオーバーロードによって `AfxBeginThread` の 2 つのバージョンを提供します。1 つはワーカー スレッドのみを作成でき、もう 1 つは、ユーザー インターフェイス スレッドまたはワーカー スレッドを作成できます。 2 番目のオーバー ロードを呼び出して、ユーザー インターフェイス スレッドを開始するには、 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)、次の情報を提供します。

- [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class)から派生したクラスの`CWinThread`します。

- (省略可) 目的の優先順位。 既定の優先順位は normal です。 使用可能な優先度のレベルの詳細については、次を参照してください。 [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK に含まれています。

- (省略可) スレッドのスタック サイズ。 既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。

- (省略可能)CREATE_SUSPENDED スレッドの中断状態で作成する場合。 既定値 0 では、スレッドを通常どおり起動します。

- (省略可) セキュリティ属性。 既定では親スレッドと同じ値になります。 このセキュリティ情報の形式の詳細については、次を参照してください。 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) Windows SDK に含まれています。

`AfxBeginThread` は、スレッド生成処理の大部分を自動的に行います。 クラスの新しいオブジェクトを作成、入力すると、情報と呼び出しを使用して初期化[::createthread](../mfc/reference/cwinthread-class.md#createthread)スレッドの実行を開始します。 なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [マルチスレッド: スレッドの終了](multithreading-terminating-threads.md)

- [マルチスレッド: マルチスレッド : ワーカー スレッドの作成](multithreading-creating-worker-threads.md)

- [プロセスとスレッド](/windows/desktop/ProcThread/processes-and-threads)

## <a name="see-also"></a>関連項目

[C++ と MFC を使用するマルチスレッド](multithreading-with-cpp-and-mfc.md)
