---
description: '詳細情報: コマンドルーティングクラス'
title: コマンド ルーティング クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.command
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
ms.openlocfilehash: d469b119eb7c42c1385f27a3d8df54f3fd47c73f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159974"
---
# <a name="command-routing-classes"></a>コマンド ルーティング クラス

ユーザーがマウスでメニューまたはコントロールバーボタンを選択してアプリケーションと対話すると、アプリケーションは、影響を受けるユーザーインターフェイスオブジェクトから適切なコマンドターゲットオブジェクトにメッセージを送信します。 から派生したコマンドターゲットクラスに `CCmdTarget` は、 [CWinApp](reference/cwinapp-class.md)、 [CWnd](reference/cwnd-class.md)、 [CDocTemplate](reference/cdoctemplate-class.md)、 [CDocument](reference/cdocument-class.md)、 [CView](reference/cview-class.md)、およびそれらから派生したクラスが含まれます。 フレームワークは、アプリケーションで現在アクティブな最も適切なオブジェクトによってコマンドを処理できるように、コマンドの自動ルーティングをサポートしています。

クラスのオブジェクト `CCmdUI` は、コマンドターゲットの更新コマンド UI ([ON_UPDATE_COMMAND_UI](reference/message-map-macros-mfc.md#on_update_command_ui)) ハンドラーに渡され、特定のコマンドのユーザーインターフェイスの状態を更新できるようになります (たとえば、メニュー項目のチェックをオンまたはオフにするため)。 オブジェクトのメンバー関数を呼び出して、 `CCmdUI` UI オブジェクトの状態を更新します。 このプロセスは、特定のコマンドに関連付けられている UI オブジェクトがメニュー項目、ボタン、またはその両方であるかどうかと同じです。

[CCmdTarget](reference/ccmdtarget-class.md)<br/>
メッセージを受信して応答できるオブジェクトのすべてのクラスの基本クラスとして機能します。

[CCmdUI](reference/ccmdui-class.md)<br/>
メニュー項目やコントロールバーボタンなどのユーザーインターフェイスオブジェクトを更新するためのプログラムインターフェイスを提供します。 コマンドターゲットオブジェクトは、このオブジェクトを使用して、ユーザーインターフェイスオブジェクトを有効にし、無効にしたり、確認したり、クリアしたりします。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
