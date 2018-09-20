---
title: 一般的な HTTP クライアント アプリケーションでのステップ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d6abb44aa9c4a59c23d8dbe8d957a32dfa4cc85
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419718"
---
# <a name="steps-in-a-typical-http-client-application"></a>典型的な HTTP クライアント アプリケーションの作成手順

次の表に、一般的な HTTP クライアント アプリケーションでの手順を示します。

|目標|操作を実行します。|効果|
|---------------|----------------------|-------------|
|HTTP セッションを開始します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|WinInet を初期化し、サーバーに接続します。|
|HTTP サーバーに接続します。|使用[代わりに](../mfc/reference/cinternetsession-class.md#gethttpconnection)します。|返します、 [CHttpConnection](../mfc/reference/chttpconnection-class.md)オブジェクト。|
|HTTP 要求を開きます。|使用[しないで](../mfc/reference/chttpconnection-class.md#openrequest)します。|返します、 [CHttpFile](../mfc/reference/chttpfile-class.md)オブジェクト。|
|HTTP 要求を送信します。|使用[CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders)と[chttpfile::sendrequest](../mfc/reference/chttpfile-class.md#sendrequest)します。|ファイルを見つけます。 ファイルが見つからない場合は FALSE を返します。|
|ファイルから読み取ります。|使用[CHttpFile](../mfc/reference/chttpfile-class.md)します。|指定した数の指定したバッファーを使用してバイトを読み取ります。|
|例外を処理する|使用して、 [CInternetException](../mfc/reference/cinternetexception-class.md)クラス。|すべての一般的なインターネット例外タイプを処理します。|
|HTTP セッションを終了します。|破棄、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|開いているファイル ハンドルと接続を自動的にクリーンアップします。|

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネット クライアント クラスの必要条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
