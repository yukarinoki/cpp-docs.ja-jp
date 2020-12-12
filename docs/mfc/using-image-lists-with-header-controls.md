---
description: '詳細情報: ヘッダーコントロールでのイメージリストの使用'
title: ヘッダー コントロールでのイメージ リストの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
ms.openlocfilehash: 549f54c9fae7e0e0a63c726f4b75d2adeb38eef8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322732"
---
# <a name="using-image-lists-with-header-controls"></a>ヘッダー コントロールでのイメージ リストの使い方

ヘッダー項目には、ヘッダー項目内に画像を表示する機能があります。 このイメージは、関連付けられたイメージリストに格納され、16 x 16 ピクセルで、リストビューコントロールで使用されるアイコンイメージと同じ特性を持ちます。 この動作を正常に実装するには、まずイメージリストを作成して初期化し、そのリストをヘッダーコントロールに関連付けてから、イメージを表示するヘッダー項目の属性を変更する必要があります。

次の手順は、ヘッダーコントロールへのポインター ( `m_pHdrCtrl` ) とイメージリストへのポインター () を使用した詳細を示してい `m_pHdrImages` ます。

### <a name="to-display-an-image-in-a-header-item"></a>ヘッダー項目に画像を表示するには

1. [コンストラクターを使用して](../mfc/reference/cimagelist-class.md)、新しいイメージリストを構築 (または既存のイメージリストオブジェクトを使用) して、結果のポインターを格納します。

1. [CImageList:: Create](../mfc/reference/cimagelist-class.md#create)を呼び出して、新しいイメージリストオブジェクトを初期化します。 この呼び出しの1つの例を次のコードに示します。

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. 各ヘッダー項目のイメージを追加します。 次のコードでは、定義済みの2つのイメージを追加します。

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. [CHeaderCtrl:: SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist)の呼び出しを使用して、イメージリストをヘッダーコントロールに関連付けます。

1. ヘッダー項目を変更して、関連付けられているイメージリストのイメージを表示します。 次の例では、最初のイメージをから `m_phdrImages` 最初のヘッダー項目に割り当て `m_pHdrCtrl` ます。

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

使用されるパラメーター値の詳細については、関連する [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)を参照してください。

> [!NOTE]
> 同じイメージリストを使用して、複数のコントロールを持つことができます。 たとえば、標準のリストビューコントロールでは、リストビューコントロールの小さいアイコンビューとリストビューコントロールのヘッダー項目の両方で使用されるイメージリスト (16 x 16 ピクセルイメージ) が存在する場合があります。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)
