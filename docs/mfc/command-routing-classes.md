---
title: コマンド ルーティング クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.command
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b467a85aca4bb1d0405f9bbddee5cb5e4f5b790
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391545"
---
# <a name="command-routing-classes"></a>コマンド ルーティング クラス

ように、ユーザーは、メニューまたはマウスでコントロール バーのボタンを選択して、アプリケーションと対話する、アプリケーションは、適切なコマンド ターゲット オブジェクトに影響を受けるユーザー インターフェイス オブジェクトからメッセージを送信します。 コマンド ターゲット クラスから派生した`CCmdTarget`含める[CWinApp](../mfc/reference/cwinapp-class.md)、 [CWnd](../mfc/reference/cwnd-class.md)、 [CDocTemplate](../mfc/reference/cdoctemplate-class.md)、 [CDocument](../mfc/reference/cdocument-class.md)、 [CView](../mfc/reference/cview-class.md)、およびそれらから派生したクラス。 フレームワークでは、コマンドの自動ルーティング コマンドは、アプリケーションで現在アクティブに最も適切なオブジェクトで処理できるようにサポートしています。

クラスのオブジェクト`CCmdUI`コマンド ターゲットの更新コマンド UI に渡される ([ON_UPDATE_COMMAND_UI](reference/message-map-macros-mfc.md#on_update_command_ui)) ハンドラーを使用する特定のコマンドのユーザー インターフェイスの状態を更新できます (たとえば、チェック、または削除するメニュー項目からチェック)。 メンバーの関数を呼び出して、 `CCmdUI` UI オブジェクトの状態を更新するオブジェクト。 このプロセスは、特定のコマンドに関連付けられている UI オブジェクトがメニュー項目をボタン、またはその両方であるかどうかは同じです。

[CCmdTarget](../mfc/reference/ccmdtarget-class.md)<br/>
受信およびメッセージに応答できるオブジェクトのすべてのクラスの基本クラスとして機能します。

[CCmdUI](../mfc/reference/ccmdui-class.md)<br/>
メニュー項目やコントロール バーのボタンなどのユーザー インターフェイス オブジェクトを更新するためのプログラム インターフェイスを提供します。 コマンド ターゲット オブジェクトは、有効、無効にします、チェック、またはこのオブジェクトとユーザー インターフェイス オブジェクトをクリアを。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

