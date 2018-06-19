---
title: 'Windows ソケット: アーカイブを使用するソケットの例 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02cd74a20f0ccc54a366c1a62d913ee30e72471a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384372"
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows ソケット: アーカイブを使用するソケットの例
この記事は、クラスを使用する例を示します[CSocket](../mfc/reference/csocket-class.md)です。 この例では`CArchive`ソケットを使用してデータをシリアル化されるオブジェクト。 このドキュメントのシリアル化する、またはファイルからではないことに注意してください。  
  
 次の例を使用してデータを送受信する、アーカイブを使用する方法を示しています。`CSocket`オブジェクト。 この例では、アプリケーション (同じコンピューター上またはネットワーク上の異なるコンピューター上) の 2 つのインスタンスがデータを交換ように設計されています。 1 つのインスタンスは、別のインスタンスを受信して承認されると、データを送信します。 どちらのアプリケーションは、交換を開始でき、サーバーまたは他のアプリケーションにクライアントとして動作いずれかのことができます。 次の関数は、アプリケーションのビュー クラスで定義されます。  
  
 [!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]  
  
 この例の最も重要な点は、その構造に似て MFC`Serialize`関数。 **PacketSerialize**で構成されるメンバー関数、**場合**ステートメントを**else**句。 2 つの関数が受け取る[CArchive](../mfc/reference/carchive-class.md)パラメーターとして参照:`arData`と`arAck`です。 場合、 `arData` (送信) を格納するためにアーカイブ オブジェクトが設定されて、**場合**分岐が実行されます。 それ以外の場合`arData`設定されている関数を受け取ります (受信) を読み込むための、 **else**分岐します。 MFC におけるシリアル化の詳細については、次を参照してください。[シリアル化](../mfc/how-to-make-a-type-safe-collection.md)です。  
  
> [!NOTE]
>  `arAck`アーカイブ オブジェクトは、の反対と見なされます`arData`です。 場合`arData`を送信するの`arAck`を受け取ると、その逆は true です。  
  
 送信する、関数の例は、指定した回数だけ、デモンストレーションのためのいくつかのランダムなデータを生成するたびにループします。 アプリケーションは、ファイルなど、いくつかのソースから実際のデータを入手します。 `arData`アーカイブの挿入演算子 (**<<**) 次の 3 つの連続するデータのチャンクのストリームを送信するために使用します。  
  
-   "Header"データの性質を指定する (この場合の値、`bValue`変数とコピーの数は送信されます)。  
  
     両方の項目は、この例のランダムに生成されます。  
  
-   データのコピーの指定した数。  
  
     内部**の**送信をループ`bValue`一定の回数。  
  
-   文字列と呼ばれる`strText`受信側がそのユーザーに表示します。  
  
 受信の関数の動作同様に、同じ (**>>**) アーカイブからデータを取得します。 受信側のアプリケーションでは、表示する、送信元アプリケーションのデータを受け取る、最終の「受信」メッセージを表示し、「送信済み」と表示されているメッセージを送り返しますを検証します。  
  
 この通信のモデル、単語「受信」では、メッセージで送信、`strText`変数は表示する、通信のもう一方の端にあるデータのパケット数が受け取ったことを受信側ユーザーを指定します。 受信側は、元の送信者の画面で「送信」、表示すると表示されている類似した文字列で応答します。 両方の文字列の確認メッセージでは、正常な通信が発生したことを示します。  
  
> [!CAUTION]
>  確立 (非 MFC) サーバーと通信するために MFC クライアント プログラムを記述する場合は、アーカイブを通じて C++ オブジェクトを送信しません。 サーバーは、送信するオブジェクトの種類を認識する MFC アプリケーションでない限りに受信し、オブジェクトを逆シリアル化することはできません。 たとえば、アーティクルで[Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)この種類の通信を示します。  
  
 詳細については、Windows ソケット仕様を参照してください: **htonl**、 **htons**、 **ntohl**、 **ntohs**です。 また、詳細についてを参照してください。  
  
-   [Windows ソケット: ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows ソケット: 予備知識](../mfc/windows-sockets-background.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [用](../mfc/reference/carchive-class.md#isstoring)   
 [CArchive::operator <<](../mfc/reference/carchive-class.md#operator_lt_lt)   
 [CArchive::operator >>](../mfc/reference/carchive-class.md#operator_lt_lt)   
 [ときは](../mfc/reference/carchive-class.md#flush)   
 [Cobject::serialize](../mfc/reference/cobject-class.md#serialize)

