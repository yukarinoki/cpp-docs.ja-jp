---
title: コントロール バー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.control
dev_langs:
- C++
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4974b7ba3b71e60b8edf2a73ea5f06fab64ddfb7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342021"
---
# <a name="control-bar-classes"></a>コントロール バー クラス
コントロール バーは、フレーム ウィンドウにアタッチされます。 ボタン、ステータス ウィンドウまたはダイアログ テンプレートが含まれます。 添付してフローティング コントロール バー, ツール パレットとも呼ばれますが実装されている、 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)オブジェクト。  
  
## <a name="framework-control-bars"></a>フレームワークのコントロール バー  
 これらのコントロール バーは、MFC フレームワークの不可欠な部分です。 使いやすくして、フレームワークに統合されているため、Windows のコントロール バーよりも強力です。 ほとんどの MFC アプリケーションでは、Windows のコントロール バーではなく、これらのコントロール バーを使用します。  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 ここで示した MFC コントロール バーの基本クラスです。 コントロール バーは、フレーム ウィンドウの端に揃えますウィンドウです。 コントロール バーを表示するか`HWND`-ベースの子コントロールまたはコントロールに基づいていない、 `HWND`、ツール バー ボタンなどです。  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 ダイアログ ボックスのテンプレートに基づいているコントロール バーです。  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 コントロールの形式で追加の子ウィンドウを含めることができるツールバーをサポートしています。  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 ビットマップ コマンド ボタンが含まれていないツール バー コントロールのウィンドウがに基づいて、`HWND`です。 ほとんどの MFC アプリケーションは、このクラスを使用してなく`CToolBarCtrl`です。  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 ステータス バー コントロールのウィンドウの基本クラスです。 ほとんどの MFC アプリケーションは、このクラスを使用してなく`CStatusBarCtrl`です。  
  
## <a name="windows-control-bars"></a>Windows のコントロール バー  
 これらのコントロール バーは、対応する Windows コントロールへのシン ラッパーです。 フレームワークとは統合しません、ためするが困難より前に示したコントロール バーを使用します。 ほとんどの MFC アプリケーションでは、上記のコントロール バーを使用します。  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 内部のコントロールを実装、`CRebar`オブジェクト。  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 水平方向のウィンドウは、通常、ペイン、アプリケーションが状態情報を表示できますに分かれています。  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Windows ツール バー コモン コントロールの機能が用意されています。  
  
## <a name="related-classes"></a>関連するクラス  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 アプリケーションでツールの用途を説明するテキストを 1 行を表示する小さなポップアップ ウィンドウです。  
  
 [変更](../mfc/reference/cdockstate-class.md)  
 永続的なストレージのドッキング コントロール バーの状態データを処理します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

