---
title: 'Windows ソケット: アーカイブ付きソケットの動作 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c03ae586e346be2ba1e7c71475b69318ded0dd18
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385217"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows ソケット : アーカイブ付きソケットの動作
この記事で説明する方法、 [CSocket](../mfc/reference/csocket-class.md)オブジェクト、 [CSocketFile](../mfc/reference/csocketfile-class.md)オブジェクト、および[CArchive](../mfc/reference/carchive-class.md)オブジェクトが結合され、Windows を使用してデータの送受信を簡略化ソケットします。  
  
 アーティクル[Windows ソケット: 例のソケットを使用してアーカイブ](../mfc/windows-sockets-example-of-sockets-using-archives.md)を表示、 **PacketSerialize**関数。 アーカイブ オブジェクトで、 **PacketSerialize**例は、MFC に渡されるアーカイブ オブジェクトと同様、動作[Serialize](../mfc/reference/cobject-class.md#serialize)関数。 重要な違いは、ソケットの場合、アーカイブが接続されている標準[CFile](../mfc/reference/cfile-class.md)オブジェクト (通常は、ディスク ファイルに関連付けられている) には、`CSocketFile`オブジェクト。 ディスク ファイルへの接続ではなく、`CSocketFile`オブジェクトの接続先、`CSocket`オブジェクト。  
  
 A`CArchive`オブジェクトは、バッファーを管理します。 格納 (送信) アーカイブのバッファーがいっぱいのとき、関連付けられている`CFile`オブジェクトが、バッファーの内容を書き込みます。 ソケットにアタッチされているアーカイブのバッファーのフラッシュは、メッセージを送信するのと同じです。 読み込み (受信) アーカイブのバッファーがいっぱいになると、ときに、`CFile`バッファーが再び使用可能になるまで、オブジェクトが読み取りを停止します。  
  
 クラス`CSocketFile`から派生した`CFile`をサポートしていませんが、 [CFile](../mfc/reference/cfile-class.md)ポジショニング関数などのメンバー関数 (`Seek`、 `GetLength`、`SetLength`など)、(ロック関数`LockRange`、 `UnlockRange`)、または`GetPosition`関数。 すべての[CSocketFile](../mfc/reference/csocketfile-class.md)オブジェクトを実行する必要がありますは書き込みまたはとの間、関連付けられているバイトのシーケンスを読み取り`CSocket`オブジェクト。 ファイルが関与しないためなどの操作`Seek`と`GetPosition`をなしません。 `CSocketFile` 派生した`CFile`ので、すべてこれらのメンバー関数の継承は通常、します。 これを防ぐため、サポートされていない`CFile`でメンバー関数がオーバーライドされて`CSocketFile`をスローする、[行わない](../mfc/reference/cnotsupportedexception-class.md)です。  
  
 `CSocketFile`オブジェクトは、メンバーの関数を呼び出してその`CSocket`データ送信または受信するオブジェクト。  
  
 次の図は、通信の両側でこれらのオブジェクト間の関係を示します。  
  
 ![CArchive、CSocketFile、CSocket](../mfc/media/vc38ia1.gif "vc38ia1")  
CArchive、CSocketFile、CSocket  
  
 この見かけ上の複雑さの目的は、自分でソケットの詳細を管理するための必要性から保護します。 ソケット、ファイル、およびアーカイブを作成してアーカイブを挿入またはアーカイブから抽出して送信または受信側のデータを開始します。 [CArchive](../mfc/reference/carchive-class.md)、 [CSocketFile](../mfc/reference/csocketfile-class.md)、および[CSocket](../mfc/reference/csocket-class.md)バック グラウンドで詳細を管理します。  
  
 A`CSocket`オブジェクトは、実際には 2 つの状態オブジェクト: 非同期場合があります (通常の状態) と同期します。 非同期状態、ソケットは、フレームワークから非同期の通知を受信できます。 ただし、受信データを送信するなどの操作中に、ソケット同期状態になります。 これは、同期操作が完了するまで、ソケットはそれ以上非同期通知を受信することを意味します。 モードを切り替えることので行うことができます、たとえば、次のような。  
  
 [!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]  
  
 場合`CSocket`実装されていなかったとして、2 つの状態オブジェクトを前の通知を処理していたときに、同じ種類のイベントの追加の通知を受信する場合があります。 たとえば、取得する可能性があります、`OnReceive`通知の処理中に、`OnReceive`です。 上記のコード片で抽出`str`アーカイブから再帰になる可能性があります。 状態を切り替えることによって`CSocket`追加の通知の防止、再帰を防止します。 一般的な規則には、通知内での通知はありません。  
  
> [!NOTE]
>  A`CSocketFile`なし (制限あり) ファイルとしても使用できます、`CArchive`オブジェクト。 既定では、`CSocketFile`コンス トラクターの`bArchiveCompatible`パラメーターは**TRUE**です。 これは、アーカイブで使用するのファイル オブジェクトであることを指定します。 使用する、アーカイブせずに、ファイル オブジェクトを渡します**FALSE**で、`bArchiveCompatible`パラメーター。  
  
 その「アーカイブ互換性のある」モードで、`CSocketFile`オブジェクトは、パフォーマンスを向上させると、「デッドロック」の危険性を軽減 デッドロックは、送信側と受信側の両方のソケットが、互いを待機してまたは一般的なリソースを待機しているときに発生します。 場合に、このような状況が発生する可能性があります、`CArchive`と協力して、オブジェクト、`CSocketFile`は方法、`CFile`オブジェクト。 `CFile`アーカイブを受信した場合、要求したバイト数、ファイルの末尾に達していると見なすことできます。 `CSocketFile`、ただし、データはメッセージ ベース以外の場合は、バッファーは、複数のメッセージを含めることができます、ように受信要求バイト数より少ないファイルの終わりを意味しません。 アプリケーションとそれほど、ここではブロックしません`CFile`バッファーが空になるまで、バッファーからメッセージの読み取りを続行するとします。 [時](../mfc/reference/carchive-class.md#isbufferempty)関数`CArchive`はこのような場合、アーカイブのバッファーの状態を監視するために便利です。  
  
 詳細については、次を参照してください[Windows ソケット: アーカイブ付きソケットの使用。](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [Cobject::serialize](../mfc/reference/cobject-class.md#serialize)

