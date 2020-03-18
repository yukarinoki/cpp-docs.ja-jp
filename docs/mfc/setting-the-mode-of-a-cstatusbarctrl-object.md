---
title: CStatusBarCtrl オブジェクトのモードの設定
ms.date: 11/04/2016
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
ms.openlocfilehash: 79b499533196447898ce62ea9dc86c1674fc0302
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446433"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトのモードの設定

`CStatusBarCtrl` オブジェクトには、単純と非単純の2つのモードがあります。 ほとんどの場合、ステータスバーコントロールには1つ以上の部分が含まれ、テキストと、おそらくアイコンやアイコンが表示されます。 これは、非単純モードと呼ばれます。 このモードの詳細については、「 [CStatusBarCtrl オブジェクトの部分の初期化](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md)」を参照してください。

ただし、1行のテキストのみを表示する必要がある場合もあります。 この場合、必要に応じて simple モードが十分です。 `CStatusBarCtrl` オブジェクトのモードを simple に変更するには、 [Setsimple](../mfc/reference/cstatusbarctrl-class.md#setsimple)メンバー関数を呼び出します。 ステータスバーコントロールが簡易モードになったら、`SetText` メンバー関数を呼び出してテキストを設定し、 *Npane*パラメーターの値として255を渡します。

[Issimple](../mfc/reference/cstatusbarctrl-class.md#issimple)関数を使用すると、`CStatusBarCtrl` オブジェクトがどのモードであるかを判断できます。

> [!NOTE]
>  ステータスバーオブジェクトが単純から単純に、またはその逆に変更されている場合は、すぐにウィンドウが再描画され、該当する場合は定義されたパーツが自動的に復元されます。

## <a name="see-also"></a>参照

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
