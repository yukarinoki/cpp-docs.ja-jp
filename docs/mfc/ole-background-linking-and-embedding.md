---
title: 'OLE 概要: リンクと埋め込み |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE embedded items [MFC]
- item types [MFC], defined
- item types [MFC]
- OLE [MFC], linked items
- linked items (OLE) [MFC]
- embedded objects [MFC]
- OLE items [MFC], types
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5dc7a5770c98323187dbabcd8c2a7bb9eb652de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-background-linking-and-embedding"></a>OLE 概要 : リンクと埋め込み
コンテナー アプリケーションで [貼り付け] コマンドを使用すると、埋め込まれたコンポーネント、または埋め込みアイテムが作成できます。 埋め込みアイテムのソース データはそれを格納する OLE ドキュメントの一部として格納されます。 この方法では、ワード プロセッサのドキュメントのドキュメント ファイルは、テキストを含めることができ、ビットマップ、グラフ、式、またはその他の種類のデータも含めることができます。  
  
 別のアプリケーションからデータを組み込むを別の方法を提供する OLE: リンクされたコンポーネント、またはリンクされた項目は、リンクを作成します。 リンクされた項目を作成する手順は、貼り付け コマンドではなくリンク貼り付け コマンドを使用することを除いて、埋め込み項目を作成するのに似ています。 埋め込みのコンポーネントとは異なりは、リンクされたコンポーネントは、別のファイルに多くの場合は、元のデータへのパスを格納します。  
  
 たとえば、作業している、単語内でプロセッサの文書、スプレッドシートのセルにリンクされた項目を作成していては、元のスプレッドシート ドキュメントに、リンク アイテムのデータが格納されます。 ワード プロセッサの文書には、項目がある、つまり、元のスプレッドシート ドキュメントへのリンクが含まれているを指定する情報のみが含まれています。 セルをダブルクリックするとスプレッドシート アプリケーションが起動される保存された場所から元のスプレッドシート ドキュメントが読み込まれます。  
  
 OLE のすべての項目では、埋め込みまたはリンクされている、かどうかを作成したアプリケーションに基づいて関連付けられている型があります。 たとえば、Microsoft ペイント ブラシ項目は、1 つの種類の項目と Microsoft Excel 項目は、別の型。 ただし、一部のアプリケーションは、1 つ以上の項目の種類を作成できます。 たとえば、Microsoft Excel では、ワークシートの項目、グラフの項目、およびマクロ シート項目を作成できます。 これらの各項目クラス識別子を使用して、システムによって一意に識別することができますか**CLSID**です。  
  
## <a name="see-also"></a>関連項目  
 [OLE の背景知識](../mfc/ole-background.md)   
 [OLE 概要: コンテナーとサーバー](../mfc/ole-background-containers-and-servers.md)   
 [コンテナー: クライアント アイテム](../mfc/containers-client-items.md)   
 [サーバー: サーバー アイテム](../mfc/servers-server-items.md)

