---
title: ヘッダー コントロールでのイメージ リストの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
ms.openlocfilehash: 8002c16d1cdf5e0683b642001409b6da9c260660
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366469"
---
# <a name="using-image-lists-with-header-controls"></a>ヘッダー コントロールでのイメージ リストの使い方

ヘッダー項目には、ヘッダー項目内に画像を表示する機能があります。 関連付けられたイメージ リストに格納されているこのイメージは、16 x 16 ピクセルで、リスト ビュー コントロールで使用されるアイコン イメージと同じ特性を持ちます。 この動作を正常に実装するには、まずイメージ リストを作成して初期化し、リストをヘッダー コントロールに関連付け、次にイメージを表示するヘッダー項目の属性を変更する必要があります。

ヘッダー コントロール ( ) へのポインターとイメージ リスト (`m_pHdrCtrl``m_pHdrImages`) へのポインターを使用した詳細を次の手順に示します。

### <a name="to-display-an-image-in-a-header-item"></a>ヘッダー項目にイメージを表示するには

1. [CImageList](../mfc/reference/cimagelist-class.md)コンストラクターを使用して、新しいイメージ リストを構築します (または既存のイメージ リスト オブジェクトを使用して、結果のポインターを格納します)。

1. を呼び出すことによって、新しいイメージ リスト オブジェクト[を初期化します](../mfc/reference/cimagelist-class.md#create)。 次のコードは、この呼び出しの一例です。

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. 各ヘッダー項目のイメージを追加します。 次のコードは、2 つの定義済みイメージを追加します。

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. イメージ リストをヘッダー コントロールに関連付け、呼び出しを使用して[CHeaderCtrl::SetImageList を呼び出します](../mfc/reference/cheaderctrl-class.md#setimagelist)。

1. ヘッダー項目を変更して、関連付けられたイメージ リストのイメージを表示します。 次の例では、最初のイメージ`m_phdrImages`を から最初のヘッダー項目に代入`m_pHdrCtrl`します。

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

使用されるパラメーター値の詳細については、 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)を参照してください。

> [!NOTE]
> 同じイメージ リストを使用して複数のコントロールを使用できます。 たとえば、標準のリスト ビュー コントロールでは、リスト ビュー コントロールの小さなアイコン ビューとリスト ビュー コントロールのヘッダー項目の両方で使用されるイメージ リスト (16 x 16 ピクセルのイメージ) が存在する可能性があります。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)
