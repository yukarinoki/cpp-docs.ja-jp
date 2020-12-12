---
description: '詳細については、「Windows ソケット: 文字列の変換」を参照してください。'
title: 'Windows ソケット : 文字列の変換'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: fe8607647192fadc7f0d5d32d7716c222ff9206f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118629"
---
# <a name="windows-sockets-converting-strings"></a>Windows ソケット : 文字列の変換

この記事と2つの記事では、Windows ソケットプログラミングにおけるいくつかの問題について説明します。 この記事では、文字列の変換について説明します。 その他の問題については、 [「Windows ソケット: ブロッキング](../mfc/windows-sockets-blocking.md) と [Windows ソケット: バイトの順序付け](../mfc/windows-sockets-byte-ordering.md)」で説明されています。

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)クラスを使用する場合、またはクラスを派生させる場合は、これらの問題を自分で管理する必要があります。 またはを使用する場合は、 [MFC でそれらを管理](../mfc/reference/csocket-class.md)します。

## <a name="converting-strings"></a>変換 (文字列を)

Unicode またはマルチバイト文字セット (MBCS) などのさまざまなワイド文字形式で格納されている文字列を使用するアプリケーション間で通信する場合、または ANSI 文字列を使用するアプリケーションと ANSI 文字列を使用するアプリケーション間で通信する場合は、で変換を管理する必要があり `CAsyncSocket` ます。 `CArchive`オブジェクトで使用されるオブジェクトは、 `CSocket` [CString](../atl-mfc-shared/reference/cstringt-class.md)クラスの機能を通じてこの変換を管理します。 詳細については、Windows SDK にある Windows ソケット仕様を参照してください。

詳細については、次を参照してください。

- [Windows ソケット: CAsyncSocket クラスの使用](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows ソケット: アーカイブでのソケットの使用](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows ソケット:背景](../mfc/windows-sockets-background.md)

- [Windows ソケット: ストリームソケット](../mfc/windows-sockets-stream-sockets.md)

- [Windows ソケット: データグラムソケット](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)
