---
description: '詳細情報: 拡張コンボボックスコントロールでのイメージリストの使用'
title: 拡張コンボ ボックス コントロールでのイメージ リストの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
ms.openlocfilehash: 9fb4b70f91a8ffc3d0175ec855cd005de10da280
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154371"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>拡張コンボ ボックス コントロールでのイメージ リストの使い方

拡張コンボボックスコントロールの主な機能は、イメージリストのイメージをコンボボックスコントロールの個々の項目と関連付ける機能です。 各項目には3つの異なるイメージを表示できます。1つは選択された状態、もう1つは非選択状態、もう1つはオーバーレイイメージ用です。

次の手順では、イメージリストを拡張コンボボックスコントロールに関連付けます。

### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>イメージリストを拡張コンボボックスコントロールに関連付けるには

1. [CImageList](../mfc/reference/cimagelist-class.md)コンストラクターを使用し、結果のポインターを格納して、新しいイメージリストを構築します (または、既存のイメージリストオブジェクトを使用します)。

1. [CImageList:: Create](../mfc/reference/cimagelist-class.md#create)を呼び出して、新しいイメージリストオブジェクトを初期化します。 この呼び出しの1つの例を次のコードに示します。

   [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]

1. 可能な状態ごとにオプションのイメージ ([選択] または [選択しない]、および [オーバーレイ]) を追加します。 次のコードでは、3つの定義済みイメージを追加します。

   [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]

1. [CComboBoxEx:: SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist)の呼び出しを使用して、イメージリストをコントロールに関連付けます。

イメージリストがコントロールに関連付けられたら、各項目で使用できる3つの状態のイメージを個別に指定できます。 詳細については、「 [個々の項目のイメージを設定](../mfc/setting-the-images-for-an-individual-item.md)する」を参照してください。

## <a name="see-also"></a>関連項目

[CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)<br/>
[コントロール](../mfc/controls-mfc.md)
