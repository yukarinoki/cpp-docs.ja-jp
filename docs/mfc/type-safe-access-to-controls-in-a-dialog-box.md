---
description: 詳細については、「ダイアログボックス内のコントロールへのアクセスの Type-Safe」を参照してください。
title: ダイアログ ボックスのコントロールへのタイプ セーフ アクセス
ms.date: 11/04/2016
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
ms.openlocfilehash: 1c8b3482ee723e95142c9cd19fa6068f32f4ebd0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263830"
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>ダイアログ ボックスのコントロールへのタイプ セーフ アクセス

ダイアログ ボックス内のコントロールは、`CListBox` や `CEdit` などの、MFC コントロール クラスのインターフェイスを使用できます。 コントロール オブジェクトを作成してダイアログ コントロールに追加することができます。 追加すると、クラス インターフェイスを通じてコントロールにアクセスできます (コントロール上で動作するメンバー関数を呼び出します)。 ここで説明する各メソッドは、コントロールに対してタイプ セーフなアクセスが可能です。 これは、エディット ボックスやリスト ボックスなどのコントロールで特に役立ちます。

ダイアログ ボックス内のコントロールと、`CDialog` 派生クラス内の C++ コントロール メンバー変数とを接続するには、次の 2 つの方法があります。

- [コード ウィザードを使用しない方法](../mfc/type-safe-access-to-controls-without-code-wizards.md)

- [コード ウィザードを使用する方法](../mfc/type-safe-access-to-controls-with-code-wizards.md)

## <a name="see-also"></a>関連項目

[ダイアログボックス](../mfc/dialog-boxes.md)
