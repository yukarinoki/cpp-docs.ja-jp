---
title: MFC を使ってインターネット クライアント アプリケーションを簡単に作成する方法
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
ms.openlocfilehash: 71b72a3079cd0d0c87289c1813c09a24d9f75c89
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618556"
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>MFC を使ってインターネット クライアント アプリケーションを簡単に作成する方法

Microsoft Foundation Classes は、MFC プログラマになじみのあるコンテキストを提供する方法で、Win32 Internet Extension (WinInet) 関数をカプセル化します。 MFC には、 [CStdioFile](reference/cstdiofile-class.md)クラスから派生した3つのインターネットファイルクラス ([CInternetFile](reference/cinternetfile-class.md)、 [CHttpFile](reference/chttpfile-class.md)、および[CGopherFile](reference/cgopherfile-class.md)) が用意されています。 これらのクラスは、ローカルファイルに使用されているプログラマになじみのあるインターネットデータの取得と操作を行い `CStdioFile` ますが、これらのクラスを使用すると、ローカルファイルとインターネットファイルを一貫性のある透過的な方法で処理できます。

MFC WinInet クラスは、 `CStdioFile` インターネット経由で転送されるデータと同じ機能を提供します。 これらのクラスは、HTTP、FTP、gopher のインターネットプロトコルを高レベルのアプリケーションプログラミングインターフェイスに抽象化し、アプリケーションをインターネット対応にするための高速で簡単なパスを提供します。 たとえば、FTP サーバーへの接続には低レベルでいくつかの手順が必要ですが、MFC 開発者は、を1回呼び出してその接続を作成するだけで済み `CInternetSession::GetFTPConnection` ます。

また、MFC WinInet クラスには次のような利点があります。

- バッファーされる i/o

- データのタイプセーフハンドル

- 多くの関数の既定のパラメーター

- 一般的なインターネットエラーの例外処理

- 開いているハンドルと接続の自動クリーンアップ

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](win32-internet-extensions-wininet.md)<br/>
[WinInet を使ってインターネット クライアント アプリケーションを簡単に作成する方法](how-wininet-makes-it-easier-to-create-internet-client-applications.md)
