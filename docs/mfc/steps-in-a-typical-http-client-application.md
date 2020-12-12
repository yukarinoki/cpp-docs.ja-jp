---
description: '詳細情報: 一般的な HTTP クライアントアプリケーションのステップ'
title: 典型的な HTTP クライアント アプリケーションの作成手順
ms.date: 11/04/2016
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
ms.openlocfilehash: 0f08ca7629c389df67b579b8c20acceeb16b0cd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216601"
---
# <a name="steps-in-a-typical-http-client-application"></a>典型的な HTTP クライアント アプリケーションの作成手順

次の表は、一般的な HTTP クライアントアプリケーションで実行できる手順を示しています。

|目標|実行する操作|エフェクト|
|---------------|----------------------|-------------|
|HTTP セッションを開始します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを作成します。|WinInet を初期化し、サーバーに接続します。|
|HTTP サーバーに接続します。|[CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection)を使用します。|[CHttpConnection](../mfc/reference/chttpconnection-class.md)オブジェクトを返します。|
|HTTP 要求を開きます。|[CHttpConnection:: OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest)を使用します。|[CHttpFile](../mfc/reference/chttpfile-class.md)オブジェクトを返します。|
|HTTP 要求を送信します。|[CHttpFile:: AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders)と[CHttpFile:: sendrequest](../mfc/reference/chttpfile-class.md#sendrequest)を使用します。|ファイルを検索します。 ファイルが見つからない場合は FALSE を返します。|
|ファイルから読み取ります。|[CHttpFile](../mfc/reference/chttpfile-class.md)を使用します。|指定したバッファーを使用して、指定したバイト数を読み取ります。|
|例外を処理する|[CInternetException](../mfc/reference/cinternetexception-class.md)クラスを使用します。|すべての一般的なインターネット例外の種類を処理します。|
|HTTP セッションを終了します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを破棄します。|開いているファイルハンドルと接続を自動的にクリーンアップします。|

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネットクライアントクラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet クラスを使用したインターネットクライアントアプリケーションの作成](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
