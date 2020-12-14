---
description: 詳細については、「ダイアログボックスでのコモンコントロールの使用」を参照してください。
title: ダイアログ ボックスでのコモン コントロールの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- dialog box controls [MFC], common controls
- Windows common controls [MFC], in dialog boxes
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
ms.openlocfilehash: 73395ae5b3542f338f3783fd5f0c41116821fed6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202406"
---
# <a name="using-common-controls-in-a-dialog-box"></a>ダイアログ ボックスでのコモン コントロールの使い方

Windows コモンコントロールは、ダイアログ [ボックス](../mfc/dialog-boxes.md)、フォームビュー、レコードビュー、およびダイアログテンプレートに基づくその他のウィンドウで使用できます。 次の手順は軽微な変更を加えて、フォームにも使用できます。

## <a name="procedures"></a>手順

#### <a name="to-use-a-common-control-in-a-dialog-box"></a>コモンコントロールをダイアログボックスで使用するには

1. ダイアログ [エディターを使用して](../mfc/using-the-dialog-editor-to-add-controls.md)、ダイアログテンプレートにコントロールを配置します。

1. コントロールを表すメンバー変数をダイアログクラスに追加します。 [ **メンバー変数の追加** ] ダイアログボックスで、[ **コントロール変数** ] チェックボックスをオンにし、カテゴリに対して [ **コントロール** **]** が選択されていることを確認します。

1. このコモンコントロールがプログラムに入力を提供している場合は、これらの入力値を処理するために、ダイアログクラスの追加のメンバー変数を宣言します。

    > [!NOTE]
    >  これらのメンバー変数は、クラスビューのコンテキストメニューを使用して追加できます (「 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)」を参照してください)。

1. ダイアログクラスの [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) で、コモンコントロールの初期条件を設定します。 前の手順で作成したメンバー変数を使用して、メンバー関数を使用して初期値とその他の設定を設定します。 設定の詳細については、次のコントロールの説明を参照してください。

   ダイアログボックスでコントロールを初期化するには、 [ダイアログデータエクスチェンジ](../mfc/dialog-data-exchange-and-validation.md) (DDX) を使用することもできます。

1. ダイアログボックスのコントロールのハンドラーでは、メンバー変数を使用してコントロールを操作します。 メソッドの詳細については、次のコントロールの説明を参照してください。

    > [!NOTE]
    >  メンバー変数は、ダイアログボックス自体が存在する間だけ存在します。 ダイアログボックスを閉じた後に、コントロールに対して入力値をクエリすることはできません。 コモンコントロールからの入力値を操作するには、 `OnOK` ダイアログクラスでをオーバーライドします。 オーバーライドで、コントロールに対して入力値をクエリし、それらの値をダイアログクラスのメンバー変数に格納します。

    > [!NOTE]
    >  ダイアログボックス内のコントロールの値を設定または取得するために、ダイアログデータエクスチェンジを使用することもできます。

## <a name="remarks"></a>解説

ダイアログボックスにいくつかの一般的なコントロールが追加されると、ダイアログボックスが機能しなくなります。 この状況の処理の詳細については [、「コントロールをダイアログに追加](../windows/adding-editing-or-deleting-controls.md) する」を参照してください。

## <a name="what-do-you-want-to-do"></a>どうしたいんですか

- [ダイアログエディターではなく、手動でコントロールをダイアログボックスに追加する](../mfc/adding-controls-by-hand.md)

- [標準の Windows コモンコントロールの1つからコントロールを派生させる](../mfc/deriving-controls-from-a-standard-control.md)

- [子ウィンドウとしてコモンコントロールを使用する](../mfc/using-a-common-control-as-a-child-window.md)

- [コントロールから通知メッセージを受信する](../mfc/receiving-notification-from-common-controls.md)

- [ダイアログデータエクスチェンジ (DDX) を使用する](../mfc/dialog-data-exchange-and-validation.md)

## <a name="see-also"></a>関連項目

[コントロールの作成と使用](../mfc/making-and-using-controls.md)<br/>
[コントロール](../mfc/controls-mfc.md)
