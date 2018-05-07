---
title: どの wininet を使って簡単をインターネット クライアント アプリケーションを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09a7427374de085de9bd2872c8b1368a6b961b35
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>WinInet を使ってインターネット クライアント アプリケーションを簡単に作成する方法
Win32 インターネット拡張機能または WinInet、gopher、FTP、HTTP など、共通のインターネット プロトコルへのアクセスを提供します。 WinInet を使用すると、WinSock、TCP/IP、または特定のインターネット プロトコルの詳細に対処しなくてもより高度なプログラミングでは、インターネット クライアント アプリケーションを記述できます。 WinInet では、Win32 API に使い慣れたインターフェイスをすべての 3 つのプロトコルの一貫性のある一連の関数を提供します。 この整合性には、場合 (たとえば、FTP から HTTP へ) プロトコルを変更する必要があるコードの変更が最小限に抑えます。  
  
 Visual C には、WinInet を使用するための 2 つの方法が用意されています。 Win32 のインターネット機能を直接呼び出すことができます (詳細については、Windows SDK での OLE ドキュメントを参照) を通じて wininet の基礎を使用することも、 [MFC WinInet クラス](../mfc/mfc-classes-for-creating-internet-client-applications.md)です。  
  
 **WinInet を使用することができます。**  
  
-   HTML ページをダウンロードします。  
  
     HTTP は、サーバーからクライアント ブラウザーに HTML ページを転送に使用されるプロトコルです。  
  
-   アップロードまたはファイルをダウンロードまたはディレクトリの一覧を取得する FTP 要求を送信します。  
  
     一般的な要求は、ファイルをダウンロードする匿名ログオンです。  
  
-   Gopher のメニュー システムを使用して、インターネット上のリソースにアクセスするためです。  
  
     メニュー項目には、その他のメニューのインデックス付きデータベースを検索することができます、ニュースグループ、またはファイルを含む、いくつかの種類を指定できます。  
  
 3 つのすべてのプロトコルをする、接続を確立し、サーバーに対して要求を行う接続を閉じます。  
  
 **MFC WinInet クラスしやすいようにします。**  
  
-   ハード ドライブからファイルを読み取るのと同じように簡単に、HTTP、FTP、および gopher サーバーから情報を読み取る。  
  
-   WinSock または TCP/IP に直接プログラミングを行わず、HTTP、FTP、および gopher プロトコルを使用します。  
  
     Win32 のインターネット機能を使用する開発者は、TCP/IP または Windows ソケットを理解する必要はありません。 ユーザーがまだプログラム ソケット レベルでは、WinSock および TCP/IP プロトコルを使用して直接が、さらに、インターネット経由でアクセス HTTP、FTP、および gopher プロトコル MFC WinInet クラスを使いやすくします。 多くの一般的な操作では、開発者が使用している特定のプロトコルの詳細を確認する必要はありません。  
  
 さまざまな操作として、インターネット上の他のコンピューターにクライアント コンピューターで実行できる時間がかかることができます。 通常、これらの操作の速度は、ネットワーク接続の速度によって制限が、他のネットワーク トラフィックと、操作の複雑さによっても影響されます。 リモート FTP サーバーへの接続などの必要があります、コンピューターがそのアドレスを検索するには、そのサーバーの名前を最初に表示されます。 アプリケーションは、そのアドレスでサーバーに接続を試みます。 接続が開かれた後、コンピューターとリモート サーバーが開始されますファイル転送プロトコルとのメッセージ交換前に、ファイルを取得する接続を実際に使用することができます。  
  
## <a name="see-also"></a>関連項目  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [MFC を使ってインターネット クライアント アプリケーションを簡単に作成する方法](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)

