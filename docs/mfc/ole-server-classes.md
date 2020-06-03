---
title: OLE サーバー クラス
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
ms.openlocfilehash: 92dec514611dcce7d6c666fdd271843e69561637
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447595"
---
# <a name="ole-server-classes"></a>OLE サーバー クラス

これらのクラスは、サーバーアプリケーションによって使用されます。 サーバードキュメントは、`CDocument`からではなく、`COleServerDoc` から派生します。 `COleServerDoc` は `COleLinkingDoc`から派生しているため、サーバードキュメントは、リンクをサポートするコンテナーでもあることに注意してください。

`COleServerItem` クラスは、文書またはドキュメントの一部を表し、別のドキュメントに埋め込むことも、リンク先として使用することもできます。

`COleIPFrameWnd` と `COleResizeBar` では、オブジェクトがコンテナー内にある間はインプレース編集がサポートされ、`COleTemplateServer` はドキュメントとビューのペアの作成をサポートしているため、他のアプリケーションからの OLE オブジェクトを編集できます。

[COleServerDoc](../mfc/reference/coleserverdoc-class.md)<br/>
サーバーアプリケーションドキュメントクラスの基本クラスとして使用されます。 `COleServerDoc` オブジェクトは、`COleServerItem` オブジェクトとの対話によってサーバー全体のサポートを提供します。 ビジュアル編集機能は、クラスライブラリのドキュメント/ビューアーキテクチャを使用して提供されます。

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
`COleClientItem` および `COleServerItem`の抽象基本クラス。 `CDocItem` から派生したクラスのオブジェクトは、ドキュメントの一部を表します。

[含ん](../mfc/reference/coleserveritem-class.md)<br/>
`COleServerDoc` 項目への OLE インターフェイスを表すために使用されます。 通常、ドキュメントの埋め込み部分を表す `COleServerDoc` オブジェクトが1つあります。 ドキュメントの一部へのリンクをサポートするサーバーでは、多くの `COleServerItem` オブジェクトがあり、それぞれがドキュメントの一部へのリンクを表します。

[クラスからではなく、](../mfc/reference/coleipframewnd-class.md)<br/>
サーバードキュメントをその場で編集しているときに、ビューのフレームウィンドウを提供します。

[COleResizeBar](../mfc/reference/coleresizebar-class.md)<br/>
インプレースサイズ変更のための標準ユーザーインターフェイスを提供します。 このクラスのオブジェクトは、常に `COleIPFrameWnd` オブジェクトと共に使用されます。

[COleTemplateServer](../mfc/reference/coletemplateserver-class.md)<br/>
フレームワークのドキュメント/ビューアーキテクチャを使用してドキュメントを作成するために使用されます。 `COleTemplateServer` オブジェクトは、そのほとんどの作業を、関連付けられた `CDocTemplate` オブジェクトにデリゲートします。

[COleException](../mfc/reference/coleexception-class.md)<br/>
OLE 処理のエラーによって発生する例外。 このクラスは、コンテナーとサーバーの両方で使用されます。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
