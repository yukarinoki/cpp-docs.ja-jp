---
title: C++ と MFC でのマルチ スレッド |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
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
ms.openlocfilehash: 2a57846311fc3332dba0b613ca37a2b5da4368d3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394635"
---
# <a name="multithreading-with-c-and-mfc"></a>C++ と MFC を使用するマルチスレッド

MFC (Microsoft Foundation Class) ライブラリでは、マルチスレッド アプリケーションがサポートされています。 このトピックでは、プロセスとスレッドについて説明します。また、MFC でマルチスレッドを使用する方法についても説明します。

プロセスとは、現在実行されているアプリケーションのインスタンスのことです。 たとえば、[メモ帳] アイコンをダブルクリックすると、メモ帳のプロセスが起動されます。

スレッドとは、プロセスの中で実行される処理の単位です。 メモ帳を起動すると、オペレーティング システムは 1 個のプロセスを生成し、このプロセスのプライマリ スレッドの処理を開始します。 プライマリ スレッドが終了すると、プロセスが終了します。 このプライマリ スレッドは、スタートアップ コードから関数アドレスによってオペレーティング システムに渡されます。 通常のアドレスは、`main`または`WinMain`提供されている機能です。

必要に応じて、プライマリ スレッド以外のスレッドを作成できます (マルチスレッド)。 新しく生成したスレッドは、ユーザーが終了を待つ必要がないバックグラウンド タスクまたはメンテナンス タスクを行う際に使用できます。 MFC アプリケーションのすべてのスレッドがによって表される[CWinThread](../mfc/reference/cwinthread-class.md)オブジェクト。 ほとんどの場合もがありません。 これらのオブジェクトを明示的に作成するには代わりに、フレームワークのヘルパー関数を呼び出す[AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)、作成し、`CWinThread`オブジェクト。

MFC では、ユーザー インターフェイス スレッドとワーカー スレッドの 2 種類に区別されます。 ユーザー インターフェイス スレッドでは主に、ユーザー入力を処理し、ユーザーが生成したイベントおよびメッセージに応答します。 ワーカー スレッドでは、ユーザー入力が必要ない、再計算などの処理を行います。 Win32 API ではこの 2 つのスレッドを区別しません。スレッドの起動アドレスがわかれば、スレッドを実行できます。 MFC では、ユーザー インターフェイス上のイベントに対してメッセージ ポンプを指定することにより、ユーザー インターフェイス スレッドに対して専用の処理を行います。 `CWinApp` は、`CWinThread` から派生したユーザー インターフェイス スレッド オブジェクトの例であり、ユーザーが生成したイベントおよびメッセージを処理します。

複数のスレッドが同一のオブジェクトにアクセスする場合は注意が必要です。 [マルチ スレッド: プログラミングのヒント](multithreading-programming-tips.md)このような状況で発生する可能性のある問題を回避するのに使用できる手法について説明します。 [マルチ スレッド: 同期クラスの使用方法](multithreading-how-to-use-the-synchronization-classes.md)複数のスレッドから 1 つのオブジェクトへのアクセスを同期に使用できるクラスを使用する方法について説明します。

マルチスレッド プログラムの作成とデバッグには高度な技術が必要です。プログラマはオブジェクトが一度に複数のスレッドからアクセスされないようにする必要があるからです。 マルチスレッドに関連するトピックでは、マルチスレッド プログラムで MFC を使用する方法について説明しますが、マルチスレッド プログラミング技術の基礎については説明していません。 Visual C++ に付属のマルチスレッド MFC サンプル アプリケーションでは、マルチスレッド機能の追加方法や MFC でサポートされない Win32 API を利用した例が示されていますが、これはほんの出発点です。

オペレーティング システムでプロセスとスレッドを処理する方法の詳細については、次を参照してください。[プロセスとスレッド](/windows/desktop/ProcThread/processes-and-threads)Windows SDK に含まれています。

MFC がサポートするマルチスレッド機能の詳細については、次のトピックを参照してください。

- [マルチスレッド: ユーザー インターフェイス スレッドの生成](multithreading-creating-user-interface-threads.md)

- [マルチスレッド: ワーカー スレッドの生成](multithreading-creating-worker-threads.md)

- [マルチスレッド: 同期クラスの使用法](multithreading-how-to-use-the-synchronization-classes.md)

- [マルチスレッド: スレッドの終了](multithreading-terminating-threads.md)

- [マルチスレッド: プログラミングのヒント](multithreading-programming-tips.md)

- [マルチスレッド: 同期クラスの使い分け](multithreading-when-to-use-the-synchronization-classes.md)

## <a name="see-also"></a>関連項目

[旧形式のコードのためのマルチスレッド サポート (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)