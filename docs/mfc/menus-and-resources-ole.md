---
title: メニューとリソース (OLE) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE visual editing servers [MFC]
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- string tables [MFC], visual editing applications
- OLE containers [MFC], menus and resources
- OLE applications [MFC], menus and resources
- OLE server applications [MFC], menus and resources
- toolbars [MFC], OLE document applications
- string editing [MFC], visual editing applications
- server applications [MFC], OLE menus and resources
- applications [OLE], menus and resources
- menus [MFC], OLE document applications
- in-place activation [MFC], OLE menus and resources
- containers [MFC], OLE container applications
- OLE menus and resources [MFC]
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ada8731be176368e1503118597fa4d6df38e3ef
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378374"
---
# <a name="menus-and-resources-ole"></a>メニューとリソース (OLE)

この記事のグループには、MFC OLE ドキュメント アプリケーションでメニューとリソースの使用について説明します。

OLE ビジュアル編集は追加の要件をメニューとコンテナー両方のモードがいくつかあるために、OLE ドキュメント アプリケーションによって提供されるその他のリソース、サーバー (コンポーネント) アプリケーションを起動して使用できます。 たとえば、フル サーバー アプリケーションは、これら 3 つのモードのいずれかで実行できます。

- スタンド アロンでします。

- インプレースでコンテナーのコンテキスト内でアイテムを編集します。

- 多くの場合、別のウィンドウで、コンテナーのコンテキスト外の項目を編集用に開く。

これには、次の 3 つの個別のメニュー レイアウトがあり、アプリケーションの各モードのいずれかが必要です。 アクセラレータ テーブルでは、新しい各モードは必要も。 コンテナー アプリケーションの可能性がありますまたはインプレース アクティブ化; はサポートされていません場合は、新しいメニュー構造を必要があるし、アクセラレータ テーブルに関連付けられています。

インプレース アクティブ化するには、コンテナーとサーバー アプリケーションが、メニューのツールバー、およびステータス バーの領域についてネゴシエートする必要があることが必要です。 すべてのリソースは、これを考慮して設計する必要があります。 この記事[メニューとリソース: メニューのマージ](../mfc/menus-and-resources-menu-merging.md)このトピックの詳細について説明します。

これらの問題があるためアプリケーション ウィザードで作成した OLE ドキュメント アプリケーションは最大 4 つの独立したメニューとアクセラレータ テーブル リソースを持つことができます。 これらは、次の理由で使用されます。

|リソース名|使用|
|-------------------|---------|
|IDR_MAINFRAME|ファイルが開いていない場合は、MDI アプリケーションで、または開いているファイルに関係なく SDI アプリケーションで使用されます。 これは、非 OLE アプリケーションで使用される標準のメニューです。|
|Idr _\<プロジェクト > の種類|ファイルが開いている場合は、MDI アプリケーションで使用されます。 アプリケーションがスタンドアロンで実行されているときに使用されます。 これは、非 OLE アプリケーションで使用される標準のメニューです。|
|Idr _\<プロジェクト > TYPE_SRVR_IP|オブジェクトの場所が開いているときに、サーバーまたはコンテナーによって使用されます。|
|Idr _\<プロジェクト > TYPE_SRVR_EMB|インプレース アクティブ化を使用せず、オブジェクトが開かれている場合は、サーバー アプリケーションで使用します。|

各リソースの名前は、メニューと、通常、アクセラレータ テーブルを表します。 似た手法は、アプリケーション ウィザードで作成されない MFC アプリケーションで使用する必要があります。

次の記事では、コンテナー、サーバー、およびインプレース アクティブ化を実装するために必要なマージ メニューに関連するトピックについて説明します。

- [メニューとリソース: コンテナーの変更点](../mfc/menus-and-resources-container-additions.md)

- [メニューとリソース: サーバーの変更点](../mfc/menus-and-resources-server-additions.md)

- [メニューとリソース: メニューの結合](../mfc/menus-and-resources-menu-merging.md)

## <a name="see-also"></a>関連項目

[OLE](../mfc/ole-in-mfc.md)

