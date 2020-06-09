---
title: OLE コンテナー クラス
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
ms.openlocfilehash: 596b94e7fdbb5d9dc1862867001f6c01c1aea7b2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617805"
---
# <a name="ole-container-classes"></a>OLE コンテナー クラス

これらのクラスは、コンテナーアプリケーションによって使用されます。 `COleLinkingDoc`と `COleDocument` の両方がオブジェクトのコレクションを管理し `COleClientItem` ます。 ドキュメントクラスをから派生させるのではなく、 `CDocument` `COleLinkingDoc` `COleDocument` ドキュメントに埋め込まれたオブジェクトへのリンクをサポートするかどうかに応じて、またはから派生させます。

別の `COleClientItem` ドキュメントに埋め込まれているか別のドキュメントへのリンクであるドキュメント内の各 OLE 項目を表すには、オブジェクトを使用します。

[COleDocObjectItem](reference/coledocobjectitem-class.md)<br/>
アクティブなドキュメントコンテインメントをサポートします。

[COleDocument](reference/coledocument-class.md)<br/>
複合ドキュメントの実装、および基本的なコンテナーのサポートに使用されます。 から派生したクラスのコンテナーとして機能 `CDocItem` します。 このクラスは、コンテナードキュメントの基本クラスとして使用でき、の基本クラスとして使用でき `COleServerDoc` ます。

[COleLinkingDoc](reference/colelinkingdoc-class.md)<br/>
`COleDocument`リンク用のインフラストラクチャを提供するから派生したクラス。 `COleDocument`埋め込みオブジェクトへのリンクをサポートする場合は、ではなく、このクラスからコンテナーアプリケーションのドキュメントクラスを派生させる必要があります。

[CRichEditDoc](reference/cricheditdoc-class.md)<br/>
リッチエディットコントロール内の OLE クライアント項目のリストを保持します。 [CRichEditView](reference/cricheditview-class.md)および[CRichEditCntrItem](reference/cricheditcntritem-class.md)と共に使用します。

[CDocItem](reference/cdocitem-class.md)<br/>
およびの抽象基本 `COleClientItem` クラス `COleServerItem` 。 から派生したクラスのオブジェクトは `CDocItem` 、ドキュメントの一部を表します。

[COleClientItem](reference/coleclientitem-class.md)<br/>
埋め込み OLE またはリンクされた OLE アイテムへのクライアント側の接続の側を表すクライアントアイテムクラス。 このクラスからクライアント項目を派生させます。

[CRichEditCntrItem](reference/cricheditcntritem-class.md)<br/>
およびと共に使用する場合に、リッチエディットコントロールに格納されている OLE 項目にクライアント側でアクセスできるようにし `CRichEditView` `CRichEditDoc` ます。

[COleException](reference/coleexception-class.md)<br/>
OLE 処理のエラーによって発生する例外。 このクラスは、コンテナーとサーバーの両方で使用されます。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
