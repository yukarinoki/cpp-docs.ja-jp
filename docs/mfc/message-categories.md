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
ms.openlocfilehash: 3875a6931b4380f0531e4c1786de6dddfccb76ca
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625466"
---
# <a name="message-categories"></a>メッセージの種類

どのような種類のメッセージに対してハンドラーを記述するかは、主に次の3つのカテゴリに分類されます。

1. Windows メッセージ

   これには、主に**WM_** プレフィックスで始まるメッセージが含まれます。ただし、WM_COMMAND は除きます。 Windows メッセージは、windows およびビューによって処理されます。 多くの場合、これらのメッセージには、メッセージの処理方法を決定するために使用されるパラメーターがあります。

1. コントロールの通知

   これには、コントロールやその他の子ウィンドウから親ウィンドウへの WM_COMMAND 通知メッセージが含まれます。 たとえば、エディットコントロールは、エディットコントロールのテキストを変更した可能性のあるアクションをユーザーが実行したときに、EN_CHANGE コントロール通知コードを含む WM_COMMAND メッセージを親に送信します。 メッセージのウィンドウのハンドラーは、コントロール内のテキストの取得など、適切な方法で通知メッセージに応答します。

   フレームワークは、他の**WM_** メッセージと同様に、コントロール通知メッセージをルーティングします。 ただし、1つの例外として、ユーザーがボタンをクリックしたときにボタンによって送信される BN_CLICKED コントロール通知メッセージがあります。 このメッセージは、コマンドメッセージとして特別に扱われ、他のコマンドと同様にルーティングされます。

1. コマンドメッセージ

   これには、ユーザーインターフェイスオブジェクト (メニュー、ツールバーボタン、およびアクセラレータキー) からの WM_COMMAND 通知メッセージが含まれます。 フレームワークは、[コマンドターゲット](command-targets.md)で説明されているように、コマンドを他のメッセージとは異なる方法で処理し、より多くの種類のオブジェクトで処理することができます。

## <a name="windows-messages-and-control-notification-messages"></a><a name="_core_windows_messages_and_control.2d.notification_messages"></a>Windows メッセージとコントロール通知メッセージ

カテゴリ1および2のメッセージ (Windows メッセージとコントロールの通知) は、windows: クラスから派生したクラスのオブジェクトによって処理されます `CWnd` 。 これには、、、、、、 `CFrameWnd` `CMDIFrameWnd` `CMDIChildWnd` `CView` `CDialog` およびこれらの基本クラスから派生した独自のクラスが含まれます。 このようなオブジェクトは `HWND` 、Windows ウィンドウへのハンドルであるをカプセル化します。

## <a name="command-messages"></a><a name="_core_command_messages"></a>コマンドメッセージ

Category 3 のメッセージ (コマンド) は、windows やビューに加えて、ドキュメント、ドキュメントテンプレート、アプリケーションオブジェクト自体など、さまざまなオブジェクトで処理できます。 コマンドが特定のオブジェクトに直接影響する場合は、そのオブジェクトがコマンドを処理することが理にかなっています。 たとえば、[ファイル] メニューの [開く] コマンドは、論理的にアプリケーションに関連付けられています。アプリケーションは、コマンドの受信時に、指定されたドキュメントを開きます。 そのため、Open コマンドのハンドラーは、application クラスのメンバー関数です。 コマンドと、それらがオブジェクトにルーティングされる方法の詳細については、「[フレームワークがハンドラーを呼び出す方法](how-the-framework-calls-a-handler.md)」を参照してください。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](messages-and-commands-in-the-framework.md)
