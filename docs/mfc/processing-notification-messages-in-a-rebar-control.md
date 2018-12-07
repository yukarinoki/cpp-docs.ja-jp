---
title: Rebar コントロールでの通知メッセージの処理
ms.date: 11/04/2016
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
ms.openlocfilehash: 4c35a1efb1c93aecf17e8f57b9e96c033aa4334a
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693185"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Rebar コントロールでの通知メッセージの処理

Rebar コントロールの親クラスで作成、`OnChildNotify`ハンドラー関数の rebar コントロールの switch ステートメントを (`CReBarCtrl`) 通知のメッセージを処理します。 ユーザーが rebar コントロール、変更、削除、rebar バンドのレイアウトと、rebar コントロールからのバンド上でオブジェクトをドラッグすると、親ウィンドウに通知が送信されます。

Rebar コントロールによっては、次の通知メッセージを送信できます。

- RBN_AUTOSIZE が (したスタイルで作成された) rebar コントロールから送信されたときに、rebar 自動的にサイズが変更されます。

- RBN_BEGINDRAG は、ユーザーがバンドのドラッグを開始するときに、rebar コントロールから送信されます。

- RBN_CHILDSIZE rebar コントロール バンドの子ウィンドウのサイズによって送信されます。

- RBN_DELETEDBAND rebar コントロール バンドが削除された後で送信されます。

- RBN_DELETINGBAND rebar コントロール バンドが削除されるときに送信されます。

- RBN_ENDDRAG は、ユーザーがバンドのドラッグを停止したとき、rebar コントロールから送信されます。

- RBN_GETOBJECT が rebar コントロール (ときスタイルで作成された) によって送信される、コントロールのバンド上にオブジェクトをドラッグするとします。

- RBN_HEIGHTCHANGE rebar コントロールの高さが変更されたときに送信されます。

- RBN_LAYOUTCHANGED は、ユーザー コントロールのバンドのレイアウトが変更されたとき、rebar コントロールから送信されます。

これらの通知の詳細については、次を参照してください。 [Rebar コントロールの参照](/windows/desktop/controls/rebar-control-reference)Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[CReBarCtrl の使い方](../mfc/using-crebarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

