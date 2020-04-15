---
title: ツール バー コントロールの外観のカスタマイズ
ms.date: 11/04/2016
f1_keywords:
- TBSTYLE_
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
ms.openlocfilehash: 9f4f9d90113d5074555d1b0cc411f854abc67fe5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377463"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>ツール バー コントロールの外観のカスタマイズ

Class`CToolBarCtrl`には、ツール バー オブジェクトの外観 (および場合によっては動作) に影響を与える多くのスタイルが用意されています。 ツール バー コントロールを最初`dwCtrlStyle`に作成するときに`CToolBarCtrl::Create`、(`CToolBar::CreateEx`または ) メンバー関数のパラメーターを設定して、ツール バー オブジェクトを変更します。

次のスタイルは、ツールバーボタンの「3D」のアスペクトとボタンテキストの配置に影響します。

- **TBSTYLE_FLAT**ツールバーとボタンの両方が透明なフラットなツールバーを作成します。 ボタンのテキストは、ボタンビットマップの下に表示されます。 このスタイルを使用すると、カーソルの下にあるボタンが自動的に強調表示されます。

- **TBSTYLE_TRANSPARENT**透明なツールバーを作成します。 透明なツールバーでは、ツールバーは透明ですが、ボタンは透明ではありません。 ボタンのテキストは、ボタンビットマップの下に表示されます。

- **TBSTYLE_LIST**ボタンのビットマップの右側にボタン テキストを配置します。

> [!NOTE]
> 再描画の問題を回避するには、ツールバー オブジェクトが表示される前に **、TBSTYLE_FLAT**と**TBSTYLE_TRANSPARENT**のスタイルを設定する必要があります。

次のスタイルは、ユーザーがドラッグ アンド ドロップを使用して、ツール バー オブジェクト内の個々のボタンを再配置できるかどうかを決定します。

- **TBSTYLE_ALTDRAG**ユーザーは、Alt キーを押しながらドラッグして、ツールバー ボタンの位置を変更できます。 このスタイルを指定しない場合、ユーザーは Shift キーを押しながらボタンをドラッグする必要があります。

    > [!NOTE]
    >  ツール バー ボタンをドラッグできるようにするには **、CCS_ADJUSTABLE**スタイルを指定する必要があります。

- **TBSTYLE_REGISTERDROP**マウス ポインターがツール バー ボタンの上を通過したときにドロップターゲット オブジェクトを要求する**TBN_GETOBJECT**通知メッセージを生成します。

残りのスタイルは、ツールバー オブジェクトのビジュアルおよび非ビジュアルの側面に影響します。

- **TBSTYLE_WRAPABLE**複数行のボタンを持つことができるツール バーを作成します。 ツールバーボタンは、ツールバーが狭くなりすぎてすべてのボタンを同じ行に含める場合に、次の行に「折り返し」できます。 折り返しは、分離境界と非グループ境界で発生します。

- **TBSTYLE_CUSTOMERASE****WM_ERASEBKGND**メッセージ**を処理するときに、NM_CUSTOMDRAW**通知メッセージを生成します。

- **TBSTYLE_TOOLTIPS**ツール バーのボタンの説明テキストを表示するためにアプリケーションが使用できるツール ヒント コントロールを作成します。

ツール バースタイルと拡張スタイルの詳細については、Windows SDK の[ツールバー コントロールとボタン スタイルと](/windows/win32/Controls/toolbar-control-and-button-styles)[ツールバー拡張スタイル](/windows/win32/Controls/toolbar-extended-styles)を参照してください。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
