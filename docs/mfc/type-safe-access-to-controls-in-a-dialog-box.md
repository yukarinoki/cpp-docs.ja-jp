---
title: ダイアログ ボックスのコントロールへのタイプ セーフ アクセス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ed8a374c34eacc48e1d877e704fdc60a20f33d9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422715"
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>ダイアログ ボックスのコントロールへのタイプ セーフ アクセス

ダイアログ ボックス内のコントロールは、`CListBox` や `CEdit` などの、MFC コントロール クラスのインターフェイスを使用できます。 コントロール オブジェクトを作成してダイアログ コントロールに追加することができます。 追加すると、クラス インターフェイスを通じてコントロールにアクセスできます (コントロール上で動作するメンバー関数を呼び出します)。 ここで説明する各メソッドは、コントロールに対してタイプ セーフなアクセスが可能です。 これは、エディット ボックスやリスト ボックスなどのコントロールで特に役立ちます。

ダイアログ ボックス内のコントロールと、`CDialog` 派生クラス内の C++ コントロール メンバー変数とを接続するには、次の 2 つの方法があります。

- [コード ウィザードを使用しません。](../mfc/type-safe-access-to-controls-without-code-wizards.md)

- [コード ウィザードを使用しました。](../mfc/type-safe-access-to-controls-with-code-wizards.md)

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)

