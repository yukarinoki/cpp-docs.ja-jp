---
title: C++ と MFC を使用するマルチ スレッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], multithreading
- threading [C++], MFC
- worker threads [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], about threading
- CWinThread class, purpose of
- multithreading [C++], MFC
- threading [MFC]
- user interface threads [C++]
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 778602a0e9236ad8cc788d8a2306e8f2d143ec49
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688571"
---
# <a name="multithreading-with-c-and-mfc"></a>C++ と MFC を使用するマルチスレッド
MFC (Microsoft Foundation Class) ライブラリでは、マルチスレッド アプリケーションがサポートされています。 このトピックでは、プロセスとスレッドについて説明します。また、MFC でマルチスレッドを使用する方法についても説明します。  
  
 プロセスとは、現在実行されているアプリケーションのインスタンスのことです。 たとえば、[メモ帳] アイコンをダブルクリックすると、メモ帳のプロセスが起動されます。  
  
 スレッドとは、プロセスの中で実行される処理の単位です。 メモ帳を起動すると、オペレーティング システムは 1 個のプロセスを生成し、このプロセスのプライマリ スレッドの処理を開始します。 プライマリ スレッドが終了すると、プロセスが終了します。 このプライマリ スレッドは、スタートアップ コードから関数アドレスによってオペレーティング システムに渡されます。 通常のアドレスは、**メイン**または`WinMain`提供されている機能です。  
  
 必要に応じて、プライマリ スレッド以外のスレッドを作成できます (マルチスレッド)。 新しく生成したスレッドは、ユーザーが終了を待つ必要がないバックグラウンド タスクまたはメンテナンス タスクを行う際に使用できます。 MFC アプリケーションのすべてのスレッドがによって表される[CWinThread](../mfc/reference/cwinthread-class.md)オブジェクト。 ほとんどの状況でもがありません。 これらのオブジェクトを明示的に作成するには代わりに、フレームワーク ヘルパー関数を呼び出して[AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)、作成する、`CWinThread`オブジェクト。  
  
 MFC では、ユーザー インターフェイス スレッドとワーカー スレッドの 2 種類に区別されます。 ユーザー インターフェイス スレッドでは主に、ユーザー入力を処理し、ユーザーが生成したイベントおよびメッセージに応答します。 ワーカー スレッドでは、ユーザー入力が必要ない、再計算などの処理を行います。 Win32 API ではこの 2 つのスレッドを区別しません。スレッドの起動アドレスがわかれば、スレッドを実行できます。 MFC では、ユーザー インターフェイス上のイベントに対してメッセージ ポンプを指定することにより、ユーザー インターフェイス スレッドに対して専用の処理を行います。 `CWinApp` は、`CWinThread` から派生したユーザー インターフェイス スレッド オブジェクトの例であり、ユーザーが生成したイベントおよびメッセージを処理します。  
  
 複数のスレッドが同一のオブジェクトにアクセスする場合は注意が必要です。 [マルチ スレッド: プログラミングのヒント](../parallel/multithreading-programming-tips.md)これらの状況で発生する可能性のある問題を回避するために使用できる手法について説明します。 [マルチ スレッド: 同期クラスの使用法](../parallel/multithreading-how-to-use-the-synchronization-classes.md)複数のスレッドから単一のオブジェクトへのアクセスを同期するために使用できるクラスを使用する方法について説明します。  
  
 マルチスレッド プログラムの作成とデバッグには高度な技術が必要です。プログラマはオブジェクトが一度に複数のスレッドからアクセスされないようにする必要があるからです。 マルチスレッドに関連するトピックでは、マルチスレッド プログラムで MFC を使用する方法について説明しますが、マルチスレッド プログラミング技術の基礎については説明していません。 Visual C++ に付属のマルチスレッド MFC サンプル アプリケーションでは、マルチスレッド機能の追加方法や MFC でサポートされない Win32 API を利用した例が示されていますが、これはほんの出発点です。  
  
 オペレーティング システムでプロセスとスレッドを処理する方法の詳細については、次を参照してください。[プロセスとスレッド](http://msdn.microsoft.com/library/windows/desktop/ms684841)で、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]です。  
  
 MFC がサポートするマルチスレッド機能の詳細については、次のトピックを参照してください。  
  
-   [マルチスレッド: ユーザー インターフェイス スレッドの生成](../parallel/multithreading-creating-user-interface-threads.md)  
  
-   [マルチスレッド: ワーカー スレッドの生成](../parallel/multithreading-creating-worker-threads.md)  
  
-   [マルチスレッド: 同期クラスの使用法](../parallel/multithreading-how-to-use-the-synchronization-classes.md)  
  
-   [マルチスレッド: スレッドの終了](../parallel/multithreading-terminating-threads.md)  
  
-   [マルチスレッド: プログラミングのヒント](../parallel/multithreading-programming-tips.md)  
  
-   [マルチスレッド: 同期クラスの使い分け](../parallel/multithreading-when-to-use-the-synchronization-classes.md)  
  
## <a name="see-also"></a>関連項目  
 [旧形式のコードのためのマルチスレッド サポート (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)