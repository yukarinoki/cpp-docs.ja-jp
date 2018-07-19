---
title: 'Windows ソケット: ポートとソケット アドレス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42ea9b8a39de8d36ecb621164d98e072a4041211
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383988"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows ソケット : ポートとソケット アドレス
この記事では、用語"port"および"address"として Windows ソケットの使用について説明します。  
  
##  <a name="_core_port"></a> ポート  
 ポートは、サービスを提供できる一意のプロセスを識別します。 現在のコンテキストでは、ポートは、Windows ソケットをサポートするアプリケーションに関連付けられます。 目的は、同時に、マシンで実行されている 1 つ以上の Windows ソケット アプリケーションがあることができますので、各 Windows ソケット アプリケーションを一意に識別します。  
  
 特定のポートは、FTP などの一般的なサービス用に予約されています。 この種のサービスを提供している場合を除き、これらのポートを使用してを避ける必要があります。 Windows ソケット仕様では、これらの予約ポートについて説明します。 WINSOCK ファイル。H では、それらも表示されます。  
  
 使用可能なポートを選択して Windows Sockets DLL をできるようにするには、ポートの値として 0 を渡します。 MFC では、10 進数は 1,024 を超えるポート値を選択します。 MFC を呼び出すことによって選択されているポートの値を取得することができます、[で](../mfc/reference/casyncsocket-class.md#getsockname)メンバー関数。  
  
##  <a name="_core_socket_address"></a> ソケット アドレス  
 各ソケット オブジェクトは、ネットワーク上、インターネット プロトコル (IP) アドレスに関連付けられます。 通常、アドレスは、「専用」などのコンピューター名または「128.56.22.8」などのピリオドで区切られた番号です。  
  
 ソケットを作成するとき、通常は、独自のアドレスを指定する必要はありません。  
  
> [!NOTE]
>  コンピューターに複数のネットワーク カード (または、アプリケーションがこのようなコンピューターで実行いつか)、可能であれば別のネットワークを表すです。 場合は、ソケットが使用されるネットワーク カードを指定するためのアドレスを提供する必要があります。 これは、高度な使用法と移植性にも問題を特定します。  
  
 詳細については次を参照してください:  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)

