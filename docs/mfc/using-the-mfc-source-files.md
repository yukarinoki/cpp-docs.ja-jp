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
ms.openlocfilehash: ac8d8ea64de9fd93487b3108857669931e31d0be
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267031"
---
# <a name="using-the-mfc-source-files"></a>MFC ソース ファイルの利用

Microsoft Foundation Class (MFC) ライブラリでは、完全なソース コードを提供します。 ヘッダー ファイル (.h) が \atlmfc\include ディレクトリです。実装ファイル (.cpp) では、\atlmfc\src\mfc ディレクトリにします。

この一連のトピックでは、MFC は各クラスのさまざまな部分、これらのコメントの意味し、各セクション内で検索する期待する必要がありますにコメントを使用している表記規則について説明します。 Visual C ウィザードで、作成するクラスのような規則を使用し、おそらくに役立つこれらの規則の独自のコード。

理解しておくことがあります、**パブリック**、**保護**、および**プライベート**C++ のキーワード。 MFC ヘッダー ファイルを調べるときに、各クラスでこれらの各いくつかあることが表示されます。 1 つ以上のパブリック メンバー変数と関数可能性があります、**パブリック**キーワード。 これは、MFC メンバー変数とアクセス許可の種類ではなく、使用方法に基づいて関数を分離するためです。 MFC を使用して**プライベート**実装の詳細は、一般的に保護されているし、何度もはパブリックでも項目と見なされます控えめ;。 実装の詳細へのアクセスは推奨されていませんが、MFC に、意思決定を残します。

MFC ソース ファイルと MFC アプリケーション ウィザードで作成されるファイルの両方では、(通常はこの順序で) でクラス宣言内で上記のようなコメントを紹介します。

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

この一連のトピックで説明したトピックは次のとおりです。

- [コメントの例](../mfc/an-example-of-the-comments.md)

- [//実装のコメント](../mfc/decrement-implementation-comment.md)

- [/Constructors コメント/](../mfc/decrement-constructors-comment.md)

- [/コメントを属性/](../mfc/decrement-attributes-comment.md)

- [//Operations コメント](../mfc/decrement-operations-comment.md)

- [//Overridables コメント](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
