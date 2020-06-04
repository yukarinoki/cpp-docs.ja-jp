---
title: 'Windows ソケット : バイトの順序付け'
ms.date: 11/04/2016
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
ms.openlocfilehash: 50548202483c4d9d4471ad2c600270c4df4503e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371060"
---
# <a name="windows-sockets-byte-ordering"></a>Windows ソケット : バイトの順序付け

この資料と 2 つの関連資料では、Windows ソケットプログラミングのいくつかの問題について説明します。 この記事では、バイト順について説明します。 その他の問題については[、「Windows ソケット: ブロック](../mfc/windows-sockets-blocking.md)と[Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)」の記事で説明します。

クラス[CAsyncSocket](../mfc/reference/casyncsocket-class.md)を使用するか、クラスから派生する場合は、これらの問題を自分で管理する必要があります。 CSocket クラスを使用するか[CSocket](../mfc/reference/csocket-class.md)、クラスから派生する場合、MFC によってそれらのクラスが管理されます。

## <a name="byte-ordering"></a>バイトの順序付け

マシンアーキテクチャによって、異なるバイトオーダーを使用してデータを格納する場合があります。 たとえば、Intel ベースのマシンは、Macintosh (モトローラ) マシンの逆の順序でデータを格納します。 「リトルエンディアン」と呼ばれるIntelバイト順は、ネットワーク標準の「ビッグエンディアン」の順序の逆でもあります。 次の表では、これらの用語について説明します。

### <a name="big--and-little-endian-byte-ordering"></a>ビッグエンディアンとリトルエンディアンのバイトオーダー

|バイトの順序付け|意味|
|-------------------|-------------|
|ビッグエンディアン|最上位バイトは単語の左端にあります。|
|リトルエンディアン|最上位バイトは単語の右端にあります。|

通常、ネットワーク経由で送受信するデータのバイト順変換について心配する必要はありませんが、バイトオーダーを変換する必要がある場合があります。

## <a name="when-you-must-convert-byte-orders"></a>バイトオーダーを変換する必要がある場合

次の場合、バイトオーダーを変換する必要があります。

- 別のマシンに送信するデータではなく、ネットワークで解釈する必要がある情報を渡しています。 たとえば、ネットワークで理解する必要があるポートとアドレスを渡すことができます。

- 通信しているサーバー アプリケーションは MFC アプリケーションではありません (ソース コードはありません)。 これは、2 台のマシンが同じバイト順を共有しない場合にバイト順変換を必要とします。

## <a name="when-you-do-not-have-to-convert-byte-orders"></a>バイトオーダーを変換する必要がない場合

次の状況では、バイトオーダーの変換作業を回避できます。

- 両端のマシンはバイトをスワップしないことに同意でき、両方のマシンは同じバイト順を使用します。

- 通信しているサーバーは MFC アプリケーションです。

- 通信しているサーバーのソース コードがあるので、バイト オーダーを変換する必要があるかどうかを明示的に知ることができます。

- サーバーを MFC に移植できます。 これは非常に簡単で、結果は通常、より小さく、より速いコードです。

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)を使用する場合は、必要なバイトオーダー変換を自分で管理する必要があります。 Windows ソケットは、"ビッグ エンディアン" のバイトオーダー モデルを標準化し、この順序と他の順序の間で変換する関数を提供します。 [CArchive](../mfc/reference/carchive-class.md)は[CSocket](../mfc/reference/csocket-class.md)と共に使用しますが、逆の (「リトル エンディアン」)`CArchive`の順序を使用しますが、バイトオーダー変換の詳細は処理します。 アプリケーションでこの標準の順序付けを使用するか、Windows ソケットのバイトオーダー変換関数を使用すると、コードの移植性を高めることができます。

MFC ソケットの理想的な使用状況は、通信の両端を自分で作成し、両端で MFC を使用する場合です。 FTP サーバーなど、非 MFC アプリケーションと通信するアプリケーションを作成する場合は、Windows ソケット変換ルーチン**ntohs**、 **ntohl**、 **htons**、**および htonl**を使用して、アーカイブ オブジェクトにデータを渡す前に、バイト スワップを自分で管理する必要があります。 MFC 以外のアプリケーションとの通信に使用されるこれらの関数の例は、この資料の後半に記載されています。

> [!NOTE]
> 通信の他方の端が MFC アプリケーションではない場合は、受信側が処理できないため、アーカイブから`CObject`派生した C++ オブジェクトのストリーミングも避ける必要があります。 Windows ソケット:[アーカイブでソケットを使用する のメモを](../mfc/windows-sockets-using-sockets-with-archives.md)参照してください。

バイト オーダーの詳細については、Windows SDK で使用できる Windows ソケットの仕様を参照してください。

## <a name="a-byte-order-conversion-example"></a>バイトオーダー変換の例

次の例は、アーカイブを使用する`CSocket`オブジェクトのシリアル化関数を示しています。 また、Windows ソケット API でバイトオーダー変換関数を使用する方法についても説明します。

この例では、ソース コードにアクセスできない非 MFC サーバー アプリケーションと通信するクライアントを作成するシナリオを示します。 このシナリオでは、非 MFC サーバーが標準のネットワーク バイト順を使用することを前提とします。 これに対し、MFC クライアント アプリケーション`CArchive`は`CSocket`オブジェクトを使用し`CArchive`、ネットワーク標準とは逆の "リトル エンディアン" バイト順を使用します。

通信を行う非 MFC サーバーに、次のようなメッセージ パケット用のプロトコルが確立されている場合を考えます。

[!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]

MFC 用語では、これは次のように表現されます。

[!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]

C++ では、**構造体**はクラスと基本的に同じものです。 構造体`Message`は、上記で宣言したメンバー関数などの`Serialize`メンバー関数を持つことができます。 メンバー`Serialize`関数は次のようになります。

[!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]

この例では、一方のエンドで非 MFC サーバー アプリケーションのバイト順と、もう一方の端の MFC クライアント アプリケーション`CArchive`で使用されるバイト順序の間に明確な不一致があるため、データのバイトオーダー変換が必要です。 この例では、Windows ソケットが提供するいくつかのバイトオーダー変換関数を示します。 次の表に、これらの関数を示します。

### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows ソケットバイトオーダー変換関数

|機能|目的|
|--------------|-------------|
|**ntohs**|ネットワークバイト順からホストバイト順(ビッグエンディアンからリトルエンディアン)に16ビットの量を変換します。|
|**ntohl**|ネットワークバイト順からホストバイト順(ビッグエンディアンからリトルエンディアン)に32ビットの量を変換します。|
|**トンズ**|ホストバイト順からネットワークバイト順(リトルエンディアンからビッグエンディアン)に16ビットの量を変換します。|
|**Htonl**|ホストバイト順からネットワークバイト順(リトルエンディアンからビッグエンディアン)に32ビットの量を変換します。|

この例のもう 1 つのポイントは、通信の反対側にあるソケット アプリケーションが非 MFC アプリケーションの場合、次のような処理を避ける必要がある点です。

`ar << pMsg;`

クラス`pMsg`から派生した C++ オブジェクトへのポインター`CObject`です。 これにより、オブジェクトに関連付けられた余分な MFC 情報が送信され、サーバーは MFC アプリケーションの場合と同様に、その情報を認識しません。

詳細については、次を参照してください。

- [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット : 予備知識](../mfc/windows-sockets-background.md)

- [Windows ソケット : ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット : データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)
