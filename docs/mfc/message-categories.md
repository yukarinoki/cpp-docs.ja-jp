---
title: メッセージの種類
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], categories
- control-notification messages [MFC]
- Windows messages [MFC], categories
- controls [MFC], notifications
- command messages [MFC]
- messages [MFC], Windows
- message handling [MFC], message types
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
ms.openlocfilehash: 686d5eef4aaa67785aa56133d820b637fbf4bb86
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364753"
---
# <a name="message-categories"></a>メッセージの種類

ハンドラには、主に次の 3 つのカテゴリに対してどのようなメッセージを記述しますか。

1. Windows メッセージ

   これには、WM_COMMANDを除いて、主に**WM_** プレフィックスで始まるメッセージが含まれます。 Windows メッセージは、ウィンドウとビューによって処理されます。 これらのメッセージには、メッセージの処理方法を決定する際に使用されるパラメーターが含まれていることがよくあります。

1. コントロールの通知

   これには、コントロールや他の子ウィンドウから親ウィンドウへの通知メッセージがWM_COMMANDされます。 たとえば、エディット コントロールは、ユーザーがエディット コントロール内のテキストを変更した可能性のあるアクションを実行したときに、その親にWM_COMMANDのコントロール通知コードを含 EN_CHANGEむメッセージを送信します。 メッセージのウィンドウのハンドラーは、コントロール内のテキストを取得するなど、適切な方法で通知メッセージに応答します。

   フレームワークは、他のWM_ メッセージと同様に、コントロール通知メッセージ**を**ルーティングします。 ただし、1 つの例外は、ボタンをクリックしたときにボタンによって送信される制御通知メッセージBN_CLICKEDです。 このメッセージは、コマンド メッセージとして特別に扱われ、他のコマンドと同様にルーティングされます。

1. コマンド メッセージ

   これには WM_COMMAND、ユーザー インターフェイス オブジェクトからの通知メッセージ (メニュー、ツール バー ボタン、アクセラレータ キー) が含まれます。 フレームワークは、他のメッセージとは異なる方法でコマンドを処理し、コマンド[ターゲット](../mfc/command-targets.md)で説明されているように、より多くの種類のオブジェクトで処理できます。

## <a name="windows-messages-and-control-notification-messages"></a><a name="_core_windows_messages_and_control.2d.notification_messages"></a>Windows メッセージとコントロール通知メッセージ

カテゴリ 1 と 2 のメッセージ ( Windows メッセージとコントロール通知 ) は、`CWnd`クラス から派生したクラスのオブジェクトである Windows によって処理されます。 これには、 `CFrameWnd` `CMDIFrameWnd`、 `CMDIChildWnd` `CView`、 `CDialog`、、およびこれらの基本クラスから派生した独自のクラスが含まれます。 このようなオブジェクトは`HWND`、Windows ウィンドウへのハンドルをカプセル化します。

## <a name="command-messages"></a><a name="_core_command_messages"></a>コマンド メッセージ

カテゴリ 3 のメッセージ — コマンド — ウィンドウやビューに加えて、ドキュメント、ドキュメント テンプレート、アプリケーション オブジェクト自体など、さまざまなオブジェクトで処理できます。 コマンドが特定のオブジェクトに直接影響する場合、そのオブジェクトにコマンドを処理させるのは理にかなっています。 たとえば、[ファイル] メニューの [開く] コマンドは、アプリケーションに論理的に関連付けられます。 したがって、Open コマンドのハンドラーは、アプリケーション クラスのメンバー関数です。 コマンドとコマンドがオブジェクトにルーティングされる方法の詳細については、「 [Framework がハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)」を参照してください。

## <a name="see-also"></a>関連項目

[フレームワーク内のメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)
