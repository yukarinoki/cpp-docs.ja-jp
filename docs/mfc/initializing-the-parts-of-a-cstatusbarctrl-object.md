---
title: CStatusBarCtrl オブジェクトの区画の初期化
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
ms.openlocfilehash: a5b65a2bbb68eaa7058f3514bb95a5209a0e5e71
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444453"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトの区画の初期化

既定では、ステータスバーに個別のペインを使用してステータス情報が表示されます。 これらのペイン (パートとも呼ばれます) には、テキスト文字列、アイコン、またはその両方を含めることができます。

[SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts)を使用して、ステータスバーに表示される部分の数と長さを定義します。 ステータスバーのパーツを作成したら、 [SetText](../mfc/reference/cstatusbarctrl-class.md#settext)と[SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon)を呼び出して、ステータスバーの特定の部分のテキストまたはアイコンを設定します。 パーツが正常に設定されると、コントロールは自動的に再描画されます。

次の例では、4つのペインを持つ既存の `CStatusBarCtrl` オブジェクト (`m_StatusBarCtrl`) を初期化し、2番目の部分にアイコン (IDI_ICON1) と一部のテキストを設定します。

[!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

`CStatusBarCtrl` オブジェクトのモードを simple に設定する方法の詳細については、「 [CStatusBarCtrl オブジェクトのモードの設定](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)」を参照してください。

## <a name="see-also"></a>参照

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
