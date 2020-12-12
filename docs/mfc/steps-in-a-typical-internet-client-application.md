---
description: '詳細情報: 一般的なインターネットクライアントアプリケーションでの手順'
title: 典型的なインターネット クライアント アプリケーションの作成手順
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
ms.openlocfilehash: 9660687136361efb0256ecdd1fd19b577c46ab26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216549"
---
# <a name="steps-in-a-typical-internet-client-application"></a>典型的なインターネット クライアント アプリケーションの作成手順

次の表は、一般的なインターネットクライアントアプリケーションで実行できる手順を示しています。

|目標|実行する操作|エフェクト|
|---------------|----------------------|-------------|
|インターネットセッションを開始します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを作成します。|WinInet を初期化し、サーバーに接続します。|
|インターネットクエリオプション (タイムアウトの制限または再試行回数など) を設定します。|[CInternetSession:: SetOption](../mfc/reference/cinternetsession-class.md#setoption)を使用します。|操作が失敗した場合は FALSE を返します。|
|セッションの状態を監視するコールバック関数を確立します。|[CInternetSession:: EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback)を使用します。|[CInternetSession:: OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)へのコールバックを確立します。 をオーバーライドし `OnStatusCallback` て、独自のコールバックルーチンを作成します。|
|インターネットサーバー、イントラネットサーバー、またはローカルファイルに接続します。|[CInternetSession:: OpenURL](../mfc/reference/cinternetsession-class.md#openurl)を使用します。|URL を解析し、指定されたサーバーへの接続を開きます。 (ローカルファイル名を渡す場合) [CStdioFile](../mfc/reference/cstdiofile-class.md) を返し `OpenURL` ます。 これは、サーバーまたはファイルから取得したデータにアクセスするために使用されるオブジェクトです。|
|ファイルから読み取ります。|[CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read)を使用します。|指定したバッファーを使用して、指定したバイト数を読み取ります。|
|例外を処理する|[CInternetException](../mfc/reference/cinternetexception-class.md)クラスを使用します。|すべての一般的なインターネット例外の種類を処理します。|
|インターネットセッションを終了します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを破棄します。|開いているファイルハンドルと接続を自動的にクリーンアップします。|

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネットクライアントクラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet クラスを使用したインターネットクライアントアプリケーションの作成](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
