---
title: ファイルを削除する典型的な FTP クライアント アプリケーションでの手順 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb595dfdc1a73ecd068e251cec5df99d4daaab30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>ファイルを削除する典型的な FTP クライアント アプリケーションの作成手順
次の表は、ファイルを削除する典型的な FTP クライアント アプリケーションで必要な手順を示します。  
  
|目標|操作を実行します。|効果|  
|---------------|----------------------|-------------|  
|FTP セッションを開始します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|WinInet を初期化し、サーバーに接続します。|  
|FTP サーバーに接続します。|使用して[CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)です。|返します、 [CFtpConnection](../mfc/reference/cftpconnection-class.md)オブジェクト。|  
|FTP サーバー上のディレクトリ位置していることを確認します。|使用して[CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory)または[CFtpConnection::GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl)です。|名前または現在選択されているメンバー関数によって、サーバー上に接続しているディレクトリの URL を返します。|  
|サーバー上に新しい FTP ディレクトリを変更します。|使用して[CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)です。|現在サーバー上に接続しているディレクトリを変更します。|  
|FTP ディレクトリの最初のファイルを検索します。|使用して[CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile)です。|最初のファイルを検索します。 ファイルが見つからない場合は、FALSE を返します。|  
|FTP ディレクトリの次のファイルを検索します。|使用して[CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)です。|次のファイルを検索します。 ファイルが見つからない場合は、FALSE を返します。|  
|によって検出されたファイルを削除**FindFile**または`FindNextFile`です。|使用して[CFtpConnection::Remove](../mfc/reference/cftpconnection-class.md#remove)、によって返されるファイル名を使用して**FindFile**または`FindNextFile`です。|サーバー上の読み取りまたは書き込みのファイルを削除します。|  
|例外を処理する|使用して、 [CInternetException](../mfc/reference/cinternetexception-class.md)クラスです。|すべての一般的なインターネット例外タイプを処理します。|  
|FTP セッションを終了します。|破棄、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|開いているファイル ハンドルと接続を自動的にクリーンアップします。|  
  
## <a name="see-also"></a>関連項目  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
