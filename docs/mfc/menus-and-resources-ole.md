---
title: メニューとリソース (OLE) |Microsoft ドキュメント
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
ms.openlocfilehash: cae180ca71b89732e073b9039483b8b46366a42a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929635"
---
# <a name="menus-and-resources-ole"></a>メニューとリソース (OLE)
この記事のグループでは、MFC OLE ドキュメント アプリケーションでメニューとリソースの使用について説明します。  
  
 OLE ビジュアル編集を配置して追加の要件、メニューと両方コンテナーにモードの数があるために、OLE ドキュメント アプリケーションによって提供される他のリソース (コンポーネント) のサーバー アプリケーションを起動して使用できます。 たとえば、フル サーバー アプリケーションは、これら 3 つのモードのいずれかで実行できます。  
  
-   スタンド アロンです。  
  
-   で、コンテナーのコンテキスト内でアイテムを編集します。  
  
-   多くの場合、別のウィンドウで、コンテナーのコンテキスト外の項目を編集用に開く。  
  
 これには、次の 3 つの個別のメニュー レイアウトがあり、アプリケーションの各モードのいずれかが必要です。 アクセラレータ テーブルは、新しい各モードのために必要なもです。 コンテナー アプリケーション サポートもありますされません、インプレース アクティブ化します。場合は、そのメニュー構造を必要があり、アクセラレータ テーブルに関連付けられています。  
  
 インプレース アクティブ化するには、コンテナーとサーバー アプリケーションする必要があります メニューのツールバー、およびステータス バーの領域についてネゴシエートすることが必要です。 すべてのリソースは、これを念頭設計する必要があります。 アーティクル[メニューとリソース: メニューのマージ](../mfc/menus-and-resources-menu-merging.md)この機能の詳細を説明します。  
  
 これらの問題があるためアプリケーション ウィザードで作成した OLE ドキュメント アプリケーションは、最大 4 つの独立したメニューとアクセラレータ テーブル リソースを持つことができます。 これらは、次の理由で使用されます。  
  
|リソース名|使用|  
|-------------------|---------|  
|IDR_MAINFRAME|MDI アプリケーションで開いている、ファイルがない場合、または開いているファイルに関係なく SDI アプリケーションで使用されます。 これは、非 OLE アプリケーションで使用される標準のメニューです。|  
|Idr _\<プロジェクト > の種類|ファイルを開いている場合に、MDI アプリケーションで使用されます。 アプリケーションがスタンドアロンで実行されているときに使用されます。 これは、非 OLE アプリケーションで使用される標準のメニューです。|  
|Idr _\<プロジェクト > TYPE_SRVR_IP|オブジェクトの場所が開いているときに、サーバーまたはコンテナーによって使用されます。|  
|Idr _\<プロジェクト > TYPE_SRVR_EMB|オブジェクトが、インプレース アクティブ化を使用せずに開かれている場合は、サーバー アプリケーションによって使用されます。|  
  
 各リソースの名前は、メニューと、通常、アクセラレータ テーブルを表します。 アプリケーション ウィザードでは作成されません MFC アプリケーションでは、同様のスキームを使用してください。  
  
 次の記事では、コンテナー、サーバー、およびインプレース アクティブ化を実装する必要をマージするメニューに関連するトピックについて説明します。  
  
-   [メニューとリソース: コンテナーの変更点](../mfc/menus-and-resources-container-additions.md)  
  
-   [メニューとリソース: サーバーの変更点](../mfc/menus-and-resources-server-additions.md)  
  
-   [メニューとリソース: メニューの結合](../mfc/menus-and-resources-menu-merging.md)  
  
## <a name="see-also"></a>関連項目  
 [OLE](../mfc/ole-in-mfc.md)

