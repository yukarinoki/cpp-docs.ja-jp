---
description: '詳細情報: ツールバーのツールヒント'
title: ツール バーのツール ヒント
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
ms.openlocfilehash: bbf60246e778b60c2a6eacbcb55441806c00fad2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264285"
---
# <a name="toolbar-tool-tips"></a>ツール バーのツール ヒント

ツールヒントは、ボタンの上に一定の時間を置いたときに、ツールバーボタンの目的の短い説明を表示する小さなポップアップウィンドウです。 ツールバーのあるアプリケーションウィザードを使用してアプリケーションを作成する場合は、ツールヒントのサポートが提供されます。 この記事では、アプリケーションウィザードで作成されたツールヒントのサポートと、アプリケーションにツールヒントサポートを追加する方法について説明します。

この記事には、次の内容が含まれます。

- [アクティブ化 (ツールヒントを)](#_core_activating_tool_tips)

- [Flyby ステータスバーの更新](#_core_fly_by_status_bar_updates)

## <a name="activating-tool-tips"></a><a name="_core_activating_tool_tips"></a> アクティブ化 (ツールヒントを)

アプリケーションでツールヒントをアクティブ化するには、次の2つの操作を行う必要があります。

- *DwStyle* パラメーターとして [CToolBar:: Create](../mfc/reference/ctoolbar-class.md#create)関数または [setbarstyle](../mfc/reference/ccontrolbar-class.md#setbarstyle)に渡された他のスタイル (WS_CHILD、WS_VISIBLE などの **CBRS_** スタイル) に CBRS_TOOLTIPS スタイルを追加します。

- 次の手順で説明されているように、ツールバーコマンドのコマンドラインプロンプトを含む文字列リソースに、改行文字 (' \n ') で区切られたツールバーのヒントテキストを追加します。 文字列リソースは、ツールバーボタンの ID を共有します。

#### <a name="to-add-the-tool-tip-text"></a>ツールヒントテキストを追加するには

1. ツールバーエディターでツールバーを編集しているときに、特定のボタンの **ツールバーボタン** の [プロパティ] ウィンドウを開きます。

1. [ **プロンプト** ] ボックスで、そのボタンのツールヒントに表示するテキストを指定します。

> [!NOTE]
> ツールバーエディターでテキストをボタンプロパティとして設定すると、前の手順が置き換えられます。この手順では、文字列リソースを開いて編集する必要がありました。

ツールヒントが有効になっているコントロールバーに子コントロールが配置されている場合、コントロールバーには、次の条件を満たす限り、コントロールバー上のすべての子コントロールのツールヒントが表示されます。

- コントロールの ID が-1 ではありません。

- リソースファイル内の子コントロールと同じ ID を持つ文字列テーブルのエントリには、ツールヒントの文字列があります。

## <a name="flyby-status-bar-updates"></a><a name="_core_fly_by_status_bar_updates"></a> Flyby ステータスバーの更新

ツールヒントに関連する機能は、"flyby" ステータスバーを更新することです。 既定では、ステータスバーのメッセージには、ボタンがアクティブになったときに特定のツールバーボタンだけが表示されます。 に渡されたスタイルの一覧に CBRS_FLYBY を含めると、実際には、ボタンをアクティブにしなくても、 `CToolBar::Create` マウスカーソルがツールバー上を通過したときに、これらのメッセージを更新できます。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [MFC ツールバーの実装 (ツールバーの概要情報)](../mfc/mfc-toolbar-implementation.md)

- [ツール バーのドッキングとフローティング](../mfc/docking-and-floating-toolbars.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md)クラスと[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)クラス

- [ToolBar コントロールの操作](../mfc/working-with-the-toolbar-control.md)

- [古い形式のツール バーの使用](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>関連項目

[MFC ツールバーの実装](../mfc/mfc-toolbar-implementation.md)
