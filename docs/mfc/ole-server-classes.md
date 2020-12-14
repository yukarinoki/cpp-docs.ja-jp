---
description: 詳細については、「OLE サーバークラス」を参照してください。
title: OLE サーバー クラス
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
ms.openlocfilehash: a2f60f148d6a24323ca6546e633c30103b315ee2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243992"
---
# <a name="ole-server-classes"></a>OLE サーバー クラス

これらのクラスは、サーバーアプリケーションによって使用されます。 サーバードキュメントは、 `COleServerDoc` からではなくから派生 `CDocument` します。 `COleServerDoc`はから派生しているため `COleLinkingDoc` 、サーバードキュメントはリンクをサポートするコンテナーでもあることに注意してください。

クラスは、文書 `COleServerItem` またはドキュメントの一部を表し、別のドキュメントに埋め込んだり、リンク先として使用したりできます。

`COleIPFrameWnd` と `COleResizeBar` は、オブジェクトがコンテナー内にあるときのインプレース編集をサポートし、 `COleTemplateServer` 他のアプリケーションからの OLE オブジェクトを編集できるように、ドキュメント/ビューペアの作成をサポートします。

[COleServerDoc](reference/coleserverdoc-class.md)<br/>
サーバーアプリケーションドキュメントクラスの基本クラスとして使用されます。 `COleServerDoc` オブジェクトを使用すると、オブジェクトとの対話によってサーバーのサポートが強化され `COleServerItem` ます。 ビジュアル編集機能は、クラスライブラリのドキュメント/ビューアーキテクチャを使用して提供されます。

[CDocItem](reference/cdocitem-class.md)<br/>
およびの抽象基本 `COleClientItem` クラス `COleServerItem` 。 から派生したクラスのオブジェクトは `CDocItem` 、ドキュメントの一部を表します。

[COleServerItem](reference/coleserveritem-class.md)<br/>
項目への OLE インターフェイスを表すために使用され `COleServerDoc` ます。 通常、 `COleServerDoc` ドキュメントの埋め込み部分を表すオブジェクトが1つあります。 ドキュメントの一部へのリンクをサポートするサーバーでは、多く `COleServerItem` のオブジェクトがあり、それぞれがドキュメントの一部へのリンクを表します。

[クラスからではなく、](reference/coleipframewnd-class.md)<br/>
サーバードキュメントをその場で編集しているときに、ビューのフレームウィンドウを提供します。

[COleResizeBar](reference/coleresizebar-class.md)<br/>
インプレースサイズ変更のための標準ユーザーインターフェイスを提供します。 このクラスのオブジェクトは、常にオブジェクトと共に使用され `COleIPFrameWnd` ます。

[COleTemplateServer](reference/coletemplateserver-class.md)<br/>
フレームワークのドキュメント/ビューアーキテクチャを使用してドキュメントを作成するために使用されます。 オブジェクトは、 `COleTemplateServer` そのほとんどの作業を、関連付けられたオブジェクトにデリゲートし `CDocTemplate` ます。

[COleException](reference/coleexception-class.md)<br/>
OLE 処理のエラーによって発生する例外。 このクラスは、コンテナーとサーバーの両方で使用されます。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
