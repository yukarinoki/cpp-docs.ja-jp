---
description: '詳細情報: コントロールの描画の最適化'
title: コントロールの描画の最適化
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
ms.openlocfilehash: 93e948d4a572f4e02c8676b2af1b6f8943004f26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331819"
---
# <a name="optimizing-control-drawing"></a>コントロールの描画の最適化

コンテナーによって提供されるデバイスコンテキストにコントロールを描画するように指示すると、通常は、GDI オブジェクト (ペン、ブラシ、フォントなど) をデバイスコンテキストに選択し、描画操作を実行して、前の GDI オブジェクトを復元します。 同じデバイスコンテキストに描画される複数のコントロールがコンテナーに存在し、各コントロールが必要とする GDI オブジェクトを選択する場合、以前に選択されたオブジェクトをコントロールが個別に復元しない場合は、時間を保存できます。 すべてのコントロールが描画された後、コンテナーは元のオブジェクトを自動的に復元できます。

コンテナーがこの手法をサポートしているかどうかを検出するために、コントロールは、 [COleControl:: IsOptimizedDraw](reference/colecontrol-class.md#isoptimizeddraw) メンバー関数を呼び出すことができます。 この関数が **TRUE** を返す場合、コントロールは、以前に選択されたオブジェクトを復元する通常の手順をスキップできます。

次の (最適化されていない) 関数を持つコントロールについて考えてみ `OnDraw` ます。

[!code-cpp[NVC_MFC_AxOpt#15](codesnippet/cpp/optimizing-control-drawing_1.cpp)]

この例のペンとブラシはローカル変数であり、(関数が終了したときに) スコープ外に出たときにデストラクターが呼び出されることを意味し `OnDraw` ます。 デストラクターは、対応する GDI オブジェクトを削除しようとします。 ただし、から戻るときにデバイスコンテキストで選択したままにする場合は、削除しないでください `OnDraw` 。

が終了したときに、 [CPen](reference/cpen-class.md) オブジェクトと [CBrush](reference/cbrush-class.md) オブジェクトが破棄されないようにするには `OnDraw` 、それらをローカル変数ではなくメンバー変数に格納します。 コントロールのクラス宣言で、2つの新しいメンバー変数の宣言を追加します。

[!code-cpp[NVC_MFC_AxOpt#16](codesnippet/cpp/optimizing-control-drawing_2.h)]
[!code-cpp[NVC_MFC_AxOpt#17](codesnippet/cpp/optimizing-control-drawing_3.h)]

次に、関数を次のように `OnDraw` 書き直します。

[!code-cpp[NVC_MFC_AxOpt#18](codesnippet/cpp/optimizing-control-drawing_4.cpp)]

この方法では、が呼び出されるたびに、ペンとブラシの作成 `OnDraw` が回避されます。 速度の向上により、追加のインスタンスデータを維持するコストがかかります。

ForeColor または BackColor プロパティが変更された場合は、ペンまたはブラシを再作成する必要があります。 これを行うには、 [OnForeColorChanged](reference/colecontrol-class.md#onforecolorchanged) および [Onbackcolorchanged](reference/colecontrol-class.md#onbackcolorchanged) メンバー関数をオーバーライドします。

[!code-cpp[NVC_MFC_AxOpt#19](codesnippet/cpp/optimizing-control-drawing_5.cpp)]

最後に、不要な呼び出しをなくすために `SelectObject` 、次のようにを変更し `OnDraw` ます。

[!code-cpp[NVC_MFC_AxOpt#20](codesnippet/cpp/optimizing-control-drawing_6.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール: 最適化](mfc-activex-controls-optimization.md)<br/>
[COleControl クラス](reference/colecontrol-class.md)<br/>
[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[MFC ActiveX コントロールウィザード](reference/mfc-activex-control-wizard.md)<br/>
[MFC ActiveX コントロール: ActiveX コントロールの描画](mfc-activex-controls-painting-an-activex-control.md)
