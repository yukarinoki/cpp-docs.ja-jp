---
title: 'Windows ソケット: 動作シーケンス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93fe2221e25951a53340d5da97f7d5c48ce477cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385259"
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows ソケット : 動作シーケンス
この記事には、サイド バイ サイドで、サーバー ソケットと、クライアント ソケットの操作のシーケンスが示しています。 ソケットを使用するため`CArchive`オブジェクト、必ずしもは[ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)です。  
  
## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>ストリーム ソケット通信のための操作のシーケンス  
 作成する時点まで、`CSocketFile`オブジェクトの次のシーケンスが (、いくつかのパラメーターの違い) の正確な両方の`CAsyncSocket`と`CSocket`です。 その時点から、シーケンスに限定されます`CSocket`です。 次の表は、クライアントとサーバー間の通信を設定するための操作のシーケンスを示しています。  
  
### <a name="setting-up-communication-between-a-server-and-a-client"></a>サーバーとクライアント間の通信の設定  
  
|サーバー|クライアント|  
|------------|------------|  
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|  
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|  
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||  
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|  
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||  
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|  
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - または -<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> または両方、|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - または -<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> または両方、|  
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - または -<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - または -<br /><br /> `arOut << dwValue;`6|  
  
 1. ここで`nPort`ポート番号です。 参照してください[Windows ソケット: ポートとソケット アドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)ポートの詳細についてです。  
  
 2. クライアントが接続できるように、サーバーはポートを指定常にする必要があります。 **作成**呼び出しもアドレスを指定します。 クライアント側で使用可能なポートを使用する MFC を依頼する既定のパラメーターを使用します。  
  
 3. ここで`nPort`ポート番号と*strAddr*はマシンのアドレスまたはインターネット プロトコル (IP) アドレスです。  
  
 4. マシンのアドレスには、いくつかの形式:「専用」、"microsoft.com"です。 IP アドレスは、「ドット形式の番号」形式「127.54.67.32」を使用します。 **接続**関数は、かどうか、アドレスはドット区切りの数値 (が数が、ネットワーク上で有効なコンピューターであることを確認するのにはチェックされません) を参照してください。 ない場合は、**接続**他の形式のいずれかのコンピューター名を前提としています。  
  
 5. 呼び出すと**Accept**サーバー側で新しいソケット オブジェクトへの参照を渡します。 最初に、このオブジェクトを構築する必要がありますが、呼び出すことはありません**作成**にします。 ただし、このソケット オブジェクトがスコープ接続は閉じられますなくなる場合。 Mfc は、新しいオブジェクトを**ソケット**を処理します。 スタック、ように、または、ヒープ上のソケットを構築することができます。  
  
 6. スコープ外に出ると、アーカイブがあり、ソケット ファイルは閉じられます。 ソケット オブジェクトのデストラクター、[閉じる](../mfc/reference/casyncsocket-class.md#close)ソケット オブジェクト、オブジェクトがスコープ外に出るか、削除時のメンバー関数。  
  
## <a name="additional-notes-about-the-sequence"></a>シーケンスに関する追加の注意事項  
 上記の表で示した呼び出しの順序は、ソケットのストリームです。 データグラム ソケットは、コネクションレス型は、必要としない、[不要なため](../mfc/reference/casyncsocket-class.md#connect)、[リッスン](../mfc/reference/casyncsocket-class.md#listen)、および[Accept](../mfc/reference/casyncsocket-class.md#accept)呼び出し (を使用できますが、必要に応じて**接続**)。 代わりに、クラスを使用している場合`CAsyncSocket`、データグラム ソケットを使用、`CAsyncSocket::SendTo`と`ReceiveFrom`メンバー関数。 (を使用する場合**接続**を使用するデータグラム ソケットを使用して**送信**と**受信**)。`CArchive`は機能しません、データグラムを使用しない`CSocket`データグラム ソケットの場合、アーカイブします。  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)すべてのサポートされない`CFile`の機能です。`CFile`などメンバー `Seek`、これをなしませんソケット通信には使用できません。 このため、一部の既定設定 MFC`Serialize`関数と互換性がない`CSocketFile`です。 これは特に、`CEditView`クラスです。 シリアル化しないでください`CEditView`を使用してデータを`CArchive`オブジェクトに関連付けられて、`CSocketFile`オブジェクトを使用して`CEditView::SerializeRaw`; を使用して**CEditView::Serialize**代わりに (記載されていない)。 [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw)関数など、関数に、ファイル オブジェクトが必要ですが`Seek`、その`CSocketFile`はサポートしていません。  
  
 詳細については次を参照してください:  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: ポートとソケット アドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [CSocket クラス](../mfc/reference/csocket-class.md)   
 [CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)   
 [CAsyncSocket::Close](../mfc/reference/casyncsocket-class.md#close)

