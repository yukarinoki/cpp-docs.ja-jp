---
title: --Implementation コメント
ms.date: 11/04/2016
helpviewer_keywords:
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
ms.openlocfilehash: 377997b66c5b9c005d1e1bee24890b756621b672
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261051"
---
# <a name="-implementation-comment"></a>// Implementation コメント

`// Implementation`セクションは、任意の MFC クラス宣言の最も重要な部分です。

このセクションでは、すべての実装の詳細を格納します。 メンバー変数とメンバー関数は、このセクションに表示できます。 MFC の将来のリリースで変更があるこの行の下のすべてのものでした。 以下の詳細に依存する必要がありますしない限り、これを回避することはできません、`// Implementation`行。 さらに、実装行の下に宣言されたメンバーは記載いないが、いくつかの実装は、テクニカル ノートで説明します。 基本クラスの仮想関数のオーバーライドは、どのセクションに関係なく、基底クラスの関数が、定義関数が基底クラスの実装をオーバーライドするという事実は、実装の詳細と見なされるため、このセクションに存在します。 通常、これらのメンバーが保護されているとは限りません。

注意してください、`CStdioFile`リスト[コメントの例](../mfc/an-example-of-the-comments.md)以下の宣言されたメンバー、`// Implementation`コメントとして宣言することがあります**パブリック**、 **を保護**、または**プライベート**します。 今後変更される可能性があるため、慎重にこれらのメンバーを使用する必要がありますのみ。 メンバーとしてのグループを宣言する**パブリック**正常に機能するクラス ライブラリの実装に必要な場合があります。 ただし、これは限りませんように宣言されたメンバーを安全に使用可能性があります。

> [!NOTE]
>  残りの種類の上または下のコメントを見つけることがあります、`// Implementation`コメント。 どちらの場合は、その下に宣言されたメンバーの種類がについて説明します。 次に出現する場合、`// Implementation`コメントの追加、メンバーがで将来のバージョンの MFC で変更される可能性を想定してください。

## <a name="see-also"></a>関連項目

[MFC ソース ファイルの利用](../mfc/using-the-mfc-source-files.md)<br/>
[コメントの例](../mfc/an-example-of-the-comments.md)<br/>
[//Constructors コメント](../mfc/decrement-constructors-comment.md)<br/>
[//Attributes コメント](../mfc/decrement-attributes-comment.md)<br/>
[//Operations コメント](../mfc/decrement-operations-comment.md)<br/>
[//Overridables コメント](../mfc/decrement-overridables-comment.md)
