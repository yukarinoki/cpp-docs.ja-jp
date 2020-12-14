---
description: 詳細については、「コードウィザードを使用しないコントロールへのアクセス Type-Safe」を参照してください。
title: コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
ms.openlocfilehash: 1e59353a17f0d841cd69fa64f792dcc7cdbfa6ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263778"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス

コントロールへのタイプセーフなアクセスを作成するための最初の方法は、次の例のように、インラインメンバー関数を使用して、クラスのメンバー関数の戻り値の型 `CWnd` `GetDlgItem` を適切な C++ コントロール型にキャストします。

[!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]

このメンバー関数を使用すると、次のようなコードを使用して、タイプセーフな方法でコントロールにアクセスできます。

[!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]

## <a name="see-also"></a>関連項目

[ダイアログボックス内のコントロールへのタイプセーフアクセス](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[コードウィザードを使用したコントロールへのタイプセーフアクセス](../mfc/type-safe-access-to-controls-with-code-wizards.md)
