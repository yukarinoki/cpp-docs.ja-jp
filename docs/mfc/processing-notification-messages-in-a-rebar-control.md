---
description: '詳細情報: Rebar コントロールでの通知メッセージの処理'
title: Rebar コントロールでの通知メッセージの処理
ms.date: 11/04/2016
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
ms.openlocfilehash: 6255f10068072f75f556cf1c8576008ab821ed27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154839"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Rebar コントロールでの通知メッセージの処理

Rebar コントロールの親クラスで、 `OnChildNotify` 処理する rebar コントロール () 通知メッセージの switch ステートメントを含むハンドラー関数を作成し `CReBarCtrl` ます。 ユーザーが rebar コントロール上でオブジェクトをドラッグしたり、rebar バンドのレイアウトを変更したり、rebar コントロールからバンドを削除したりすると、通知が親ウィンドウに送信されます。

Rebar コントロールオブジェクトは、次の通知メッセージを送信できます。

- Rebar が自動的にサイズを変更したときに rebar コントロール (RBS_AUTOSIZE スタイルで作成) によって送信さ RBN_AUTOSIZE。

- ユーザーがバンドのドラッグを開始したときに rebar コントロールによって送信さ RBN_BEGINDRAG。

- バンドの子ウィンドウのサイズが変更されたときに rebar コントロールによって送信さ RBN_CHILDSIZE。

- バンドが削除された後に rebar コントロールによって送信さ RBN_DELETEDBAND。

- バンドが削除されようとしているときに rebar コントロールによって送信さ RBN_DELETINGBAND。

- ユーザーがバンドのドラッグを停止したときに rebar コントロールによって送信さ RBN_ENDDRAG。

- オブジェクトがコントロールのバンド上にドラッグされたときに、rebar コントロールによって (RBS_REGISTERDROP スタイルで作成された) RBN_GETOBJECT 送信されます。

- 高さが変化したときに rebar コントロールによって送信 RBN_HEIGHTCHANGE ます。

- RBN_LAYOUTCHANGED、ユーザーがコントロールのバンドのレイアウトを変更したときに rebar コントロールによって送信されます。

これらの通知の詳細については、Windows SDK の「 [Rebar コントロールリファレンス](/windows/win32/controls/rebar-control-reference) 」を参照してください。

## <a name="see-also"></a>関連項目

[CReBarCtrl の使い方](using-crebarctrl.md)<br/>
[コントロール](controls-mfc.md)
