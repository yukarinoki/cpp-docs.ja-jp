---
description: '詳細については、「サーバー: サーバードキュメントの実装」を参照してください。'
title: 'サーバー : サーバー ドキュメントの実装'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
ms.openlocfilehash: b8843d3e2ac662cbb018a3063c9f04f5dd8d6f10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217329"
---
# <a name="servers-implementing-server-documents"></a>サーバー : サーバー ドキュメントの実装

この記事では、アプリケーションウィザードで OLE サーバーオプションを指定しなかった場合に、サーバードキュメントを正常に実装するために必要な手順について説明します。

#### <a name="to-define-a-server-document-class"></a>サーバードキュメントクラスを定義するには

1. ドキュメントクラスをの代わりにから派生させ `COleServerDoc` `CDocument` ます。

1. から派生したサーバー項目クラスを作成 `COleServerItem` します。

1. `OnGetEmbeddedItem`サーバードキュメントクラスのメンバー関数を実装します。

   `OnGetEmbeddedItem` は、コンテナーアプリケーションのユーザーが埋め込み項目を作成または編集するときに呼び出されます。 このメソッドは、ドキュメント全体を表す項目を返します。 これは、派生クラスのオブジェクトである必要があり `COleServerItem` ます。

1. メンバー関数をオーバーライドして、 `Serialize` ドキュメントの内容をシリアル化します。 ドキュメント内のネイティブデータを表すために使用している場合を除き、サーバー項目の一覧をシリアル化する必要はありません。 詳細については、「サーバー項目 [: サーバー項目](../mfc/servers-server-items.md)」の「サーバー *項目の実装*」を参照してください。

サーバードキュメントを作成すると、フレームワークによってドキュメントが OLE システム Dll に自動的に登録されます。 これにより、Dll はサーバードキュメントを識別できます。

詳細については、*クラスライブラリリファレンス* の「 [COleServerItem](../mfc/reference/coleserveritem-class.md) and [COleServerDoc](../mfc/reference/coleserverdoc-class.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[サーバー](../mfc/servers.md)<br/>
[サーバー: サーバー項目](../mfc/servers-server-items.md)<br/>
[サーバー: サーバーの実装](../mfc/servers-implementing-a-server.md)<br/>
[サーバー: In-Place フレームウィンドウの実装](../mfc/servers-implementing-in-place-frame-windows.md)
