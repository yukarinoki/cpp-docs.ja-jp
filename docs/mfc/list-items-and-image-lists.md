---
title: リスト項目とイメージ リスト
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
ms.openlocfilehash: d378c6e07280349f9995981ad794039ebc015b25
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353049"
---
# <a name="list-items-and-image-lists"></a>リスト項目とイメージ リスト

リスト コントロール ([CListCtrl](../mfc/reference/clistctrl-class.md)) の "項目" は、アイコン、ラベル、および他の情報 ("サブ項目" の場合もある) で構成されます。

リスト コントロール項目のアイコンは、イメージ リストに含まれています。 1 つのイメージ リストには、アイコン ビューで使用されるフルサイズのアイコンが含まれています。 2 番目のオプションのイメージ リストには、コントロールの他のビューで使用する同じアイコンの小さなバージョンが含まれています。 3 番目のオプション リストには、チェック ボックスなどの "状態" イメージが含まれています。 4 番目の省略可能なリストには、リスト コントロールの個々のヘッダー項目に表示されるイメージが含まれます。

> [!NOTE]
> リスト ビュー コントロールがLVS_SHAREIMAGELISTS スタイルで作成された場合、イメージ リストが使用されなくなったときに、そのリストを破棄する必要があります。 同じイメージ リストを複数のリスト ビュー コントロールに割り当てる場合は、このスタイルを指定します。そうしないと、複数のコントロールが同じイメージ リストを破棄しようとする可能性があります。

リスト項目の詳細については、「Windows SDK の[リスト ビュー イメージ リスト](/windows/win32/Controls/using-list-view-controls)と[アイテムとサブアイテム](/windows/win32/Controls/using-list-view-controls)」を参照してください。 また *、MFC リファレンス*のクラス[CImageList](../mfc/reference/cimagelist-class.md)とこのファミリの[CImageList](../mfc/using-cimagelist.md)の使用も参照してください。

リスト コントロールを作成するには、新しい項目をリストに挿入するときに使用するイメージ リストを指定する必要があります。 次の例は *、m_pImagelist*が型`CImageList`のポインターであり、データ メンバー *m_listctrl*場合のこの`CListCtrl`プロシージャを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]

ただし、リスト ビューやリスト コントロールにアイコンを表示する予定がない場合は、イメージ リストは必要ありません。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
