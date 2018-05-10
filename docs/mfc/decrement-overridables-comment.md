---
title: --Overridables コメント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Overridables comment in MFC source files
- MFC source files, Overridables comment
- overriding, Overridables comment in MFC source files
- comments, MFC
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b71d61175e5446ac33dd0ff6a011d06f601b5a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="-overridables-comment"></a>// Overridables コメント
`// Overridables`の MFC クラス宣言のセクションには、基本クラスの動作を変更する必要がある場合、派生クラスでオーバーライドできる仮想関数が含まれています。 これらの名前は通常"On"で始まる必ずしも必要はありません。 オーバーライドして多くの場合、実装したり、何らかの"callback"または「フック」を提供する関数が設計されています 通常、これらのメンバーは保護されます。  
  
 MFC 自体の純粋仮想関数は常に、このセクションの配置します。 C++ の純粋仮想関数では、フォームのいずれかです。  
  
 `virtual void OnDraw( ) = 0;`  
  
 クラスを一覧表示するサンプルの`CStdioFile`の[のコメントの例](../mfc/an-example-of-the-comments.md)一覧に overridables セクションが含まれていません。 クラス**CDocument**、その一方で、約 10 のオーバーライド可能なメンバー関数を一覧表示します。  
  
 一部のクラス内もコメントを参照してください可能性があります`// Advanced Overridables`です。 これらは、のみ高度な関数をオーバーライドするプログラマが試みる必要があります。 おそらく、これらをオーバーライドする必要があります。  
  
> [!NOTE]
>  この記事で説明する規則も機能も、一般に、(以前の OLE オートメーション) オートメーション メソッドおよびプロパティに対してします。 オートメーション メソッドは、MFC の操作に似ています。 オートメーションのプロパティは、MFC の属性に似ています。 (以前の OLE コントロールの ActiveX コントロールのサポート) オートメーション イベントは、MFC のオーバーライド可能なメンバー関数に似ています。  
  
## <a name="see-also"></a>関連項目  
 [MFC ソース ファイルを使用します。](../mfc/using-the-mfc-source-files.md)   
 [コメントの例](../mfc/an-example-of-the-comments.md)   
 [//Implementation コメント](../mfc/decrement-implementation-comment.md)   
 [//Constructors コメント](../mfc/decrement-constructors-comment.md)   
 [//Attributes コメント](../mfc/decrement-attributes-comment.md)   
 [//Operations コメント](../mfc/decrement-operations-comment.md)

