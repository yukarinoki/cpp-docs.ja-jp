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
ms.openlocfilehash: 3977308776c4ec6fed844038c4453ad03d065f98
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445940"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows ソケット: CAsyncSocket クラスの使い方

この記事では、 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)クラスの使用方法について説明します。 このクラスでは、Windows Sockets API が非常に低いレベルでカプセル化されていることに注意してください。 `CAsyncSocket` は、ネットワーク通信の詳細を把握しているが、ネットワークイベントの通知にコールバックを使用する必要があるプログラマによって使用されます。 この前提に基づいて、この記事では基本的な手順のみを説明します。 Windows ソケットを使用して、MFC アプリケーションで複数のネットワークプロトコルを簡単に処理できるようにする必要があるが、柔軟性を犠牲にしたくない場合は、`CAsyncSocket` を使用することを検討してください。 また、クラス `CSocket`の汎用的な代替モデルを使用するよりも、より効率的に通信をプログラミングすることにより、効率を向上させることができます。

`CAsyncSocket` は、「 *MFC リファレンス*」に記載されています。 またC++ 、Visual は、Windows SDK にある Windows ソケット仕様も提供します。 詳細はお持ちのままです。 ビジュアルC++には `CAsyncSocket`のサンプルアプリケーションが用意されていません。

ネットワーク通信について十分な知識がなく、単純なソリューションが必要な場合は、`CArchive` オブジェクト[と共にクラスを使用](../mfc/reference/csocket-class.md)します。 詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

この記事には、次の内容が含まれます。

- `CAsyncSocket` オブジェクトの作成と使用

- [CAsyncSocket による責任](#_core_your_responsibilities_with_casyncsocket)。

##  <a name="_core_creating_and_using_a_casyncsocket_object"></a>CAsyncSocket オブジェクトの作成と使用

#### <a name="to-use-casyncsocket"></a>CAsyncSocket を使用するには

1. [CAsyncSocket](../mfc/reference/casyncsocket-class.md)オブジェクトを構築し、オブジェクトを使用して基になる**ソケット**ハンドルを作成します。

   ソケットの作成は、2段階構築の MFC パターンに従います。

   例 :

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     または

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   上の1つ目のコンストラクターは、スタック上に `CAsyncSocket` オブジェクトを作成します。 2番目のコンストラクターは、ヒープに `CAsyncSocket` を作成します。 上記の最初の[Create](../mfc/reference/casyncsocket-class.md#create)呼び出しでは、既定のパラメーターを使用してストリームソケットを作成します。 2番目の `Create` 呼び出しは、指定されたポートとアドレスを使用してデータグラムソケットを作成します。 (どちらの構築方法でも `Create` バージョンのいずれかを使用できます)。

   `Create` するパラメーターは次のとおりです。

   - "Port": 短整数。

      サーバーソケットの場合は、ポートを指定する必要があります。 クライアントソケットの場合は、通常、このパラメーターの既定値をそのまま使用します。これにより、Windows ソケットがポートを選択できるようになります。

   - ソケットの種類: **SOCK_STREAM** (既定値) または**SOCK_DGRAM**です。

   - "Ftp.microsoft.com" や "128.56.22.8" などのソケットの "アドレス"。

      これは、ネットワーク上のインターネットプロトコル (IP) アドレスです。 このパラメーターの既定値を常に使用することがあります。

   「 [Windows ソケット: ポートとソケット](../mfc/windows-sockets-ports-and-socket-addresses.md)アドレス」では、"ポート" と "ソケットアドレス" という用語について説明しています。

1. ソケットがクライアントの場合は、 [CAsyncSocket:: connect](../mfc/reference/casyncsocket-class.md#connect)を使用して、ソケットオブジェクトをサーバーソケットに接続します。

     または

   ソケットがサーバーである場合は、クライアントからの接続試行に対して ( [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen)を使用した) リッスンを開始するようにソケットを設定します。 接続要求を受け取ったら、 [CAsyncSocket:: accept](../mfc/reference/casyncsocket-class.md#accept)で受け入れます。

   接続を受け入れると、パスワードの検証などのタスクを実行できます。

    > [!NOTE]
    >  `Accept` メンバー関数は、新しい空の `CSocket` オブジェクトへの参照をそのパラメーターとして受け取ります。 `Accept`を呼び出す前に、このオブジェクトを作成する必要があります。 このソケットオブジェクトがスコープ外に出ると、接続は閉じられます。 この新しいソケットオブジェクトに対して `Create` を呼び出さないでください。 例については、「 [Windows ソケット: 操作のシーケンス](../mfc/windows-sockets-sequence-of-operations.md)」を参照してください。

1. Windows Sockets API 関数をカプセル化する `CAsyncSocket` オブジェクトのメンバー関数を呼び出すことによって、他のソケットとの通信を実行します。

   『 *MFC リファレンス*』の「Windows Sockets specification And class [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 」を参照してください。

1. `CAsyncSocket` オブジェクトを破棄します。

   ソケットオブジェクトをスタック上に作成した場合は、含んでいる関数がスコープ外に出ると、そのデストラクターが呼び出されます。 **New**演算子を使用してヒープにソケットオブジェクトを作成した場合は、 **delete**演算子を使用してオブジェクトを破棄する必要があります。

   デストラクターは、オブジェクトを破棄する前に、オブジェクトの[Close](../mfc/reference/casyncsocket-class.md#close)メンバー関数を呼び出します。

コード内のこのシーケンスの例 (実際には `CSocket` オブジェクト) については、「 [Windows ソケット: 操作のシーケンス](../mfc/windows-sockets-sequence-of-operations.md)」を参照してください。

##  <a name="_core_your_responsibilities_with_casyncsocket"></a>CAsyncSocket による責任

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)クラスのオブジェクトを作成すると、オブジェクトは Windows**ソケット**ハンドルをカプセル化し、そのハンドルに対する操作を提供します。 `CAsyncSocket`を使用する場合は、API を直接使用する場合に直面する可能性のあるすべての問題に対処する必要があります。 例 :

- "ブロッキング" シナリオ。

- 送信側と受信側のコンピューターのバイト順の違い。

- Unicode とマルチバイト文字セット (MBCS) の文字列間の変換。

これらの用語の定義と追加情報については、「 [Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md)、 [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)、 [Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)」を参照してください。

これらの問題が発生しても、アプリケーションで取得できる柔軟性と制御がすべて必要な場合は、クラス `CAsycnSocket` が適切な選択肢となります。 そうでない場合は、代わりにクラス `CSocket` を使用することを検討してください。 `CSocket` は、さまざまな詳細を非表示にします。ブロック呼び出し中に Windows メッセージをポンプし、バイト順の違いと文字列変換を管理する `CArchive`にアクセスできるようにします。

詳細については、次を参照してください。

- [Windows ソケット: 予備知識](../mfc/windows-sockets-background.md)

- [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>参照

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)
