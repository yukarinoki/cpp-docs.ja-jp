---
description: 詳細については、「CStatusBarCtrl オブジェクトの部分の初期化」を参照してください。
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
ms.openlocfilehash: 52eb738f5fe54a54e54a6415a602a68123869b32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197531"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトの区画の初期化

既定では、ステータスバーに個別のペインを使用してステータス情報が表示されます。 これらのペイン (パートとも呼ばれます) には、テキスト文字列、アイコン、またはその両方を含めることができます。

[SetParts](reference/cstatusbarctrl-class.md#setparts)を使用して、ステータスバーに表示される部分の数と長さを定義します。 ステータスバーのパーツを作成したら、 [SetText](reference/cstatusbarctrl-class.md#settext) と [SetIcon](reference/cstatusbarctrl-class.md#seticon) を呼び出して、ステータスバーの特定の部分のテキストまたはアイコンを設定します。 パーツが正常に設定されると、コントロールは自動的に再描画されます。

次の例では、 `CStatusBarCtrl` 4 つのペインを持つ既存のオブジェクト () を初期化した `m_StatusBarCtrl` 後、2番目の部分でアイコン (IDI_ICON1) と一部のテキストを設定します。

[!code-cpp[NVC_MFCControlLadenDialog#31](codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

オブジェクトのモードを simple に設定する方法の詳細につい `CStatusBarCtrl` ては、「 [CStatusBarCtrl オブジェクトのモードの設定](setting-the-mode-of-a-cstatusbarctrl-object.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CStatusBarCtrl の使い方](using-cstatusbarctrl.md)<br/>
[コントロール](controls-mfc.md)
