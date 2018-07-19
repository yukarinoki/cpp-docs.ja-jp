---
title: 'Windows ソケット: 文字列の変換 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bad57be68ce716cddf2ce44f12e94c545a7bbfd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383761"
---
# <a name="windows-sockets-converting-strings"></a>Windows ソケット : 文字列の変換
この記事の内容と 2 部構成の記事は、Windows ソケット プログラミングのいくつかの問題を説明します。 この記事では、文字列の変換について説明します。 その他の問題については、「 [Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md)と[Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)です。  
  
 使用するか、またはクラスから派生させる場合[CAsyncSocket](../mfc/reference/casyncsocket-class.md)、これらの問題を管理する必要があります。 使用するか、またはクラスから派生させる場合[CSocket](../mfc/reference/csocket-class.md)MFC では、それらを管理します。  
  
## <a name="converting-strings"></a>文字列を変換します。  
 Unicode とマルチバイト文字セット (MBCS) など、さまざまなワイド文字形式で格納されている文字列を使用するアプリケーション間やこれらのいずれかと ANSI 文字の文字列を使用してアプリケーションを通信する場合は、変換を管理する必要があります。自分で`CAsyncSocket`です。 `CArchive`で使用されるオブジェクト、`CSocket`オブジェクトはこの変換を行う機能によってクラスの管理[CString](../atl-mfc-shared/reference/cstringt-class.md)です。 詳細については、Windows SDK には、Windows ソケット仕様を参照してください。  
  
 詳細については次を参照してください:  
  
-   [Windows ソケット: CAsyncSocket クラスの使い方](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows ソケット: アーカイブ付きソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows ソケット: 予備知識](../mfc/windows-sockets-background.md)  
  
-   [Windows ソケット: ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows ソケット: データグラム ソケット](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)

