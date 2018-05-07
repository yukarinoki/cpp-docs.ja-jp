---
title: MFC における Windows ソケット |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84fc25ab6515b22fa647b3cc32833c791b59f2b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-in-mfc"></a>MFC における Windows ソケット
> [!NOTE]
>  MFC Windows ソケット 1 のサポートはサポートしていません[Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673)です。 まず Windows Sockets 2 は付属の Windows 98、Windows 2000 に付属するバージョンになります。  
  
 MFC では、次の 2 つの MFC クラスに組み込まれた Windows ソケットを使用するネットワーク通信プログラムを記述するための 2 つのモデルを提供します。 これらのモデルについて説明し、詳細をさらに MFC ソケットのサポートします。 「ソケット」は、通信エンドポイントです。 アプリケーション通信に使用する他の Windows ソケット アプリケーションでネットワーク経由でのオブジェクト。  
  
 Windows ソケットの場合、そのソケットの概念の説明については、次を参照してください。 [Windows ソケット: バック グラウンド](../mfc/windows-sockets-background.md)です。  
  
##  <a name="_core_sockets_programming_models"></a> ソケット プログラミング モデル  
 次のクラスでは、次の 2 つの MFC Windows ソケット プログラミング モデルがサポートされています。  
  
-   `CAsyncSocket`  
  
     このクラスは、Windows ソケット API をカプセル化します。 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)ネットワーク プログラミングを把握し、ソケット API に直接プログラミングの柔軟性もしますが、コールバック関数の利便性ネットワーク イベントの通知するプログラマにとってはします。 C++ で使用するためのフォームのオブジェクト指向のソケットをパッケージ化、以外のみ追加抽象化によって、このクラスを提供しますが特定ソケットに関連する Windows メッセージに変換コールバック。 詳細については、次を参照してください。 [Windows ソケット: ソケット通知](../mfc/windows-sockets-socket-notifications.md)です。  
  
-   `CSocket`  
  
     このクラスから派生`CAsyncSocket`、を通じて MFC ソケットの操作を高いレベルの抽象化を提供[CArchive](../mfc/reference/carchive-class.md)オブジェクト。 アーカイブを使用して、ソケットを使用すると、大幅にするには、MFC のファイルのシリアル化のプロトコルを使用するようになります。 これによりより使いやすく、`CAsyncSocket`モデル。 [CSocket](../mfc/reference/csocket-class.md)から多くのメンバー関数を継承`CAsyncSocket`Windows ソケット Api をカプセル化する。 これらの関数の一部を使用し、ソケット プログラミングの一般的にを理解する必要がです。 しかし、`CSocket`生 API またはクラスのいずれかを使用して自分で行う必要があります、通信の多くの側面を管理する`CAsyncSocket`です。 最も重要なは、 `CSocket` (バック グラウンド処理の Windows メッセージ) を使用してブロックを提供の同期の動作に不可欠である`CArchive`です。  
  
 作成と使用`CSocket`と`CAsyncSocket`オブジェクトについては、「 [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)と[Windows ソケット: を使用してクラス CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)です。  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows Sockets Dll  
 Microsoft Windows オペレーティング システムでは、Windows ソケットのダイナミック リンク ライブラリ (DLL) を指定します。 Visual C では、適切なヘッダー ファイルとライブラリと、Windows ソケット仕様を提供します。  
  
 Windows ソケットの詳細についてを参照してください。  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: 動作シーケンス](../mfc/windows-sockets-sequence-of-operations.md)  
  
-   [Windows ソケット: アーカイブを使用するソケットの例](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの動作](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: ソケット クラスからの派生](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows ソケット: ソケット通知](../mfc/windows-sockets-socket-notifications.md)  
  
-   [Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md)  
  
-   [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows ソケット: 文字列の変換](../mfc/windows-sockets-converting-strings.md)  
  
-   [Windows ソケット: ポートとソケット アドレス](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## <a name="see-also"></a>関連項目  
 [Windows ソケット](../mfc/windows-sockets.md)

