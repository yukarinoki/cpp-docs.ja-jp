---
title: コントロールの描画の最適化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8103e1e342756f9b715c1a0959ed256403e130bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351295"
---
# <a name="optimizing-control-drawing"></a>コントロールの描画の最適化
コントロールは、コンテナーが指定したデバイス コンテキストに自身で描画するように指示されますが通常デバイス コンテキストに (ペン、ブラシ、フォントなど) の GDI オブジェクトを選択、その図面の操作を実行し、以前の GDI オブジェクトが復元されます。 場合は、コンテナーは、同じデバイス コンテキストに描画するのには、複数のコントロールを持ち、各コントロールが必要な GDI オブジェクトを選択、コントロールが以前に選択したオブジェクトを個別に復元しないでください場合に、時間を保存することができます。 すべてのコントロールが描画されると、コンテナーによって元のオブジェクトが自動的に復元します。  
  
 コンテナーがこの手法をサポートしているかどうかを検出するには、コントロールを呼び出すことができます、 [COleControl::IsOptimizedDraw](../mfc/reference/colecontrol-class.md#isoptimizeddraw)メンバー関数。 この関数を返した場合**TRUE**、以前に選択したオブジェクトを復元するの通常の手順を省略できます。  
  
 (最適化されていない)、次のあるコントロールを検討してください`OnDraw`関数。  
  
 [!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/cpp/optimizing-control-drawing_1.cpp)]  
  
 ペンとブラシはこの例では、ローカル変数、つまり、スコープ外に出ると、それぞれのデストラクターが呼び出されます (ときに、`OnDraw`関数の終了)。 デストラクターは、対応する GDI オブジェクトを削除しようとします。 削除してはいけないから戻ったときにデバイス コンテキストに選択されたままにする場合は`OnDraw`します。  
  
 防ぐために、 [CPen](../mfc/reference/cpen-class.md)と[CBrush](../mfc/reference/cbrush-class.md)ときに破棄されないオブジェクト`OnDraw`が終了したら、変数に格納メンバー ローカル変数の代わりにします。 コントロールのクラス宣言では、2 つの新しいメンバー変数の宣言を追加します。  
  
 [!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/cpp/optimizing-control-drawing_2.h)]  
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/cpp/optimizing-control-drawing_3.h)]  
  
 次に、`OnDraw`関数を次のように書き換えることができます。  
  
 [!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/cpp/optimizing-control-drawing_4.cpp)]  
  
 この方法を使用するたびにブラシ、ペンの作成`OnDraw`と呼びます。 追加のインスタンス データを維持する欠点は、速度の向上。  
  
 前景色または背景色のプロパティが変更された場合、ブラシ、ペンを再度作成する必要があります。 これを行うには、上書き、 [OnForeColorChanged](../mfc/reference/colecontrol-class.md#onforecolorchanged)と[OnBackColorChanged](../mfc/reference/colecontrol-class.md#onbackcolorchanged)メンバー関数。  
  
 [!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/cpp/optimizing-control-drawing_5.cpp)]  
  
 最後に、不要に`SelectObject`呼び出し、変更`OnDraw`次のようにします。  
  
 [!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/cpp/optimizing-control-drawing_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)   
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)   
 [MFC ActiveX コントロール: ActiveX コントロールの描画](../mfc/mfc-activex-controls-painting-an-activex-control.md)

