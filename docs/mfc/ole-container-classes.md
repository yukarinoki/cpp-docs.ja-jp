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
ms.openlocfilehash: 61db5310637d13da2d2cc183f12f8f62aa60e328
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447658"
---
# <a name="ole-container-classes"></a>OLE コンテナー クラス

これらのクラスは、コンテナーアプリケーションによって使用されます。 `COleLinkingDoc` と `COleDocument` はどちらも `COleClientItem` オブジェクトのコレクションを管理します。 ドキュメントクラスを `CDocument`から派生させるのではなく、ドキュメントに埋め込まれたオブジェクトへのリンクをサポートするかどうかに応じて、`COleLinkingDoc` または `COleDocument`から派生させます。

別のドキュメントに埋め込まれているか別のドキュメントへのリンクであるドキュメント内の各 OLE 項目を表すには、`COleClientItem` オブジェクトを使用します。

[COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)<br/>
アクティブなドキュメントコンテインメントをサポートします。

[COleDocument](../mfc/reference/coledocument-class.md)<br/>
複合ドキュメントの実装、および基本的なコンテナーのサポートに使用されます。 `CDocItem`から派生したクラスのコンテナーとして機能します。 このクラスは、コンテナードキュメントの基本クラスとして使用でき、`COleServerDoc`の基本クラスとして使用できます。

[COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)<br/>
リンク用のインフラストラクチャを提供する `COleDocument` から派生したクラス。 埋め込みオブジェクトへのリンクをサポートする場合は、`COleDocument` ではなく、このクラスからコンテナーアプリケーションのドキュメントクラスを派生させる必要があります。

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
リッチエディットコントロール内の OLE クライアント項目のリストを保持します。 [CRichEditView](../mfc/reference/cricheditview-class.md)および[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)と共に使用します。

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
`COleClientItem` および `COleServerItem`の抽象基本クラス。 `CDocItem` から派生したクラスのオブジェクトは、ドキュメントの一部を表します。

[COleClientItem](../mfc/reference/coleclientitem-class.md)<br/>
埋め込み OLE またはリンクされた OLE アイテムへのクライアント側の接続の側を表すクライアントアイテムクラス。 このクラスからクライアント項目を派生させます。

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
`CRichEditView` および `CRichEditDoc`と共に使用する場合に、リッチエディットコントロールに格納されている OLE 項目にクライアント側でアクセスできるようにします。

[COleException](../mfc/reference/coleexception-class.md)<br/>
OLE 処理のエラーによって発生する例外。 このクラスは、コンテナーとサーバーの両方で使用されます。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
