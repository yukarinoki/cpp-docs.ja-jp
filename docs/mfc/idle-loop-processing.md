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
ms.openlocfilehash: 0d0e3fcba9ce447ec359958fc5ed59c6d596dd7a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287136"
---
# <a name="idle-loop-processing"></a>アイドリング ループ処理

多くのアプリケーションの実行時間のかかる処理"バック グラウンドします" 場合によってマルチ スレッドを使用して、このような作業のパフォーマンスに関する考慮事項に影響します。 MFC では、アイドル時間の作業のような単純なタスクには推奨されませんので、スレッドは、開発に余分なオーバーヘッドを伴う、 [OnIdle](../mfc/reference/cwinthread-class.md#onidle)関数。 この記事では、アイドル状態の処理について説明します。 詳細については、マルチ スレッドを参照してください[マルチ スレッドのトピック](../parallel/multithreading-support-for-older-code-visual-cpp.md)します。

バック グラウンド処理の種類によっては、ユーザーがそれ以外の場合、アプリケーションと対話しない間隔中に適切に実行されます。 Microsoft Windows オペレーティング システム用に開発されたアプリケーションで、アプリケーションは、時間のかかるプロセスを多数の小さなフラグメントに分割してアイドル状態時の処理を実行できます。 各フラグメントを処理した後、アプリケーションが Windows を使用する実行の制御を生成、 [PeekMessage](/windows/desktop/api/winuser/nf-winuser-peekmessagea)ループします。

この記事では、アイドル、アプリケーションで処理を行う 2 つの方法について説明します。

- 使用して**PeekMessage** MFC のメイン メッセージ ループ内で。

- 別の埋め込み**PeekMessage**アプリケーションで他の場所をループします。

##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a> MFC のメッセージ ループで PeekMessage

MFC で開発したアプリケーションは、メイン メッセージ ループで、`CWinThread`クラスには、呼び出すメッセージ ループが含まれています、 [PeekMessage](/windows/desktop/api/winuser/nf-winuser-peekmessagea) Win32 API です。 これは、ループの呼び出しにも、`OnIdle`のメンバー関数`CWinThread`メッセージ間。 アプリケーションはオーバーライドすることでこのアイドル時間のメッセージを処理することができます、`OnIdle`関数。

> [!NOTE]
>  `Run`、 `OnIdle`、およびその他の特定のメンバー関数は、クラスのメンバーであるようになりました`CWinThread`クラスのではなく`CWinApp`します。 `CWinApp` は、`CWinThread` から派生しています。

アイドル処理の詳細については、次を参照してください。 [OnIdle](../mfc/reference/cwinthread-class.md#onidle)で、 *MFC リファレンス*します。

##  <a name="_core_peekmessage_elsewhere_in_your_application"></a> PeekMessage、アプリケーションで別の場所

アプリケーションでアイドル処理を実行するための別の方法では、関数のいずれかでメッセージ ループを埋め込む必要があります。 このメッセージ ループがある、MFC のメイン メッセージ ループとよく似ています[CWinThread::Run](../mfc/reference/cwinthread-class.md#run)します。 つまり、このようなループは、MFC で開発されたアプリケーションでは、メイン メッセージ ループと同じ機能の多くを実行する必要があります。 次のコード フラグメントでは、MFC と互換性があるメッセージ ループを示しています。

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

関数の場合に埋め込まれた、このコードは、実行する処理がアイドル状態がある限り、ループ処理します。 入れ子になったループの繰り返しの呼び出し、ループ内で`PeekMessage`します。 その呼び出しが 0 以外の値を返す限り、ループを呼び出す`CWinThread::PumpMessage`変換の通常のメッセージおよびディスパッチを実行します。 `PumpMessage`は文書化、Visual C インストールの \atlmfc\src\mfc ディレクトリに ThrdCore.Cpp ファイルでは、そのソース コードを調べることができます。

1 回、内側のループの終了、外側のループ処理を実行しますアイドル状態に 1 つまたは複数の呼び出しで`OnIdle`します。 最初の呼び出しは、MFC の目的です。 追加の呼び出しを行うことができます`OnIdle`バック グラウンド作業を行います。

アイドル処理の詳細については、次を参照してください。 [OnIdle](../mfc/reference/cwinthread-class.md#onidle) MFC ライブラリのリファレンス。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
