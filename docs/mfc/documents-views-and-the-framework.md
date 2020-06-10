---
title: ドキュメント、ビュー、フレームワーク
ms.date: 11/19/2018
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
ms.openlocfilehash: 17956c0b175e978c6e4e2fefcdad5f744929d457
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621835"
---
# <a name="documents-views-and-the-framework"></a>ドキュメント、ビュー、フレームワーク

MFC フレームワークの中核となるのは、ドキュメントとビューの概念です。 ドキュメントは、ユーザーが編集セッションを操作するときに使用するデータオブジェクトです。 これは、[**ファイル**] メニューの [**新規**作成] または [**開く**] コマンドによって作成され、通常はファイルに保存されます。 (クラスから派生した標準の MFC ドキュメント `CDocument` は、アクティブなドキュメントや OLE 複合ドキュメントとは異なります)。ビューは、ユーザーがドキュメントを操作するときに使用するウィンドウオブジェクトです。

実行中のアプリケーションの主要なオブジェクトは次のとおりです。

- ドキュメントまたはドキュメント。

   ドキュメントクラス ( [CDocument](reference/cdocument-class.md)から派生) は、アプリケーションのデータを指定します。

   アプリケーションで OLE 機能が必要な場合は、必要な機能の種類に応じて、 [COleDocument](reference/coledocument-class.md)またはその派生クラスのいずれかからドキュメントクラスを派生させます。

- ビューまたはビュー。

   ビュークラス ( [CView](reference/cview-class.md)から派生) は、ユーザーの "データに対するウィンドウ" です。 ビュークラスは、ユーザーがドキュメントのデータを確認し、それと対話する方法を制御します。 場合によっては、ドキュメントにデータの複数のビューを含めることが必要になることがあります。

   スクロールが必要な場合は、 [CScrollView](reference/cscrollview-class.md)から派生します。 ダイアログテンプレートリソースにレイアウトされたユーザーインターフェイスがビューにある場合は、 [CFormView](reference/cformview-class.md)から派生します。 単純なテキストデータの場合は、CEditView を使用するか、または[CEditView](reference/ceditview-class.md)から派生させます。 データ入力プログラムなど、フォームベースのデータアクセスアプリケーションの場合は、 [CRecordView](reference/crecordview-class.md) (ODBC の場合) から派生します。 また、 [CTreeView](reference/ctreeview-class.md)、 [CListView](reference/clistview-class.md)、 [CRichEditView](reference/cricheditview-class.md)の各クラスも使用できます。

- フレームウィンドウ

   ビューは、"ドキュメントフレームウィンドウ" 内に表示されます。 SDI アプリケーションでは、ドキュメントフレームウィンドウはアプリケーションの "メインフレームウィンドウ" でもあります。 MDI アプリケーションでは、ドキュメントウィンドウはメインフレームウィンドウ内に表示される子ウィンドウです。 派生メインフレームウィンドウクラスでは、ビューを含むフレームウィンドウのスタイルとその他の特性を指定します。 フレームウィンドウをカスタマイズする必要がある場合は、 [CFrameWnd](reference/cframewnd-class.md)から派生して、SDI アプリケーション用のドキュメントフレームウィンドウをカスタマイズします。 MDI アプリケーションのメインフレームウィンドウをカスタマイズするには、 [CMDIFrameWnd](reference/cmdiframewnd-class.md)から派生します。 また、 [CMDIChildWnd](reference/cmdichildwnd-class.md)からクラスを派生させて、アプリケーションがサポートするさまざまな種類の MDI ドキュメントフレームウィンドウをカスタマイズします。

- ドキュメントテンプレート

   ドキュメントテンプレートは、ドキュメント、ビュー、およびフレームウィンドウの作成を調整します。 クラス[CDocTemplate](reference/cdoctemplate-class.md)から派生した特定のドキュメントテンプレートクラスは、1つの種類のすべての開いているドキュメントを作成し、管理します。 複数の種類のドキュメントをサポートするアプリケーションには、複数のドキュメントテンプレートがあります。 SDI アプリケーションには[CSingleDocTemplate](reference/csingledoctemplate-class.md)クラスを使用し、MDI アプリケーションには[CMultiDocTemplate](reference/cmultidoctemplate-class.md)クラスを使用します。

- アプリケーションオブジェクト

   アプリケーションクラス ( [CWinApp](reference/cwinapp-class.md)から派生) は、上のすべてのオブジェクトを制御し、初期化やクリーンアップなどのアプリケーションの動作を指定します。 アプリケーションの1つのアプリケーションオブジェクトのみが、アプリケーションがサポートするドキュメントの種類のドキュメントテンプレートを作成および管理します。

- スレッドオブジェクト

   たとえば、バックグラウンドで計算を実行するために、アプリケーションが個別の実行スレッドを作成する場合は、 [CWinThread](reference/cwinthread-class.md)から派生したクラスを使用します。 [CWinApp](reference/cwinapp-class.md)自体はから派生 `CWinThread` し、アプリケーションの実行のプライマリスレッド (またはメインプロセス) を表します。 セカンダリスレッドで MFC を使用することもできます。

実行中のアプリケーションでは、これらのオブジェクトは、コマンドやその他のメッセージによって連結されたユーザー操作に協調的に応答します。 1つのアプリケーションオブジェクトが1つ以上のドキュメントテンプレートを管理します。 各ドキュメントテンプレートは、1つまたは複数のドキュメントを作成および管理します (アプリケーションが SDI と MDI のどちらであるかによって異なります)。 ユーザーは、フレームウィンドウ内に含まれるビューを使用してドキュメントを表示および操作します。 次の図は、SDI アプリケーションのこれらのオブジェクト間の関係を示しています。

![実行中の SDI アプリケーション内のオブジェクト](../mfc/media/vc386v1.gif "実行中の SDI アプリケーションのオブジェクト") <br/>
動作中の SDI アプリケーションのオブジェクト

この記事の残りの部分では、フレームワークツール、MFC アプリケーションウィザード、およびリソースエディターを使用してこれらのオブジェクトを作成する方法、それらのオブジェクトを連携させる方法、およびプログラミングでそれらを使用する方法について説明します。 ドキュメント、ビュー、フレームウィンドウの詳細については、 [「ウィンドウオブジェクト](window-objects.md)と[ドキュメント/ビューアーキテクチャ](document-view-architecture.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスを使用した Windows アプリケーションの作成](using-the-classes-to-write-applications-for-windows.md)
