---
description: 詳細については、User-Interface オブジェクトに関連付けられたメッセージ型」を参照してください。
title: ユーザー インターフェイス オブジェクトに関連付けられたメッセージ
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.uiobject.msgs
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
ms.openlocfilehash: 78ddb9e5290d17f92714d6b50a57ac097bbf104c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219279"
---
# <a name="message-types-associated-with-user-interface-objects"></a>ユーザー インターフェイス オブジェクトに関連付けられたメッセージ

次の表は、作業に使用するオブジェクトの種類と、それらに関連付けられているメッセージの種類を示しています。

### <a name="user-interface-objects-and-associated-messages"></a>ユーザーインターフェイスオブジェクトと関連付けられたメッセージ

|Object ID|メッセージ|
|---------------|--------------|
|クラス名。格納しているウィンドウを表します。|[CWnd](../../mfc/reference/cwnd-class.md)の派生クラスに適した Windows メッセージ: ダイアログボックス、ウィンドウ、子ウィンドウ、MDI 子ウィンドウ、または最上位のフレームウィンドウ。|
|メニューまたはアクセラレータの識別子|-コマンドメッセージ (プログラム関数を実行します)。<br />-UPDATE_COMMAND_UI メッセージ (メニュー項目を動的に更新します)。|
|コントロール識別子|選択されたコントロール型の通知メッセージを制御します。|

## <a name="see-also"></a>関連項目

[関数へのメッセージのマッピング](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[クラス各部へのジャンプ](../../ide/navigate-code-cpp.md)
