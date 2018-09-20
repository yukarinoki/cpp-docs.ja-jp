---
title: --Operations コメント |Microsoft Docs
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
ms.openlocfilehash: 73c4a7a70c9f2ed987337426793bd462c2a94309
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372497"
---
# <a name="-operations-comment"></a>// Operations コメント

`// Operations`の MFC クラスの宣言セクションには、処理を実行したり、(操作) の操作を実行するオブジェクトで呼び出すことのできるメンバー関数が含まれています。 これらの関数は通常**const**副作用があるためです。 仮想またはクラスのニーズに応じて非があります。 通常、これらのメンバーはパブリックです。

一覧表示するクラスからサンプル`CStdioFile`で、[コメントの例](../mfc/an-example-of-the-comments.md)、一覧にこのコメントの下の 2 つのメンバー関数が含まれています:`ReadString`と`WriteString`。

属性を持つようには、操作をさらに分割します。

## <a name="see-also"></a>関連項目

[MFC ソース ファイルの利用](../mfc/using-the-mfc-source-files.md)<br/>
[コメントの例](../mfc/an-example-of-the-comments.md)<br/>
[//Implementation コメント](../mfc/decrement-implementation-comment.md)<br/>
[//Constructors コメント](../mfc/decrement-constructors-comment.md)<br/>
[//Attributes コメント](../mfc/decrement-attributes-comment.md)<br/>
[//Overridables コメント](../mfc/decrement-overridables-comment.md)

