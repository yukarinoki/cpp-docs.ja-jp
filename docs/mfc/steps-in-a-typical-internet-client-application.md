---
title: 典型的なインターネット クライアント アプリケーションでの手順 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1c7a7053b8378ea62dc0291dba1b79b794dd099
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381275"
---
# <a name="steps-in-a-typical-internet-client-application"></a>典型的なインターネット クライアント アプリケーションの作成手順
次の表は、典型的なインターネット クライアント アプリケーションで必要な手順を示します。  
  
|目標|操作を実行します。|効果|  
|---------------|----------------------|-------------|  
|インターネット セッションを開始します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|WinInet を初期化し、サーバーに接続します。|  
|タイムアウトの制限 (たとえばの再試行の回数) のインターネット クエリ オプションを設定します。|使用して[CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption)です。|操作が成功した場合は、FALSE を返します。|  
|セッションの状態を監視するコールバック関数を確立します。|使用して[CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback)です。|コールバックを確立[:onstatuscallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)です。 オーバーライド`OnStatusCallback`を独自のコールバック ルーチンを作成します。|  
|インターネット サーバー、イントラネット サーバー、またはローカル ファイルに接続します。|使用して[できます](../mfc/reference/cinternetsession-class.md#openurl)です。|URL を解析し、指定されたサーバーへの接続を開きます。 返します、 [CStdioFile](../mfc/reference/cstdiofile-class.md) (を渡した場合`OpenURL`ローカルのファイル名)。 これは、サーバーまたはファイルから取得されたデータにアクセスするオブジェクトです。|  
|ファイルから読み取られました。|使用して[細かい](../mfc/reference/cinternetfile-class.md#read)です。|指定した数の入力バッファーを使用してバイトを読み取ります。|  
|例外を処理する|使用して、 [CInternetException](../mfc/reference/cinternetexception-class.md)クラスです。|すべての一般的なインターネット例外タイプを処理します。|  
|インターネット セッションを終了します。|破棄、 [CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクト。|開いているファイル ハンドルと接続を自動的にクリーンアップします。|  
  
## <a name="see-also"></a>関連項目  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント クラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
