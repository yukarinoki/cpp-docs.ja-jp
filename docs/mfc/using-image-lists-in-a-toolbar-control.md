---
title: ツール バー コントロールでのイメージ リストの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: f8b19cd54a6fb2dca940c354ef23e7d06b35f0b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584575"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>ツール バー コントロールでのイメージ リストの使い方

既定では、ツール バー コントロールのボタンで使用されるイメージは、1 つのビットマップとして格納されます。 ただし、一連のイメージ リストのボタンのイメージを格納することもできます。 ツールバーのコントロール オブジェクトは、最大 3 つの別々 のイメージ リストを使用できます。

- 現在有効になっているツール バー ボタンのイメージ リストの値を含むイメージを有効になります。

- 現在無効になっているツール バー ボタンのイメージ リストの値を含むイメージを無効になります。

- 現在強調表示されているツール バー ボタンのイメージ リストの値を含むイメージを強調表示されます。 このイメージ リストは、ツールバーが TBSTYLE_FLAT スタイルを使用する場合のみ使用されます。

これらを関連付けると、これらのイメージ リストがツール バー コントロールで使用、`CToolBarCtrl`オブジェクト。 この関連付けを呼び出すことで実現[CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist)、 [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)、および[SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)します。

既定では、MFC を使用して、 `CToolBar` MFC アプリケーションのツールバーを実装するクラス。 ただし、 `GetToolBarCtrl` 、埋め込みを取得するメンバー関数を使用できる`CToolBarCtrl`オブジェクト。 呼び出しを行うことができますし、`CToolBarCtrl`返されたオブジェクトを使用するメンバー関数。

次の例は、有効に割り当てることでこの手法を示します (`m_ToolBarImages`)、無効になります (`m_ToolBarDisabledImages`) にするイメージ リストを`CToolBarCtrl`オブジェクト (`m_ToolBarCtrl`)。

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
>  ツールバーのオブジェクトによって使用されるイメージのリストは、パーマネント オブジェクトである必要があります。 このため、それらは通常、MFC クラスのデータ メンバーです。この例では、メイン フレーム ウィンドウ クラス。

関連付けられているイメージ リストと、`CToolBarCtrl`オブジェクト、フレームワークは、適切なボタンのイメージを自動的に表示されます。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

