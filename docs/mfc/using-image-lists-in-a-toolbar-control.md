---
title: ツール バー コントロールでのイメージ リストの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50e7cb936c55ced1f16a325a031dccd1edde7d06
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951908"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>ツール バー コントロールでのイメージ リストの使い方
既定では、ツール バー コントロールのボタンが使用するイメージは、1 つのビットマップとして格納されます。 ただし、一連のイメージ リストのボタンのイメージを保存することもできます。 ツール バー コントロール オブジェクトは、最大 3 つの別々 のイメージ リストを使用できます。  
  
-   イメージ リストは、現在有効になっているツール バー ボタンのイメージを含むを有効になります。  
  
-   イメージ リストは、現在無効になっているツール バー ボタンのイメージを含むを無効になります。  
  
-   イメージ リストは、現在強調表示されているツール バー ボタンのイメージを含むを強調表示されます。 このイメージ リストは、ツールバーが TBSTYLE_FLAT スタイルを使用する場合のみ使用されます。  
  
 これらを関連付けるときにこれらのイメージ リストがツール バー コントロールで使用される、`CToolBarCtrl`オブジェクト。 この関連付けを呼び出すことで実現[CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist)、 [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)、および[SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)です。  
  
 既定では、MFC を使用して、 `CToolBar` MFC アプリケーションのツールバーを実装するクラス。 ただし、`GetToolBarCtrl`埋め込みを取得するメンバー関数を使用できます`CToolBarCtrl`オブジェクト。 呼び出しを行うことができますし、`CToolBarCtrl`返されたオブジェクトを使用してメンバー関数。  
  
 次の例は、有効なを割り当てることでこの方法を示します (`m_ToolBarImages`)] と [無効 (`m_ToolBarDisabledImages`) イメージ リストを`CToolBarCtrl`オブジェクト (`m_ToolBarCtrl`)。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  ツール バー オブジェクトで使用されるイメージ リストは、パーマネント オブジェクトである必要があります。 このため、それらは通常、MFC クラスのデータ メンバーです。この例では、メイン フレーム ウィンドウ クラスです。  
  
 イメージ リストが関連付けられていると、`CToolBarCtrl`オブジェクト、フレームワークは、適切なボタンのイメージを自動的に表示されます。  
  
## <a name="see-also"></a>関連項目  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

