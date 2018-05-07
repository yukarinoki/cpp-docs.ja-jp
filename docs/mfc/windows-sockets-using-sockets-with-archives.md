---
title: 'Windows ソケット: アーカイブ付きソケットの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7ad4e5b94403582f9073e4d3bd3542f8aa75d08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows ソケット: アーカイブ付きソケットの使用
この記事の内容について説明します、 [CSocket プログラミング モデル](#_core_the_csocket_programming_model)です。 クラス[CSocket](../mfc/reference/csocket-class.md)クラスよりも高い抽象化レベルでのソケットのサポートを提供[CAsyncSocket](../mfc/reference/casyncsocket-class.md)です。 `CSocket` MFC のシリアル化プロトコルのバージョンを介して MFC ソケット オブジェクトからデータを受け渡すを使用して[CArchive](../mfc/reference/carchive-class.md)オブジェクト。 `CSocket` ブロックしているときに Windows メッセージのバック グラウンド処理の管理) を提供し、により利用できる`CArchive`、raw API またはクラスのいずれかを使用して自分で行う必要があります、通信の多くの側面を管理する`CAsyncSocket`です。  
  
> [!TIP]
>  クラスを使用して`CSocket`の方が便利なバージョンとして、単独で`CAsyncSocket`が、最も単純なプログラミング モデルを使用する`CSocket`で、`CArchive`オブジェクト。  
  
 アーカイブ付きソケットの実装の動作方法の詳細については、次を参照してください。 [Windows ソケット: 作業のアーカイブ付きソケット](../mfc/windows-sockets-how-sockets-with-archives-work.md)です。 コード例を参照してください[Windows ソケット: 動作シーケンス](../mfc/windows-sockets-sequence-of-operations.md)と[Windows ソケット: 例のソケットを使用してアーカイブ](../mfc/windows-sockets-example-of-sockets-using-archives.md)です。 ソケット クラスから独自のクラスを派生することにより得られる利点に関する一部の機能について、次を参照してください。 [Windows ソケット: ソケット クラスから派生する](../mfc/windows-sockets-deriving-from-socket-classes.md)です。  
  
> [!NOTE]
>  確立 (非 MFC) サーバーと通信するために MFC クライアント プログラムを記述する場合は、アーカイブを通じて C++ オブジェクトを送信しません。 サーバーは、送信するオブジェクトの種類を認識する MFC アプリケーションでない限りが、受信し、オブジェクトを逆シリアル化することはできません。 非 MFC アプリケーションとの通信のサブジェクトで関連資料も記事を参照して、 [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)です。  
  
##  <a name="_core_the_csocket_programming_model"></a> CSocket プログラミング モデル  
 使用して、`CSocket`を作成して、いくつかの MFC クラス オブジェクトを関連付け、オブジェクトが含まれます。 次の一般的な手順で各ステップはサーバー ソケットと、クライアント ソケット、手順 3. を除く各ソケットの種類が、別の操作を必要との両方によって取得されます。  
  
> [!TIP]
>  実行時に、サーバー アプリケーション通常最初を開始する準備をして、クライアント アプリケーションの接続をシークするときに「リッスン」します。 クライアントが接続しようとするときに、サーバーが準備されていない場合は、後でもう一度接続を試みるユーザー アプリケーションが通常必要です。  
  
#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>サーバー ソケットと、クライアント ソケットの間の通信をセットアップするには  
  
1.  構築、 [CSocket](../mfc/reference/csocket-class.md)オブジェクト。  
  
2.  オブジェクトを使用して、基になる作成**ソケット**を処理します。  
  
     `CSocket`クライアント オブジェクトを既定のパラメーターを使用する必要があります通常[作成](../mfc/reference/casyncsocket-class.md#create)データグラム ソケットが必要でない限り、します。 `CSocket`サーバー オブジェクトでポートを指定する必要があります、**作成**呼び出します。  
  
    > [!NOTE]
    >  `CArchive` データグラム ソケットでは機能しません。 使用する場合`CSocket`データグラム ソケットに関して、使用すると、クラスを使用する必要があります`CAsyncSocket`,、つまり、アーカイブせずにします。 データグラムは信頼性が高くないため、(必ず到着して、繰り返される可能性がありますいない、または誤った順序)、アーカイブをシリアル化と互換性がありません。 シリアル化操作が確実、かつシーケンス内を完了するはずです。 使用しようとする場合`CSocket`で、 `CArchive` MFC アサーションは失敗し、データグラムのオブジェクトします。  
  
3.  ソケットがクライアントの場合は、呼び出す[不要なため](../mfc/reference/casyncsocket-class.md#connect)サーバー ソケットにソケット オブジェクトを接続します。  
  
     - または -  
  
     ソケットがサーバーの場合は、呼び出す[CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)を開始するクライアントからの接続の試行がリッスンしています。 接続要求を受信するには、その内容に同意を呼び出して[CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept)です。  
  
    > [!NOTE]
    >  **Accept**メンバー関数は、新しい空への参照を受け取ります`CSocket`オブジェクトをパラメーターとして。 呼び出す前に、このオブジェクトを構築する必要があります**Accept**です。 このソケット オブジェクトがスコープ外に出ると、接続は閉じられます。 呼び出す必要はありません**作成**この新しいソケット オブジェクト。  
  
4.  作成、 [CSocketFile](../mfc/reference/csocketfile-class.md)オブジェクト、関連付け、`CSocket`それを持つオブジェクト。  
  
5.  作成、 [CArchive](../mfc/reference/carchive-class.md)の読み込み (受信) または (送信) のデータを格納するオブジェクト。 アーカイブに関連付けられている、`CSocketFile`オブジェクト。  
  
     ただし、`CArchive`データグラム ソケットでは機能しません。  
  
6.  使用して、`CArchive`クライアントとサーバー ソケットの間でデータを渡すオブジェクト。  
  
     注意してください、指定された`CArchive`オブジェクトは、一方向のみでデータを移動: (受信) の読み込みまたは格納 (送信) のいずれか。 場合によっては、使用する 2 つ`CArchive`オブジェクト: 受信確認を受信するため、その他のデータを送信する 1 つです。  
  
     後の接続を受け入れると、アーカイブの設定、パスワードの検証などのタスクを実行することができます。  
  
7.  アーカイブ、ソケット ファイル、およびソケット オブジェクトを破棄します。  
  
    > [!NOTE]
    >  クラス`CArchive`提供、`IsBufferEmpty`クラスで使用できるメンバー関数`CSocket`です。 バッファーにデータの複数のメッセージが含まれている場合は、それらのすべてが読み取られ、バッファーをクリアするまでループする必要があります。 それ以外の場合、次の通知を受信するデータがあること遅れる可能性があります無期限にします。 使用して`IsBufferEmpty`すべてのデータを取得することを保証します。  
  
 アーティクル[Windows ソケット: 動作シーケンス](../mfc/windows-sockets-sequence-of-operations.md)のコード例では、このプロセスの両方の側を示しています。  
  
 詳細については次を参照してください:  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [CSocket::Create](../mfc/reference/csocket-class.md#create)

