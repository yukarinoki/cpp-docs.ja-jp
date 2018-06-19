---
title: --Implementation コメント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1556c690478b242d929b8a5558264218ddf0b63e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343035"
---
# <a name="-implementation-comment"></a>// Implementation コメント
`// Implementation`セクションは、任意の MFC クラス宣言の最も重要な部分です。  
  
 このセクションでは、すべての実装の詳細を格納します。 メンバー変数とメンバー関数の両方が、このセクションに表示できます。 MFC の将来のリリースで変更があるこの行の下のすべてのものでした。 これを回避できない場合を除き、以下の詳細に依存する必要がありますしないして、`// Implementation`行です。 さらに、実装行以下に宣言されたメンバーは記載いないが、何らかの実装は、テクニカル ノートで説明します。 仮想関数のオーバーライド、基底クラスでは、セクションに関係なく、基底クラス関数が定義されて、関数が基底クラスの実装をオーバーライドするファクトは、実装の詳細と見なされるため、このセクションに存在します。 通常、これらのメンバーは保護されて、常にではありません。  
  
 注意してください、`CStdioFile`下にあるを一覧表示する[コメントの例を](../mfc/an-example-of-the-comments.md)メンバーが以下に宣言された、`// Implementation`コメントとして宣言することは**パブリック**、 `protected`、または`private`. だけ、今後変わる可能性があるために、これらのメンバーを注意が必要を使用する必要があります。 グループのメンバーとしてを宣言する**パブリック**正常に機能するクラス ライブラリの実装に必要な場合があります。 ただし、これはいないというように宣言されているメンバーを安全に使用可能性があります。  
  
> [!NOTE]
>  上または下に、残りの種類のコメントを見つけることがあります、`// Implementation`コメントです。 どちらの場合は、その下で宣言されたメンバーの種類、について説明します。 次に出現する場合、`// Implementation`コメントの追加、メンバーが将来的に MFC のバージョンで変更があると想定する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [MFC ソース ファイルを使用します。](../mfc/using-the-mfc-source-files.md)   
 [コメントの例](../mfc/an-example-of-the-comments.md)   
 [//Constructors コメント](../mfc/decrement-constructors-comment.md)   
 [//Attributes コメント](../mfc/decrement-attributes-comment.md)   
 [//Operations コメント](../mfc/decrement-operations-comment.md)   
 [//Overridables コメント](../mfc/decrement-overridables-comment.md)

