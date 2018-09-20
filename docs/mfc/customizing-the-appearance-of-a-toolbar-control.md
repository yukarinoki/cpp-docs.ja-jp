---
title: ツール バー コントロールの外観のカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TBSTYLE_
dev_langs:
- C++
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c8c66990335e2925e6edd7a884b119df3fc9f88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430229"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>ツール バー コントロールの外観のカスタマイズ

クラス`CToolBarCtrl`外観 (および、場合によっては、動作)、ツールバーのオブジェクトの影響を与える多くのスタイルを提供します。 設定して、ツールバーのオブジェクトを変更、`dwCtrlStyle`のパラメーター、 `CToolBarCtrl::Create` (または`CToolBar::CreateEx`) メンバー関数は、ツール バー コントロールを作成します。

次のスタイルは、ツール バー ボタンの"3D"側面と、ボタンのテキストの配置に影響します。

- **TBSTYLE_FLAT**ツールバーとボタンの両方が透過的なフラット ツールバーを作成します。 ボタンのビットマップ ボタンのテキストが表示されます。 このスタイルを使用する場合、カーソルの下のボタンが強調表示されます。

- **バーオブジェクト**透明なツールバーを作成します。 透過的なツールバーで、ツールバーは透明が、ボタンはできません。 ボタンのビットマップ ボタンのテキストが表示されます。

- **TBSTYLE_LIST**場所ボタンのボタンの右側にテキスト。

> [!NOTE]
>  再描画の問題を防ぐために、 **TBSTYLE_FLAT**と**バーオブジェクト**ツールバー オブジェクトが表示される前に、スタイルを設定する必要があります。

次のスタイルは、ツールバーにユーザーがドラッグを使用して、ツールバーのオブジェクト内の各ボタンの位置を変更し、削除ができるかどうかを決定します。

- **TBSTYLE_ALTDRAG** alt キーを押しながらドラッグすることで、ツールバーのボタンの位置を変更することができます。 このスタイルが指定されていない場合は、ユーザーがボタンをドラッグするときに shift キーを押しする必要があります。

    > [!NOTE]
    >  **ツール**をドラッグできるツール バー ボタンを有効にするスタイルを指定する必要があります。

- **TBSTYLE_REGISTERDROP**生成**TBN_GETOBJECT**通知にマウス ポインターがツール バー ボタン上に配置時に、要求するメッセージがターゲット オブジェクトを削除します。

残りのスタイルでは、ツールバーのオブジェクトの表示と非ビジュアルの側面に影響します。

- **TBSTYLE_WRAPABLE**をボタンの複数の行をできるツールバーを作成します。 ツール バー ボタンできます「ラップ」次の行に、ツールバーが狭すぎてを同じ行にすべてのボタンが含まれます。 分離および折り返されます境界での折り返しが発生します。

- **TBSTYLE_CUSTOMERASE**生成**NM_CUSTOMDRAW**の通知メッセージの処理時に**WM_ERASEBKGND**メッセージ。

- **TBSTYLE_TOOLTIPS**ツールバーにボタンの説明テキストを表示するアプリケーションが使用できるツール ヒント コントロールを作成します。

Toolbar のスタイルと拡張スタイルの完全な一覧については、次を参照してください。[ツール バー コントロールとボタンのスタイル](/windows/desktop/Controls/toolbar-control-and-button-styles)と[ツールバー拡張スタイル](/windows/desktop/Controls/toolbar-extended-styles)Windows SDK にします。

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

