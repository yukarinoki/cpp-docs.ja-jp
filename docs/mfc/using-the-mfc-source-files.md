---
title: MFC を使用して、ソース ファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73177d8b73d5f4be6d886b0bda84f1e1241488cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384336"
---
# <a name="using-the-mfc-source-files"></a>MFC ソース ファイルの利用
Microsoft Foundation Class (MFC) ライブラリでは、完全なソース コードを提供します。 ヘッダー ファイル (.h) が \atlmfc\include ディレクトリです。実装ファイル (.cpp) は、\atlmfc\src\mfc ディレクトリにします。  
  
 この一連のトピックでは、MFC は各クラスのさまざまな部分、これらのコメントの意味、および各セクションの内容を期待できる新機能にコメントを使用している表記規則について説明します。 Visual C ウィザードで、作成するクラスのような規則を使用し、おそらくに役立つこれらの規則の独自のコード。  
  
 精通している可能性があります、**パブリック**、 `protected`、および`private`C++ のキーワードです。 MFC ヘッダー ファイルを見るときに、各クラスでこれらの各いくつかあることが表示されます。 たとえば、パブリック メンバー変数と関数いる可能性があります複数**パブリック**キーワード。 これは、MFC メンバー変数とアクセス許可の種類ではなく、使用方法に基づいて関数を分離するためです。 MFC を使用して`private`慎重; アイテムもと見なされて実装の詳細については、一般的に保護されている、回数はパブリックです。 実装の詳細へのアクセスは推奨されていませんが、MFC に、意思決定のままです。  
  
 MFC ソース ファイルと MFC アプリケーション ウィザードで作成されるファイルの両方で (通常この順序で) クラス宣言内で上記のようなコメントが表示されます。  
  
 `// Constructors`  
  
 `// Attributes`  
  
 `// Operations`  
  
 `// Overridables`  
  
 `// Implementation`  
  
 この一連のトピックで説明されているトピックは次のとおりです。  
  
-   [コメントの例](../mfc/an-example-of-the-comments.md)  
  
-   [/実装のコメント](../mfc/decrement-implementation-comment.md)  
  
-   [//Constructors コメント](../mfc/decrement-constructors-comment.md)  
  
-   [またはコメントを属性/](../mfc/decrement-attributes-comment.md)  
  
-   [//Operations コメント](../mfc/decrement-operations-comment.md)  
  
-   [//Overridables コメント](../mfc/decrement-overridables-comment.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)

