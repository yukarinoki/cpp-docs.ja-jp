---
title: 'Windows ソケット: アーカイブを使用するソケットの例'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
ms.openlocfilehash: 253a65430ae230fbc4deeb9bd5288f28237310d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371088"
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows ソケット: アーカイブを使用するソケットの例

この記事では、クラス[CSocket](../mfc/reference/csocket-class.md)を使用する例を示します。 この例では、`CArchive`ソケットを介してデータをシリアル化するオブジェクトを使用します。 これは、ファイルとの間でのドキュメントのシリアル化ではありません。

次の例は、アーカイブを使用してオブジェクトを介してデータを送受信`CSocket`する方法を示しています。 この例は、アプリケーションの 2 つのインスタンス (同じコンピューター上またはネットワーク上の異なるマシン上) がデータを交換するように設計されています。 1 つのインスタンスは、他のインスタンスが受信し、確認するデータを送信します。 どちらのアプリケーションも交換を開始でき、サーバーとして、または他のアプリケーションのクライアントとして機能することができます。 アプリケーションのビュー クラスでは、次の関数が定義されています。

[!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]

この例で最も重要なことは、その構造体が MFC`Serialize`関数の構造と並列に行うということです。 メンバー`PacketSerialize`関数は **、else**句を持つ**if**ステートメントで構成されます。 関数は、パラメータとして 2 つの[CArchive](../mfc/reference/carchive-class.md)参照を受け取ります: *arData*と*arAck*. *arData*アーカイブオブジェクトが保存 (送信) 用に設定されている場合は **、if**ブランチが実行されます。それ以外の場合 *、arData*が読み込み (受信) に設定されている場合、関数は**else**ブランチを受け取ります。 MFC でのシリアル化の詳細については、「[シリアル化](../mfc/how-to-make-a-type-safe-collection.md)」を参照してください。

> [!NOTE]
> *arAck*アーカイブ オブジェクトは*arData*の反対であると見なされます。 *arData*が送信用の場合 *、arAck*は受信し、逆の場合は true です。

送信の場合、関数例は指定された回数ループし、毎回デモ用にランダムなデータを生成します。 アプリケーションは、ファイルなどのソースから実際のデータを取得します。 *arData*アーカイブの挿入演算子 (**<<**) は、連続する 3 つのデータ・チャンクのストリームを送信するために使用されます。

- データの性質 (この場合は*bValue*変数の値と送信されるコピーの数) を指定する「ヘッダー」。

   この例では、両方のアイテムがランダムに生成されます。

- データの指定されたコピー数。

   内部**の for**ループは、指定された回数*bValue*を送信します。

- 受信者がユーザーに表示する*strText*という文字列。

受信の場合、アーカイブの抽出演算子 (**>>**) を使用してアーカイブからデータを取得する点を除いて、関数も同様に動作します。 受信側のアプリケーションは、受信したデータを確認し、最後の "Received" メッセージを表示し、送信側アプリケーションが表示する "Sent" というメッセージを返します。

この通信モデルにおいて *、strText*変数で送信されるメッセージである「Received」という語は、通信の他方の端に表示するため、ある数のデータが受信されたことを受信側のユーザに指定する。 受信者は、元の送信者の画面に表示するために、"Sent" と表示される同様の文字列で応答します。 両方の文字列を受信すると、通信が正常に完了したことを示します。

> [!CAUTION]
> 確立された (非 MFC) サーバーと通信する MFC クライアント プログラムを作成する場合は、アーカイブを通じて C++ オブジェクトを送信しないでください。 サーバーが、送信するオブジェクトの種類を理解する MFC アプリケーションでない限り、オブジェクトを受信および逆シリアル化することはできません。 「Windows[ソケット: バイト順](../mfc/windows-sockets-byte-ordering.md)」の記事の例は、この種類の通信を示しています。

詳細については、「 Windows ソケットの仕様 : **htonl**, **htons**, **ntohl**, **ntohs**」を参照してください。 また、詳細については、次の項目を参照してください。

- [Windows ソケット : ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows ソケット : アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows ソケット : 予備知識](../mfc/windows-sockets-background.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[アーカイブ::Is格納](../mfc/reference/carchive-class.md#isstoring)<br/>
[アーカイブ::オペレーター <<](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[アーカイブ::オペレーター >>](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[アーカイブ::フラッシュ](../mfc/reference/carchive-class.md#flush)<br/>
[Cオブジェクト::シリアライズ](../mfc/reference/cobject-class.md#serialize)
