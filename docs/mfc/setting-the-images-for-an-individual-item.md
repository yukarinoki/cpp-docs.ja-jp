---
title: 各項目のイメージの設定
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
ms.openlocfilehash: 61e152534dbea09fbca0af819b0847e82a1c4146
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512074"
---
# <a name="setting-the-images-for-an-individual-item"></a>各項目のイメージの設定

拡張コンボ ボックスの項目で使用されるイメージのさまざまな種類は内の値によって決まります、*画像を*、 *iSelectedImage*、および*iOverlay* のメンバー[受け取る](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema)構造体。 各値は、コントロールの関連付けられているイメージ リスト内のイメージのインデックスです。 既定では、これらのメンバーを項目のイメージを表示しないコントロールの原因を 0 に設定されます。 特定の項目のイメージを使用する場合、コンボ ボックス アイテムを挿入する場合または既存のコンボ ボックス項目を変更することで状況に応じて、構造を変更することができます。

## <a name="setting-the-image-for-a-new-item"></a>新しい項目のイメージの設定

新しい項目を挿入する場合は、初期化、*画像を*、 *iSelectedImage*、および*iOverlay*への呼び出しを持つ項目を挿入し、適切な値を持つメンバーを構造体であり[CComboBoxEx::InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem)します。

次の例は、新しい拡張コンボ ボックス項目を挿入 (`cbi`) 拡張コンボ ボックス コントロールに (`m_comboEx`)、3 つのすべての状態のイメージのインデックスを指定します。

[!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]

## <a name="setting-the-image-for-an-existing-item"></a>既存の項目のイメージの設定

使用する必要がある既存の項目を変更する場合は、*マスク*のメンバー、**受け取る**構造体。

#### <a name="to-modify-an-existing-item-to-use-images"></a>イメージを使用する既存の項目を変更するには

1. 宣言を**受け取る**構造体し、設定、*マスク*変更興味があるデータ メンバーの値にします。

1. 呼び出しをこの構造体を使用して行う[CComboBoxEx::GetItem](../mfc/reference/ccomboboxex-class.md#getitem)します。

1. 変更、*マスク*、*画像を*、および*iSelectedImage*適切な値を使用して、新しく返された構造体のメンバー。

1. 呼び出す[CComboBoxEx::SetItem](../mfc/reference/ccomboboxex-class.md#setitem)、変更された構造体に渡します。

次の例では、3 番目の拡張コンボ ボックス アイテムの選択と選択されていないイメージをスワップしてこの手順を示しています。

[!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]

## <a name="see-also"></a>関連項目

[CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)<br/>
[コントロール](../mfc/controls-mfc.md)

