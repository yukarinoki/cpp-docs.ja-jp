---
title: メニューとリソース (OLE)
ms.date: 11/04/2016
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
ms.openlocfilehash: e705f28476df7b594f9648aee8317759211c66c9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626210"
---
# <a name="menus-and-resources-ole"></a>メニューとリソース (OLE)

この一連の記事では、MFC OLE ドキュメントアプリケーションでのメニューとリソースの使用について説明します。

OLE ビジュアル編集では、コンテナーとサーバー (コンポーネント) アプリケーションの両方を起動して使用できるようになるため、OLE ドキュメントアプリケーションによって提供される、メニューやその他のリソースに追加の要件があります。 たとえば、フルサーバーアプリケーションは、次の3つのモードのいずれかで実行できます。

- スタンドアロン。

- コンテナーのコンテキスト内の項目を編集するために使用します。

- コンテナーのコンテキストの外部にある項目を編集するために開きます。多くの場合、別のウィンドウに表示されます。

これには、アプリケーションの可能なモードごとに1つずつ、3つの異なるメニューレイアウトが必要です。 アクセラレータテーブルは、新しいモードごとにも必要です。 コンテナーアプリケーションでは、インプレースライセンス認証がサポートされている場合とサポートされていない場合があります。存在する場合は、新しいメニュー構造と関連するアクセラレータテーブルが必要です。

インプレースライセンス認証を使用するには、コンテナーとサーバーアプリケーションがメニュー、ツールバー、ステータスバーの領域に対してネゴシエートする必要があります。 すべてのリソースは、この点を念頭に置いて設計する必要があります。 記事のメニュー[とリソース: メニューのマージ](menus-and-resources-menu-merging.md)については、このトピックで詳しく説明します。

これらの問題のため、アプリケーションウィザードで作成された OLE ドキュメントアプリケーションは、最大4つの個別のメニューとアクセラレータテーブルリソースを持つことができます。 これらは、次の理由で使用されます。

|リソース名|使用|
|-------------------|---------|
|IDR_MAINFRAME|ファイルが開かれていない場合は MDI アプリケーションで、開いているファイルに関係なく SDI アプリケーションでは使用されます。 これは、非 OLE アプリケーションで使用される標準のメニューです。|
|IDR_ の \<project> 種類|ファイルが開いている場合に、MDI アプリケーションで使用します。 アプリケーションがスタンドアロンで実行されている場合に使用されます。 これは、非 OLE アプリケーションで使用される標準のメニューです。|
|IDR_ \<project> TYPE_SRVR_IP|オブジェクトがインプレースで開かれている場合に、サーバーまたはコンテナーによって使用されます。|
|IDR_ \<project> TYPE_SRVR_EMB|インプレースアクティベーションを使用せずにオブジェクトが開かれた場合に、サーバーアプリケーションによって使用されます。|

これらの各リソース名は、メニューと通常はアクセラレータテーブルを表します。 同様のスキームは、アプリケーションウィザードで作成されていない MFC アプリケーションで使用する必要があります。

次の記事では、コンテナー、サーバー、および埋め込み先でのライセンス認証を実装するために必要なメニューのマージに関連するトピックについて説明します。

- [メニューとリソース : コンテナーの変更点](menus-and-resources-container-additions.md)

- [メニューとリソース: サーバーの変更点](menus-and-resources-server-additions.md)

- [メニューとリソース : メニューの結合](menus-and-resources-menu-merging.md)

## <a name="see-also"></a>関連項目

[OLE●ole○](ole-in-mfc.md)
