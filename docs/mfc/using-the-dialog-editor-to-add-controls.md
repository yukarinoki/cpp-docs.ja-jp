---
description: 詳細については、「ダイアログエディターを使用したコントロールの追加」を参照してください。
title: ダイアログ エディターを使用したコントロールの追加
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controls [MFC], adding to dialog boxes
- Dialog editor, creating controls
- common controls [MFC], adding
ms.assetid: d3f9f994-7e54-4656-a545-42c204557c36
ms.openlocfilehash: a57031539c284529b6ad21d51fd5fd2c409e2a3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314556"
---
# <a name="using-the-dialog-editor-to-add-controls"></a>ダイアログ エディターを使用したコントロールの追加

ダイアログ [エディター](../windows/dialog-editor.md)を使用してダイアログテンプレートリソースを作成する場合は、コントロールパレットからコントロールをドラッグして、ダイアログボックスにドロップします。 これにより、そのコントロール型の仕様がダイアログテンプレートリソースに追加されます。 ダイアログオブジェクトを構築し、その `Create` 関数または `DoModal` メンバー関数を呼び出すと、フレームワークによって Windows コントロールが作成され、画面のダイアログウィンドウに配置されます。

代わりに、必要 [に応じて手動でコントロールを作成](../mfc/adding-controls-by-hand.md) できます。 これはより多くの作業です。

## <a name="see-also"></a>関連項目

[コントロールの作成と使用](../mfc/making-and-using-controls.md)<br/>
[コントロール](../mfc/controls-mfc.md)
