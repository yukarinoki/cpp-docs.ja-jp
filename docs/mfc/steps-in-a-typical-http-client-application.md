---
title: 一般的な HTTP クライアント アプリケーションでの手順 |Microsoft ドキュメント
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
ms.openlocfilehash: c25402662296a9ebf2f15fe902dcefabb9d47073
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380959"
---
# <a name="steps-in-a-typical-http-client-application"></a>典型的な HTTP クライアント アプリケーションの作成手順
次の表に、一般的な HTTP クライアント アプリケーションでの手順を示します。  
  
|目標|操作を実行します。|効果|  
|---------------|----------------------|-------------|  
|HTTP セッションを開始します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|WinInet を初期化し、サーバーに接続します。|  
|HTTP サーバーに接続します。|使用して[代わりに](../mfc/reference/cinternetsession-class.md#gethttpconnection)です。|返します、 [CHttpConnection](../mfc/reference/chttpconnection-class.md)オブジェクト。|  
|HTTP 要求を開きます。|使用して[しないで](../mfc/reference/chttpconnection-class.md#openrequest)です。|返します、 [CHttpFile](../mfc/reference/chttpfile-class.md)オブジェクト。|  
|HTTP 要求を送信します。|使用して[CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders)と[chttpfile::sendrequest](../mfc/reference/chttpfile-class.md#sendrequest)です。|ファイルを見つけます。 ファイルが見つからない場合は、FALSE を返します。|  
|ファイルから読み取られました。|使用して[CHttpFile](../mfc/reference/chttpfile-class.md)です。|指定した数の入力バッファーを使用してバイトを読み取ります。|  
|例外を処理する|使用して、 [CInternetException](../mfc/reference/cinternetexception-class.md)クラスです。|すべての一般的なインターネット例外タイプを処理します。|  
|HTTP セッションを終了します。|破棄、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|開いているファイル ハンドルと接続を自動的にクリーンアップします。|  
  
## <a name="see-also"></a>関連項目  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
