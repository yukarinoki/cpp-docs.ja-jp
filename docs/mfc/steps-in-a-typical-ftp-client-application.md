---
title: 典型的な FTP クライアント アプリケーションでの手順 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fe5a55afda9e77db6e8baddd68c09f4250071bb
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951202"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>典型的な FTP クライアント アプリケーションの作成手順
典型的な FTP クライアント アプリケーションを作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)と[CFtpConnection](../mfc/reference/cftpconnection-class.md)オブジェクト。 これらの MFC WinInet クラスによって、プロキシの種類の設定; は実際に制御しないように注意してください。IIS では。  
  
 また、これらのサポート技術情報記事を参照してください。  
  
-   方法: WinInet API を使用してプロキシを CERN ベースでの FTP (アーティクル ID: Q166961)  
  
-   例: CERN ベースのパスワードを使用して FTP 保護プロキシ (アーティクル ID: Q216214)  
  
-   インターネット サービス マネージャーがインストール済みのプロキシ サービスの表示に失敗する (アーティクル ID: Q216802)  
  
 次の表は、典型的な FTP クライアント アプリケーションで必要な手順を示します。  
  
|目標|操作を実行します。|効果|  
|---------------|----------------------|-------------|  
|FTP セッションを開始します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|WinInet を初期化し、サーバーに接続します。|  
|FTP サーバーに接続します。|使用して[CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)です。|返します、 [CFtpConnection](../mfc/reference/cftpconnection-class.md)オブジェクト。|  
|サーバー上に新しい FTP ディレクトリを変更します。|使用して[CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)です。|現在サーバー上に接続しているディレクトリを変更します。|  
|FTP ディレクトリの最初のファイルを検索します。|使用して[CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile)です。|最初のファイルを検索します。 ファイルが見つからない場合は、FALSE を返します。|  
|FTP ディレクトリの次のファイルを検索します。|使用して[CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)です。|次のファイルを検索します。 ファイルが見つからない場合は、FALSE を返します。|  
|によって検出されたファイルを開く`FindFile`または`FindNextFile`の読み取りまたは書き込み。|使用して[CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile)、によって返されるファイル名を使用して[FindFile](../mfc/reference/cftpfilefind-class.md#findfile)または[FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)です。|サーバー上の読み取りまたは書き込みのファイルを開きます。 返します、 [CInternetFile](../mfc/reference/cinternetfile-class.md)オブジェクト。|  
|読み込まれたり、ファイルに書き込みます。|使用して[細かい](../mfc/reference/cinternetfile-class.md#read)または[CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write)です。|読み取りまたは書き込みを指定した入力バッファーを使用して、バイト数。|  
|例外を処理する|使用して、 [CInternetException](../mfc/reference/cinternetexception-class.md)クラスです。|すべての一般的なインターネット例外タイプを処理します。|  
|FTP セッションを終了します。|破棄、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|開いているファイル ハンドルと接続を自動的にクリーンアップします。|  
  
## <a name="see-also"></a>関連項目  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
