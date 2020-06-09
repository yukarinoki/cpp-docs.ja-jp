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
ms.openlocfilehash: 74ca89d91cf4e60b09a063551b526f177caed161
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624515"
---
# <a name="idle-loop-processing"></a>アイドリング ループ処理

多くのアプリケーションは、時間のかかる処理をバックグラウンドで実行します。 パフォーマンスに関する考慮事項は、このような作業にマルチスレッドを使用することがあります。 スレッドには追加の開発オーバーヘッドが伴います。そのため、MFC が[OnIdle](reference/cwinthread-class.md#onidle)関数で実行するアイドル時間の作業のような単純なタスクには推奨されません。 この記事では、アイドル処理に焦点を当てています。 マルチスレッドの詳細については、[マルチスレッドのトピック](../parallel/multithreading-support-for-older-code-visual-cpp.md)を参照してください。

バックグラウンド処理の中には、ユーザーがアプリケーションと対話できない間隔で適切に実行されるものもあります。 Microsoft Windows オペレーティングシステム用に開発されたアプリケーションでは、長いプロセスを多数の小さなフラグメントに分割することによって、アプリケーションでアイドル時の処理を実行できます。 各フラグメントの処理後、アプリケーションは[PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew)ループを使用して Windows に実行制御を戻します。

この記事では、アプリケーションでアイドル処理を実行する2つの方法について説明します。

- MFC のメインメッセージループで**PeekMessage**を使用します。

- アプリケーションの他の場所に別の**PeekMessage**ループを埋め込みます。

## <a name="peekmessage-in-the-mfc-message-loop"></a><a name="_core_peekmessage_in_the_mfc_message_loop"></a>MFC メッセージループの PeekMessage

MFC を使用して開発されたアプリケーションでは、クラスのメインメッセージループに、 `CWinThread` [PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) Win32 API を呼び出すメッセージループが含まれています。 このループでは、 `OnIdle` メッセージ間のメンバー関数も呼び出され `CWinThread` ます。 アプリケーションでは、関数をオーバーライドすることによって、このアイドル時間でメッセージを処理でき `OnIdle` ます。

> [!NOTE]
> `Run`、 `OnIdle` 、およびその他の特定のメンバー関数は、クラスではなくクラスのメンバーになりました `CWinThread` `CWinApp` 。 `CWinApp` は、`CWinThread` から派生しています。

アイドル処理の実行の詳細については、 *MFC リファレンス*の「 [OnIdle](reference/cwinthread-class.md#onidle) 」を参照してください。

## <a name="peekmessage-elsewhere-in-your-application"></a><a name="_core_peekmessage_elsewhere_in_your_application"></a>アプリケーション内の他の場所に PeekMessage

アプリケーションでアイドル処理を実行するもう1つの方法として、関数のいずれかにメッセージループを埋め込む方法があります。 このメッセージループは、 [CWinThread:: Run](reference/cwinthread-class.md#run)で検出された MFC のメインメッセージループとよく似ています。 つまり、MFC を使用して開発されたアプリケーションのこのようなループは、メインメッセージループと同じ機能の多くを実行する必要があります。 次のコードフラグメントは、MFC と互換性のあるメッセージループを記述する方法を示しています。

[!code-cpp[NVC_MFCDocView#8](codesnippet/cpp/idle-loop-processing_1.cpp)]

関数に埋め込まれたこのコードは、実行するアイドル処理がある限りループします。 このループ内では、入れ子になったループはを繰り返し呼び出し `PeekMessage` ます。 この呼び出しが0以外の値を返す限り、ループは `CWinThread::PumpMessage` を呼び出して通常のメッセージの変換とディスパッチを実行します。 はドキュメントに `PumpMessage` 記載されていませんが、Visual C++ インストールの \ atl/srcディレクトリにある ThrdCore .cpp ファイルのソースコードを調べることができます。

内側のループが終了すると、外側のループはの1回以上の呼び出しを使用してアイドル処理を実行し `OnIdle` ます。 最初の呼び出しは、MFC の目的で使用されます。 の追加の呼び出しを行っ `OnIdle` て、独自のバックグラウンド処理を行うことができます。

アイドル処理の実行の詳細については、「MFC ライブラリリファレンス」の「 [OnIdle](reference/cwinthread-class.md#onidle) 」を参照してください。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](general-mfc-topics.md)
