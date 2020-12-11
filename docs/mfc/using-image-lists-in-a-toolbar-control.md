---
description: 詳細については、「ツールバーコントロールでのイメージリストの使用」を参照してください。
title: ツール バー コントロールでのイメージ リストの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: dbdac26f1d17997e14ed4ba16875ef3794e46a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154436"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>ツール バー コントロールでのイメージ リストの使い方

既定では、ツールバーコントロールのボタンによって使用されるイメージは、1つのビットマップとして格納されます。 ただし、ボタンイメージは、一連のイメージリストに格納することもできます。 Toolbar コントロールオブジェクトは、最大3つの異なるイメージリストを使用できます。

- 有効になっているイメージリストには、現在有効になっているツールバーボタンのイメージが含まれています。

- 無効なイメージの一覧には、現在無効になっているツールバーボタンのイメージが含まれています。

- 強調表示されたイメージリストには、現在強調表示されているツールバーボタンのイメージが含まれます。 このイメージリストは、ツールバーが TBSTYLE_FLAT スタイルを使用している場合にのみ使用されます。

これらのイメージリストは、オブジェクトに関連付けたときに、ツールバーコントロールによって使用され `CToolBarCtrl` ます。 この関連付けは、 [CToolBarCtrl:: SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist)、 [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)、および [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)を呼び出すことによって実現されます。

既定では、MFC はクラスを使用して `CToolBar` mfc アプリケーションのツールバーを実装します。 ただし、 `GetToolBarCtrl` メンバー関数は、埋め込みオブジェクトを取得するために使用でき `CToolBarCtrl` ます。 その後 `CToolBarCtrl` 、返されたオブジェクトを使用してメンバー関数を呼び出すことができます。

次の例では、有効 ( `m_ToolBarImages` ) と無効 ( `m_ToolBarDisabledImages` ) のイメージリストをオブジェクト () に割り当てて、この手法を示し `CToolBarCtrl` `m_ToolBarCtrl` ます。

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
> ツールバーオブジェクトで使用されるイメージリストは、永続的なオブジェクトである必要があります。 このため、これらは通常、MFC クラスのデータメンバーです。この例では、メインフレームウィンドウクラスです。

イメージリストがオブジェクトに関連付けられると、フレームワークによって `CToolBarCtrl` 自動的に適切なボタンイメージが表示されます。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
