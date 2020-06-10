---
title: MFC ツール バーの実装
ms.date: 11/04/2016
helpviewer_keywords:
- toolbars [MFC], creating
- buttons [MFC], MFC toolbars
- toolbars [MFC], docking
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- floating toolbars [MFC]
- toolbars [MFC], floating
- docking toolbars [MFC]
- bitmaps [MFC], toolbar
- toolbar controls [MFC]
- CToolBarCtrl class [MFC], implementing toolbars
- tool tips [MFC], enabling
- toolbars [MFC]
- toolbars [MFC], implementing MFC toolbars
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
ms.openlocfilehash: 7876e9403389c19a24e5a482534d0f223eaa4bf5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626123"
---
# <a name="mfc-toolbar-implementation"></a>MFC ツール バーの実装

ツールバーは、コントロールのビットマップイメージを含む[コントロールバー](control-bars.md)です。 これらのイメージはプッシュ ボタン、チェック ボックス、オプション ボタンに似た動作をすることができます。 MFC[には](reference/ctoolbar-class.md)、ツールバーを管理するためのクラスが用意されています。

これを有効にすると、MFC ツール バーのユーザーは、ツール バーをウィンドウの端にドッキングするか、アプリケーション ウィンドウ内の任意の場所にツール バーを "フローティング" させることができます。 MFC では、開発環境のようなカスタマイズ可能なツール バーをサポートしていません。

MFC では、ツール ヒントもサポートしています。これは、マウス ポインターをボタンの上に移動したときに、ツール バー ボタンの目的を説明する小さなポップアップ ウィンドウです。 既定では、ユーザーがツール バー ボタンをクリックすると、ステータス バー (表示されている場合) の中に、ステータス文字列が表示されます。 ボタンをクリックせずに、マウス ポインターをツール バー ボタンの上に移動したときに、ステータス文字列の表示を更新する、"フライ バイ" (リアルタイム更新) ステータス バーを有効にすることもできます。

> [!NOTE]
> MFC バージョン 4.0 の時点で、ツール バーとツール ヒントは、MFC 固有の以前の実装ではなく、Windows 95 以降の機能を使用して実装されています。

旧バージョンとの互換性のために、MFC では、以前のツールバーの実装がクラスに保持され `COldToolBar` ます。 以前のバージョンの MFC のドキュメントは、「」に記載されて `COldToolBar` `CToolBar` います。

アプリケーション ウィザードの [ツール バー] オプションをクリックし、プログラムの最初のツール バーを作成します。 追加のツール バーを作成することもできます。

この記事では、次の項目を紹介します。

- [ツールバーのボタン](#_core_toolbar_buttons)

- [ツール バーのフローティングとドッキング](#_core_docking_and_floating_toolbars)

- [ツールバーとツールヒント](#_core_toolbars_and_tool_tips)

- [CToolBar クラスと CToolBarCtrl クラス](#_core_the_ctoolbar_and_ctoolbarctrl_classes)

- [ツールバーのビットマップ](#_core_the_toolbar_bitmap)

## <a name="toolbar-buttons"></a><a name="_core_toolbar_buttons"></a>ツールバーのボタン

ツール バー内のボタンは、メニュー内の項目に似ています。 どちらの種類のユーザー インターフェイス オブジェクトも、コマンドを生成します。プログラムはハンドラー関数を提供して、これらのコマンドを処理します。 多くの場合、ツール バー ボタンはメニュー コマンドの機能を複製したものであり、同じ機能に対する別のユーザー インターフェイスを提供します。 このような重複は、単純にボタンとメニュー項目に対して同じ ID を付与する方法で実現できます。

ツール バー内で、プッシュ ボタン、チェック ボックス、またはオプション ボタンと同じ外観でボタンを作成し、同じ動作をさせることができます。 詳細については、「クラス[CToolBar](reference/ctoolbar-class.md)」を参照してください。

## <a name="docking-and-floating-toolbars"></a><a name="_core_docking_and_floating_toolbars"></a>ドッキングツールバーとフローティングツールバー

MFC ツール バーでは、次のことを実行できます。

- 親ウィンドウの 1 つの辺に固定したままにします。

- ドラッグして、親ウィンドウの任意の辺に "ドッキング" させます (取り付けます)。

- フレーム ウィンドウから切り離し、ミニフレーム ウィンドウの形でツール バーとして使用します。このツール バーは、ユーザーが任意の場所に移動できます。

- フローティング中にサイズを変更します。

詳細については、「[ドッキングツールバーとフローティングツールバー](docking-and-floating-toolbars.md)」を参照してください。

## <a name="toolbars-and-tool-tips"></a><a name="_core_toolbars_and_tool_tips"></a>ツールバーとツールヒント

MFC ツール バーには "ツール ヒント" を表示させることもできます。ツール ヒントとは、ツール バー ボタンの用途を説明する短いテキストを表示する小さなポップアップ ウィンドウのことです。 ユーザーがツール バー ボタンの上にマウス ポインタを置くと、ヒントを示すツール ヒントのウィンドウがポップアップ表示されます。 詳細については、「[ツールバーツールのヒント](toolbar-tool-tips.md)」を参照してください。

## <a name="the-ctoolbar-and-ctoolbarctrl-classes"></a><a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a>CToolBar クラスと CToolBarCtrl クラス

アプリケーションのツールバーは、 [CToolBar](reference/ctoolbar-class.md)クラスを使用して管理します。 MFC Version 4.0 では、Windows 95 以降、および Windows NT Version 3.51 以降のバージョンで使用されているツール バー コモン コントロールを使用できるように、`CToolBar` が再実装されています。

この再実装により、それらのオペレーティング システムでサポートされているコントロールを MFC で利用できるため、ツール バー関連の MFC コードは少なくなりました。 また、この再実装によって性能も向上しています。 メンバー関数を使用すると `CToolBar` 、ツールバーを操作できます。また、基になる[CToolBarCtrl](reference/ctoolbarctrl-class.md)オブジェクトへの参照を取得し、そのメンバー関数を呼び出して、ツールバーのカスタマイズや追加機能を行うこともできます。

> [!TIP]
> 以前の形式の `CToolBar` を実装するために多大な労力を費やしてきた場合は、そのまま以前の形式のツール バーを使用できます。 [前のツールバーの使用に](using-your-old-toolbars.md)関する記事をご覧ください。

MFC の一般的なサンプル[DOCKTOOL](../overview/visual-cpp-samples.md)も参照してください。

## <a name="the-toolbar-bitmap"></a><a name="_core_the_toolbar_bitmap"></a>ツールバーのビットマップ

`CToolBar` オブジェクトは、いったん生成された後は、各ボタンのイメージを含む 1 つのビットマップを読み込んでツール バー イメージを作成します。 アプリケーションウィザードでは、Visual C++[ツールバーエディター](../windows/toolbar-editor.md)を使用してカスタマイズできる標準のツールバービットマップが作成されます。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ツールバーの基礎](toolbar-fundamentals.md)

- [ツール バーのフローティングとドッキング](docking-and-floating-toolbars.md)

- [ツールバーのツールヒント](toolbar-tool-tips.md)

- [ツールバーコントロールの操作](working-with-the-toolbar-control.md)

- [以前のツールバーの使用](using-your-old-toolbars.md)

- [CToolBar](reference/ctoolbar-class.md)クラスと[CToolBarCtrl](reference/ctoolbarctrl-class.md)クラス

## <a name="see-also"></a>関連項目

[[ツール バー]](toolbars.md)<br/>
[ツールバーエディター](../windows/toolbar-editor.md)
