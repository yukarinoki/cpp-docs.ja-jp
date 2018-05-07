---
title: Rebar コントロールでダイアログ バーを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WM_EX_TRANSPARENT
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47894c14e3b3d694847f94e7f981c9397383e598
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Rebar コントロールでのダイアログ バーの使い方
説明したよう[Rebar コントロールとバンド](../mfc/rebar-controls-and-bands.md)、各バンドは、1 つだけの子ウィンドウ (またはコントロール) を含めることができます。 帯域外あたり 1 つ以上の子ウィンドウがある場合、制限があります。 便利な回避策では、複数のコントロールにダイアログ バー リソースを作成し、rebar コントロールに rebar バンド (ダイアログ バーを含む) を追加します。  
  
 通常、設定ダイアログ バー バンドを透明に表示する場合は、 **WS_EX_TRANSPARENT**ダイアログ バー オブジェクトのスタイルを拡張します。 ただし、ため**WS_EX_TRANSPARENT**ダイアログ バーの背景を正しく描画いくつかの問題、所定の効果を実現するために少しの余分な作業を行う必要があります。  
  
 次の手順を使用せずに透過性を実現するために必要な手順の詳細、 **WS_EX_TRANSPARENT**拡張スタイル。  
  
### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Rebar バンドで透過的なダイアログ バーを実装するには  
  
1.  使用して、[クラスの追加 ダイアログ ボックス](../mfc/reference/adding-an-mfc-class.md)、新しいクラスを追加 (たとえば、 `CMyDlgBar`)、ダイアログ バー オブジェクトを実装します。  
  
2.  ハンドラーを追加、`WM_ERASEBKGND`メッセージ。  
  
3.  新しいハンドラーでは、次の例に示すように既存のコードを変更します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  ハンドラーを追加、`WM_MOVE`メッセージ。  
  
5.  新しいハンドラーでは、次の例に示すように既存のコードを変更します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 新しいハンドラーは、転送によってダイアログ バーの透明度をシミュレート、`WM_ERASEBKGND`親ウィンドウに表示するメッセージし、ダイアログ バー オブジェクトを移動するたびに強制的に再描画します。  
  
## <a name="see-also"></a>関連項目  
 [CReBarCtrl の使い方](../mfc/using-crebarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

