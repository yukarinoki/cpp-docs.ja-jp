---
title: 'Windows ソケット : ポートとソケット アドレス'
ms.date: 11/04/2016
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
ms.openlocfilehash: 791bf07c927e80e65e0fda79fae8a50235bc2def
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371046"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows ソケット : ポートとソケット アドレス

この資料では、Windows ソケットで使用される "ポート" と "アドレス" という用語について説明します。

## <a name="port"></a><a name="_core_port"></a>ポート

ポートは、サービスを提供できる固有のプロセスを識別します。 現在のコンテキストでは、ポートは Windows ソケットをサポートするアプリケーションに関連付けられています。 この考え方は、各 Windows ソケット アプリケーションを一意に識別して、複数の Windows ソケット アプリケーションを 1 台のコンピューターで同時に実行できるようにすることです。

一部のポートは、FTP などの一般的なサービス用に予約されています。 そのようなサービスを提供する場合を除き、これらのポートの使用は避けてください。 Windows ソケットの仕様では、これらの予約ポートについて詳しく説明します。 WINSOCK ファイル。H は、それらを一覧表示します。

Windows ソケット DLL で使用できるポートを選択するには、ポート値として 0 を渡します。 MFC は、1,024 を超えるポート値を選択します。 メンバー関数を呼び出すことで、MFC が選択したポート値[を](../mfc/reference/casyncsocket-class.md#getsockname)取得できます。

## <a name="socket-address"></a><a name="_core_socket_address"></a>ソケットアドレス

各ソケット オブジェクトは、ネットワーク上のインターネット プロトコル (IP) アドレスに関連付けられます。 通常、アドレスは"ftp.microsoft.com"などのコンピュータ名、または点線の数字 ("128.56.22.8" など) です。

ソケットを作成しようとする場合、通常は独自のアドレスを指定する必要はありません。

> [!NOTE]
> マシンに複数のネットワークカードがある場合 (またはアプリケーションがいつかそのようなマシンで実行される可能性があります)、それぞれが異なるネットワークを表している可能性があります。 その場合は、ソケットが使用するネットワーク カードを指定するためにアドレスを指定する必要があります。 これは、高度な使用法と可能性のある移植性の問題であることが確実です。

詳細については、次を参照してください。

- [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows ソケット : アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows ソケット : ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット : データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)
