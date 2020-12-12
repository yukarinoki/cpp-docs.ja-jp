---
description: 詳細については、「リスト項目とイメージリスト」を参照してください。
title: リスト項目とイメージ リスト
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
ms.openlocfilehash: 674c67c2eb104d86f0bd80732469129b6c70e0f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283369"
---
# <a name="list-items-and-image-lists"></a>リスト項目とイメージ リスト

リストコントロール ([CListCtrl](reference/clistctrl-class.md)) の "項目" は、アイコン、ラベル、および場合によっては ("サブ項目" 内の) 他の情報で構成されます。

リストコントロール項目のアイコンは、イメージリストに含まれています。 1つのイメージリストには、アイコンビューで使用されるフルサイズのアイコンが含まれています。 2番目のオプションのイメージリストには、コントロールの他のビューで使用する同じアイコンの小さいバージョンが含まれています。 3番目のオプションリストには、特定のビューの小さいアイコンの前に表示するためのチェックボックスなどの "状態" のイメージが含まれています。 4番目のオプションリストには、リストコントロールの個々のヘッダー項目に表示される画像が含まれています。

> [!NOTE]
> リストビューコントロールが LVS_SHAREIMAGELISTS スタイルで作成されている場合は、使用されなくなったときにイメージリストを破棄する必要があります。 同じイメージリストを複数のリストビューコントロールに割り当てる場合は、このスタイルを指定します。それ以外の場合は、複数のコントロールが同じイメージリストを破棄しようとすることがあります。

リスト項目の詳細については、「Windows SDK の [リストビューのイメージリスト](/windows/win32/Controls/using-list-view-controls) と [項目および](/windows/win32/Controls/using-list-view-controls) サブ項目」を参照してください。 また、 *MFC リファレンス* のクラス [cimagelist](reference/cimagelist-class.md)と、このファミリーの記事の「 [cimagelist](using-cimagelist.md) 」を参照してください。

リストコントロールを作成するには、リストに新しい項目を挿入するときに使用するイメージリストを指定する必要があります。 次の例では、 *m_pImagelist* が型のポインターであり `CImageList` *m_listctrl* がデータメンバーであるこの手順を示し `CListCtrl` ます。

[!code-cpp[NVC_MFCControlLadenDialog#19](codesnippet/cpp/list-items-and-image-lists_1.cpp)]

ただし、リストビューまたはリストコントロールにアイコンを表示する予定がない場合は、イメージリストは必要ありません。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](using-clistctrl.md)<br/>
[コントロール](controls-mfc.md)
