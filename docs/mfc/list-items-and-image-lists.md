---
title: リスト項目とイメージ リスト
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
ms.openlocfilehash: 1679b5c59c6dd55ca47c70ea7c880493304ebf4e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304315"
---
# <a name="list-items-and-image-lists"></a>リスト項目とイメージ リスト

リスト コントロールの"item"([CListCtrl](../mfc/reference/clistctrl-class.md))、アイコン、ラベル、および可能性があります (「サブ」) では、その他の情報で構成されます。

リスト コントロール項目のアイコン イメージ リストに格納されます。 1 つのイメージ リストにはアイコン表示で使用されるフルサイズのアイコンが含まれています。 2 番目、省略可能、イメージの一覧には、コントロールの他のビューで使用する同じアイコンの縮小版が含まれています。 3 番目の省略可能なリストには、特定のビューで小さいアイコンの前に表示するためのチェック ボックスなどの"state"イメージが含まれています。 4 番目の省略可能なリストには、リスト コントロールの個々 のヘッダー項目に表示されるイメージが含まれています。

> [!NOTE]
>  LVS_SHAREIMAGELISTS スタイルを使用してリスト ビュー コントロールを作成して使用が不要になった場合は、イメージ リストを破棄する必要があります。 同じイメージを割り当てる場合は、このスタイルは、複数のリスト ビュー コントロールにリストを指定します。それ以外の場合、1 つ以上のコントロールは同じイメージのリストを破棄しよう可能性があります。

リスト項目の詳細については、次を参照してください。[リスト ビューのイメージが一覧表示](/windows/desktop/Controls/using-list-view-controls)と[項目とサブ項目](/windows/desktop/Controls/using-list-view-controls)Windows SDK に含まれています。 クラスを参照してください[CImageList](../mfc/reference/cimagelist-class.md)で、 *MFC リファレンス*と[を使用して CImageList](../mfc/using-cimagelist.md)記事のこのファミリにします。

リスト コントロールを作成するには、リストに新しい項目を挿入するときに使用されるイメージのリストを指定する必要があります。 次の例では、この手順では、場所*m_pImagelist*型のポインターは、`CImageList`と*m_listctrl*は、`CListCtrl`データ メンバー。

[!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]

ただし、リスト ビューまたはリスト コントロールにアイコンを表示する予定がない場合は、イメージ リストを必要はありません。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
