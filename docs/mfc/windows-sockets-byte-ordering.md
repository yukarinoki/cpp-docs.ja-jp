---
title: 'Windows ソケット : バイトの順序付け'
ms.date: 11/04/2016
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
ms.openlocfilehash: f00936f3de07df8c1e4d9df1c678b2cfd5f3e3ad
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226803"
---
# <a name="windows-sockets-byte-ordering"></a>Windows ソケット : バイトの順序付け

この記事と2つの記事では、Windows ソケットプログラミングにおけるいくつかの問題について説明します。 この記事では、バイトの順序付けについて説明します。 その他の問題については、「 [Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md)と[Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)」の記事で説明されています。

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)クラスを使用する場合、またはクラスを派生させる場合は、これらの問題を自分で管理する必要があります。 またはを使用する場合は、 [MFC でそれらを管理](../mfc/reference/csocket-class.md)します。

## <a name="byte-ordering"></a>バイトの順序付け

異なるコンピューターアーキテクチャでは、異なるバイトオーダーを使用してデータを格納する場合があります。 たとえば、Intel ベースのコンピューターでは、Macintosh (Motorola) コンピューターの逆の順序でデータが保存されます。 "リトルエンディアン" と呼ばれる Intel のバイトオーダーも、ネットワークの標準の "ビッグエンディアン" の順序と逆になります。 次の表では、これらの用語について説明します。

### <a name="big--and-little-endian-byte-ordering"></a>ビッグエンディアンのバイト順

|バイトの順序付け|意味|
|-------------------|-------------|
|ビッグエンディアン|最上位バイトは単語の左端にあります。|
|リトルエンディアン|最上位バイトは単語の右端にあります。|

通常、ネットワーク経由で送受信されるデータのバイトオーダーの変換について心配する必要はありませんが、バイトオーダーを変換する必要がある場合があります。

## <a name="when-you-must-convert-byte-orders"></a>バイトオーダーを変換する必要がある場合

次の状況では、バイトオーダーを変換する必要があります。

- 別のコンピューターに送信するデータではなく、ネットワークによって解釈される必要がある情報を渡しています。 たとえば、ネットワークが認識する必要があるポートとアドレスを渡すことができます。

- 通信中のサーバーアプリケーションは、MFC アプリケーションではありません (ソースコードはありません)。 2台のコンピューターが同じバイト順序を共有していない場合、はバイト順変換を呼び出します。

## <a name="when-you-do-not-have-to-convert-byte-orders"></a>バイトオーダーを変換する必要がない場合

次の状況では、バイトオーダーの変換作業を回避できます。

- 両端のマシンは、バイトをスワップしないことに同意し、両方のコンピューターが同じバイト順を使用します。

- 通信しているサーバーは MFC アプリケーションです。

- 通信しているサーバーのソースコードがあるため、バイトオーダーを変換する必要があるかどうかを明示的に判断できます。

- サーバーを MFC に移植できます。 これは非常に簡単です。通常、結果はより小さく、より高速なコードです。

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)を使用する場合は、必要なバイト順変換を自分で管理する必要があります。 Windows ソケットは、"ビッグエンディアン" バイト順モデルを標準化し、この順序と他の順序の間で変換を行う関数を提供します。 ただし、 [CSocket](../mfc/reference/csocket-class.md)で使用する[CArchive](../mfc/reference/carchive-class.md)は、逆の ("リトルエンディアン") 順序を使用し `CArchive` ますが、バイト順変換の詳細を処理します。 アプリケーションでこの標準の順序付けを使用するか、Windows ソケットのバイト順変換関数を使用することにより、コードの移植性を高めることができます。

MFC ソケットの理想的な使用状況は、通信の両端を自分で作成し、両端で MFC を使用する場合です。 FTP サーバーなど、MFC 以外のアプリケーションと通信するアプリケーションを作成する場合は、Windows Sockets 変換ルーチン**ntohs**、 **ntohl**、 **htons**、および**htonl**を使用して、アーカイブオブジェクトにデータを渡す前に、バイトスワップを自分で管理する必要があります。 MFC 以外のアプリケーションとの通信で使用されるこれらの関数の例については、この記事の後半で説明します。

> [!NOTE]
> 通信のもう一方の側が MFC アプリケーションでない場合は、から派生した C++ オブジェクトを、受信側がそれを処理できないのでアーカイブに保存しないようにする必要もあり `CObject` ます。 「 [Windows ソケット: アーカイブでのソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)」の注を参照してください。

バイトオーダーの詳細については、Windows SDK で使用可能な Windows ソケット仕様を参照してください。

## <a name="a-byte-order-conversion-example"></a>バイト順変換の例

次の例は、アーカイブを使用するオブジェクトのシリアル化関数を示して `CSocket` います。 また、Windows Sockets API でバイト順変換関数を使用する方法についても説明します。

この例は、ソースコードにアクセスできない非 MFC サーバーアプリケーションと通信するクライアントを作成するシナリオを示しています。 このシナリオでは、非 MFC サーバーが標準的なネットワークのバイト順を使用することを前提としています。 これに対し、MFC クライアントアプリケーションでは、オブジェクトを使用してオブジェクトを使用 `CArchive` `CSocket` し、ネットワーク標準とは逆の `CArchive` "リトルエンディアン" バイト順を使用します。

通信を計画している非 MFC サーバーが、次のようなメッセージパケットに対して確立されたプロトコルを持っているとします。

[!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]

MFC の用語では、これは次のように表されます。

[!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]

C++ では、は基本的には **`struct`** クラスと同じです。 構造体には、 `Message` 上で宣言されたメンバー関数などのメンバー関数を含めることができ `Serialize` ます。 `Serialize`メンバー関数は次のようになります。

[!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]

この例では、データのバイト順変換に対してを呼び出しています。これは、一方の端にある非 MFC サーバーアプリケーションのバイト順と、もう一方の側の `CArchive` mfc クライアントアプリケーションで使用されるが明確に一致しないためです。 この例は、Windows ソケットが提供するバイト順変換関数のいくつかを示しています。 次の表では、これらの関数について説明します。

### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows ソケットのバイト順変換関数

|機能|目的|
|--------------|-------------|
|**ntohs**|16ビットの数量をネットワークのバイト順からホストのバイト順 (ビッグエンディアンからリトルエンディアン) に変換します。|
|**ntohl**|32ビットの数量をネットワークのバイト順からホストのバイト順 (ビッグエンディアンからリトルエンディアン) に変換します。|
|**Htons**|16ビットの数量をホストのバイト順からネットワークのバイト順 (リトルエンディアンからビッグエンディアン) に変換します。|
|**Htonl**|32ビットの数量をホストのバイト順からネットワークのバイト順 (リトルエンディアンからビッグエンディアン) に変換します。|

この例のもう1つの点は、通信の相手側のソケットアプリケーションが非 MFC アプリケーションである場合、次のような処理を避ける必要があることです。

`ar << pMsg;`

ここ `pMsg` で、はクラスから派生した C++ オブジェクトへのポインターです `CObject` 。 これにより、オブジェクトに関連付けられている追加の MFC 情報が送信されます。これは、MFC アプリケーションの場合と同様に、サーバーでは認識されません。

詳細については、次を参照してください。

- [Windows ソケット: CAsyncSocket クラスの使用](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット:背景](../mfc/windows-sockets-background.md)

- [Windows ソケット: ストリームソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット: データグラムソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)
