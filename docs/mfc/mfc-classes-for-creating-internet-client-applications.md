---
title: インターネット クライアント アプリケーションの作成用の MFC クラス
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, WinInet classes
- WinInet classes [MFC], classes
- classes [MFC], MFC
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
ms.openlocfilehash: 578fd5b72e6c04610aa862f1a6631895a32a9bfe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358214"
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>インターネット クライアント アプリケーションの作成用の MFC クラス

MFC には、インターネット クライアント アプリケーションを作成するための次のクラスとグローバル関数が用意されています。 インデントは、クラスが、その上のインデントされていないクラスから派生したことを示します。 `CGopherFile`など`CHttpFile`から派生`CInternetFile`します。 これらのクラスとグローバル関数は AFXINET で宣言されています。AFX`CFileFind`で宣言されているを除く H。H。

## <a name="classes"></a>クラス

- [CInternetSession](../mfc/reference/cinternetsession-class.md)

- [CInternetConnection](../mfc/reference/cinternetconnection-class.md)

  - [CFtpConnection](../mfc/reference/cftpconnection-class.md)

  - [CGopherConnection](../mfc/reference/cgopherconnection-class.md)

  - [CHttpConnection](../mfc/reference/chttpconnection-class.md)

- [CInternetFile](../mfc/reference/cinternetfile-class.md)

  - [CGopherFile](../mfc/reference/cgopherfile-class.md)

  - [CHttpFile](../mfc/reference/chttpfile-class.md)

- [CFileFind](../mfc/reference/cfilefind-class.md)

  - [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)

  - [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)

- [CGopherLocator](../mfc/reference/cgopherlocator-class.md)

- [CInternetException](../mfc/reference/cinternetexception-class.md)

## <a name="global-functions"></a>グローバル関数

- [AfxParseURL](reference/internet-url-parsing-globals.md#afxparseurl)

- [AfxGetInternetHandleType](reference/internet-url-parsing-globals.md#afxgetinternethandletype)

- [AfxThrowInternetException](reference/internet-url-parsing-globals.md#afxthrowinternetexception)

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネット クライアント クラスの必要条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
