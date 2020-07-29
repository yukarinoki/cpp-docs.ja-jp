---
title: 'Windows ソケット: アーカイブを使用するソケットの例'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
ms.openlocfilehash: 275a6c274648225fedcec9d42c280f77af68158e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226777"
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows ソケット: アーカイブを使用するソケットの例

この記事では、クラス[CSocket](../mfc/reference/csocket-class.md)の使用例を示します。 この例では、 `CArchive` オブジェクトを使用してソケットを介してデータをシリアル化します。 これは、ファイルとの間でドキュメントをシリアル化するものではないことに注意してください。

次の例は、アーカイブを使用してオブジェクトを介してデータを送受信する方法を示してい `CSocket` ます。 この例は、アプリケーションの2つのインスタンス (同じコンピューター上またはネットワーク上の別のコンピューター上) がデータを交換するように設計されています。 一方のインスタンスはデータを送信し、もう一方のインスタンスはデータを受信して確認します。 どちらのアプリケーションも exchange を開始でき、サーバーとして、または他のアプリケーションに対するクライアントとして機能できます。 アプリケーションの view クラスでは、次の関数が定義されています。

[!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]

この例に関する最も重要な点は、その構造体が MFC 関数の構造と同じであることです `Serialize` 。 この `PacketSerialize` メンバー関数は、 **`if`** 句を含むステートメントで構成さ **`else`** れます。 関数は、 *Ardata*および*ardata*という2つの[CArchive](../mfc/reference/carchive-class.md)参照をパラメーターとして受け取ります。 *Ardata*アーカイブオブジェクトが格納 (送信) 用に設定されている場合は、分岐が実行されます **`if`** 。それ以外の場合は、 *ardata*が読み込み (受信) 用に設定されていると、関数は分岐を受け取り **`else`** ます。 MFC でのシリアル化の詳細については、「[シリアル化](../mfc/how-to-make-a-type-safe-collection.md)」を参照してください。

> [!NOTE]
> *Arack* archive オブジェクトは、 *arack*の逆であると見なされます。 *Ardata*が送信用であり、 *ardata*が受信され、逆の場合は true になります。

送信の場合、例の関数は、デモンストレーションのためにランダムなデータを生成するたびに、指定された回数だけループします。 アプリケーションでは、ファイルなどのソースから実際のデータを取得します。 *Ardata* archive の挿入演算子 ( **<<** ) は、次の3つの連続したデータチャンクのストリームを送信するために使用されます。

- データの性質を指定する "ヘッダー"。この場合は、 *Bvalue*変数の値と送信するコピーの数を指定します。

   この例では、両方の項目がランダムに生成されます。

- 指定されたデータのコピー数。

   内側 **`for`** のループは、指定された回数だけ*bvalue*を送信します。

- 受信者がユーザーに表示する*strText*という文字列。

受信の場合、関数は同様に動作しますが、アーカイブの抽出演算子 ( **>>** ) を使用してアーカイブからデータを取得する点が異なります。 受信側のアプリケーションは、受信したデータを検証し、最終的な "受信済み" メッセージを表示して、送信元アプリケーションが表示する "送信" というメッセージを返信します。

この通信モデルでは、 *strText*変数で送信されたメッセージである "received" という語が通信のもう一方の端に表示されます。そのため、受信側のユーザーに対して、特定の数のデータパケットを受信したことを指定します。 受信者は、元の送信者の画面に表示するために、"送信済み" という類似した文字列を返します。 両方の文字列を受け取ると、通信が成功したことを示します。

> [!CAUTION]
> 確立された (非 MFC) サーバーと通信するように MFC クライアントプログラムを作成している場合は、アーカイブを通じて C++ オブジェクトを送信しないでください。 サーバーが、送信するオブジェクトの種類を認識する MFC アプリケーションでない限り、オブジェクトを受信したり、逆シリアル化したりすることはできません。 「 [Windows ソケット: バイトの順序](../mfc/windows-sockets-byte-ordering.md)」の例では、この型の通信が示されています。

詳細については、「Windows Sockets Specification: **htonl**、 **htons**、 **ntohl**、 **ntohs**」を参照してください。 また、詳細については、以下を参照してください。

- [Windows ソケット: ソケットクラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows ソケット: アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows ソケット:背景](../mfc/windows-sockets-background.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[CArchive:: IsStoring](../mfc/reference/carchive-class.md#isstoring)<br/>
[CArchive:: operator <<](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive:: operator >>](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive:: Flush](../mfc/reference/carchive-class.md#flush)<br/>
[CObject:: Serialize](../mfc/reference/cobject-class.md#serialize)
