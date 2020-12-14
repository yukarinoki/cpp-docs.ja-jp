---
description: '詳細情報: 典型的な FTP クライアントアプリケーションでファイルを削除する手順'
title: ファイルを削除する典型的な FTP クライアント アプリケーションの作成手順
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
ms.openlocfilehash: 0de5ba71ac127a44c964571d243997bcb49faaa0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216653"
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>ファイルを削除する典型的な FTP クライアント アプリケーションの作成手順

次の表は、ファイルを削除する典型的な FTP クライアントアプリケーションで実行できる手順を示しています。

|目標|実行する操作|エフェクト|
|---------------|----------------------|-------------|
|FTP セッションを開始します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを作成します。|WinInet を初期化し、サーバーに接続します。|
|FTP サーバーに接続します。|[CInternetSession:: GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)を使用します。|[CFtpConnection](../mfc/reference/cftpconnection-class.md)オブジェクトを返します。|
|FTP サーバーの適切なディレクトリにあることを確認してください。|[CFtpConnection:: GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory)または[CFtpConnection:: GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl)を使用します。|選択されたメンバー関数に応じて、サーバー上で現在接続しているディレクトリの名前または URL を返します。|
|サーバー上の新しい FTP ディレクトリに変更します。|[CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)を使用します。|サーバー上で現在接続しているディレクトリを変更します。|
|FTP ディレクトリ内の最初のファイルを検索します。|[CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile)を使用します。|最初のファイルを検索します。 ファイルが見つからない場合は FALSE を返します。|
|FTP ディレクトリ内の次のファイルを検索します。|[CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)を使用します。|次のファイルを検索します。 ファイルが見つからない場合は FALSE を返します。|
|またはによって検出されたファイルを削除し `FindFile` `FindNextFile` ます。|またはによって返されたファイル名を使用して、 [CFtpConnection:: Remove](../mfc/reference/cftpconnection-class.md#remove)を使用し `FindFile` `FindNextFile` ます。|読み取りまたは書き込み用にサーバー上のファイルを削除します。|
|例外を処理する|[CInternetException](../mfc/reference/cinternetexception-class.md)クラスを使用します。|すべての一般的なインターネット例外の種類を処理します。|
|FTP セッションを終了します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを破棄します。|開いているファイルハンドルと接続を自動的にクリーンアップします。|

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネットクライアントクラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet クラスを使用したインターネットクライアントアプリケーションの作成](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
