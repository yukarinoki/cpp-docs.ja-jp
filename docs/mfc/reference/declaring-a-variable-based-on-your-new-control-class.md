---
title: 新しいコントロール クラスに基づいた変数の宣言
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.control.variable
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
ms.openlocfilehash: 994f81524001a80d1cf0dd3783b9de742d61e84d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365843"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>新しいコントロール クラスに基づいた変数の宣言

MFC コントロール クラスを作成したら、そのクラスに基づいて変数を宣言できます。 新しい変数のコンテキストを指定するには、ダイアログ エディターを開き、再利用可能なコントロールを使用するダイアログ ボックスを編集する必要があります。 また、ダイアログ ボックスには、関連付けられたクラスが既に存在している必要があります。 ダイアログ エディタの使用については、「ダイアログ[エディタ](../../windows/dialog-editor.md)」を参照してください。

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>再利用可能なクラスに基づいて変数を宣言するには

1. ダイアログ ボックスの編集中に、新しいコントロールの基本クラスと同じ種類のコントロールを[コントロール]ツールバーからダイアログ ボックスにドラッグします。

1. ドロップしたコントロールの上にマウス ポインタを置きます。

1. Ctrl キーを押しながら、コントロールをダブルクリックします。

   [[メンバー変数の追加](../../ide/add-member-variable-wizard.md)] ダイアログ ボックスが表示されます。

1. [**アクセス**] ボックスで、コントロールに対する適切なアクセス権を選択します。

1. [**コントロール変数**] チェック ボックスをオンにします。

1. [**変数名**] ボックスに名前を入力します。

1. [**カテゴリ]** の [**コントロール**] をクリックします。

1. [**コントロール ID] ボックス**の一覧で、追加したコントロールを選択します。 **変数の型**リストには正しい変数型が表示され、**コントロールタイプ**ボックスに正しいコントロールタイプが表示されます。

1. [**コメント**] ボックスに、コードに表示するコメントを追加します。

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
