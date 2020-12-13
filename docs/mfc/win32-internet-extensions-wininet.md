---
description: Win32 インターネット拡張機能についての詳細情報 (WinInet)
title: Win32 インターネット拡張機能 (WinInet)
ms.date: 11/04/2016
helpviewer_keywords:
- Internet applications [MFC], Win32 Internet Extensions
- Internet client applications [MFC], about Internet client applications
- client applications [MFC], Win32 Internet
- WinInet classes [MFC], about WinInet classes
ms.assetid: f8c80f0b-ce14-4f0d-a3cf-4f7d8c5cca59
ms.openlocfilehash: 52f04be25e16aa6c1c0546e68a7a702335ae5a09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342596"
---
# <a name="win32-internet-extensions-wininet"></a>Win32 インターネット拡張機能 (WinInet)

インターネットクライアントアプリケーションは、gopher、FTP、HTTP などのインターネットプロトコルを使用してネットワークデータソース (サーバー) から情報にアクセスするプログラムです。 たとえば、インターネットクライアントアプリケーションは、サーバーにアクセスして、気象地図、株価、新聞ヘッドラインなどのデータを取得する場合があります。 インターネットクライアントは、外部ネットワーク (インターネット) または内部ネットワーク (イントラネットとも呼ばれます) を介してサーバーにアクセスできます。

MFC には、インターネットクライアントアプリケーションを作成するための Win32 インターネット拡張機能 (WinInet) が含まれています。 MFC では、これらのインターネット拡張機能を、標準的で使いやすいクラスのセットとしてカプセル化しています。 WinInet クライアントアプリケーションを作成するには、直接 Win32 関数を呼び出すか、MFC WinInet クラスを使用します。

Microsoft Win32 インターネット機能 (WinInet) を使用すると、インターネットを任意のアプリケーションの不可欠な部分にすることができます。 WININET.DLL に含まれる新しい関数は、HTTP (ハイパーテキスト転送プロトコル)、FTP (ファイル転送プロトコル)、および gopher を使用したインターネットへのアクセスを簡略化します。

次のトピックでは、インターネットクライアントアプリケーションを作成するプロセスについて説明します。

- [WinInet を使用してインターネットクライアントアプリケーションを簡単に作成する方法](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

- [MFC を使用してインターネットクライアントアプリケーションを簡単に作成する方法](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)

- [インターネットクライアントアプリケーションを作成するための MFC クラス](../mfc/mfc-classes-for-creating-internet-client-applications.md)

- [インターネットクライアントクラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)

- [MFC WinInet クラスを使用したインターネットクライアントアプリケーションの作成](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

次のトピックでは、一般的な WinInet タスクを実行する手順について説明します。

- [一般的なインターネットクライアントアプリケーションの手順](../mfc/steps-in-a-typical-internet-client-application.md)

- [一般的な FTP クライアントアプリケーションの手順](../mfc/steps-in-a-typical-ftp-client-application.md)

- [一般的な FTP クライアントアプリケーションでファイルを削除する手順](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)

- [一般的な Gopher クライアントアプリケーションの手順](../mfc/steps-in-a-typical-gopher-client-application.md)

- [一般的な HTTP クライアントアプリケーションの手順](../mfc/steps-in-a-typical-http-client-application.md)

## <a name="see-also"></a>関連項目

[MFC インターネットプログラミングの基礎](../mfc/mfc-internet-programming-basics.md)<br/>
[WinInet の基礎](../mfc/wininet-basics.md)
