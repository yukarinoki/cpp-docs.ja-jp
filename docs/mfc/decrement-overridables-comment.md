---
title: --Overridables コメント
ms.date: 11/04/2016
helpviewer_keywords:
- Overridables comment in MFC source files
- MFC source files, Overridables comment
- overriding, Overridables comment in MFC source files
- comments, MFC
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
ms.openlocfilehash: 90d6a585f62de589299147edce87332d96c6dbb8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57282046"
---
# <a name="-overridables-comment"></a>// Overridables コメント

`// Overridables`の MFC クラスの宣言セクションには、基底クラスの動作を変更する必要がある場合、派生クラスでオーバーライドできる仮想関数が含まれています。 これらの名前は通常"On"で始まるは厳密には必要ありませんが。 無効にして多くの場合、実装したり、ある種の"callback"または「フック」を提供する関数が設計されています 通常、これらのメンバーは保護されます。

MFC 自体は、純粋仮想関数がこのセクションでは常に配置されます。 C++ では、純粋仮想関数では、フォームの 1 つです。

`virtual void OnDraw( ) = 0;`

一覧表示するクラスからサンプル`CStdioFile`で、[コメントの例](../mfc/an-example-of-the-comments.md)一覧にオーバーライド可能な関数のセクションが含まれていません。 クラス`CDocument`、その一方で、約 10 のオーバーライド可能なメンバー関数を一覧表示します。

いくつかのクラス内もコメントを参照してください可能性があります`// Advanced Overridables`します。 これらは高度なだけ関数をオーバーライドするプログラマが試行する必要があります。 おそらく、これらをオーバーライドする必要があります。

> [!NOTE]
>  この記事で説明されている規則もうまく機能、一般に、(以前の OLE オートメーション) オートメーション メソッドとプロパティ。 オートメーション メソッドは、MFC の操作に似ています。 オートメーションのプロパティは、MFC の属性に似ています。 (以前の OLE コントロールの ActiveX コントロールのサポート) オートメーション イベントは、MFC のオーバーライド可能なメンバー関数に似ています。

## <a name="see-also"></a>関連項目

[MFC ソース ファイルの利用](../mfc/using-the-mfc-source-files.md)<br/>
[コメントの例](../mfc/an-example-of-the-comments.md)<br/>
[//Implementation コメント](../mfc/decrement-implementation-comment.md)<br/>
[//Constructors コメント](../mfc/decrement-constructors-comment.md)<br/>
[//Attributes コメント](../mfc/decrement-attributes-comment.md)<br/>
[//Operations コメント](../mfc/decrement-operations-comment.md)
