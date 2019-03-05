---
title: ツリー コントロールのスタイル
ms.date: 11/04/2016
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
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
ms.openlocfilehash: d03961c1c905689af5894897a59262c8f00e73fa
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290766"
---
# <a name="tree-control-styles"></a>ツリー コントロールのスタイル

ツリー コントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) のスタイルは、ツリー コントロールの外観の側面を制御します。 ツリー コントロールを作成するときに、初期のスタイルを設定します。 取得しを使用してツリーのコントロールを作成した後、スタイルを変更することができます、 [GetWindowLong](/windows/desktop/api/winuser/nf-winuser-getwindowlonga)と[SetWindowLong](/windows/desktop/api/winuser/nf-winuser-setwindowlonga) Windows 関数を指定する**GWL_STYLE**の*nIndex*パラメーター。 スタイルの完全な一覧を参照してください。[ツリー ビュー コントロールのウィンドウ スタイル](/windows/desktop/Controls/tree-view-control-window-styles)Windows SDK に含まれています。

**線でつなぐ**スタイルは、対応する親項目に子項目をリンクしている線を描画でツリー コントロールの階層のグラフィック表現を強化します。 このスタイルは、階層のルートにある項目をリンクしていません。 これを行うには、結合する必要があります、**線でつなぐ**と**ルート項目**スタイル。

ユーザーは、展開したり、親アイテムをダブルクリックして子項目の親項目の一覧を折りたたんだりできます。 ツリー コントロールを持つ、 **TVS_SINGLEEXPAND**スタイルと展開に、選択された項目と、縮小します。 シングル クリックで選択した項目にマウスを使用し、その項目が閉じられた場合は展開されます。 選択した項目が開いているときに、クリックした場合は折りたたまされます。

ツリー コントロールを持つ、**切り替え**スタイルは、各親項目の左側にボタンを追加します。 ユーザーを展開または親項目をダブルクリックする代わりに子項目を折りたたむボタンをクリックできます。 **切り替え**ボタンは、階層のルートにある項目を追加しません。 これを行うには、結合する必要があります**線でつなぐ**、**ルート項目**、および**切り替え**します。

**TVS_EDITLABELS**スタイルでは、ユーザーは、ツリー コントロール項目のラベルを編集します。 ラベルの編集に関する詳細については、次を参照してください。[ツリー コントロールのラベルの編集](../mfc/tree-control-label-editing.md)このトピックで後述します。

**TVS_NOTOOLTIPS**スタイルは、ツリー ビュー コントロールの自動ツール ヒント機能を無効にします。 この機能は、全体のタイトルに現在表示されていない場合は、マウスのカーソルの下の項目のタイトルを含む、ツール ヒントを自動的に表示されます。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
