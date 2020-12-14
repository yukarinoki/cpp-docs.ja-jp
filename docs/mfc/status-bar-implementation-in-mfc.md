---
description: '詳細情報: MFC でのステータスバーの実装'
title: MFC でのステータス バーの実装
ms.date: 11/19/2018
f1_keywords:
- COldStatusBar
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
ms.openlocfilehash: d42f8b4bf6ae72cf8eb4a12d1f5eafb8603c5e1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216757"
---
# <a name="status-bar-implementation-in-mfc"></a>MFC でのステータス バーの実装

[CStatusBar](../mfc/reference/cstatusbar-class.md)オブジェクトは、テキスト出力ペインの行を含むコントロールバーです。 出力ペインは、通常、メッセージ行として、また状態インジケーターとして使用されます。 たとえば、選択したメニューコマンドを簡単に説明するメニューのヘルプメッセージ行や、スクロールロック、NUMLOCK、およびその他のキーの状態を示すインジケーターがあります。

MFC バージョン4.0 では、ステータスバーは [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)クラスを使用して実装されます。このクラスは、ステータスバーコモンコントロールをカプセル化します。 旧バージョンとの互換性のために、MFC では、以前のステータスバーの実装はクラスで保持されて `COldStatusBar` います。 以前のバージョンの MFC のドキュメントでは、について説明して `COldStatusBar` `CStatusBar` います。

MFC 4.0 の新機能である[CStatusBar:: GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl)では、Windows コモンコントロールのステータスバーのカスタマイズと追加機能のサポートを利用できます。 `CStatusBar` メンバー関数は、Windows コモンコントロールのほとんどの機能を提供します。ただし、を呼び出すと `GetStatusBarCtrl` 、ステータスバーの特性をさらに詳細に指定できます。 を呼び出すと `GetStatusBarCtrl` 、オブジェクトへの参照が返され `CStatusBarCtrl` ます。 この参照を使用して、ステータスバーコントロールを操作できます。

次の図は、複数のインジケーターを表示するステータスバーを示しています。

![ステータスバー](../mfc/media/vc37dy1.gif "ステータス バー") <br/>
ステータス バー

ツールバーと同様に、ステータスバーオブジェクトは親フレームウィンドウに埋め込まれ、フレームウィンドウが構築されるときに自動的に構築されます。 ステータスバーは、すべてのコントロールバーと同様に、親フレームが破棄されると自動的に破棄されます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ステータスバーペインのテキストの更新](../mfc/updating-the-text-of-a-status-bar-pane.md)

- MFC クラス [CStatusBar](../mfc/reference/cstatusbar-class.md) と [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)

- [コントロール バー](../mfc/control-bars.md)

- [ダイアログ バー](../mfc/dialog-bars.md)

- [ツールバー (MFC ツールバーの実装)](../mfc/mfc-toolbar-implementation.md)

## <a name="see-also"></a>関連項目

[ステータスバー](../mfc/status-bars.md)
