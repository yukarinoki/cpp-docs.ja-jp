---
title: コントロールのスタイルのツリー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
dev_langs:
- C++
helpviewer_keywords:
- TVS_LINESATROOT [MFC]
- styles [MFC], CTreeCtrl
- styles [MFC], tree control
- TVS_HASLINES
- TVS_SINGLEEXPAND
- CTreeCtrl class [MFC], styles
- TVS_EDITLABELS [MFC]
- TVS_NOTOOLTIPS [MFC]
- TVS_HASBUTTONS [MFC]
- tree controls [MFC], styles
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c0158bfc24eb86f88695b58943989fbb7cac435
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-styles"></a>ツリー コントロールのスタイル
ツリー コントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) スタイルのツリー コントロールの外観の側面を制御します。 ツリー コントロールを作成するときに、初期のスタイルを設定します。 取得してを使用してツリーのコントロールを作成した後、スタイルを変更することができます、 [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584)と[SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows 関数を指定する**GWL_STYLE**の`nIndex`パラメーター。 スタイルの一覧については、次を参照してください。[ツリー ビュー コントロールのウィンドウ スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760013)Windows SDK に含まれています。  
  
 **線でつなぐ**スタイルでは、ツリー コントロールの階層のグラフィック表示を対応する親項目に子項目をリンク線を描画します。 このスタイルは、階層のルートにある項目をリンクできません。 これを行うには、結合する必要があります、**線でつなぐ**と**ルート**スタイル。  
  
 ユーザーは、展開したり、親アイテムをダブルクリックして、親項目の子項目の一覧を折りたたんだりできます。 ツリー コントロールを持つ、 **TVS_SINGLEEXPAND**スタイルでは、展開に、選択された項目と、項目を折りたたみます。 選択した項目をシングル クリックして、マウスが使用され、その項目が閉じられた場合は、展開されます。 場合は、選択した項目が開いているときに、クリックしては解除されます。  
  
 ツリー コントロールを持つ、**切り替え**スタイルは、各親項目の左側にボタンを追加します。 ユーザーを展開または親項目をダブルクリックする代わりに、子項目を折りたたむボタンをクリックできます。 **切り替え**ボタンは、階層のルートにある項目に追加されません。 結合する必要があるためには、**線でつなぐ**、**ルート**、および**切り替え**です。  
  
 **TVS_EDITLABELS**スタイルでは、ユーザーは、ツリー コントロール項目のラベルを編集します。 ラベルの編集に関する詳細については、次を参照してください。[ツリー コントロールのラベルの編集](../mfc/tree-control-label-editing.md)このトピックで後述します。  
  
 **TVS_NOTOOLTIPS**スタイルのツリー ビュー コントロールの自動ツール ヒント機能を無効にします。 この機能は、全体のタイトルに現在表示されていない場合は、マウス カーソルの下にある項目のタイトルを含む、ツール ヒントを自動的に表示します。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

