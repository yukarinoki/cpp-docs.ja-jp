---
title: MFC における Windows ソケット
ms.date: 11/04/2016
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
ms.openlocfilehash: 8e5562b028d3d9b7cba4b47716b63fd1392c514f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371094"
---
# <a name="windows-sockets-in-mfc"></a>MFC における Windows ソケット

> [!NOTE]
> MFC は Windows ソケット 1 をサポートしていますが[、Windows ソケット 2 は](/windows/win32/WinSock/windows-sockets-start-page-2)サポートしていません。 Windows ソケット 2 は、Windows 98 に初めて付属しており、Windows 2000 に付属のバージョンです。

MFC には、Windows ソケットを使用してネットワーク通信プログラムを記述するための 2 つのモデルが用意されています。 この資料では、これらのモデルについて説明し、MFC ソケットのサポートについて詳しく説明します。 "ソケット" は通信のエンドポイントであり、アプリケーションがネットワークを介して他の Windows ソケット アプリケーションと通信するオブジェクトです。

ソケットの概念の説明を含む Windows ソケットの詳細については、「 [Windows ソケット : バックグラウンド](../mfc/windows-sockets-background.md)」を参照してください。

## <a name="sockets-programming-models"></a><a name="_core_sockets_programming_models"></a>ソケットプログラミングモデル

2 つの MFC Windows ソケット プログラミング モデルは、次のクラスでサポートされています。

- `CAsyncSocket`

   このクラスは、Windows ソケット API をカプセル化します。 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)は、ネットワーク プログラミングを知っていて、ソケット API に直接プログラミングする柔軟性を必要とし、ネットワーク イベントの通知のためのコールバック関数の利便性を必要とするプログラマ向けです。 C++ で使用するオブジェクト指向形式のソケットのパッケージ化以外に、このクラスが提供する追加の抽象化は、特定のソケット関連の Windows メッセージをコールバックに変換する方法だけです。 詳細については、「 [Windows ソケット : ソケット通知](../mfc/windows-sockets-socket-notifications.md)」を参照してください。

- `CSocket`

   から`CAsyncSocket`派生したこのクラスは、MFC [CArchive](../mfc/reference/carchive-class.md)オブジェクトを介してソケットを操作するためのより高いレベルの抽象化を提供します。 MFC のファイル シリアル化プロトコルを使用する場合、アーカイブを含むソケットを使用する場合と非常によく似ています。 これにより、`CAsyncSocket`モデルよりも使いやすくなります。 [CSocket](../mfc/reference/csocket-class.md)は、Windows ソケット`CAsyncSocket`API をカプセル化するメンバー関数を多数継承します。これらの関数のいくつかを使用し、ソケットプログラミングを一般的に理解する必要があります。 しかし`CSocket`、生の API または クラス`CAsyncSocket`を使用して自分で行う必要がある通信の多くの側面を管理します。 最も重要なことは`CSocket`、(Windows メッセージのバックグラウンド処理を伴う) ブロッキングを提供し、`CArchive`これは の同期操作に不可欠です。

オブジェクトの作成`CSocket`と`CAsyncSocket`使用については、「Windows ソケット: アーカイブと Windows[ソケットでのソケット](../mfc/windows-sockets-using-sockets-with-archives.md)の[使用: クラス CAsyncSocket を使用する](../mfc/windows-sockets-using-class-casyncsocket.md)」で説明しています。

## <a name="windows-sockets-dlls"></a><a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>ソケット DLL

Windows オペレーティング システムは、Windows ソケットダイナミック リンク ライブラリ (DLL) を提供します。 Visual C++ には、適切なヘッダー ファイルとライブラリと Windows ソケットの仕様が用意されています。

Windows ソケットの詳細については、次を参照してください。

- [Windows ソケット : ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット : データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)

- [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows ソケット : 動作シーケンス](../mfc/windows-sockets-sequence-of-operations.md)

- [Windows ソケット: アーカイブを使用するソケットの例](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows ソケット : アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット : ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows ソケット : ソケット通知](../mfc/windows-sockets-socket-notifications.md)

- [Windows ソケット : ブロッキング](../mfc/windows-sockets-blocking.md)

- [Windows ソケット : バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)

- [Windows ソケット : 文字列の変換](../mfc/windows-sockets-converting-strings.md)

- [Windows ソケット : ポートとソケット アドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>関連項目

[Windows ソケット](../mfc/windows-sockets.md)
