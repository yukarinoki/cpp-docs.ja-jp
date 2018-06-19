---
title: OLE コンテナー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfdff6023beeedfa14d37e5b404fa3c223691b85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349050"
---
# <a name="ole-container-classes"></a>OLE コンテナー クラス
これらのクラスは、コンテナー アプリケーションによって使用されます。 両方`COleLinkingDoc`と`COleDocument`のコレクションを管理`COleClientItem`オブジェクト。 ドキュメント クラスの派生ではなく**CDocument**から派生します`COleLinkingDoc`または`COleDocument`文書に埋め込まれているオブジェクトへのリンクでサポートが必要かどうかによって異なります。  
  
 使用して、`COleClientItem`別のドキュメントから埋め込むまたは別のドキュメントへのリンクは、ドキュメント内の各 OLE 項目を表すオブジェクト。  
  
 [関数](../mfc/reference/coledocobjectitem-class.md)  
 Active ドキュメント コンテインメントをサポートしています。  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 複合ドキュメントの実装、および基本的なコンテナー サポートに対して使用されます。 派生したクラスのコンテナーとして機能する`CDocItem`です。 このクラスは、文書化しの基本クラスは、コンテナーの基底クラスとして使用できる`COleServerDoc`です。  
  
 [直接](../mfc/reference/colelinkingdoc-class.md)  
 派生したクラス`COleDocument`をリンクするため、インフラストラクチャを提供します。 代わりにこのクラスから、コンテナー アプリケーションのドキュメント クラスを派生させる必要があります`COleDocument`埋め込みオブジェクトへのリンクをサポートするようにする場合。  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 リッチ エディット コントロールに含まれる OLE クライアント アイテムの一覧を保持します。 と共に使用[CRichEditView](../mfc/reference/cricheditview-class.md)と[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)です。  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 抽象基本クラスの`COleClientItem`と`COleServerItem`です。 派生したクラスのオブジェクトを`CDocItem`文書の一部を表します。  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 埋め込みまたはリンクされている OLE アイテムへの接続のクライアント側を表すクライアント アイテム クラスです。 クライアント アイテムは、このクラスから派生します。  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 クライアント側のアクセスは、項目で使用する場合は、リッチ エディット コントロールに格納されている OLE`CRichEditView`と`CRichEditDoc`です。  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE の処理中のエラーによる例外。 このクラスは、コンテナーとサーバーの両方で使用されます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

