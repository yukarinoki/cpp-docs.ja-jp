---
title: 関数へのメッセージの割り当て
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.mapping.msg.function
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
ms.openlocfilehash: 33aa12626e92eb40606e3ec9b12ebb7bcac571ec
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2019
ms.locfileid: "66741651"
---
# <a name="mapping-messages-to-functions"></a>関数へのメッセージの割り当て

[プロパティ] ウィンドウでは、アプリケーションのリソースによって生成されたメッセージを使用すると、メッセージ ハンドラー (MFC ユーザー インターフェイス クラスのメンバー関数) をバインドできます。 使用する[MFC メッセージ マップ](../../mfc/messages-and-commands-in-the-framework.md)バインディングを作成します。

クラス ビューを使用して、framework のクラスのいずれかから派生した新しいクラスを作成するときに、自動的に機能とクラス ヘッダー (.h) と実装 (.cpp) で指定したファイルです。

> [!NOTE]
>  メッセージを処理しない新しいクラスを追加するには、テキスト エディターで直接、クラスを作成します。

### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>定義またはプロパティ ウィンドウを使用してメッセージ ハンドラーを削除するには

1. クラス ビューで、クラスをクリックします。

1. [プロパティ] ウィンドウ、**メッセージ**ボタンをクリックします。

    > [!NOTE]
    >  **メッセージ**クラス ビュー、またはソース ウィンドウ内をクリックしたときにクラス名を選択すると、ボタンは使用できます。

   プロジェクトには、メッセージのハンドラーがある、メッセージの横にある右側の列に、ハンドラーの名前が表示されます。

1. ハンドラーとしての推奨される名前を表示する [プロパティ] ウィンドウで、右側の列のセルがクリックしてハンドラー、メッセージがない場合は、\<追加 >*HandlerName*します。 (たとえば、WM_TIMER メッセージ ハンドラーを示します\<追加 >`OnTimer`)。

1. 推奨される名前をクリックして、関数のスタブ コードを追加します。

1. メッセージ ハンドラーを編集するには、クラス ビューでメッセージをダブルクリックし、ソース ウィンドウ内のコードを編集します。

メッセージ ハンドラーを削除する右側の列にハンドラをダブルクリックし、選択\<削除 >*HandlerName*します。 関数のコードがコメントアウトされます。

## <a name="see-also"></a>関連項目

[MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[クラス各部へのジャンプ](../../ide/navigate-code-cpp.md)
