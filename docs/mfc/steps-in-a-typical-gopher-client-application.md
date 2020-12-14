---
description: '詳細情報: 一般的な Gopher クライアントアプリケーションの手順'
title: 典型的な Gopher クライアント アプリケーションの作成手順
ms.date: 11/04/2016
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
ms.openlocfilehash: 23940457acf52009b6d334deec129324a53a7583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216627"
---
# <a name="steps-in-a-typical-gopher-client-application"></a>典型的な Gopher クライアント アプリケーションの作成手順

次の表は、一般的な gopher クライアントアプリケーションで実行できる手順を示しています。

|目標|実行する操作|エフェクト|
|---------------|----------------------|-------------|
|Gopher セッションを開始します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを作成します。|WinInet を初期化し、サーバーに接続します。|
|Gopher サーバーに接続します。|[CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection)を使用します。|[CGopherConnection](../mfc/reference/cgopherconnection-class.md)オブジェクトを返します。|
|Gopher の最初のリソースを検索します。|[CGopherFileFind:: FindFile](../mfc/reference/cgopherfilefind-class.md#findfile)を使用します。|最初のファイルを検索します。 ファイルが見つからない場合は FALSE を返します。|
|Gopher で次のリソースを検索します。|[CGopherFileFind:: FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile)を使用します。|次のファイルを検索します。 ファイルが見つからない場合は FALSE を返します。|
|またはによって検出されたファイルを `FindFile` `FindNextFile` 読み取り用に開きます。|[CGopherFileFind:: GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator)を使用して gopher ロケーターを取得します。 [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)を使用します。|ロケーターによって指定されたファイルを開きます。 `OpenFile`[CGopherFile](../mfc/reference/cgopherfile-class.md)オブジェクトを返します。|
|指定した gopher ロケーターを使用してファイルを開きます。|[CGopherConnection:: CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator)を使用して gopher ロケーターを作成します。 [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)を使用します。|ロケーターによって指定されたファイルを開きます。 `OpenFile`[CGopherFile](../mfc/reference/cgopherfile-class.md)オブジェクトを返します。|
|ファイルから読み取ります。|[CGopherFile](../mfc/reference/cgopherfile-class.md)を使用します。|指定したバッファーを使用して、指定したバイト数を読み取ります。|
|例外を処理する|[CInternetException](../mfc/reference/cinternetexception-class.md)クラスを使用します。|すべての一般的なインターネット例外の種類を処理します。|
|Gopher セッションを終了します。|[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトを破棄します。|開いているファイルハンドルと接続を自動的にクリーンアップします。|

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネットクライアントクラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet クラスを使用したインターネットクライアントアプリケーションの作成](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
