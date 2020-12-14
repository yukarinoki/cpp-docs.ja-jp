---
description: 詳細については、一般的な FTP クライアントアプリケーションでの手順に関するページを参照してください。
title: 典型的な FTP クライアント アプリケーションの作成手順
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
ms.openlocfilehash: caac613adf3ad886c4b36ae567a3b8c5c928ee10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216640"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>典型的な FTP クライアント アプリケーションの作成手順

一般的な FTP クライアントアプリケーションは、 [CInternetSession](../mfc/reference/cinternetsession-class.md) と [CFtpConnection](../mfc/reference/cftpconnection-class.md) オブジェクトを作成します。 これらの MFC WinInet クラスは、実際にはプロキシ型の設定を制御していないことに注意してください。IIS では、

次の表は、一般的な FTP クライアントアプリケーションで実行できる手順を示しています。

|目標|実行する操作|エフェクト|
|---------------|----------------------|-------------|
|FTP セッションを開始します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを作成します。|WinInet を初期化し、サーバーに接続します。|
|FTP サーバーに接続します。|[CInternetSession:: GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)を使用します。|[CFtpConnection](../mfc/reference/cftpconnection-class.md)オブジェクトを返します。|
|サーバー上の新しい FTP ディレクトリに変更します。|[CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)を使用します。|サーバー上で現在接続しているディレクトリを変更します。|
|FTP ディレクトリ内の最初のファイルを検索します。|[CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile)を使用します。|最初のファイルを検索します。 ファイルが見つからない場合は FALSE を返します。|
|FTP ディレクトリ内の次のファイルを検索します。|[CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)を使用します。|次のファイルを検索します。 ファイルが見つからない場合は FALSE を返します。|
|`FindFile`読み取りまたは書き込みのために、またはによって検出されたファイルを開き `FindNextFile` ます。|[FindFile](../mfc/reference/cftpfilefind-class.md#findfile)または[FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)によって返されたファイル名を使用して、 [CFtpConnection:: OpenFile](../mfc/reference/cftpconnection-class.md#openfile)を使用します。|読み取りまたは書き込みのために、サーバー上でファイルを開きます。 [CInternetFile](../mfc/reference/cinternetfile-class.md)オブジェクトを返します。|
|ファイルの読み取りまたは書き込みを行います。|[CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read)または[CInternetFile:: Write](../mfc/reference/cinternetfile-class.md#write)を使用します。|指定したバッファーを使用して、指定したバイト数を読み取りまたは書き込みます。|
|例外を処理する|[CInternetException](../mfc/reference/cinternetexception-class.md)クラスを使用します。|すべての一般的なインターネット例外の種類を処理します。|
|FTP セッションを終了します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを破棄します。|開いているファイルハンドルと接続を自動的にクリーンアップします。|

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネットクライアントクラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet クラスを使用したインターネットクライアントアプリケーションの作成](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
