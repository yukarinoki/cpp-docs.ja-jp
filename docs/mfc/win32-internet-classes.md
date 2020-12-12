---
description: '詳細情報: Win32 インターネットクラス'
title: Win32 インターネット クラス
ms.date: 09/12/2018
f1_keywords:
- vc.classes.win32
helpviewer_keywords:
- Internet classes [MFC]
- WinInet classes [MFC], classes
- Win32 [MFC], Internet classes
- Windows API [MFC], Internet classes
ms.assetid: b49601d5-3025-4068-9408-316b54ee4375
ms.openlocfilehash: 8b6acad5f867444c33ed86cb7e70f4f1eec42df0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197479"
---
# <a name="win32-internet-classes"></a>Win32 インターネット クラス

MFC では、インターネットプログラミングを容易にするために、Win32 インターネット (WinInet) と ActiveX テクノロジをラップしています。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

[CInternetSession](../mfc/reference/cinternetsession-class.md)<br/>
1つのインターネットセッションまたは複数の同時インターネットセッションを作成して初期化します。また、必要に応じて、プロキシサーバーへの接続について説明します。

[CInternetConnection](../mfc/reference/cinternetconnection-class.md)<br/>
インターネット サーバーへの接続を管理します。

[CInternetFile](../mfc/reference/cinternetfile-class.md)<br/>
このクラスとその派生クラスは、インターネットプロトコルを使用するリモートシステム上のファイルへのアクセスを許可します。

[CHttpConnection](../mfc/reference/chttpconnection-class.md)<br/>
HTTP サーバーへの接続を管理します。

[CHttpFile](../mfc/reference/chttpfile-class.md)<br/>
HTTP サーバー上のファイルの検索と読み取りを行う機能を提供します。

[CGopherFile](../mfc/reference/cgopherfile-class.md)<br/>
gopher サーバー上のファイルを検索し、読み込む機能が用意されています。

[CFtpConnection](../mfc/reference/cftpconnection-class.md)<br/>
FTP サーバーへの接続を管理します。

[CGopherConnection](../mfc/reference/cgopherconnection-class.md)<br/>
Gopher サーバーへの接続を管理します。

[CFileFind](../mfc/reference/cfilefind-class.md)<br/>
ローカルファイルとインターネットファイルの検索を実行します。

[CFtpFileFind](../mfc/reference/cftpfilefind-class.md)<br/>
FTP サーバーのインターネット ファイル検索を支援します。

[CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)<br/>
gopher サーバーのインターネット ファイル検索を支援します。

[CGopherLocator](../mfc/reference/cgopherlocator-class.md)<br/>
gopher ロケーターを gopher サーバーから取得し、ロケーター種別を判断し、`CGopherFileFind` 用に準備します。

[CInternetException](../mfc/reference/cinternetexception-class.md)<br/>
インターネット操作に関する例外条件を表します。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)
