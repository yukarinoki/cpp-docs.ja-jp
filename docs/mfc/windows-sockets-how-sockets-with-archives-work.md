---
description: '詳細については、「Windows ソケット: アーカイブを使用したソケットのしくみ」を参照してください。'
title: 'Windows ソケット : アーカイブ付きソケットの動作'
ms.date: 11/19/2018
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
ms.openlocfilehash: 19b24a9942b7405304c9037091266b4535bffbc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263544"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows ソケット : アーカイブ付きソケットの動作

この記事では、Windows ソケットを使用したデータの送受信を簡略化するために、 [CSocket](../mfc/reference/csocket-class.md) オブジェクト、 [CSocketFile](../mfc/reference/csocketfile-class.md) オブジェクト、および [CArchive](../mfc/reference/carchive-class.md) オブジェクトを組み合わせる方法について説明します。

記事「 [Windows ソケット: アーカイブを使用するソケットの例](../mfc/windows-sockets-example-of-sockets-using-archives.md) 」では、関数を示して `PacketSerialize` います。 この例の archive オブジェクトは、 `PacketSerialize` MFC の [Serialize](../mfc/reference/cobject-class.md#serialize) 関数に渡される archive オブジェクトとよく似ています。 重要な違いは、ソケットの場合、アーカイブは標準の [CFile](../mfc/reference/cfile-class.md) オブジェクト (通常はディスクファイルに関連付けられています) にではなく、オブジェクトにアタッチされることです `CSocketFile` 。 オブジェクトは、ディスクファイルに接続するのではなく、 `CSocketFile` オブジェクトに接続し `CSocket` ます。

オブジェクトは、 `CArchive` バッファーを管理します。 格納 (送信) アーカイブのバッファーがいっぱいになると、関連付けられた `CFile` オブジェクトはバッファーの内容を書き込みます。 ソケットにアタッチされているアーカイブのバッファーをフラッシュすることは、メッセージを送信することと同じです。 読み込み (受信) アーカイブのバッファーがいっぱいになると、 `CFile` バッファーが再び使用可能になるまでオブジェクトは読み取りを停止します。

クラスは `CSocketFile` から派生 `CFile` しますが、配置関数 (、、 [](../mfc/reference/cfile-class.md) `Seek` `GetLength` `SetLength` など)、ロック関数 ( `LockRange` 、)、 `UnlockRange` または `GetPosition` 関数などの CFile メンバー関数はサポートしていません。 すべての [CSocketFile](../mfc/reference/csocketfile-class.md) オブジェクトは、関連付けられているオブジェクトとの間で、またはそのオブジェクトとの間でバイトシーケンスの書き込みまたは読み取りを行う必要があり `CSocket` ます。 ファイルは関係しないため、やなどの操作は `Seek` `GetPosition` 意味がありません。 `CSocketFile` はから派生 `CFile` しているため、通常はこれらのすべてのメンバー関数を継承します。 これを回避するために、ではサポートされていない `CFile` メンバー関数がオーバーライドされ、 `CSocketFile` [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)がスローされます。

オブジェクトは、 `CSocketFile` オブジェクトのメンバー関数を呼び出して、 `CSocket` データを送受信します。

次の図は、通信の両側におけるこれらのオブジェクト間の関係を示しています。

![CArchive、CSocketFile、CSocket](../mfc/media/vc38ia1.gif "CArchive、CSocketFile、CSocket") <br/>
CArchive、CSocketFile、CSocket

このような複雑さを明確にする目的は、ソケットの詳細を自分で管理する必要があることを防ぐことです。 ソケット、ファイル、およびアーカイブを作成した後、データの送信または受信を開始するには、アーカイブに挿入するか、アーカイブからデータを抽出します。 [CArchive](../mfc/reference/carchive-class.md)、 [CSocketFile](../mfc/reference/csocketfile-class.md)、および [CSocket](../mfc/reference/csocket-class.md) は、バックグラウンドで詳細を管理します。

オブジェクトは、実際には `CSocket` 2 つの状態のオブジェクトです。非同期 (通常の状態) である場合もあれば、同期する場合もあります。 非同期状態では、ソケットは、フレームワークから非同期通知を受け取ることができます。 ただし、データの受信や送信などの操作中に、ソケットが同期されます。 これは、同期操作が完了するまで、ソケットはそれ以上非同期通知を受信しないことを意味します。 たとえば、モードを切り替えるため、次のような操作を行うことができます。

[!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]

が `CSocket` 2 つの状態のオブジェクトとして実装されていない場合は、以前の通知を処理しているときに、同じ種類のイベントに対して追加の通知を受け取ることができます。 たとえば、の処理中に通知を受け取る場合があり `OnReceive` `OnReceive` ます。 上記のコード片では、 `str` アーカイブから抽出すると再帰が生じる可能性があります。 状態を切り替えることにより、 `CSocket` 追加の通知を防ぐことで再帰を防止できます。 一般規則は通知内に通知されません。

> [!NOTE]
> は、 `CSocketFile` オブジェクトなしで (制限された) ファイルとして使用することもでき `CArchive` ます。 既定では、 `CSocketFile` コンストラクターの *bArchiveCompatible* パラメーターは **TRUE** です。 これは、ファイルオブジェクトがアーカイブで使用されることを指定します。 アーカイブのないファイルオブジェクトを使用するには、 *bArchiveCompatible* パラメーターに **FALSE** を渡します。

"アーカイブ互換" モードでは、 `CSocketFile` オブジェクトを使用すると、パフォーマンスが向上し、"デッドロック" の危険性が軽減されます。 デッドロックは、送信側と受信側の両方のソケットが互いに待機しているか、共通のリソースを待機しているときに発生します。 このような状況は、オブジェクトがオブジェクトを使用して動作する場合に発生する可能性があり `CArchive` `CSocketFile` `CFile` ます。 では `CFile` 、要求されたバイト数よりも多くのバイトを受信した場合、ファイルの終わりに達したと見なすことができます。 `CSocketFile`ただし、では、データはメッセージベースであり、バッファーには複数のメッセージを含めることができます。したがって、受信したバイト数よりも少なくともファイルの終端を示すことはできません。 この場合、アプリケーションはと同様にブロックしません `CFile` 。バッファーが空になるまで、バッファーからのメッセージの読み取りを続行できます。 の [Isbufferempty](../mfc/reference/carchive-class.md#isbufferempty) 関数 `CArchive` は、このような場合にアーカイブのバッファーの状態を監視するのに便利です。

詳細については、「 [Windows ソケット: アーカイブでのソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[CObject:: Serialize](../mfc/reference/cobject-class.md#serialize)
