---
description: '詳細については、「サーバー: サーバーの実装」を参照してください。'
title: 'サーバー : サーバーの実装'
ms.date: 11/04/2016
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
ms.openlocfilehash: 3ced10f88ce062ab571841610ba4b000571835b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217381"
---
# <a name="servers-implementing-a-server"></a>サーバー : サーバーの実装

この記事では、visual 編集サーバーアプリケーション用に MFC アプリケーションウィザードによって作成されるコードについて説明します。 アプリケーションウィザードを使用していない場合、この記事では、サーバーアプリケーションを実装するコードを記述する必要がある領域の一覧を示します。

アプリケーションウィザードを使用して新しいサーバーアプリケーションを作成する場合は、サーバー固有の大量のコードが提供されます。 既存のアプリケーションにビジュアル編集サーバーの機能を追加する場合は、必要なサーバーコードの残りの部分を追加する前に、アプリケーションウィザードによって提供されたコードを複製する必要があります。

アプリケーションウィザードが提供するサーバーコードは、次のいくつかのカテゴリに分類されます。

- サーバーリソースの定義:

  - サーバーが独自のウィンドウで埋め込み項目を編集しているときに使用されるメニューリソース。

  - サーバーが適切に配置されている場合に使用するメニューおよびツールバーのリソース。

  これらのリソースの詳細については、「 [メニューとリソース: サーバーの追加](../mfc/menus-and-resources-server-additions.md)」を参照してください。

- から派生した項目クラスを定義 `COleServerItem` します。 サーバー項目の詳細については、「サーバー [: サーバー項目](../mfc/servers-server-items.md)」を参照してください。

- ドキュメントクラスの基本クラスをに変更 `COleServerDoc` します。 詳細については、「サーバー [: サーバードキュメントの実装](../mfc/servers-implementing-server-documents.md)」を参照してください。

- から派生したフレームウィンドウクラスを定義 `COleIPFrameWnd` します。 詳細については、「 [サーバー: In-Place フレームウィンドウの実装](../mfc/servers-implementing-in-place-frame-windows.md)」を参照してください。

- Windows 登録データベースにサーバーアプリケーションのエントリを作成し、OLE システムにサーバーの新しいインスタンスを登録します。 このトピックの詳細については、「 [登録](../mfc/registration.md)」を参照してください。

- サーバーアプリケーションを初期化して起動しています。 このトピックの詳細については、「 [登録](../mfc/registration.md)」を参照してください。

詳細については、*クラスライブラリリファレンス* の「 [COleServerItem](../mfc/reference/coleserveritem-class.md)、 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)、および [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[サーバー](../mfc/servers.md)<br/>
[Containers](../mfc/containers.md)<br/>
[メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[登録](../mfc/registration.md)
