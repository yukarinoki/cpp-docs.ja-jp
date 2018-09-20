---
title: MFC における Windows ソケット |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff86123f395e9647ef848ad017fe3cb69b69dd71
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427681"
---
# <a name="windows-sockets-in-mfc"></a>MFC における Windows ソケット

> [!NOTE]
>  MFC は Windows Sockets 1 をサポートしていますが、サポートしていません[Windows Sockets 2](/windows/desktop/WinSock/windows-sockets-start-page-2)します。 まず、Windows Sockets 2 は、Windows 98 に付属し、Windows 2000 に付属するバージョンは、します。

MFC では、Windows ソケット、2 つの MFC クラスに組み込まれていると、ネットワーク通信を行うプログラムを記述するための 2 つのモデルを提供します。 この記事では、これらのモデルをについて説明し、さらに詳細 MFC ソケットのサポート。 「ソケット」は、通信のエンドポイント: アプリケーション通信に使用する他の Windows ソケット アプリケーションをネットワーク経由でのオブジェクト。

Windows ソケット、ソケットの概念の説明などを含むに関する情報を参照してください。 [Windows ソケット: バック グラウンド](../mfc/windows-sockets-background.md)します。

##  <a name="_core_sockets_programming_models"></a> ソケット プログラミング モデル

次のクラスでは、2 つの MFC Windows ソケット プログラミング モデルがサポートされています。

- `CAsyncSocket`

     このクラスは、Windows ソケット API をカプセル化します。 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)ネットワーク プログラミングを理解し、ソケット API に対して直接プログラミングの柔軟性もネットワーク イベントの通知のコールバック関数の利便性を必要するプログラマにとっては。 C++ で使用するためのフォームのオブジェクト指向のソケットをパッケージ化、以外、のみ追加の抽象化がこのクラスは提供はコールバックに特定のソケットに関連する Windows メッセージを変換します。 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../mfc/windows-sockets-socket-notifications.md)します。

- `CSocket`

     このクラスから派生した`CAsyncSocket`、MFC からソケットを操作するためより高いレベルの抽象化を提供[CArchive](../mfc/reference/carchive-class.md)オブジェクト。 アーカイブを使用して、ソケットを使用すると、大幅にするには、MFC のファイルのシリアル化プロトコルを使用してに似ています。 これによりより使いやすく、`CAsyncSocket`モデル。 [CSocket](../mfc/reference/csocket-class.md)から多くのメンバー関数を継承`CAsyncSocket`Windows Sockets Api をカプセル化する。 これらの関数を使用して、ソケットの通常のプログラミングを理解する必要があります。 `CSocket`生 API またはクラスのいずれかを使用して自分で行う必要がありますの通信の多くの側面を管理`CAsyncSocket`します。 最も重要なは、 `CSocket` (バック グラウンド処理の Windows メッセージ) を使用してブロックを提供するための同期操作に不可欠である`CArchive`します。

作成と使用`CSocket`と`CAsyncSocket`オブジェクトについては、「 [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)と[Windows ソケット: を使用してクラス CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)します。

##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows Sockets Dll

Microsoft Windows オペレーティング システムでは、Windows ソケットのダイナミック リンク ライブラリ (DLL) を指定します。 Visual C では、適切なヘッダー ファイルとライブラリ、および Windows Sockets の仕様を提供します。

Windows ソケットの詳細についてを参照してください。

- [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)

- [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows ソケット: 動作シーケンス](../mfc/windows-sockets-sequence-of-operations.md)

- [Windows ソケット: アーカイブを使用するソケットの例](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows ソケット: アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット: ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows ソケット: ソケット通知](../mfc/windows-sockets-socket-notifications.md)

- [Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md)

- [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)

- [Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)

- [Windows ソケット: ポートとソケット アドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>関連項目

[Windows ソケット](../mfc/windows-sockets.md)

