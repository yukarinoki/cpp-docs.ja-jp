---
title: ダイアログ エディターを使用してコントロールを追加する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controls [MFC], adding to dialog boxes
- Dialog editor, creating controls
- common controls [MFC], adding
ms.assetid: d3f9f994-7e54-4656-a545-42c204557c36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ffbfad4025e9daf72a9555ca69a8639cba6d68c5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374724"
---
# <a name="using-the-dialog-editor-to-add-controls"></a>ダイアログ エディターを使用したコントロールの追加

ダイアログ テンプレート リソースを作成する場合、[ダイアログ エディター](../windows/dialog-editor.md)、コントロール パレットからコントロールをドラッグし、ダイアログ ボックスにドロップします。 これにより、そのコントロール型の仕様がダイアログ テンプレート リソースを追加します。 ダイアログ オブジェクトと呼び出しを構築する際にその`Create`または`DoModal`メンバー関数は、フレームワークが Windows コントロールを作成し、画面のダイアログ ウィンドウに配置されます。

代わりにできます[コントロールを手動で作成](../mfc/adding-controls-by-hand.md)たい場合。 これより多くの作業です。

## <a name="see-also"></a>関連項目

[コントロールの作成方法と使い方](../mfc/making-and-using-controls.md)<br/>
[コントロール](../mfc/controls-mfc.md)

