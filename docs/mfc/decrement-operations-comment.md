---
title: --Operations コメント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Operations comment in MFC source files
- comments, MFC
- MFC source files, Operations comments
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee6bf4a330a5fdf1ac294157e69dab39b5f2bdd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342272"
---
# <a name="-operations-comment"></a>// Operations コメント
`// Operations`の MFC クラス宣言のセクションには、操作を実行したり、(操作を実行する) アクションを実行するオブジェクトで呼び出すことができるメンバー関数が含まれています。 これらの関数は通常**const**副作用があるためです。 仮想またはクラスのニーズに応じて、非仮想があります。 通常、これらのメンバーはパブリックです。  
  
 クラスを一覧表示するサンプルで`CStdioFile`の[のコメントの例](../mfc/an-example-of-the-comments.md)、一覧には、このコメントの下の 2 つのメンバー関数が含まれています:`ReadString`と`WriteString`です。  
  
 同様に、属性は、操作をさらに分割します。  
  
## <a name="see-also"></a>関連項目  
 [MFC ソース ファイルを使用します。](../mfc/using-the-mfc-source-files.md)   
 [コメントの例](../mfc/an-example-of-the-comments.md)   
 [//Implementation コメント](../mfc/decrement-implementation-comment.md)   
 [//Constructors コメント](../mfc/decrement-constructors-comment.md)   
 [//Attributes コメント](../mfc/decrement-attributes-comment.md)   
 [//Overridables コメント](../mfc/decrement-overridables-comment.md)

