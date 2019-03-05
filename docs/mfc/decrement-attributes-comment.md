---
title: --Attributes コメントします。
ms.date: 11/04/2016
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
ms.openlocfilehash: a74d0f9d6ffb0bd2d057cf46f7308d8b6a81f98c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303236"
---
# <a name="-attributes-comment"></a>// Attributes コメント

`// Attributes` MFC クラスの宣言のセクションには、オブジェクトのパブリックの属性 (またはプロパティ) が含まれています。 通常これらは、メンバー変数、または関数を取得または設定します。 "Get"と"Set"関数は、仮想できない可能性があります。 "Get"関数は、通常、 **const**、ほとんどの場合、副作用があるないためです。 これらのメンバーは通常はパブリックです。protected および private の属性は、通常、implementation セクションにあります。

クラスを一覧表示するサンプルで`CStdioFile`[コメントの例](../mfc/an-example-of-the-comments.md)、一覧には、1 つのメンバー変数が含まれています。 *m_pStream*します。 クラス`CDC`このコメントの下にある 20 個近くのメンバーを一覧表示されます。

> [!NOTE]
>  などの大クラス`CDC`と`CWnd`、単に 1 つのグループのすべての属性を一覧表示をわかりやすくするためには追加できません非常に多くのメンバーがあります。 このような場合は、クラス ライブラリは、さらに、メンバーを記述するその他のコメントを見出しとして使用します。 たとえば、`CDC`使用`// Device-Context Functions`、 `// Drawing Tool Functions`、`// Drawing Attribute Functions`など。 属性を表すグループは、上記で説明した通常の構文に従います。 OLE クラスの多くがあるという実装セクション`// Interface Maps`します。

## <a name="see-also"></a>関連項目

[MFC ソース ファイルの利用](../mfc/using-the-mfc-source-files.md)<br/>
[コメントの例](../mfc/an-example-of-the-comments.md)<br/>
[//Implementation コメント](../mfc/decrement-implementation-comment.md)<br/>
[//Constructors コメント](../mfc/decrement-constructors-comment.md)<br/>
[//Operations コメント](../mfc/decrement-operations-comment.md)<br/>
[//Overridables コメント](../mfc/decrement-overridables-comment.md)
