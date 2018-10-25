---
title: リフレクション メッセージ用のメッセージ ハンドラーの定義 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.defining.msg.msghandler
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 104f9e0be67a350a1725dfbcd2bf234a8bc79553
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052565"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>リフレクション メッセージ用のメッセージ ハンドラーの定義

新しい MFC コントロール クラスを作成すると、そのメッセージ ハンドラーを定義できます。 リフレクション メッセージ ハンドラーは、親によってメッセージの受信前に、独自のメッセージを処理するコントロール クラスを使用できます。 MFC を使用する[CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage)コントロールから親ウィンドウにメッセージを送信する関数。

(オーナー描画) を実行する親ウィンドウに依存するのではなくなどのことがこの機能により、自身を再描画するリスト ボックスを作成します。 反映されたメッセージの詳細については、次を参照してください。[反映されたメッセージの処理](../../mfc/handling-reflected-messages.md)します。

作成する、 [ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)、同じ機能を持つ ActiveX コントロールのプロジェクトを作成する必要があります。

> [!NOTE]
>  リフレクション メッセージを追加することはできません (ocm _*メッセージ*) の ActiveX を使用して制御プロパティ ウィンドウで、次のようです。 これらのメッセージを手動で追加する必要があります。

### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>[プロパティ] ウィンドウから反映されたメッセージのメッセージ ハンドラーを定義するには

1. リストなどのコントロールや rebar コントロール、ツールバー、ツリー コントロールを MFC プロジェクトに追加します。

1. クラス ビューで、コントロール クラスの名前をクリックします。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、コントロール クラス名が表示されます、**クラス名**一覧。

1. をクリックして、**メッセージ**コントロールに追加できる Windows メッセージを表示するボタンをクリックします。

1. 見出しが表示されるまでは、[プロパティ] ウィンドウ内のメッセージの一覧をスクロールして**反映済み**します。 または、クリックして、**カテゴリ**ボタンをクリックし、表示するビューを折りたたんだり、**反映済み**見出し。

1. リフレクションにハンドラーを定義するメッセージを選択します。 反映されたメッセージは、等号 (=) でマークされます。

1. ハンドラーとしての推奨される名前を表示する [プロパティ] ウィンドウで、右側の列のセルをクリックして\<追加 >*HandlerName*します。 (たとえば、 **= WM_CTLCOLOR**メッセージ ハンドラーを提案\<追加 >**CtlColor**)。

1. 受け入れるように推奨される名前をクリックします。 ハンドラーは、プロジェクトに追加されます。

   リフレクション メッセージ ウィンドウの右側の列に追加したメッセージ ハンドラー名が表示されます。

9. を編集またはメッセージ ハンドラーを削除するには、手順 4 ~ 7 を繰り返します。 編集または削除、および適切なタスクをクリックします。 ハンドラー名を含むセルをクリックします。

## <a name="see-also"></a>関連項目

[マップ (関数にメッセージを)](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[クラス各部へのジャンプ](../../ide/navigating-the-class-structure-visual-cpp.md)
