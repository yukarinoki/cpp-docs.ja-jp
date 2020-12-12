---
description: 詳細については、「ツリーコントロールの使用」を参照してください。
title: ツリー コントロールの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
ms.openlocfilehash: 7b8a10acc3ee256f4b26c9988c4de7df900e1535
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143196"
---
# <a name="using-tree-controls"></a>ツリー コントロールの使い方

通常、ツリーコントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) の使用方法は次のパターンに従います。

- コントロールが作成されます。 コントロールがダイアログボックステンプレートで指定されている場合、またはを使用している場合は `CTreeView` 、ダイアログボックスまたはビューの作成時に作成が自動的に作成されます。 他のウィンドウの子ウィンドウとしてツリーコントロールを作成する場合は、 [create](../mfc/reference/ctreectrl-class.md#create) member 関数を使用します。

- ツリーコントロールでイメージを使用する場合は、 [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist)を呼び出してイメージリストを設定します。 また、 [Setindent](../mfc/reference/ctreectrl-class.md#setindent)を呼び出してインデントを変更することもできます。 これを行うには、 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (ダイアログボックスのコントロールの場合) または [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (ビューの場合) を使用することをお勧めします。

- データ `CTreeCtrl` 項目ごとに1回の [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) 関数を呼び出して、データをコントロールに配置します。 `InsertItem` 子項目を追加するときなど、後で参照するために使用できる項目へのハンドルを返します。 データの初期化には、 `OnInitDialog` (ダイアログボックスのコントロールの場合) または `OnInitialUpdate` (ビューの場合) の方が適しています。

- ユーザーがコントロールと対話すると、さまざまな通知メッセージが送信されます。 コントロールウィンドウのメッセージマップに ON_NOTIFY_REFLECT マクロを追加するか、または親ウィンドウのメッセージマップに ON_NOTIFY マクロを追加することによって、処理する各メッセージを処理する関数を指定できます。 使用可能な通知の一覧については、このトピックの後半の「 [ツリーコントロールの通知メッセージ](../mfc/tree-control-notification-messages.md) 」を参照してください。

- さまざまな Set メンバー関数を呼び出して、コントロールの値を設定します。 行うことができる変更には、インデントを設定したり、アイテムに関連付けられたテキスト、画像、またはデータを変更したりすることがあります。

- さまざまな Get 関数を使用して、コントロールの内容を確認します。 また、ツリーコントロールの内容を、指定した項目の親、子、および兄弟へのハンドルの取得を可能にする関数を使用して走査することもできます。 特定のノードの子を並べ替えることもできます。

- コントロールが完成したら、適切に破棄されていることを確認します。 ツリーコントロールがダイアログボックス内にある場合、またはビューである場合、オブジェクトは `CTreeCtrl` 自動的に破棄されます。 それ以外の場合は、コントロールとオブジェクトの両方が正しく破棄されていることを確認する必要があり `CTreeCtrl` ます。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
