---
title: 個々 の項目のイメージの設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7f3dbdf4d386e40802d74459dd2854035b5b7c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380602"
---
# <a name="setting-the-images-for-an-individual-item"></a>各項目のイメージの設定
拡張コンボ ボックス項目を使用するイメージのさまざまな種類は内の値によって決まります、 `iImage`、 **iSelectedImage**、および**iOverlay**のメンバー、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)構造体。 各値は、関連付けられているイメージ リストには、コントロールのイメージのインデックスです。 既定では、これらのメンバーを項目のイメージを表示しない、コントロールの原因を 0 に設定されます。 特定の項目のイメージを使用する場合、コンボ ボックス項目を挿入するときにまたは既存のコンボ ボックス項目を変更することで同様に、構造を変更することができます。  
  
## <a name="setting-the-image-for-a-new-item"></a>新しい項目のイメージの設定  
 新しい項目を挿入する場合は、初期化、 `iImage`、 **iSelectedImage**、および**iOverlay**適切な値を持つメンバーを構造化しを呼び出して、項目を挿入[CComboBoxEx::InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem)です。  
  
 次の例は、新しい拡張コンボ ボックス項目を挿入 (`cbi`) 拡張コンボ ボックス コントロールに (`m_comboEx`) の状態を画像 3 つのすべてのインデックスを指定します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]  
  
## <a name="setting-the-image-for-an-existing-item"></a>既存の項目のイメージの設定  
 使用する必要がある既存の項目を変更する場合、**マスク**のメンバー、**受け取る**構造体。  
  
#### <a name="to-modify-an-existing-item-to-use-images"></a>イメージを使用する既存の項目を変更するには  
  
1.  宣言、**受け取る**を構造化し、設定、**マスク**データ メンバーの値に興味のある変更です。  
  
2.  この構造体を使用してへの呼び出しを行う[CComboBoxEx::GetItem](../mfc/reference/ccomboboxex-class.md#getitem)です。  
  
3.  変更、**マスク**、 `iImage`、および**iSelectedImage**適切な値を使用して、新しく返された構造体のメンバーです。  
  
4.  呼び出しを行う[CComboBoxEx::SetItem](../mfc/reference/ccomboboxex-class.md#setitem)、変更された構造体で成功します。  
  
 次の例では、3 番目の拡張コンボ ボックスの項目の選択と選択されていないイメージをスワップしてこの手順を示しています。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)   
 [コントロール](../mfc/controls-mfc.md)

