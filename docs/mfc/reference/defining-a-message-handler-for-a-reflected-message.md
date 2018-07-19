---
title: リフレクション メッセージ用のメッセージ ハンドラーの定義 |Microsoft ドキュメント
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
ms.openlocfilehash: 3ed941816824c77f14a3364b06af0b3da171ee8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373170"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>リフレクション メッセージ用のメッセージ ハンドラーの定義
新しい MFC コントロール クラスを作成した後は、そのメッセージ ハンドラーを定義できます。 リフレクション メッセージ ハンドラーは、親でメッセージを受信する前に、独自のメッセージを処理するコントロール クラスを使用できます。 MFC を使用する[CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage)コントロールから親ウィンドウにメッセージを送信する関数。  
  
 その (オーナー描画) を行うには、親ウィンドウで証明書利用者のではなく、作成できますが、たとえば、この機能により、自身を再描画するリスト ボックスを作成します。 リフレクション メッセージの詳細については、次を参照してください。[反映されたメッセージの処理](../../mfc/handling-reflected-messages.md)です。  
  
 作成する、 [ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)、同じ機能を持つ ActiveX コントロールのプロジェクトを作成する必要があります。  
  
> [!NOTE]
>  リフレクション メッセージを追加することはできません (ocm _*メッセージ*) ActiveX の制御 [プロパティ] ウィンドウを使用して以下のとおりです。 これらのメッセージを手動で追加する必要があります。  
  
### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>[プロパティ] ウィンドウから反映されたメッセージのメッセージ ハンドラーを定義するには  
  
1.  リストなどのコントロール、rebar コントロール、ツールバー、またはツリー コントロールを MFC プロジェクトに追加します。  
  
2.  クラス ビュー で、コントロール クラスの名前をクリックします。  
  
3.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、コントロールのクラス名に表示されます、**クラス名** ボックスの一覧です。  
  
4.  クリックして、**メッセージ**コントロールに追加できる Windows メッセージを表示するボタンをクリックします。  
  
5.  見出しが表示されるまでは、[プロパティ] ウィンドウ内のメッセージの一覧をスクロールして**反映済み**です。 または、クリックして、**カテゴリ**ボタンをクリックし、表示するビューを折りたたんだり、**反映済み**見出し。  
  
6.  リフレクション メッセージ ハンドラーを定義するを選択します。 リフレクション メッセージは、等号 (=) でマークされます。  
  
7.  プロパティ ウィンドウに、ハンドラーの名前を表示するには、右側の列のセルをクリックして\<追加 >*HandlerName*です。 (たとえば、 **= WM_CTLCOLOR**メッセージ ハンドラーを提案\<追加 >**CtlColor**)。  
  
8.  受け入れるように推奨される名前をクリックします。 ハンドラーは、プロジェクトに追加されます。  
  
     リフレクション メッセージ ウィンドウの右側の列に追加されているメッセージ ハンドラーの名前が表示されます。  
  
9. を編集またはメッセージのハンドラーを削除するには、手順 4 ~ 7 を繰り返します。 編集または削除し、適切なタスクをクリックして、ハンドラーの名前を含むセルをクリックします。  
  
## <a name="see-also"></a>関連項目  
 [関数へのメッセージの割り当てください。](../../mfc/reference/mapping-messages-to-functions.md)   
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../../ide/navigating-the-class-structure-visual-cpp.md)
