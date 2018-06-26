---
title: CDocument からのドキュメント クラスの派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a81f3c3a36f049e3f47401efa31b36677b3b9ba6
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931750"
---
# <a name="deriving-a-document-class-from-cdocument"></a>CDocument からのドキュメント クラスの派生
ドキュメントし、アプリケーションのデータを管理します。 MFC アプリケーション ウィザードで提供されるドキュメント クラスを使用するには、次の操作を行う必要があります。  
  
-   クラスを派生`CDocument`ドキュメントの種類ごとにします。  
  
-   各ドキュメントのデータを格納するためのメンバー変数を追加します。  
  
-   オーバーライド`CDocument`の`Serialize`ドキュメント クラスのメンバー関数。 `Serialize` 書き込みをして、ディスクからのドキュメントのデータを読み取ります。  
  
## <a name="other-document-functions-often-overridden"></a>多くの場合、オーバーライドされたその他のドキュメント関数  
 その他をオーバーライドすることも`CDocument`メンバー関数。 具体的には、オーバーライドする必要があります[でも実質的](../mfc/reference/cdocument-class.md#onnewdocument)と[かまいません](../mfc/reference/cdocument-class.md#onopendocument)ドキュメントのデータ メンバーを初期化して[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)を破棄するにはデータを動的に割り当てられます。 オーバーライド可能なメンバーについては、クラスを参照してください。 [CDocument](../mfc/reference/cdocument-class.md)で、 *『 MFC リファレンス*です。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメントの使い方](../mfc/using-documents.md)

