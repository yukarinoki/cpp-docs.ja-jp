---
title: ヘッダー コントロールでのリストのイメージを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: 2da3737b54c53903f8fc8ff30cccba6165cbde45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-image-lists-with-header-controls"></a>ヘッダー コントロールでのイメージ リストの使い方
ヘッダー項目には、ヘッダー項目内のイメージを表示する機能があります。 関連付けられているイメージ リストに格納された、このイメージは、16 x 16 ピクセルをなり、リスト ビュー コントロールで使用するアイコンの画像と同じ特性を持ちます。 この動作を正常に実装するためにする必要があります最初に作成およびイメージ リストの初期化、リスト コントロールに関連付ける、ヘッダー、およびイメージを表示するヘッダー項目の属性を変更します。  
  
 次の手順は、ヘッダー コントロールへのポインターを使用して、詳細を示しています (`m_pHdrCtrl`) とイメージ リストへのポインター (`m_pHdrImages`)。  
  
### <a name="to-display-an-image-in-a-header-item"></a>ヘッダー項目にイメージを表示するには  
  
1.  新しいイメージ リストの構築 (または既存のイメージ リスト オブジェクトを使用) を使用して、 [CImageList](../mfc/reference/cimagelist-class.md)コンス トラクター、結果のポインターを格納します。  
  
2.  呼び出して、新しいイメージ リスト オブジェクトを初期化[CImageList::Create](../mfc/reference/cimagelist-class.md#create)です。 次のコードでは、この呼び出しの 1 つの例を示します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]  
  
3.  各ヘッダー項目のイメージを追加します。 次のコードでは、次の 2 つの定義済みのイメージを追加します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]  
  
4.  イメージ リストへの呼び出しにヘッダー コントロールに関連付けられる[CHeaderCtrl::SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist)です。  
  
5.  関連付けられているイメージ リストからイメージを表示するヘッダーの項目を変更します。 次の例では、最初のイメージを割り当ててから`m_phdrImages`、最初のヘッダー項目に`m_pHdrCtrl`です。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]  
  
 使用されるパラメーター値の詳細についてを参照してください、関連する[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)です。  
  
> [!NOTE]
>  同じイメージのリストを使用して複数のコントロールを設定することができます。 たとえば、標準のリスト ビュー コントロールでは、可能性があります (16 x 16 ピクセルの画像) のリスト ビュー コントロールの小さいアイコン ビューとリスト ビュー コントロールのヘッダー項目で使用されるイメージ リスト。  
  
## <a name="see-also"></a>関連項目  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)

