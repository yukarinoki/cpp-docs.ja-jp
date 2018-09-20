---
title: ヘッダー コントロールでリストのイメージを使用して |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 477ed175e6f8e81acdae5c873d1436e6c3dbbd60
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423560"
---
# <a name="using-image-lists-with-header-controls"></a>ヘッダー コントロールでのイメージ リストの使い方

ヘッダー項目には、ヘッダー項目内のイメージを表示する機能があります。 このイメージは、関連付けられているイメージ リストに格納されている 16 x 16 ピクセルは、リスト ビュー コントロールで使用されるアイコンのイメージとして同じ特性を持ちます。 この動作を正常に実装するために最初に作成しイメージ リストの初期化、ヘッダー コントロール、リストを関連付けるしてイメージを表示するヘッダー項目の属性を変更します。

次の手順は、ヘッダー コントロールへのポインターを使用して、詳細を示しています (`m_pHdrCtrl`) とイメージ リストへのポインター (`m_pHdrImages`)。

### <a name="to-display-an-image-in-a-header-item"></a>ヘッダー項目にイメージを表示するには

1. 新しいイメージ リストの構築 (または既存のイメージ リスト オブジェクトを使用) を使用して、 [CImageList](../mfc/reference/cimagelist-class.md)コンス トラクター、結果のポインターを格納します。

1. 新しいイメージ リスト オブジェクトを呼び出すことによって初期化[CImageList::Create](../mfc/reference/cimagelist-class.md#create)します。 次のコードは、この呼び出しの 1 つの例です。

     [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. 各ヘッダー項目のイメージを追加します。 次のコードは、2 つの定義済みのイメージを追加します。

     [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. イメージ リストへの呼び出しでヘッダー コントロールに関連付けられる[CHeaderCtrl::SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist)します。

1. 関連付けられているイメージ リストからイメージを表示するヘッダー アイテムを変更します。 次の例では、最初のイメージを割り当ててから`m_phdrImages`、最初のヘッダー項目に`m_pHdrCtrl`します。

     [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

使用されるパラメーター値の詳細については、参照、関連する[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)します。

> [!NOTE]
>  同じイメージのリストを使用して複数のコントロールを含めることは可能になります。 たとえば、標準的なリスト ビュー コントロールでは、可能性があります (16 x 16 ピクセルの画像) のリスト ビュー コントロールの小さいアイコン ビューとリスト ビュー コントロールのヘッダー項目で使用されるイメージ リスト。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)

