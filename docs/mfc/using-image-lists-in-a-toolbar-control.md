---
title: ツール バー コントロールでのイメージ リストの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: 81468528c15300a7e9ace6b20fd9fb34818f1928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366490"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>ツール バー コントロールでのイメージ リストの使い方

既定では、ツール バー コントロールのボタンで使用されるイメージは、1 つのビットマップとして格納されます。 ただし、ボタンイメージは一連のイメージリストに保存することもできます。 ツール バー コントロール オブジェクトは、最大 3 つの個別のイメージ リストを使用できます。

- 有効なイメージ リスト 現在有効になっているツール バー ボタンのイメージが含まれています。

- [無効なイメージ一覧] 現在無効になっているツール バー ボタンのイメージが含まれています。

- 強調表示されたイメージ リスト 現在強調表示されているツール バー ボタンのイメージが含まれています。 このイメージ リストは、ツールバーがTBSTYLE_FLAT スタイルを使用する場合にのみ使用されます。

これらのイメージ リストは、オブジェクトに関連付けるときにツール バー`CToolBarCtrl`コントロールによって使用されます。 この関連付けは、呼び出しを行うことによって達成[されます](../mfc/reference/ctoolbarctrl-class.md#setimagelist)[。](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist) [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)

既定では、MFC は`CToolBar`MFC アプリケーション ツール バーを実装するためにクラスを使用します。 ただし、メンバー`GetToolBarCtrl`関数を使用して埋め込み`CToolBarCtrl`オブジェクトを取得することはできます。 その後、返されたオブジェクト`CToolBarCtrl`を使用してメンバー関数を呼び出すことができます。

次の`m_ToolBarImages`例では、有効な ( ) および無効な (`m_ToolBarDisabledImages`) イメージ`CToolBarCtrl`リストを`m_ToolBarCtrl`オブジェクト ( ) に割り当てることによって、この手法を示します。

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
> ツール バー オブジェクトで使用されるイメージ リストは、永続的なオブジェクトである必要があります。 このため、通常は MFC クラスのデータ メンバーです。この例では、メイン フレーム ウィンドウ クラスです。

イメージ リストがオブジェクトに`CToolBarCtrl`関連付けられると、フレームワークは自動的に適切なボタン イメージを表示します。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
