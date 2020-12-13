---
description: '詳細情報: WinInet によってインターネットクライアントアプリケーションを簡単に作成する方法'
title: WinInet を使ってインターネット クライアント アプリケーションを簡単に作成する方法
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
ms.openlocfilehash: efee0b201a165fab8aaf838eedb2ba83b9a5b946
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330132"
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>WinInet を使ってインターネット クライアント アプリケーションを簡単に作成する方法

Win32 インターネット拡張機能 (WinInet) は、gopher、FTP、HTTP などの一般的なインターネットプロトコルへのアクセスを提供します。 WinInet を使用すると、より高いレベルのプログラミングでインターネットクライアントアプリケーションを作成できます。その際、WinSock、TCP/IP、または特定のインターネットプロトコルの詳細を処理する必要はありません。 WinInet は、3つのプロトコルすべてに対して一貫した一連の関数を提供し、使い慣れた Win32 API インターフェイスを備えています。 この一貫性により、基になるプロトコルが変更された場合 (たとえば、FTP から HTTP へ)、必要なコードの変更を最小限に抑えることができます。

Visual C++ には、WinInet を使用する2つの方法があります。 Win32 インターネット関数を直接呼び出すことができます (詳細については、Windows SDK の OLE ドキュメントを参照してください)。または、 [MFC wininet クラス](mfc-classes-for-creating-internet-client-applications.md)を使用して wininet を使用することもできます。

**WinInet を使用すると、次のことができます。**

- HTML ページをダウンロードします。

   HTTP は、サーバーからクライアントブラウザーに HTML ページを転送するために使用されるプロトコルです。

- FTP 要求を送信して、ファイルをアップロードまたはダウンロードしたり、ディレクトリの一覧を取得したりします。

   一般的な要求とは、ファイルをダウンロードするための匿名ログオンのことです。

- Gopher のメニューシステムを使用して、インターネット上のリソースにアクセスします。

   メニュー項目は、他のメニュー、検索できるインデックス付きデータベース、ニュースグループ、ファイルなど、いくつかの種類にすることができます。

3つのプロトコルすべてについて、接続を確立し、サーバーに要求を行い、接続を閉じます。

**MFC WinInet クラスを使用すると、次のことが簡単になります。**

- HTTP、FTP、および gopher サーバーからの情報を、ハードドライブからのファイルの読み取りと同じくらい簡単に読み取ることができます。

- WinSock または TCP/IP に直接プログラミングを行わずに、HTTP、FTP、および gopher プロトコルを使用します。

   Win32 インターネット機能を使用する開発者は、TCP/IP または Windows ソケットについて理解している必要はありません。 WinSock と TCP/IP プロトコルを直接使用してソケットレベルでプログラムを実行することもできますが、MFC WinInet クラスを使用してインターネット経由で HTTP、FTP、および gopher プロトコルにアクセスする方が簡単です。 多くの一般的な操作では、開発者が使用している特定のプロトコルの詳細を知る必要はありません。

コンピューターがインターネット上の他のコンピューターに対してクライアントとして実行できる多くの操作には、長い時間がかかることがあります。 これらの操作の速度は、通常、ネットワーク接続の速度によって制限されますが、他のネットワークトラフィックや操作の複雑さによっても影響を受ける可能性があります。 たとえば、リモート FTP サーバーに接続するには、コンピューターが最初にそのサーバーの名前を参照してそのアドレスを検索する必要があります。 アプリケーションは、そのアドレスにあるサーバーへの接続を試行します。 接続が開かれると、実際に接続を使用してファイルを取得する前に、コンピューターとリモートサーバーがファイル転送プロトコルとのメッセージ交換を開始します。

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](win32-internet-extensions-wininet.md)<br/>
[MFC を使用してインターネットクライアントアプリケーションを簡単に作成する方法](how-mfc-makes-it-easier-to-create-internet-client-applications.md)
