---
title: 拡張コンボ ボックス コントロールでのイメージ リストの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c9a701871631fead48c22b1ffb2cbc3c386b960
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383346"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>拡張コンボ ボックス コントロールでのイメージ リストの使い方
拡張コンボ ボックス コントロールの主な機能は、コンボ ボックス コントロール内の各項目にはイメージ リストのイメージを関連付ける機能です。 各項目は次の 3 つのさまざまなイメージを表示できません: 選択した状態、その選択解除状態、およびオーバーレイを表す 3 番目に 1 つのいずれか。  
  
 次の手順では、拡張コンボ ボックス コントロールのイメージ リストが関連付けられます。  
  
### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>拡張コンボ ボックス コントロールにイメージ リストを関連付ける  
  
1.  新しいイメージ リストの構築 (または、既存のイメージ リスト オブジェクトを使用して) を使用して、 [CImageList](../mfc/reference/cimagelist-class.md)コンス トラクターと結果のポインターを格納します。  
  
2.  呼び出して、新しいイメージ リスト オブジェクトを初期化[CImageList::Create](../mfc/reference/cimagelist-class.md#create)です。 次のコードでは、この呼び出しの 1 つの例を示します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]  
  
3.  各状態の省略可能なイメージの追加: 選択したか、解除、およびオーバーレイします。 次のコードでは、次の 3 つの定義済みのイメージを追加します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]  
  
4.  イメージ リストへの呼び出しを持つコントロールに関連付けられる[CComboBoxEx::SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist)です。  
  
 イメージ リストがコントロールに関連付けられると、各項目は、3 つの状態を使用するイメージを個別に指定できます。 詳細については、次を参照してください。[個々 の項目のイメージの設定](../mfc/setting-the-images-for-an-individual-item.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)   
 [コントロール](../mfc/controls-mfc.md)

