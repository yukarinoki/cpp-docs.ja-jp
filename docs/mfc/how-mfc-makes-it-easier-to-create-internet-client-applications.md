---
title: MFC を使ってインターネット クライアント アプリケーションを簡単に作成する方法
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
ms.openlocfilehash: b288db54a020b0074766ee69debdb9f397d3bd03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573438"
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>MFC を使ってインターネット クライアント アプリケーションを簡単に作成する方法

Microsoft Foundation Classes は、MFC のプログラマにとって使い慣れたコンテキストを提供する方法で Win32 インターネット拡張機能 (WinInet) 機能をカプセル化します。 MFC には、インターネット ファイルの 3 つのクラスが用意されています ([CInternetFile](../mfc/reference/cinternetfile-class.md)、 [CHttpFile](../mfc/reference/chttpfile-class.md)、および[CGopherFile](../mfc/reference/cgopherfile-class.md)) から派生した、 [CStdioFile](../mfc/reference/cstdiofile-class.md)クラス. だけでなくはこれらのクラスを取得して、インターネットのデータの操作を使用していたプログラマになじみ`CStdioFile`ローカル ファイルとインターネットのファイルを処理、一貫性があり、透過的な方法で、ローカル ファイル、これらのクラス。

MFC WinInet クラスと同じ機能を提供する`CStdioFile`インターネット経由で転送されるデータ。 これらのクラスは、高レベルのアプリケーション プログラミング インターフェイス、インターネット対応のアプリケーションへの高速で簡単なパスを提供することに、HTTP、FTP、および gopher インターネット プロトコルを抽象化します。 たとえば、低レベルは、いくつかの手順が必要に FTP サーバーに接続する、MFC 開発者としてのみする必要しますが、ありますに 1 回の呼び出しを行う`CInternetSession::GetFTPConnection`その接続を作成します。

さらに、MFC WinInet クラスは、次の利点を提供します。

- バッファー内の I/O

- タイプ セーフは、データを処理します。

- 多くの関数の既定のパラメーター

- インターネットの一般的なエラーの例外処理

- 開いているハンドルと接続の自動クリーンアップ

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[WinInet を使ってインターネット クライアント アプリケーションを簡単に作成する方法](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

