---
description: '詳細については、「Windows ソケット: 操作のシーケンス」を参照してください。'
title: 'Windows ソケット : 動作シーケンス'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
ms.openlocfilehash: 89870de642abcc8e0584c2c5dc93860eda9785e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263375"
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows ソケット : 動作シーケンス

この記事では、サーバーソケットとクライアントソケットの一連の操作を並べて説明します。 ソケットはオブジェクトを使用するので `CArchive` 、必ずしも [ストリームソケット](../mfc/windows-sockets-stream-sockets.md)です。

## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>ストリームソケット通信の一連の操作

オブジェクトを構築するまでの間 `CSocketFile` 、との両方に対して、次のシーケンスが正確に (パラメーターの違いがいくつか `CAsyncSocket` `CSocket` あります)、 その時点から、シーケンスはに対して厳密に `CSocket` なります。 次の表は、クライアントとサーバー間の通信を設定するための一連の操作を示しています。

### <a name="setting-up-communication-between-a-server-and-a-client"></a>サーバーとクライアント間の通信の設定

|サーバー|Client|
|------------|------------|
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5/5||
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> または<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> またはその両方-|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> または<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> またはその両方-|
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> または<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> または<br /><br /> `arOut << dwValue;`6|

1. ここで、 *nport* はポート番号です。 ポートの詳細については [、「Windows ソケット: ポートとソケットアドレス](../mfc/windows-sockets-ports-and-socket-addresses.md) 」を参照してください。

2. クライアントが接続できるように、サーバーは常にポートを指定する必要があります。 呼び出しは、 `Create` アドレスを指定することもあります。 クライアント側で、既定のパラメーターを使用します。これにより、使用可能な任意のポートを MFC に要求します。

3. ここで、 *Nport* はポート番号、 *straddr* はコンピューターアドレスまたはインターネットプロトコル (IP) アドレスです。

4. コンピューターアドレスには、"ftp.microsoft.com"、"microsoft.com" という複数の形式があります。 IP アドレスは、"127.54.67.32" という形式の "ドット付き数字" を使用します。 `Connect`この関数は、アドレスがドットで示されているかどうかを確認します (ただし、この番号がネットワーク上の有効なコンピューターであるかどうかは確認されません)。 それ以外の場合は、 `Connect` 他の形式のコンピューター名を前提とします。

5. サーバー側でを呼び出すと `Accept` 、新しいソケットオブジェクトへの参照が渡されます。 このオブジェクトは最初に構築する必要がありますが、を呼び出すことはできません `Create` 。 このソケットオブジェクトがスコープ外に出ると、接続が閉じられることに注意してください。 MFC は、新しいオブジェクトを **ソケット** ハンドルに接続します。 ここで示したように、またはヒープ上にソケットを作成できます。

6. アーカイブとソケットファイルは、スコープ外に出ると閉じられます。 また、ソケットオブジェクトのデストラクターは、オブジェクトがスコープ外に出るか削除されたときに、ソケットオブジェクトの [Close](../mfc/reference/casyncsocket-class.md#close) メンバー関数も呼び出します。

## <a name="additional-notes-about-the-sequence"></a>シーケンスに関するその他の注意事項

前の表に示す呼び出しのシーケンスは、ストリームソケット用です。 コネクションレスのデータグラムソケットは、 [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect)、 [Listen](../mfc/reference/casyncsocket-class.md#listen)、 [Accept](../mfc/reference/casyncsocket-class.md#accept) の呼び出しを必要としません (オプションでを使用することもでき `Connect` ます)。 代わりに、クラスを使用している場合、 `CAsyncSocket` データグラムソケットは、 `CAsyncSocket::SendTo` `ReceiveFrom` メンバー関数とメンバー関数を使用します。 (データグラムソケットでを使用する場合は、 `Connect` とを使用し `Send` `Receive` ます)。 `CArchive` はデータグラムで動作しないため、 `CSocket` ソケットがデータグラムの場合はアーカイブでを使用しないでください。

[CSocketFile](../mfc/reference/csocketfile-class.md) は、のすべての機能をサポートしているわけではありません。 `CFile` `CFile` `Seek` ソケット通信には意味がないなどのメンバーは使用できません。 このため、一部の既定の MFC `Serialize` 関数はと互換性がありません `CSocketFile` 。 これは、クラスに特に当てはまり `CEditView` ます。 を使用してオブジェクトにアタッチされたオブジェクトを介してデータをシリアル化することは避けてください。代わりにを使用してください `CEditView` `CArchive` `CSocketFile` `CEditView::SerializeRaw` `CEditView::Serialize` (ドキュメント化されていません)。 [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw)関数は、をサポートしていないなどの関数をファイルオブジェクトに持つことを想定してい `Seek` `CSocketFile` ます。

詳細については、次を参照してください。

- [Windows ソケット: アーカイブでのソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows ソケット: CAsyncSocket クラスの使用](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット: ポートとソケットアドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)

- [Windows ソケット: ストリームソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット: データグラムソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket クラス](../mfc/reference/csocket-class.md)<br/>
[CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)<br/>
[CAsyncSocket:: Close](../mfc/reference/casyncsocket-class.md#close)
