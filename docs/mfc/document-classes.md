---
description: '詳細情報: ドキュメントクラス'
title: ドキュメント クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.document
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
ms.openlocfilehash: 7f5bd3011dec84cad20b10668e0a997838e79dbb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330281"
---
# <a name="document-classes"></a>ドキュメント クラス

ドキュメントテンプレートオブジェクトによって作成されたドキュメントクラスオブジェクトは、アプリケーションのデータを管理します。 これらのクラスのいずれかからドキュメントのクラスを派生させます。

ドキュメントクラスオブジェクトは、ビューオブジェクトと対話します。 View objects は、ウィンドウのクライアント領域を表し、ドキュメントのデータを表示して、ユーザーが対話できるようにします。 ドキュメントとビューは、ドキュメントテンプレートオブジェクトによって作成されます。

[CDocument](reference/cdocument-class.md)<br/>
アプリケーション固有のドキュメントの基本クラス。 ドキュメントクラスまたはクラスをから派生させ `CDocument` ます。

[COleDocument](reference/coledocument-class.md)<br/>
複合ドキュメントの実装、および基本的なコンテナーのサポートに使用されます。 [CDocItem](reference/cdocitem-class.md)から派生したクラスのコンテナーとして機能します。 このクラスは、コンテナードキュメントの基本クラスとして使用でき、の基本クラスとして使用でき `COleServerDoc` ます。

[COleLinkingDoc](reference/colelinkingdoc-class.md)<br/>
`COleDocument`リンク用のインフラストラクチャを提供するから派生したクラス。 `COleDocument`埋め込みオブジェクトへのリンクをサポートする場合は、ではなく、このクラスからコンテナーアプリケーションのドキュメントクラスを派生させる必要があります。

[CRichEditDoc](reference/cricheditdoc-class.md)<br/>
リッチエディットコントロール内の OLE クライアント項目のリストを保持します。 [CRichEditView](reference/cricheditview-class.md)および[CRichEditCntrItem](reference/cricheditcntritem-class.md)と共に使用します。

[COleServerDoc](reference/coleserverdoc-class.md)<br/>
サーバーアプリケーションドキュメントクラスの基本クラスとして使用されます。 `COleServerDoc` オブジェクトは、 [COleServerItem](reference/coleserveritem-class.md) オブジェクトとの対話によって、サーバーのサポートを大量に提供します。 ビジュアル編集機能は、クラスライブラリのドキュメント/ビューアーキテクチャを使用して提供されます。

[CHtmlEditDoc](reference/chtmleditdoc-class.md)<br/>
は、MFC のドキュメント/ビューアーキテクチャのコンテキスト内で、WebBrowser HTML 編集プラットフォームの機能を [CHtmlEditView](reference/chtmleditview-class.md)で提供します。

## <a name="related-classes"></a>関連クラス

ドキュメントクラスオブジェクトは、永続的なものにすることができます。つまり、状態をストレージメディアに書き込んで読み戻すことができます。 MFC には、 `CArchive` ドキュメントのデータをストレージメディアに転送しやすくするクラスが用意されています。

[CArchive](reference/carchive-class.md)<br/>
Cooperates [を使用して](reference/cfile-class.md) 、シリアル化によってオブジェクトの永続的なストレージを実装します ( [CObject:: Serialize](reference/cobject-class.md#serialize)を参照)。

ドキュメントには OLE オブジェクトを含めることもできます。 `CDocItem` は、サーバーおよびクライアントアイテムの基本クラスです。

[CDocItem](reference/cdocitem-class.md)<br/>
[COleClientItem](reference/coleclientitem-class.md)と[COleServerItem](reference/coleserveritem-class.md)の抽象基本クラス。 から派生したクラスのオブジェクトは `CDocItem` 、ドキュメントの一部を表します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
