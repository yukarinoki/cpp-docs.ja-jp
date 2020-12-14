---
description: '詳細については、Windows ソケット: ポートとソケットアドレスに関するページを参照してください。'
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
ms.openlocfilehash: 354505796ff60cc8968b2e10a2aac98be2eb4666
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263401"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows ソケット : ポートとソケット アドレス

この記事では、Windows ソケットで使用される "ポート" と "アドレス" という用語について説明します。

## <a name="port"></a><a name="_core_port"></a> ポート

ポートは、サービスを提供できる一意のプロセスを識別します。 現在のコンテキストでは、ポートは Windows ソケットをサポートするアプリケーションに関連付けられています。 1台のコンピューターで複数の Windows ソケットアプリケーションを同時に実行できるように、各 Windows ソケットアプリケーションを一意に識別します。

特定のポートは、FTP などの一般的なサービス用に予約されています。 そのようなサービスを提供する場合を除き、これらのポートの使用は避けてください。 Windows ソケット仕様では、これらの予約済みポートが詳細に説明されています。 ファイル WINSOCK。また、これらの一覧も示します。

Windows ソケット DLL で使用可能なポートを選択できるようにするには、ポート値として0を渡します。 MFC は、1024 10 進数を超えるポート値を選択します。 [CAsyncSocket:: GetSockName](../mfc/reference/casyncsocket-class.md#getsockname)メンバー関数を呼び出すことによって、MFC が選択したポート値を取得できます。

## <a name="socket-address"></a><a name="_core_socket_address"></a> ソケットアドレス

各ソケットオブジェクトは、ネットワーク上のインターネットプロトコル (IP) アドレスに関連付けられています。 通常、このアドレスは、"ftp.microsoft.com" などのコンピューター名、またはドットで区切った数字 ("128.56.22.8" など) です。

ソケットを作成する場合は、通常、独自のアドレスを指定する必要はありません。

> [!NOTE]
> コンピューターに複数のネットワークカードがある (またはアプリケーションがそのようなコンピューター上で実行される可能性があります)。それぞれが異なるネットワークを表している可能性があります。 その場合は、ソケットが使用するネットワークカードを指定するためにアドレスを指定することが必要になる場合があります。 これは、高度な使用方法と考えられる移植性の問題であることがあります。

詳細については、次を参照してください。

- [Windows ソケット: CAsyncSocket クラスの使用](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット: アーカイブでのソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows ソケット: アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows ソケット: ストリームソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット: データグラムソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)
