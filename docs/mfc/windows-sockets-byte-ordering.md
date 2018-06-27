---
title: 'Windows ソケット: バイトの順序付け |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a95725565dee2b25fd7f2e39927fde88c9cddff
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956003"
---
# <a name="windows-sockets-byte-ordering"></a>Windows ソケット : バイトの順序付け
この記事の内容と 2 部構成の記事は、Windows ソケット プログラミングのいくつかの問題を説明します。 この記事では、バイトの順序付けについて説明します。 他の問題については、技術情報: [Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md)と[Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)です。  
  
 使用するか、またはクラスから派生させる場合[CAsyncSocket](../mfc/reference/casyncsocket-class.md)、これらの問題を管理する必要があります。 使用するか、またはクラスから派生させる場合[CSocket](../mfc/reference/csocket-class.md)MFC では、それらを管理します。  
  
## <a name="byte-ordering"></a>バイトの順序付け  
 異なるマシン アーキテクチャは、場合によって異なるバイト順を使用してデータを格納します。 たとえば、Intel ベースのマシンは、Macintosh (Motorola) マシンの逆の順序でデータを格納します。 「リトル エンディアン、」と呼ばれる、Intel のバイト順ネットワーク標準的な「ビッグ エンディアン」順序の逆順になってもします。 次の表では、これらの用語について説明します。  
  
### <a name="big--and-little-endian-byte-ordering"></a>ビッグ エンディアンとリトル エンディアン バイト順  
  
|バイトの順序付け|説明|  
|-------------------|-------------|  
|ビッグ エンディアン|単語の左端が最上位バイトです。|  
|リトル エンディアン|最上位バイトは、単語の右端にです。|  
  
 通常、ネットワーク経由で送受信するデータの変換でバイト順について心配する必要はありませんが、バイト順を変換する必要があります状況があります。  
  
## <a name="when-you-must-convert-byte-orders"></a>バイト順を変換する際にする必要があります。  
 次の状況でバイト順の変換が必要です。  
  
-   別のコンピューターに送信するデータではなく、ネットワークで解釈する必要がある情報を渡しています。 たとえば、渡すような場合のポートとアドレスは、ネットワークを理解する必要があります。  
  
-   接続しているサーバー アプリケーションは、MFC アプリケーションではない (およびそれに対して、ソース コードはありません)。 これは、2 台のコンピューターは同じバイト順序を共有していない場合場合に、バイト順の変換に対して呼び出されます。  
  
## <a name="when-you-do-not-have-to-convert-byte-orders"></a>バイト順の変換があるない場合  
 次の状況でバイト順の変換を回避できます。  
  
-   スワップ (バイト単位) が両方の end が上のマシンが同意でき、両方のコンピューターが同じバイト順を使用します。  
  
-   通信するサーバーは、MFC アプリケーションです。  
  
-   わかるように明示的にか、バイト順を変換する必要があるかどうかと、通信しているサーバーのソース コードがあります。  
  
-   MFC にサーバーを移植することができます。 これは非常に簡単に行うし、結果が小さく高速のコードでは通常です。  
  
 扱う[CAsyncSocket](../mfc/reference/casyncsocket-class.md)、すべてのバイト順のために必要な変換を自主管理する必要があります。 Windows ソケットは、「ビッグ エンディアン」のバイト順のモデルを標準化および、この順序とその他のユーザー間で変換する機能を提供します。 [CArchive](../mfc/reference/carchive-class.md)、ただし、これと共に使用する[CSocket](../mfc/reference/csocket-class.md)、その逆の (「リトル エンディアン」) の順序を使用してが`CArchive`バイト順変換のための詳細を行います。 このアプリケーションで標準的な順序または Windows Sockets バイト順の変換関数を使用してを使用して行うことができます、コード移植性を高める。  
  
 MFC ソケットの理想的な使用状況は、通信の両端を自分で作成し、両端で MFC を使用する場合です。 バイトのスワッピング データをアーカイブ オブジェクトに渡す前に管理する必要があります、FTP サーバーなどの非 MFC アプリケーションと通信するアプリケーションを作成している場合は、Windows ソケット変換ルーチンを使用して**ntohs**、 **ntohl**、 **htons**、および**htonl**です。 非 MFC アプリケーションとの通信で使用されるこれらの関数の例では、この記事で後述が表示されます。  
  
> [!NOTE]
>  通信のもう一方の端は、MFC アプリケーションではない、ときにも使わないようにしてくださいから派生した C++ オブジェクトのストリーミング`CObject`アーカイブに、受信側がそれらを処理できないためです。 注を参照してください[Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)です。  
  
 バイト順の詳細については、Windows SDK で使用できる Windows ソケット仕様を参照してください。  
  
## <a name="a-byte-order-conversion-example"></a>バイト順の変換例  
 次の例のシリアル化の関数を示しています、`CSocket`アーカイブを使用するオブジェクト。 Windows ソケット API では、バイト順の変換関数を使用しても示します。  
  
 この例では、非 MFC サーバー アプリケーションがあるないソース コードへのアクセスと通信するクライアントを記述するシナリオを示します。 このシナリオでは、非 MFC サーバーが標準的なネットワークのバイト順を使用すると見なす必要があります。 MFC クライアント アプリケーションを使用してこれに対し、`CArchive`オブジェクトを`CSocket`オブジェクト、および`CArchive`「リトル エンディアン」バイト順を逆の標準のネットワークを使用します。  
  
 通信を計画、非 MFC サーバーは、次のようなメッセージ パケットのプロトコルが設定されているとします。  
  
 [!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]  
  
 MFC には、この表記は次のように。  
  
 [!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]  
  
 C++ では、**構造体**クラスとして基本的に同じです。 `Message`構造がなどのメンバー関数を持つことができます、`Serialize`上メンバー関数が宣言されています。 `Serialize`メンバー関数は、次のようになります。  
  
 [!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]  
  
 この例は、一方の端で非 MFC サーバー アプリケーションのバイトの順序付けの間オフ不一致があるためデータのバイト順の変換を呼び出し、`CArchive`もう一方の end を MFC クライアント アプリケーションで使用します。 Windows ソケットを提供するバイト順の変換機能のいくつかを示します。 次の表では、これらの関数について説明します。  
  
### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows ソケットのバイト順の変換関数  
  
|関数|目的|  
|--------------|-------------|  
|**ntohs**|16 ビット値をネットワーク バイト オーダーからホストのバイト順 (ビッグ エンディアン リトル エンディアンに) 変換します。|  
|**ntohl**|32 ビット値をネットワーク バイト オーダーからホストのバイト順 (ビッグ エンディアン リトル エンディアンに) 変換します。|  
|**Htons**|ホストのバイト順から 16 ビットの数をネットワークのバイト順 (リトル エンディアン ビッグ エンディアンに) に変換します。|  
|**Htonl**|ホストのバイト順から 32 ビット値をネットワークのバイト順 (リトル エンディアン ビッグ エンディアンに) に変換します。|  
  
 この例の別のポイントは、通信のもう一方の端のソケット アプリケーションが、非 MFC アプリケーションの場合は、必要がありますしないようにして、次のような処理が実行を示します。  
  
 `ar << pMsg;`  
  
 ここで`pMsg`クラスから派生した C++ オブジェクトへのポインターは、`CObject`です。 MFC アプリケーションの場合と同様のオブジェクトとサーバーに関連付けられている追加の MFC 情報は、それを理解されません送信されます。  
  
 詳細については次を参照してください:  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: 予備知識](../mfc/windows-sockets-background.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)

