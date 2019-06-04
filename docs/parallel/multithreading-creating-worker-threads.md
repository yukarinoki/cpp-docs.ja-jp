---
title: マルチ スレッド。MFC でのワーカー スレッドの作成
ms.date: 11/04/2016
helpviewer_keywords:
- multithreading [C++], worker threads
- background tasks [C++]
- threading [C++], worker threads
- worker threads [C++]
- threading [C++], creating threads
- threading [MFC], worker threads
- threading [C++], user input not required
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
ms.openlocfilehash: 38757337b1bfe5c7994f9a9f26aad2526aa0279c
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504578"
---
# <a name="multithreading-creating-worker-threads-in-mfc"></a>マルチ スレッド。MFC でのワーカー スレッドの作成

ワーカー スレッドでは、主にバックグラウンド タスクを処理します。アプリケーション処理の中で、ユーザーがその終了を待つ必要がない処理はバックグラウンド タスクにできます。 再計算やバックグラウンド印刷などはワーカー スレッドの良い例です。 このトピックでは、ワーカー スレッドの作成手順について詳しく説明します。 ここでは、次の内容について説明します。

- [スレッドの起動](#_core_starting_the_thread)

- [制御関数の実装](#_core_implementing_the_controlling_function)

- [例](#_core_controlling_function_example)

ワーカー スレッドの作成は比較的簡単なタスクです。 スレッドを実行するために必要な手順は、(1) 制御関数の作成、(2) スレッドの起動の 2 つだけです。 クラスを派生する必要はありません[CWinThread](../mfc/reference/cwinthread-class.md)します。 `CWinThread` の専用の派生クラスが必要な場合は派生できますが、通常、単純なワーカー スレッドを実行する場合は必要ありません。 `CWinThread` をそのまま使用できます。

##  <a name="_core_starting_the_thread"></a> スレッドの起動

`AfxBeginThread` には、2 つのオーバーロード バージョンがあります。1 つはワーカー スレッドのみを作成でき、もう 1 つは、ユーザー インターフェイス スレッドとワーカー スレッドの両方を作成できます。 最初のオーバー ロードを使用して、ワーカー スレッドの実行を開始するには、呼び出す[AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)、次の情報を提供します。

- 制御関数のアドレス。

- 制御関数に渡すパラメーター。

- (省略可) スレッドの優先順位。 既定の優先順位は normal です。 使用可能な優先度のレベルの詳細については、次を参照してください。 [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK に含まれています。

- (省略可) スレッドのスタック サイズ。 既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。

- (省略可能)CREATE_SUSPENDED スレッドの中断状態で作成する場合。 既定値 0 では、スレッドを通常どおり起動します。

- (省略可) セキュリティ属性。 既定では親スレッドと同じ値になります。 このセキュリティ情報の形式の詳細については、次を参照してください。 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) Windows SDK に含まれています。

`AfxBeginThread` 関数は、`CWinThread` オブジェクトを生成、初期化、および起動し、生成した CWinThread オブジェクトのアドレスを返します。このアドレスは後でプログラムから参照できます。 なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。

##  <a name="_core_implementing_the_controlling_function"></a> 制御関数の実装

制御関数によってスレッドを定義します。 この関数に入ると、スレッドが起動され、この関数が終了すると、スレッドも終了します。 次に、この関数のプロトタイプを示します。

```
UINT MyControllingFunction( LPVOID pParam );
```

パラメーターは単一の値です。 関数がこのパラメーターで受け取る値は、スレッド オブジェクトを生成したときにコンストラクターに渡した値です。 制御関数のデザインしだいで、この値の解釈が異なります。 スカラー値として解釈させることも、複数のパラメーターを含めた構造体へのポインターとして解釈させることもできます。また、値を無視することもできます。 パラメーターで構造体を参照すると、構造体を使って呼び出し元からスレッドに値を渡すだけでなく、スレッドから呼び出し元に値を渡すこともできます。 このようにスレッドから構造体を使って呼び出し元に値を渡すときは、スレッドから呼び出し元に対して戻り値の送出が整ったことを通知します。 ワーカー スレッドから呼び出し元への通信については、次を参照してください。[マルチ スレッド。プログラミングのヒント](multithreading-programming-tips.md)します。

関数が終了するときに、終了の理由を示す UINT 値を返します。 通常は 0 が成功を、その他の値はエラーの種類を示します。 戻り値の仕様は純粋に実装に依存します。 たとえば、オブジェクトの使用数を管理するスレッドでは、現在の情報を返すことができます。 アプリケーションがこの値を取得する方法については、次を参照してください。[マルチ スレッド。スレッドの終了](multithreading-terminating-threads.md)します。

MFC ライブラリで作成されたマルチスレッド プログラムで実行できることには、いくつかの制約があります。 これらの制限事項とスレッドの使用に関するその他のヒントの説明については、次を参照してください。[マルチ スレッド。プログラミングのヒント](multithreading-programming-tips.md)します。

##  <a name="_core_controlling_function_example"></a> 制御関数の例

制御関数を定義し、プログラムの別の部分からこの関数を使用する方法の例を次に示します。

```
UINT MyThreadProc( LPVOID pParam )
{
    CMyObject* pObject = (CMyObject*)pParam;

    if (pObject == NULL ||
        !pObject->IsKindOf(RUNTIME_CLASS(CMyObject)))
    return 1;   // if pObject is not valid

    // do something with 'pObject'

    return 0;   // thread completed successfully
}

// inside a different function in the program
.
.
.
pNewObject = new CMyObject;
AfxBeginThread(MyThreadProc, pNewObject);
.
.
.
```

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [マルチスレッド: ユーザー インターフェイス スレッドの生成](multithreading-creating-user-interface-threads.md)

## <a name="see-also"></a>関連項目

[C++ と MFC を使用するマルチスレッド](multithreading-with-cpp-and-mfc.md)
