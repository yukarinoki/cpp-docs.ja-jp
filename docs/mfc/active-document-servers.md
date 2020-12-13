---
description: '詳細情報: Active ドキュメントサーバー'
title: Active ドキュメント サーバー
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], servers
- servers [MFC], active document
- active document servers [MFC]
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
ms.openlocfilehash: 37a8e74b0c4b1b37bb031db522bed394c2a9d545
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150320"
---
# <a name="active-document-servers"></a>Active ドキュメント サーバー

Word、Excel、PowerPoint などの active ドキュメントサーバーは、アクティブなドキュメントと呼ばれる他のアプリケーションの種類のドキュメントをホストします。 OLE 埋め込みオブジェクト (別のドキュメントのページ内に表示されます) とは異なり、アクティブドキュメントには、それらを作成するサーバーアプリケーションの完全なインターフェイスと完全なネイティブ機能が用意されています。 ユーザーは、お気に入りのアプリケーションを最大限に活用してドキュメントを作成でき (アクティブなドキュメントが有効になっている場合)、結果のプロジェクトを1つのエンティティとして扱うことができます。

アクティブなドキュメントには複数のページを含めることができ、常にアクティブになります。 Active documents は、ユーザーインターフェイスの一部を制御し、そのメニューをコンテナーの [ **ファイル** ] メニューと [ **ヘルプ** ] メニューと結合します。 コンテナーの編集領域全体を占有し、プリンターページ (余白、フッターなど) のビューとレイアウトを制御します。

MFC では、ドキュメント/ビューインターフェイス、コマンドディスパッチマップ、印刷、メニュー管理、およびレジストリ管理を使用して、アクティブなドキュメントサーバーを実装します。 特定のプログラミング要件については、「 [active ドキュメント](active-documents.md)」で説明します。

MFC は、 [CDocObjectServer](reference/cdocobjectserver-class.md)クラスを使用したアクティブなドキュメントをサポートしています。このクラスは、 [CDocObjectServerItem](reference/cdocobjectserveritem-class.md)から派生し[たもので](reference/ccmdtarget-class.md)、 [COleServerItem](reference/coleserveritem-class.md)から派生したものです。 MFC では、 [COleClientItem](reference/coleclientitem-class.md)から派生した[COleDocObjectItem](reference/coledocobjectitem-class.md)クラスを使用した active ドキュメントコンテナーがサポートされています。

`CDocObjectServer` アクティブドキュメントインターフェイスをマップし、アクティブなドキュメントを初期化してアクティブ化します。 MFC には、アクティブなドキュメント内のコマンドルーティングを処理するマクロも用意されています。 アプリケーションでアクティブなドキュメントを使用するには、Stdafx.h ファイルに AfxDocOb を含めます。

通常の MFC サーバーは、独自 `COleServerItem` の派生クラスをフックします。 [ **ミニサーバー** ] または [ **完全サーバー** ] チェックボックスをオンにしてアプリケーションサーバーの複合ドキュメントをサポートする場合は、MFC アプリケーションウィザードによってこのクラスが生成されます。 [ **Active ドキュメントサーバー** ] チェックボックスもオンにした場合、MFC アプリケーションウィザードでは、代わりにから派生したクラスが生成され `CDocObjectServerItem` ます。

`COleDocObjectItem`クラスを使用すると、OLE コンテナーをアクティブドキュメントコンテナーにすることができます。 Mfc アプリケーションウィザードの [複合ドキュメントのサポート] ページで [ **アクティブドキュメントコンテナー** ] チェックボックスをオンにすると、active ドキュメントコンテナーを作成できます。 詳細については、「 [Active ドキュメントコンテナーアプリケーションの作成](creating-an-active-document-container-application.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Active ドキュメントコンテインメント](active-document-containment.md)
