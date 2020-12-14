---
description: '詳細情報: [表示時にアクティブ化] オプションをオフにする'
title: '[表示時にアクティブ] オプションのオフ'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
ms.openlocfilehash: fcb5f7ef0518cbf257ef9ee7a659c9617092b7d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263869"
---
# <a name="turning-off-the-activate-when-visible-option"></a>[表示時にアクティブ] オプションのオフ

各コントロールには、アクティブおよび非アクティブという 2 つの基本的な状態があります。 従来、これらの状態は、コントロールがウィンドウを持つかどうかという形で判別されていました。 アクティブなコントロールはウィンドウを持ち、非アクティブなコントロールはウィンドウを持たないという分類でした。 ウィンドウなしのアクティブ状態が導入された結果、この区別はもう普遍的ではありませんが、今でも多くのコントロールに適用されます。

通常、ActiveX コントロールによって実行される初期化の残りの部分と比較すると、ウィンドウの作成は非常に負荷のかかる操作になります。 理想的には、コントロールは、必要になるまでウィンドウの作成を遅らせることができます。

多くのコントロールは、コンテナーに表示されるまで、アクティブにする必要はありません。 多くの場合、コントロールは、ユーザーがアクティブになる必要がある操作を実行するまで (マウスを使用するか TAB キーを押すなど)、非アクティブ状態のままにすることができます。 コンテナーでアクティブ化が必要になるまで、コントロールが非アクティブなままになるようにするには、コントロールのその他のフラグから **OLEMISC_ACTIVATEWHENVISIBLE** フラグを削除します。

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

コントロールを作成するときに、MFC ActiveX コントロールウィザードの [[コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)] ページで [**表示時にアクティブ** にする] オプションをオフにすると、 **OLEMISC_ACTIVATEWHENVISIBLE** フラグは自動的に省略されます。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)
