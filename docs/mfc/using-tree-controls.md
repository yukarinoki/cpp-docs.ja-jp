---
title: ツリー コントロールの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bd7210f2f63d55fc4244a6b88456ede1265c8e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-tree-controls"></a>ツリー コントロールの使い方
ツリー コントロールの一般的な使用法 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 次のパターンします。  
  
-   コントロールが作成されます。 コントロールがダイアログ ボックスのテンプレートで指定されている場合、または使用する場合`CTreeView`、ダイアログ ボックスまたはビューの作成時に、作成は自動です。 その他のいくつかのウィンドウの子ウィンドウとしてツリーのコントロールを作成する場合を使用して、[作成](../mfc/reference/ctreectrl-class.md#create)メンバー関数。  
  
-   ツリー コントロールのイメージを使用する場合は、イメージ リストを呼び出して設定[SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist)です。 呼び出して、インデント設定を変更することも[SetIndent](../mfc/reference/ctreectrl-class.md#setindent)です。 これを行う適切な時刻が含まれる[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (でのコントロールのダイアログ ボックス) または[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)(views) 用です。  
  
-   呼び出して、コントロールにデータをまとめる、`CTreeCtrl`の[InsertItem](../mfc/reference/ctreectrl-class.md#insertitem)データ項目ごとに 1 回の関数。 `InsertItem` 場合など、後でそれを参照する際の項目へのハンドルを返すは、子項目を追加します。 データを初期化するために適切な時刻が含まれる`OnInitDialog`(でのコントロールのダイアログ ボックス) または`OnInitialUpdate`(views) 用です。  
  
-   ユーザー対話するので、コントロールで、さまざまな通知メッセージが送信されます。 各追加することで処理するメッセージを処理する関数を指定することができます、 **ON_NOTIFY_REFLECT**マクロ コントロール ウィンドウのメッセージ マップに追加したりして、`ON_NOTIFY`を親ウィンドウのメッセージ マップ マクロです。 参照してください[ツリー コントロールの通知メッセージ](../mfc/tree-control-notification-messages.md)可能な通知の一覧については、このトピックで後述します。  
  
-   コントロールの値を設定する、さまざまなセットのメンバー関数を呼び出します。 実行できる変更には、インデントを設定し、テキスト、画像、または項目に関連付けられているデータの変更が含まれます。  
  
-   さまざまな Get 関数を使用して、コントロールの内容を確認します。 親、子、および指定した項目の兄弟へのハンドルを取得できるようにする関数で、ツリー コントロールの内容を走査することもできます。 特定のノードの子を並べ替えることもできます。  
  
-   コントロールに完了したらが正常に破棄されることを確認します。 ツリー コントロール ダイアログ ボックスか場合は、ビュー、および`CTreeCtrl`オブジェクトは自動的に破棄されます。 かどうか、する必要はありません、両方のコントロールをことを確認して、`CTreeCtrl`オブジェクトが破棄されました。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

