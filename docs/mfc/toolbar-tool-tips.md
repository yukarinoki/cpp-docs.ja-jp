---
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
ms.openlocfilehash: 1762931b75734801659fd6271377260bd0473614
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373457"
---
# <a name="toolbar-tool-tips"></a>ツール バーのツール ヒント

ツール ヒントは、一定期間ボタンの上にマウスを置いたときに、ツール バー ボタンの目的の短い説明を示す小さなポップアップ ウィンドウです。 ツールバーを備えたアプリケーション ウィザードを使用してアプリケーションを作成する場合、ツール ヒントのサポートが提供されます。 この資料では、アプリケーション ウィザードで作成されたツール ヒントのサポートと、アプリケーションにツール ヒント サポートを追加する方法の両方について説明します。

この記事には、次の内容が含まれます。

- [ツール ヒントのアクティブ化](#_core_activating_tool_tips)

- [フライバイステータスバーの更新](#_core_fly_by_status_bar_updates)

## <a name="activating-tool-tips"></a><a name="_core_activating_tool_tips"></a>ツール ヒントのアクティブ化

アプリケーションでツール ヒントをアクティブにするには、次の 2 つの操作を行う必要があります。

- *dwStyle*パラメーターとして渡された他のスタイル (WS_CHILD、WS_VISIBLE、その他の**CBRS_** スタイルなど) にCBRS_TOOLTIPSスタイルを[CToolBar::Create](../mfc/reference/ctoolbar-class.md#create)[追加します。](../mfc/reference/ccontrolbar-class.md#setbarstyle)

- 次の手順で説明するように、ツールバーのヒントテキストを改行文字 ('\n') で区切って、ツールバー コマンドのコマンド ライン プロンプトを含む文字列リソースに追加します。 文字列リソースは、ツール バー ボタンの ID を共有します。

#### <a name="to-add-the-tool-tip-text"></a>ツール ヒント テキストを追加するには

1. ツールバーエディタでツールバーを編集しているときに、指定された**ボタンのツールバーボタンのプロパティ**ウィンドウを開きます。

1. [**プロンプト**] ボックスで、ボタンのツール ヒントに表示するテキストを指定します。

> [!NOTE]
> ツールバー エディタでテキストをボタン プロパティとして設定すると、文字列リソースを開いて編集する必要があった前のプロシージャが置き換えられます。

ツール ヒントが有効になっているコントロール バーに子コントロールが配置されている場合、コントロール バーには、次の条件を満たす限り、コントロール バー上のすべての子コントロールのツール ヒントが表示されます。

- コントロールの ID は - 1 ではありません。

- リソース ファイル内の子コントロールと同じ ID を持つ文字列テーブル エントリには、ツール ヒント文字列があります。

## <a name="flyby-status-bar-updates"></a><a name="_core_fly_by_status_bar_updates"></a>フライバイ ステータス バーの更新

ツールヒントに関連する機能は、ステータスバーの更新「フライバイ」です。 既定では、ステータス バーのメッセージは、ボタンがアクティブになったときに特定のツール バー ボタンのみを示します。 に渡すスタイルのリストにCBRS_FLYBYを`CToolBar::Create`含めることで、マウス カーソルがツール バー上を通過したときに、ボタンを実際にアクティブにすることなく、これらのメッセージを更新できます。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [MFC ツール バーの実装 (ツール バーの概要情報)](../mfc/mfc-toolbar-implementation.md)

- [ツール バーのフローティングとドッキング](../mfc/docking-and-floating-toolbars.md)

- [クラス](../mfc/reference/ctoolbar-class.md)[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)

- [ToolBar コントロールの操作](../mfc/working-with-the-toolbar-control.md)

- [古い形式のツール バーの使用](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>関連項目

[MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)
