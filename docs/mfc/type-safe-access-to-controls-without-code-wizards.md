---
title: コード ウィザードを使用しないコントロールへのタイプ セーフ アクセス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2685c946b9ee1c738ee83f9413b7fd955857febb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438341"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス

タイプ セーフ アクセス コントロールを作成する最初のアプローチは、クラスの戻り値の型をキャストするインライン メンバー関数を使用して`CWnd`の`GetDlgItem`この例のように、適切な C++ コントロール型にメンバー関数。

[!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]

このメンバー関数は、コードを次のようなタイプ セーフな方法でコントロールにアクセスし使用できます。

[!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-with-code-wizards.md)

