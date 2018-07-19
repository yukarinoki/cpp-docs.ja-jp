---
title: OLE サーバー クラス |Microsoft ドキュメント
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
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9d0c75325c62a92f65c56f2c76350bf752228fd
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932222"
---
# <a name="ole-server-classes"></a>OLE サーバー クラス
これらのクラスは、サーバー アプリケーションによって使用されます。 サーバー ドキュメントがから派生した`COleServerDoc`からではなく`CDocument`です。 ため`COleServerDoc`から派生した`COleLinkingDoc`サーバーのドキュメントには、リンクをサポートするコンテナーがすることもできます。  
  
 `COleServerItem`クラスは、ドキュメントまたは別のドキュメントに埋め込まれているしたりできるにリンクされているドキュメントの一部を表します。  
  
 `COleIPFrameWnd` `COleResizeBar`インプレース オブジェクトが、コンテナーの間の編集をサポートし、`COleTemplateServer`他のアプリケーションから OLE オブジェクトを編集できるように、ドキュメント/ビューのペアの作成をサポートします。  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 サーバー アプリケーションのドキュメント クラスの基底クラスとして使用します。 `COleServerDoc` オブジェクトとの対話を通じてサーバーのサポートの大部分を提供する`COleServerItem`オブジェクト。 ビジュアル編集機能は、クラス ライブラリのドキュメント/ビュー アーキテクチャを使用して提供されます。  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 抽象基本クラスの`COleClientItem`と`COleServerItem`です。 派生したクラスのオブジェクトを`CDocItem`文書の一部を表します。  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 OLE インターフェイスを表すために使用`COleServerDoc`項目。 通常は 1 つ`COleServerDoc`ドキュメントの埋め込みの一部を表すオブジェクト。 ドキュメントの部分へのリンクをサポートするサーバーであります多く`COleServerItem`ドキュメントの部分にリンクを表すオブジェクト。  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 サーバー ドキュメントを一括で編集するときに、ビューのフレーム ウィンドウを提供します。  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 埋め込み先サイズ変更するためには、標準のユーザー インターフェイスを提供します。 このクラスのオブジェクトは、常と組み合わせて使用`COleIPFrameWnd`オブジェクト。  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 フレームワークのドキュメント/ビュー アーキテクチャを使用してドキュメントを作成するために使用します。 A`COleTemplateServer`オブジェクトは、関連付けられている作業のほとんどを代行`CDocTemplate`オブジェクト。  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE の処理中のエラーによる例外。 このクラスは、コンテナーとサーバーの両方で使用されます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

