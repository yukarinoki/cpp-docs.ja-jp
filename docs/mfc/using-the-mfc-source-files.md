---
title: MFC ソース ファイルの利用
ms.date: 11/04/2016
helpviewer_keywords:
- public members
- source files
- MFC, source files
- MFC source files
- comments, MFC
- private member access
- protected member access
- source files, MFC
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
ms.openlocfilehash: 6f23f792f750e4352494bf3e4bde08f0fe360439
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980489"
---
# <a name="using-the-mfc-source-files"></a>MFC ソース ファイルの利用

MFC (Microsoft Foundation Class) ライブラリには、完全なソースコードが用意されています。 ヘッダーファイル (.h) は、\ atlmfc\ include ディレクトリにあります。実装ファイル (.cpp) は、\ atlmfcディレクトリにあります。

この一連の記事では、MFC が各クラスのさまざまな部分をコメント化する際に使用する規則、これらのコメントの意味、および各セクションで検索する必要があることについて説明します。 ビジュアルC++ウィザードでは、独自に作成したクラスに対して同様の規則が使用されます。また、これらの規則が独自のコードに役立つ場合もあります。

**Public**、 **protected**、および**private** C++キーワードについて理解している場合もあります。 MFC ヘッダーファイルでは、各クラスに複数のクラスが含まれていることがわかります。 たとえば、パブリックメンバーの変数と関数は、複数の**public**キーワードの下にある場合があります。 これは、MFC では、メンバー変数と関数が、許可されるアクセスの種類ではなく、使用方法に基づいて分離されるためです。 MFC では、控えめに使用します。 実装の詳細と見なされる項目も**保護**され、多くの場合、**パブリック**になります。 実装の詳細へのアクセスは推奨されていませんが、MFC では決定を行いません。

Mfc のソースファイルと MFC アプリケーションウィザードによって作成されるヘッダーファイルの両方で、次のようなコメントがクラス宣言 (通常はこの順序) に含まれています。

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

この記事ファミリで説明するトピックは次のとおりです。

- [コメントの例](../mfc/an-example-of-the-comments.md)

- [//実装コメント](../mfc/decrement-implementation-comment.md)

- [//コンストラクターコメント](../mfc/decrement-constructors-comment.md)

- [//属性コメント](../mfc/decrement-attributes-comment.md)

- [//操作コメント](../mfc/decrement-operations-comment.md)

- [//Overridables コメント](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
