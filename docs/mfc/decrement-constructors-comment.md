---
title: --Constructors コメントします。
ms.date: 11/04/2016
helpviewer_keywords:
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
ms.openlocfilehash: ee36ad991f2a19211b494010d6ff0a5338b80557
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480705"
---
# <a name="-constructors-comment"></a>// Constructors コメント

`// Constructors` MFC クラスの宣言のセクション (C++ の) コンス トラクターと実際にオブジェクトを使用するために必要なすべての初期化関数を宣言します。 たとえば、`CWnd::Create`ため、使用する前に、コンス トラクターのセクションでは、`CWnd`オブジェクト、その必要があります「を完全に構築」まず、C++ コンス トラクターを呼び出すし、呼び出すことによって、`Create`関数。 通常、これらのメンバーはパブリックです。

たとえば、クラス`CStdioFile`の下の一覧に示したが 1 つ、3 つのコンス トラクターを持つ[コメントの例](../mfc/an-example-of-the-comments.md)します。

## <a name="see-also"></a>関連項目

[MFC ソース ファイルの利用](../mfc/using-the-mfc-source-files.md)<br/>
[//Implementation コメント](../mfc/decrement-implementation-comment.md)<br/>
[//Attributes コメント](../mfc/decrement-attributes-comment.md)<br/>
[//Operations コメント](../mfc/decrement-operations-comment.md)<br/>
[//Overridables コメント](../mfc/decrement-overridables-comment.md)

