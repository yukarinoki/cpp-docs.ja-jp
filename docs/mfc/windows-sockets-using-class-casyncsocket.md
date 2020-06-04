---
title: 'Windows ソケット: CAsyncSocket クラスの使い方'
ms.date: 11/04/2016
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
ms.openlocfilehash: d3fc32d9da54d9cf8c79e9e5de45b81c2ef64a6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371967"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows ソケット: CAsyncSocket クラスの使い方

この記事では、クラス[CAsyncSocket](../mfc/reference/casyncsocket-class.md)を使用する方法について説明します。 このクラスは、Windows ソケット API を非常に低いレベルでカプセル化していることに注意してください。 `CAsyncSocket`ネットワーク通信を詳細に知っているが、ネットワークイベントの通知のためのコールバックの利便性を望むプログラマが使用します。 この前提に基づき、この記事では基本的な指示のみを提供します。 Windows ソケットが`CAsyncSocket`MFC アプリケーションで複数のネットワーク プロトコルを扱いやすくするが、柔軟性を犠牲にしたくない場合は、おそらく使用を検討する必要があります。 また、より一般的な代替モデルのクラス`CSocket`を使用するよりも、通信をより直接的にプログラミングすることで、効率を高めることができると感じるかもしれません。

`CAsyncSocket`は MFC*リファレンス*に記載されています。 また、Windows のソケット仕様も提供します。 詳細はあなたに委ねされます。 Visual C++ では、サンプル アプリケーション`CAsyncSocket`は提供されません。

ネットワーク通信に関する知識が豊富で、簡単なソリューションが必要な場合は、オブジェクトと共`CArchive`にクラス[CSocket](../mfc/reference/csocket-class.md)を使用します。 詳細については[、「Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

この記事には、次の内容が含まれます。

- `CAsyncSocket`オブジェクトの作成と使用

- [あなたの責任は、CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).

## <a name="creating-and-using-a-casyncsocket-object"></a><a name="_core_creating_and_using_a_casyncsocket_object"></a>CAsync ソケット オブジェクトの作成と使用

#### <a name="to-use-casyncsocket"></a>同期ソケットを使用するには

1. [CAsyncSocket](../mfc/reference/casyncsocket-class.md)オブジェクトを構築し、そのオブジェクトを使用して基になる**ソケット**ハンドルを作成します。

   ソケットの作成は、2 段階の構築の MFC パターンに従います。

   次に例を示します。

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     \- または -

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   上記の最初のコンストラクタは`CAsyncSocket`、スタック上にオブジェクトを作成します。 2 番目のコンストラクター`CAsyncSocket`は、ヒープ上に を作成します。 上記の最初の[Create](../mfc/reference/casyncsocket-class.md#create)呼び出しでは、デフォルトのパラメーターを使用してストリームソケットを作成します。 2`Create`番目の呼び出しは、指定されたポートとアドレスを持つデータグラム ソケットを作成します。 (どちらの方法でも`Create`どちらのバージョンでも使用できます。

   次のパラメータ`Create`を指定します。

   - "ポート" : 短整数。

      サーバー ソケットの場合は、ポートを指定する必要があります。 クライアント ソケットの場合、通常は、このパラメーターの既定値を受け入れます。

   - ソケットタイプ: **SOCK_STREAM** (デフォルト) または**SOCK_DGRAM。**

   - ソケット「アドレス」、"ftp.microsoft.com"または"128.56.22.8"。

      これは、ネットワーク上のインターネット プロトコル (IP) アドレスです。 このパラメータの既定値は常に使用されます。

   「ポート」と「ソケットアドレス」という用語は[、Windows ソケット: ポートとソケット アドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)で説明されています。

1. ソケットがクライアントの場合は、ソケットオブジェクトを[CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect)を使用してサーバーソケットに接続します。

     \- または -

   ソケットがサーバーの場合、クライアントからの接続試行に対して[(CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)を使用して) リッスンを開始するようにソケットを設定します。 接続要求を受信した後、[それを受け入れるのは、CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept)です。

   接続を受け入れた後、パスワードの検証などのタスクを実行できます。

    > [!NOTE]
    >  メンバー`Accept`関数は、新しい空`CSocket`のオブジェクトへの参照をパラメーターとして受け取ります。 このオブジェクトは、 を呼び`Accept`出す前に構築する必要があります。 このソケット オブジェクトがスコープ外に出ると、接続は閉じます。 この新しい`Create`ソケット オブジェクトを呼び出しません。 例については[、「Windows ソケット: 操作のシーケンス](../mfc/windows-sockets-sequence-of-operations.md)」を参照してください。

1. Windows ソケット API 関数をカプセル化`CAsyncSocket`するオブジェクトのメンバー関数を呼び出して、他のソケットと通信します。

   *MFC リファレンス*の Windows ソケット仕様とクラス[CAsyncSocket](../mfc/reference/casyncsocket-class.md)を参照してください。

1. オブジェクトを`CAsyncSocket`破棄します。

   スタック上にソケット オブジェクトを作成した場合、そのオブジェクトのデストラクターは、包含する関数がスコープ外に出るときに呼び出されます。 **new**演算子を使用してヒープにソケット オブジェクトを作成した場合は **、delete**演算子を使用してオブジェクトを破棄する必要があります。

   デストラクターは、オブジェクトを破棄する前に、オブジェクトの[Close](../mfc/reference/casyncsocket-class.md#close)メンバー関数を呼び出します。

コード内のこのシーケンスの例 (実際には`CSocket`オブジェクトの場合) については、「 Windows ソケット :[操作のシーケンス](../mfc/windows-sockets-sequence-of-operations.md)」を参照してください。

## <a name="your-responsibilities-with-casyncsocket"></a><a name="_core_your_responsibilities_with_casyncsocket"></a>CAsyncSocket を使用したあなたの責任

[クラス CAsyncSocket](../mfc/reference/casyncsocket-class.md)のオブジェクトを作成すると、オブジェクトは Windows**ソケット**ハンドルをカプセル化し、そのハンドルに操作を提供します。 を使用`CAsyncSocket`する場合は、API を直接使用する場合に直面する可能性のあるすべての問題に対処する必要があります。 次に例を示します。

- 「ブロッキング」シナリオ。

- 送信側と受信側のマシン間でバイトの順序が異なる。

- ユニコード文字セット (MBCS) 文字列間の変換。

これらの用語の定義と追加情報については、「 [Windows ソケット : ブロック](../mfc/windows-sockets-blocking.md)、 Windows ソケット :[バイト順](../mfc/windows-sockets-byte-ordering.md)の設定[、Windows ソケット : 文字列の変換](../mfc/windows-sockets-converting-strings.md)」を参照してください。

これらの問題にもかかわらず、アプリケーション`CAsycnSocket`で必要なすべての柔軟性と制御が必要な場合は、クラスが最適な選択肢になる場合があります。 ない場合は、代わりにクラス`CSocket`を使用することを検討してください。 `CSocket`ブロック呼び出し中に Windows メッセージを送り込み、バイトオーダーの違いや`CArchive`文字列変換を管理する にアクセスできます。

詳細については、次を参照してください。

- [Windows ソケット : 予備知識](../mfc/windows-sockets-background.md)

- [Windows ソケット : ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット : データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)
