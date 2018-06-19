---
title: ステータス バーの実装 (MFC の) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- COldStatusBar
dev_langs:
- C++
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13a85ba03089a9536c8c6512bccd09f1eb34c0a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381089"
---
# <a name="status-bar-implementation-in-mfc"></a>MFC でのステータス バーの実装
A [CStatusBar](../mfc/reference/cstatusbar-class.md)オブジェクトは、テキスト出力ペインの行を持つコントロール バーです。 出力ウィンドウは、状態インジケーター、およびメッセージ行としてよく使用されます。 例としては、選択されたメニュー コマンドを簡単に説明するメニュー ヘルプ メッセージ行や SCROLL LOCK、NUM LOCK、およびその他のキーの状態を示すインジケーターです。  
  
 クラスを使用して MFC バージョン 4.0 の時点でステータス バーが実装されます[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)、ステータス バー コモン コントロールをカプセル化します。 旧バージョンと互換性のため、MFC では、古いステータス バーの実装クラスで**COldStatusBar**です。 MFC の以前のバージョンのドキュメントについて説明して**COldStatusBar** `CStatusBar`です。  
  
 [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl)、メンバー関数は、新しい MFC 4.0 を取得できるようにのステータス バーのカスタマイズと追加の機能の Windows コモン コントロールのサポートを利用します。 `CStatusBar` メンバー関数は、Windows のコモン コントロール以外の機能のほとんどを与えるただし、呼び出す`GetStatusBarCtrl`、ステータス バーの特性の詳細も、ステータス バーを与えることができます。 呼び出すと`GetStatusBarCtrl`への参照が返されます、`CStatusBarCtrl`オブジェクト。 その参照を使用すると、ステータス バー コントロールを操作します。  
  
 次の図では、いくつかのインジケーターを表示するステータス バーが表示されます。  
  
 ![ステータス バー](../mfc/media/vc37dy1.gif "vc37dy1")  
ステータス バー  
  
 ツールバーのようには、ステータス バー オブジェクトは、親フレーム ウィンドウに埋め込まれているし、フレーム ウィンドウを作成するときに自動的に構築します。 すべてのコントロール バーのように、ステータス バーは自動的に破棄も、親フレームが破棄されるときにします。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ステータス バー ペインのテキストの更新](../mfc/updating-the-text-of-a-status-bar-pane.md)  
  
-   MFC クラス[CStatusBar](../mfc/reference/cstatusbar-class.md)と[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
  
-   [コントロール バー](../mfc/control-bars.md)  
  
-   [ダイアログ バー](../mfc/dialog-bars.md)  
  
-   [ツールバー (MFC ツールバーの実装)](../mfc/mfc-toolbar-implementation.md)  
  
## <a name="see-also"></a>関連項目  
 [ステータス バー](../mfc/status-bars.md)

