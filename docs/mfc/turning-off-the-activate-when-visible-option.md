---
title: オプションのオフ、アクティブ化するときに表示される |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5625e7d05ea09188aaa2ea50ca629204a4bacc07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="turning-off-the-activate-when-visible-option"></a>[表示時にアクティブ] オプションのオフ
各コントロールには、アクティブおよび非アクティブという 2 つの基本的な状態があります。 従来、これらの状態は、コントロールがウィンドウを持つかどうかという形で判別されていました。 アクティブなコントロールはウィンドウを持ち、非アクティブなコントロールはウィンドウを持たないという分類でした。 ウィンドウなしのアクティブ状態が導入された結果、この区別はもう普遍的ではありませんが、今でも多くのコントロールに適用されます。  
  
 通常、ActiveX コントロールによって実行される初期化の残りの部分と比べると、ウィンドウの作成は、非常に高価な操作です。 理想的には、コントロールでは、絶対に必要になるまで、そのウィンドウの作成が延期します。  
  
 多くのコントロールをアクティブにする時間全体では、コンテナーに表示されている必要はありません。 多くの場合、コントロールは、(たとえば、マウスでクリックするか、TAB キーを押して) アクティブにする必要がある操作をユーザーが実行されるまで非アクティブな状態を維持できます。 コンテナーにアクティブになるまでに非アクティブに保持するためのコントロールには、削除、**されて**コントロールの他のフラグからフラグ。  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 **されて**フラグがオフにした場合に自動的に省略すると、**表示時にアクティブ化**オプション、[コントロール設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)MFC ActiveX のページコントロールを作成するときに、ウィザードを制御します。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)

