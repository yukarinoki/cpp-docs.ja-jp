---
title: 'Windows ソケット: Casyncsocket クラス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CAsyncSocket
dev_langs:
- C++
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a96ccdd4ce5c49f18c12aa85060954fc97a3408b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows ソケット: CAsyncSocket クラスの使い方
この記事は、クラスを使用する方法を説明します。 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)です。 このクラスが非常に低いレベルで Windows ソケット API をカプセル化ことに注意してください。 `CAsyncSocket` ネットワーク通信がネットワーク イベントの通知のコールバックをするプログラマによって使用されます。 この想定に基づいて、この記事は、基本的な命令のみを提供します。 使用を検討する必要がありますおそらく`CAsyncSocket`Windows ソケットの MFC アプリケーションで複数のネットワーク プロトコルを処理する簡単なは柔軟性を犠牲にしたくない場合。 複数の通信をよりでしたモデルを使用して、一般的な代替クラスの直接プログラミングの効率向上を取得できることが多いとも`CSocket`します。  
  
 `CAsyncSocket` 記載されて、 *『 MFC リファレンス*です。 Visual C では、Windows SDK には、Windows ソケット仕様も提供します。 詳細についてに残されます。 Visual C のサンプル アプリケーションを指定していません`CAsyncSocket`です。  
  
 ネットワーク通信についてあまり知識がなく、簡単な方法するときは、クラスを使用して[CSocket](../mfc/reference/csocket-class.md)で、`CArchive`オブジェクト。 参照してください[Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)詳細についてはします。  
  
 この記事では次の内容について説明します。  
  
-   作成と使用、`CAsyncSocket`オブジェクト。  
  
-   [お客様の責任で CAsyncSocket](#_core_your_responsibilities_with_casyncsocket)です。  
  
##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> CAsyncSocket オブジェクトの作成と  
  
#### <a name="to-use-casyncsocket"></a>CAsyncSocket を使用するには  
  
1.  構築、 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)オブジェクトを基になるを作成するオブジェクトを使用して**ソケット**を処理します。  
  
     ソケットの作成は、2 段階の構築の MFC パターンに従います。  
  
     例えば:  
  
     [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]  
  
     - または -  
  
     [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]  
  
     上記の最初のコンス トラクターを作成、`CAsyncSocket`スタック上のオブジェクト。 2 番目のコンス トラクターを作成、`CAsyncSocket`ヒープにします。 最初の[作成](../mfc/reference/casyncsocket-class.md#create)上記の呼び出しでは、既定のパラメーターを使用して、ストリーム ソケットを作成します。 2 番目**作成**呼び出しは、指定したポートとアドレスを持つデータグラム ソケットを作成します。 (いずれかを使用する**作成**いずれかの構築方法とバージョンです)。  
  
     パラメーターを**作成**は。  
  
    -   "Port": 短整数。  
  
         サーバー ソケットの場合、ポートを指定する必要があります。 クライアント ソケットの場合は、一般にこのパラメーターは、により、Windows ソケットのポートの選択の既定値を受け取ります。  
  
    -   ソケットの種類: **SOCK_STREAM** (既定) または**SOCK_DGRAM**です。  
  
    -   ソケット"address"「専用」または「128.56.22.8」など。  
  
         これは、ネットワーク上、インターネット プロトコル (IP) アドレスです。 このパラメーターの既定値に依存するは常に可能性があります。  
  
     用語"port"および「ソケット アドレス」で説明されて[Windows ソケット: ポートとソケット アドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)です。  
  
2.  ソケットがクライアントの場合は、ソケット オブジェクトをサーバーに接続を使用して、ソケット[不要なため](../mfc/reference/casyncsocket-class.md#connect)です。  
  
     - または -  
  
     ソケットがサーバーの場合は、設定の待機を開始するソケット (で[CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)) クライアントからの接続試行します。 接続要求を受信するには、その内容に同意を[CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept)です。  
  
     接続を受け入れると、パスワードの検証などのタスクを実行できます。  
  
    > [!NOTE]
    >  **Accept**メンバー関数は、新しい空への参照を受け取ります`CSocket`オブジェクトをパラメーターとして。 呼び出す前に、このオブジェクトを構築する必要があります**Accept**です。 このソケット オブジェクトがスコープ外に出ると、接続は閉じられます。 呼び出す必要はありません**作成**この新しいソケット オブジェクト。 例については、記事を参照してください。 [Windows ソケット: 動作シーケンス](../mfc/windows-sockets-sequence-of-operations.md)です。  
  
3.  呼び出して他のソケットとの通信を実行、 `CAsyncSocket` Windows ソケット API 関数をカプセル化するオブジェクトのメンバー関数。  
  
     Windows ソケット仕様とクラスを参照してください[CAsyncSocket](../mfc/reference/casyncsocket-class.md)で、 *『 MFC リファレンス*です。  
  
4.  破棄、`CAsyncSocket`オブジェクト。  
  
     スタックにソケット オブジェクトを作成する場合は、含まれる関数がスコープ外に出るときにデストラクターが呼び出されます。 使用して、ヒープ上のソケット オブジェクトを作成した場合、**新しい**演算子、必要がありますを使用して、**削除**オブジェクトを破棄する演算子です。  
  
     デストラクターは、オブジェクトの[閉じる](../mfc/reference/casyncsocket-class.md#close)メンバー関数は、オブジェクトを破棄する前にします。  
  
 コードでは、このシーケンスの例については (を実際には、`CSocket`オブジェクト) を参照してください[Windows ソケット: 動作シーケンス](../mfc/windows-sockets-sequence-of-operations.md)です。  
  
##  <a name="_core_your_responsibilities_with_casyncsocket"></a> CAsyncSocket でお客様の責任  
 クラスのオブジェクトを作成するときに[CAsyncSocket](../mfc/reference/casyncsocket-class.md)、オブジェクトは、Windows をカプセル化**ソケット**を処理し、そのハンドルに対する操作を提供します。 使用すると`CAsyncSocket`API を直接使用する場合に考慮しなければならないすべての問題に対処する必要があります。 例えば:  
  
-   「ブロック」シナリオです。  
  
-   バイト順序の違いは、送信および受信マシン間。  
  
-   Unicode およびマルチバイト文字の間の変換 (MBCS) 文字列を設定します。  
  
 これらの条項と追加情報の定義は、次を参照してください[Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md)、 [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)、 [Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md).  
  
 クラスのこれらの問題に関係なく**CAsycnSocket**場合があります、最適な選択肢をアプリケーションで必要なすべての柔軟性と制御を取得できます。 クラスを使用してを考慮する必要があります、場合`CSocket`代わりにします。 `CSocket` 多くのお客様からの詳細を非表示にします。 Windows ブロッキング呼び出し中にメッセージと、ポンプへのアクセスを it `CArchive`、バイト順序の違いと文字列の変換を行うを管理します。  
  
 詳細については次を参照してください:  
  
-   [Windows ソケット: 予備知識](../mfc/windows-sockets-background.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)

