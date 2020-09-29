---
title: ドキュメント、ビュー、および MFC (Microsoft Foundation Class) ライブラリフレームワーク
description: MFC (Microsoft Foundation Class) ライブラリのドキュメントとビューの説明。
ms.date: 09/25/2020
helpviewer_keywords:
- document templates [MFC], template objects
- applications [MFC]
- MFC, application framework
- application objects [MFC], relation to other MFC objects
- documents [MFC]
- MFC, documents
- document objects [MFC], in relation to other MFC objects
- view objects [MFC], relation to other MFC objects
- MFC, views
- document/view architecture [MFC], about document/view architecture
- objects [MFC], MFC applications
- MFC object relationships
- thread objects [MFC]
ms.assetid: 409ddd9b-66ad-4625-84f7-bf55a41d697b
ms.openlocfilehash: 41e145224e512b95d8674109f6ed3dcee39fffb1
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414101"
---
# <a name="documents-views-and-the-framework"></a>ドキュメント、ビュー、フレームワーク

MFC フレームワークの中核となるのは、ドキュメントとビューの概念です。 ドキュメントは、ユーザーが編集セッションを操作するときに使用するデータオブジェクトです。 これは、[**ファイル**] メニューの [**新規**作成] または [**開く**] コマンドによって作成され、通常はファイルに保存されます。 (クラスから派生した標準の MFC ドキュメント `CDocument` は、アクティブなドキュメントや OLE 複合ドキュメントとは異なります)。ビューは、ユーザーがドキュメントを操作するときに使用するウィンドウオブジェクトです。

実行中のアプリケーションの主要なオブジェクトは次のとおりです。

- スレッドオブジェクト

   たとえば、バックグラウンドで計算を実行するために、アプリケーションが個別の実行スレッドを作成する場合は、から派生したクラスを使用し [`CWinThread`](reference/cwinthread-class.md) ます。 [`CWinApp`](reference/cwinapp-class.md) 自体はから派生 `CWinThread` し、アプリケーションの実行のプライマリスレッド (またはメインプロセス) を表します。 セカンダリスレッドで MFC を使用することもできます。

- アプリケーションオブジェクト

   アプリケーションクラス (から派生 [`CWinApp`](reference/cwinapp-class.md) ) は、上のすべてのオブジェクトを制御し、初期化やクリーンアップなどのアプリケーションの動作を指定します。 アプリケーションの1つのアプリケーションオブジェクトのみが、アプリケーションがサポートするドキュメントの種類のドキュメントテンプレートを作成および管理します。

- ドキュメントテンプレート

   ドキュメントテンプレートは、ドキュメント、ビュー、およびフレームウィンドウの作成を調整します。 クラスから派生した特定のドキュメントテンプレートクラスは、 [`CDocTemplate`](reference/cdoctemplate-class.md) 1 つの種類のすべての開いているドキュメントを作成し、管理します。 複数の種類のドキュメントをサポートするアプリケーションには、複数のドキュメントテンプレートがあります。 SDI アプリケーションの場合は [CSingleDocTemplate](reference/csingledoctemplate-class.md) クラスを使用し、MDI アプリケーションの場合はクラスを使用し [`CMultiDocTemplate`](reference/cmultidoctemplate-class.md) ます。

- フレームウィンドウ

   ビューは、"ドキュメントフレームウィンドウ" 内に表示されます。 SDI アプリケーションでは、ドキュメントフレームウィンドウはアプリケーションの "メインフレームウィンドウ" でもあります。 MDI アプリケーションでは、ドキュメントウィンドウはメインフレームウィンドウ内に表示される子ウィンドウです。 派生メインフレームウィンドウクラスでは、ビューを含むフレームウィンドウのスタイルとその他の特性を指定します。 フレームウィンドウをカスタマイズする必要がある場合は、から派生させて、 [`CFrameWnd`](reference/cframewnd-class.md) SDI アプリケーション用のドキュメントフレームウィンドウをカスタマイズします。 から派生して [`CMDIFrameWnd`](reference/cmdiframewnd-class.md) 、MDI アプリケーションのメインフレームウィンドウをカスタマイズします。 また、からクラスを派生させて [`CMDIChildWnd`](reference/cmdichildwnd-class.md) 、アプリケーションがサポートするさまざまな種類の MDI ドキュメントフレームウィンドウをカスタマイズします。

- ドキュメントまたはドキュメント。

   ドキュメントクラス (から派生) によって [`CDocument`](reference/cdocument-class.md) 、アプリケーションのデータが指定されます。

   アプリケーションで OLE 機能が必要な場合は、 [`COleDocument`](reference/coledocument-class.md) 必要な機能の種類に応じて、またはその派生クラスのいずれかからドキュメントクラスを派生させます。

- ビューまたはビュー。

   ビュークラス (から派生 [`CView`](reference/cview-class.md) ) は、ユーザーの "データに対するウィンドウ" です。 ビュークラスは、ユーザーがドキュメントのデータを確認し、それと対話する方法を制御します。 場合によっては、ドキュメントにデータの複数のビューを含めることが必要になることがあります。

   スクロールが必要な場合は、から派生 [`CScrollView`](reference/cscrollview-class.md) します。 ダイアログテンプレートリソースにレイアウトされたユーザーインターフェイスがビューにある場合は、から派生 [`CFormView`](reference/cformview-class.md) します。 単純なテキストデータの場合は、を使用するか、から派生させ [`CEditView`](reference/ceditview-class.md) ます。 データ入力プログラムなど、フォームベースのデータアクセスアプリケーションの場合は、から派生し [`CRecordView`](reference/crecordview-class.md) ます (ODBC の場合)。 クラス [`CTreeView`](reference/ctreeview-class.md) 、、およびも使用でき [`CListView`](reference/clistview-class.md) [`CRichEditView`](reference/cricheditview-class.md) ます。

実行中のアプリケーションでは、これらのオブジェクトは、コマンドやその他のメッセージによって連結されたユーザー操作に協調的に応答します。 1つのアプリケーションオブジェクトが1つ以上のドキュメントテンプレートを管理します。 各ドキュメントテンプレートは、1つまたは複数のドキュメントを作成および管理します (アプリケーションが SDI と MDI のどちらであるかによって異なります)。 ユーザーは、フレームウィンドウ内に含まれるビューを使用してドキュメントを表示および操作します。 次の図は、SDI アプリケーションのこれらのオブジェクト間の関係を示しています。

![実行中の SDI アプリケーション内のオブジェクト](../mfc/media/vc386v1.gif "実行中の SDI アプリケーションのオブジェクト")\
動作中の SDI アプリケーションのオブジェクト

この記事の残りの部分では、フレームワークツール、MFC アプリケーションウィザード、およびリソースエディターを使用してこれらのオブジェクトを作成する方法、それらのオブジェクトを連携させる方法、およびプログラミングでそれらを使用する方法について説明します。 ドキュメント、ビュー、フレームウィンドウの詳細については、 [「ウィンドウオブジェクト](window-objects.md) と [ドキュメント/ビューアーキテクチャ](document-view-architecture.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスを使用して Windows 用のアプリケーションを作成する](using-the-classes-to-write-applications-for-windows.md)
