---
title: ツール バー コントロールの外観のカスタマイズ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TBSTYLE_
dev_langs:
- C++
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96ec459e1c956c805991f2e37d22b8260f0ffdf2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>ツール バー コントロールの外観のカスタマイズ
クラス`CToolBarCtrl`外観 (および場合によっては、動作) のツールバー オブジェクトに影響する多くのスタイルを提供します。 設定してツール バー オブジェクトを変更、`dwCtrlStyle`のパラメーター、 `CToolBarCtrl::Create` (または`CToolBar::CreateEx`) メンバー関数は、ツール バー コントロールを作成します。  
  
 次のスタイルは、ツールバーのボタンの"3D"縦横比とボタンのテキストの配置に影響します。  
  
-   **TBSTYLE_FLAT**ツールバーとボタンの両方が透過的なフラット ツールバーを作成します。 ボタンのビットマップ ボタンのテキストが表示されます。 このスタイルを使用すると、カーソルの下のボタンが自動的に強調表示されます。  
  
-   **バーオブジェクト**透過ツールバーを作成します。 透明なツールバーで、ツールバーは透明が、ボタンはできません。 ボタンのビットマップ ボタンのテキストが表示されます。  
  
-   **TBSTYLE_LIST**場所ボタンのボタンのビットマップの右側にテキストです。  
  
> [!NOTE]
>  再描画の問題を防ぐために、 **TBSTYLE_FLAT**と**バーオブジェクト**ツールバー オブジェクトを表示する前に、スタイルを設定する必要があります。  
  
 次のスタイルでは、ツールバーがドラッグを使用して、ツールバーのオブジェクト内の各ボタンの位置を変更および削除するユーザーを使用するかどうかを決定します。  
  
-   **TBSTYLE_ALTDRAG** alt キーを押しながらドラッグして、ツール バー ボタンの位置を変更することができます。 このスタイルが指定されていない場合、ユーザーはボタンをドラッグし、shift キーを押し必要があります。  
  
    > [!NOTE]
    >  `CCS_ADJUSTABLE`をドラッグできるツール バー ボタンを有効にするスタイルを指定する必要があります。  
  
-   **TBSTYLE_REGISTERDROP**生成**TBN_GETOBJECT**通知を要求するメッセージは、マウス ポインターがツール バー ボタン上に置いたときにターゲット オブジェクトを削除します。  
  
 残りのスタイルでは、ツールバーのオブジェクトのビジュアルとビジュアルの側面に影響します。  
  
-   `TBSTYLE_WRAPABLE` ボタンの複数の行を持つことができるツールバーを作成します。 ツール バー ボタン「ラップできます」次の行に、ツールバーが狭いが同じ直線上のすべてのボタンを含めるためになったとき。 分離と折り返されます境界での折り返しが発生します。  
  
-   **TBSTYLE_CUSTOMERASE**生成**NM_CUSTOMDRAW**の通知メッセージを処理するとき`WM_ERASEBKGND`メッセージ。  
  
-   `TBSTYLE_TOOLTIPS` ツールバーのボタンの説明テキストを表示するアプリケーションで使用できる、ツール ヒント コントロールを作成します。  
  
 ツール バー スタイルや拡張スタイルの完全な一覧については、次を参照してください。[ツール バー コントロールとボタンのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760439)と[ツールバー拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760430)Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

