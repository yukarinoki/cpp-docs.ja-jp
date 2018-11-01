---
title: CStatusBarCtrl オブジェクトの区画の初期化
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
ms.openlocfilehash: c813ef53f94fb773b62f102a484eed2be859772e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662164"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトの区画の初期化

既定では、ステータス バーには、個別のペインを使用して状態情報が表示されます。 これらのウィンドウ (パーツとも呼ばれます) には、テキスト文字列、アイコン、またはその両方を含めることができます。

使用[呼び出した](../mfc/reference/cstatusbarctrl-class.md#setparts)パーツの数と長さを定義する、ステータス バーになります。 ステータス バーのパーツを作成した後は、呼び出しを行う[SetText](../mfc/reference/cstatusbarctrl-class.md#settext)と[SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon)テキストやステータス バーの特定の部分のアイコンを設定します。 パーツが正常に設定されていると、コントロールが自動的に再描画されます。

次の例では、既存を初期化します`CStatusBarCtrl`オブジェクト (`m_StatusBarCtrl`) 4 つのペインにし、2 番目の部分で、アイコン (IDI_ICON1) といくつかのテキストを設定します。

[!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

モードの設定の詳細について、`CStatusBarCtrl`単純で、「」を参照するオブジェクト[CStatusBarCtrl オブジェクト モードの設定](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)します。

## <a name="see-also"></a>関連項目

[CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

