---
description: 詳細については、「ウィザードでのプロパティシート」を参照してください。
title: ウィザードとしてのプロパティ シート
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
ms.openlocfilehash: 2a68a16936e8ab134bab2fe78dac0d29c125b4db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248867"
---
# <a name="property-sheets-as-wizards"></a>ウィザードとしてのプロパティ シート

ウィザードのプロパティシートの重要な特性は、ナビゲーションがタブではなく [次へ] または [完了]、[戻る]、および [キャンセル] の各ボタンと共に提供されることです。 この機能を利用するには、プロパティシートオブジェクトで[CPropertySheet::D oModal](../mfc/reference/cpropertysheet-class.md#domodal)を呼び出す前に、 [CPropertySheet:: setwizardmode](../mfc/reference/cpropertysheet-class.md#setwizardmode)を呼び出す必要があります。

ユーザーは、あるページから別のページに移動している間に、同じ [CPropertyPage:: OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) と [CPropertyPage:: OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) 通知を受け取ります。 [次へ] ボタンと [完了] ボタンは相互に排他的なコントロールです。つまり、一度に表示されるのは、そのうちの1つだけです。 最初のページで、[次へ] ボタンが有効になっている必要があります。 ユーザーが最後のページにある場合、[完了] ボタンが有効になっている必要があります。 これは、フレームワークによって自動的には実行されません。 これを実現するには、最後のページで [CPropertySheet:: SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) を呼び出す必要があります。

すべての既定のボタンを表示するには、[完了] ボタンを表示し、[次へ] ボタンを移動 mush ます。 その後、[戻る] ボタンを移動して、[次へ] ボタンへの相対位置を維持します。

## <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>関連項目

[プロパティシート](../mfc/property-sheets-mfc.md)
