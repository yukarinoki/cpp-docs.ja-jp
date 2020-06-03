---
title: アイドリング ループ処理
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, background processing
- PeekMessage method [MFC], elsewhere than message loop
- PeekMessage method [MFC]
- MFC, messages
- messages [MFC], loops
- OnIdle method [MFC]
- processing [MFC], background
- idle loop processing [MFC]
- idle processing [MFC]
- threading [MFC], alternatives to multithreading
- processing, during idle loop
- processing [MFC]
- background processing [MFC]
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
ms.openlocfilehash: 9579d4bb8768b0227453af401d6fdc8a8bd482b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376009"
---
# <a name="idle-loop-processing"></a>アイドリング ループ処理

多くのアプリケーションは、「バックグラウンドで」長時間の処理を実行します。 パフォーマンスに関する考慮事項によって、このような作業にマルチスレッドを使用する場合があります。 スレッドには開発オーバーヘッドが伴うため、MFC が[OnIdle](../mfc/reference/cwinthread-class.md#onidle)関数で行うアイドル時間の作業のような単純なタスクには推奨されません。 この記事では、アイドル処理に重点を置きます。 マルチスレッドの詳細については、「[マルチスレッド化のトピック」を参照してください](../parallel/multithreading-support-for-older-code-visual-cpp.md)。

バックグラウンド処理の種類によっては、ユーザーがアプリケーションと対話しない間隔で適切に行われます。 Microsoft Windows オペレーティング システム用に開発されたアプリケーションでは、アプリケーションは、時間のかかるプロセスを多数の小さなフラグメントに分割することによって、アイドル時間処理を実行できます。 各フラグメントを処理した後、アプリケーションは[、PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew)ループを使用して Windows に実行制御を生成します。

この記事では、アプリケーションでアイドル処理を実行する 2 つの方法について説明します。

- MFC のメイン メッセージ ループで**の PeekMessage**の使用。

- 別の**PeekMessage**ループをアプリケーションの他の場所に埋め込みます。

## <a name="peekmessage-in-the-mfc-message-loop"></a><a name="_core_peekmessage_in_the_mfc_message_loop"></a>MFC メッセージ ループ内のメッセージをピークにする

MFC を使用して開発されたアプリケーションでは、`CWinThread`クラスのメイン メッセージ ループには[、PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) Win32 API を呼び出すメッセージ ループが含まれています。 このループは、メッセージ`OnIdle`間の`CWinThread`メンバー関数も呼び出します。 アプリケーションは、このアイドル時間に、関数をオーバーライドすることによってメッセージ`OnIdle`を処理できます。

> [!NOTE]
> `Run`、、`OnIdle`および他の特定のメンバー関数は、クラス`CWinThread``CWinApp`ではなくクラスのメンバーになりました。 `CWinApp` は、`CWinThread` から派生しています。

アイドル処理の実行の詳細については *、MFC リファレンス*の[OnIdle](../mfc/reference/cwinthread-class.md#onidle)を参照してください。

## <a name="peekmessage-elsewhere-in-your-application"></a><a name="_core_peekmessage_elsewhere_in_your_application"></a>アプリケーション内の他の場所でメッセージをピークにする

アプリケーションでアイドル処理を実行するもう 1 つの方法として、メッセージ ループを関数の 1 つに埋め込む方法があります。 このメッセージ ループは[、MFC](../mfc/reference/cwinthread-class.md#run)のメイン メッセージ ループとよく似ています。 つまり、MFC で開発されたアプリケーションでこのようなループは、メイン メッセージ ループと同じ関数の多くを実行する必要があります。 次のコードは、MFC と互換性のあるメッセージ ループを記述する方法を示しています。

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

このコードは、関数に埋め込まれているもので、アイドル処理が行う場合に限りループします。 そのループ内では、ネストされたループが繰り`PeekMessage`返し呼び出されます。 その呼び出しが 0 以外の値を返`CWinThread::PumpMessage`す限り、ループは通常のメッセージ変換とディスパッチを実行するために呼び出します。 文書化`PumpMessage`されていませんが、Visual C++ インストールの \atlmfc\src\mfc ディレクトリにある ThrdCore.Cpp ファイル内のソース コードを調べることができます。

内部ループが終了すると、外側のループは、 への 1 回以上の`OnIdle`呼び出しでアイドル処理を実行します。 最初の呼び出しは、MFC の目的です。 独自のバックグラウンド作業を行`OnIdle`うために追加の呼び出しを行うことができます。

アイドル処理の実行の詳細については、MFC ライブラリ リファレンスの[OnIdle](../mfc/reference/cwinthread-class.md#onidle)を参照してください。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
