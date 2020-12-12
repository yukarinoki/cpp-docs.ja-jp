---
description: 詳細については、「新しいコントロールクラスに基づいた変数の宣言」を参照してください。
title: 新しいコントロール クラスに基づいた変数の宣言
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.control.variable
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
ms.openlocfilehash: aa38a38b3113e4c4826756b020860d79e03ef16b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220228"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>新しいコントロール クラスに基づいた変数の宣言

MFC コントロールクラスを作成したら、それに基づいて変数を宣言できます。 新しい変数のコンテキストを提供するには、ダイアログエディターを開いて、再利用可能なコントロールを使用するダイアログボックスを編集する必要があります。 また、ダイアログボックスには、関連付けられたクラスが既に存在している必要があります。 ダイアログエディターの使用方法の詳細については、「 [ダイアログエディター](../../windows/dialog-editor.md)」を参照してください。

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>再利用可能なクラスに基づいて変数を宣言するには

1. ダイアログボックスの編集中に、新しいコントロールの基本クラスと同じ型のコントロールを、[コントロール] ツールバーからダイアログボックスにドラッグします。

1. ドロップされたコントロールの上にマウスポインターを置きます。

1. CTRL キーを押しながら、コントロールをダブルクリックします。

   [ [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard) ] ダイアログボックスが表示されます。

1. [ **アクセス** ] ボックスで、コントロールに適切なアクセスを選択します。

1. [ **制御変数** ] チェックボックスをオンにします。

1. [ **変数名** ] ボックスに名前を入力します。

1. [ **カテゴリ**] の [ **コントロール**] をクリックします。

1. [ **コントロール ID** ] の一覧で、追加したコントロールを選択します。 [ **変数の型** ] の一覧に正しい変数の型が表示され、[ **コントロールの種類** ] ボックスに正しいコントロールの種類が表示されます。

1. [ **コメント** ] ボックスに、コードに表示するコメントを追加します。

1. **[OK]** をクリックします。

## <a name="see-also"></a>関連項目

[関数へのメッセージのマッピング](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[クラス各部へのジャンプ](../../ide/navigate-code-cpp.md)
