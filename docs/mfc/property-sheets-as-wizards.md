---
title: ウィザードとしてのプロパティ シート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 634359763f24e02987664fe3de1094e3e7fec64c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347332"
---
# <a name="property-sheets-as-wizards"></a>ウィザードとしてのプロパティ シート
ウィザードのプロパティ シートの主な特徴は、タブの代わりに、[次へ] または [完了]、バックアップ、および [キャンセル] ボタンでナビゲーションが提供されることです。 呼び出す必要がある[CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode)呼び出す前に[する](../mfc/reference/cpropertysheet-class.md#domodal)プロパティ シート オブジェクトでこの機能を活用するためにします。  
  
 ユーザーは同じ[CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive)と[CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive)別のページに 1 つのページから移動する際に通知します。 [次へ] および [完了] ボタンは、相互に排他的なコントロールです。つまり、一度にうち片方だけが表示されます。 最初のページで、[次へ] ボタンを有効にする必要があります。 ユーザーが最後のページにある場合は、[完了] ボタンを有効にする必要があります。 これを行わない自動的に、フレームワークによってです。 呼び出す必要がある[CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons)これを実現するために最後のページにします。  
  
 すべての既定のボタンを表示するは、[完了] ボタンを表示し、[次へ] ボタンを移動します。 次のボタンに相対的位置を維持するため、[戻る] ボタンを移動します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [プロパティ シート](../mfc/property-sheets-mfc.md)

