---
title: リフレクション メッセージ用のメッセージ ハンドラーの定義
ms.date: 09/07/2019
f1_keywords:
- vc.codewiz.defining.msg.msghandler
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
ms.openlocfilehash: f7f90d3347ac61abcfcb48e77ef39aa2626ae5c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365853"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>リフレクション メッセージ用のメッセージ ハンドラーの定義

新しい MFC コントロール クラスを作成したら、そのクラスのメッセージ ハンドラーを定義できます。 リフレクション メッセージ ハンドラーを使用すると、コントロール クラスは、親がメッセージを受信する前に、独自のメッセージを処理できます。 MFC [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage)関数を使用すると、コントロールから親ウィンドウにメッセージを送信できます。

この機能を使用すると、たとえば、親ウィンドウに依存するのではなく、自分自身を再描画するリスト ボックスを作成できます (所有者が描画)。 リフレクションメッセージの詳細については、リ[フレクションメッセージの処理を](../../mfc/handling-reflected-messages.md)参照してください。

同じ機能を持つ[ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)を作成するには、ActiveX コントロール用のプロジェクトを作成する必要があります。

> [!NOTE]
> クラス ウィザードを使用して、ActiveX コントロール OCM_に対して、次の説明に従って、メッセージ (*メッセージ*) を追加することはできません。 これらのメッセージは手動で追加する必要があります。

### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-class-wizard"></a>クラス ウィザードからのリフレクション メッセージのメッセージ ハンドラーを定義するには

1. リスト、Rebar コントロール、ツール バー、ツリー コントロールなどのコントロールを MFC プロジェクトに追加します。

1. クラス ビューで、コントロール クラスの名前をクリックします。

1. クラス[ウィザード](mfc-class-wizard.md)の [クラス名] ボックスの一覧に、コントロール**クラス名**が表示されます。

1. [**メッセージ**] タブをクリックして、コントロールに追加できる Windows メッセージを表示します。

1. ハンドラを定義するリフレクション メッセージを選択します。 リフレクションされたメッセージは等号 (=) でマークされます。

1. クラス ウィザードの右側の列のセルをクリックすると、ハンドラーの候補名が\<*[HandlerName*>追加として表示されます。 (たとえば **、=WM_CTLCOLOR**メッセージ ハンドラは\< **CtlColor**>追加を提案します。

1. 同意する候補名をクリックします。 ハンドラーがプロジェクトに追加されます。

1. メッセージ・ハンドラーを編集または削除するには、ステップ 4 から 7 を繰り返します。 編集または削除するハンドラ名を含むセルをクリックし、該当するタスクをクリックします。

## <a name="see-also"></a>関連項目

[関数へのメッセージのマッピング](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[クラス各部へのジャンプ](../../ide/navigate-code-cpp.md)
