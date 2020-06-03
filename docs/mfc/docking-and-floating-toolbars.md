---
title: ツール バーのドッキングとフローティング
ms.date: 11/04/2016
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
helpviewer_keywords:
- size [MFC], toolbars
- size
- frame windows [MFC], toolbar docking
- CBRS_ALIGN_ANY constant [MFC]
- palettes, floating
- toolbars [MFC], docking
- CBRS_SIZE_DYNAMIC constant [MFC]
- floating toolbars
- toolbars [MFC], size
- toolbars [MFC], floating
- fixed-size toolbars
- CBRS_SIZE_FIXED constant [MFC]
- toolbar controls [MFC], wrapping
- toolbars [MFC], wrapping
- floating palettes
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
ms.openlocfilehash: 30113565167b96b0df84a65768a1dfabe92ceffe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369769"
---
# <a name="docking-and-floating-toolbars"></a>ツール バーのドッキングとフローティング

Microsoft Foundation クラス ライブラリは、ドッキング可能なツール バーをサポートしています。 ドッキング可能なツール バーは、親ウィンドウの任意の側にアタッチまたはドッキングするか、独自のミニフレーム ウィンドウで切り離したり浮動させたりすることができます。 この記事では、アプリケーションでドッキング可能なツール バーを使用する方法について説明します。

アプリケーション ウィザードを使用してアプリケーションのスケルトンを生成する場合は、ドッキング可能なツールバーを作成するかどうかを選択するよう求められます。 既定では、アプリケーション ウィザードは、アプリケーションにドッキング可能なツールバーを配置するために必要な 3 つのアクションを実行するコードを生成します。

- [フレーム ウィンドウでのドッキングを有効に](#_core_enabling_docking_in_a_frame_window)する:

- [ツールバーのドッキングを有効に](#_core_enabling_docking_for_a_toolbar)する:

- [ツールバーをフレーム ウィンドウにドッキング](#_core_docking_the_toolbar)します。

これらの手順のいずれかが欠落している場合は、アプリケーションに標準ツールバーが表示されます。 最後の 2 つの手順は、アプリケーションのドッキング可能なツール バーごとに実行する必要があります。

この資料で取り上げるその他のトピックには、次のものがあります。

- [ツールバーを固定する](#_core_floating_the_toolbar)

- [ツール バーの動的なサイズ変更](#_core_dynamically_resizing_the_toolbar)

- [固定スタイルのツールバーの折り返し位置を設定する](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)

例については、MFC の一般的なサンプル[の DOCKTOOL](../overview/visual-cpp-samples.md)を参照してください。

## <a name="enabling-docking-in-a-frame-window"></a><a name="_core_enabling_docking_in_a_frame_window"></a>フレーム ウィンドウでのドッキングの有効化

フレーム ウィンドウにツール バーをドッキングするには、ドッキングを許可するためにフレーム ウィンドウ (または出力先) を有効にする必要があります。 これは、フレーム ウィンドウのどちら側がドッキングを受け入れるかを示すスタイル ビットのセットである 1 つの*DWORD*パラメーターを受け取る[CFrameWnd::EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking)関数を使用して行われます。 ドッキングするツールバーが複数ある場合、渡されたパラメーターに示されている辺`EnableDocking`は、上、下、左、右の順序で使用されます。 コントロール バーを任意の場所にドッキングできるようにする場合は **、CBRS_ALIGN_ANY** `EnableDocking`を に渡します。

## <a name="enabling-docking-for-a-toolbar"></a><a name="_core_enabling_docking_for_a_toolbar"></a>ツールバーのドッキングを有効にする

ドッキング先を準備したら、ツールバー (またはソース) を同様の方法で準備する必要があります。 [CControlBar::ドッキングする](../mfc/reference/ccontrolbar-class.md#enabledocking)各ツールバーの有効化ドッキングを呼び出し、ドッキング先の辺を指定します。 フレーム ウィンドウでドッキングが有効になっている辺に`CControlBar::EnableDocking`一致するように呼び出しで指定された辺がない場合、ツール バーはドッキングできません。 フローティング状態になると、フローティング ツールバーのままで、フレーム ウィンドウにドッキングできなくなります。

目的の効果が永続的に浮動ツールバーの場合は`EnableDocking`、0 をパラメーターとして呼び出します。 次に[、CFrameWnd::フロートコントロールバー](../mfc/reference/cframewnd-class.md#floatcontrolbar)を呼び出します。 ツールバーは固定されたままで、固定はできません。

## <a name="docking-the-toolbar"></a><a name="_core_docking_the_toolbar"></a>ツールバーのドッキング

フレームワークは、ドッキングを許可するフレーム ウィンドウの側面にツール バーをドロップしようとすると[、CFrameWnd::DockControlBar](../mfc/reference/cframewnd-class.md#dockcontrolbar)を呼び出します。

また、この関数を呼び出して、コントロール バーをフレーム ウィンドウにドッキングできます。 これは通常、初期化中に行われます。 複数のツールバーをフレーム ウィンドウの特定の側面にドッキングできます。

## <a name="floating-the-toolbar"></a><a name="_core_floating_the_toolbar"></a>ツールバーのフローティング

ドッキング可能なツールバーをフレーム ウィンドウから切り離す場合は、ツールバーをフローティングと呼びます。 これを行うには[、CFrameWnd::フロートコントロールバー](../mfc/reference/cframewnd-class.md#floatcontrolbar)を呼び出します。 浮動するツールバー、配置する点、およびフローティング ツールバーが水平か垂直かを決定する配置スタイルを指定します。

ユーザーがドッキング位置からツール バーをドラッグしてドッキングが有効になっていない場所にドロップすると、フレームワークはこの関数を呼び出します。 これはフレーム ウィンドウの内側または外側の任意の場所に配置できます。 と同様`DockControlBar`に、初期化中にこの関数を呼び出すこともできます。

ドッキング可能なツール バーの MFC 実装では、ドッキング可能なツール バーをサポートする一部のアプリケーションで使用できる拡張機能の一部は提供されません。 カスタマイズ可能なツールバーなどの機能は提供されません。

## <a name="dynamically-resizing-the-toolbar"></a><a name="_core_dynamically_resizing_the_toolbar"></a>ツール バーの動的なサイズ変更

Visual C++ バージョン 4.0 では、アプリケーションのユーザーが浮動ツールバーのサイズを動的に変更できるようにすることができます。 通常、ツールバーには長い直線形状があり、水平に表示されます。 ただし、ツールバーの向きや形状は変更できます。 たとえば、ユーザーがフレーム ウィンドウの垂直側面の 1 つに対してツール バーをドッキングすると、図形は垂直方向のレイアウトに変わります。 また、ツールバーの形状を複数のボタン行を持つ四角形に変更することもできます。

次のようにすることができます。

- 動的サイズ設定をツールバー特性として指定します。

- 固定サイズをツールバー特性として指定します。

このサポートを提供するために[、CToolBar::Create](../mfc/reference/ctoolbar-class.md#create)メンバー関数の呼び出しで使用する 2 つの新しいツール バー スタイルがあります。 これらは次のとおりです。

- **CBRS_SIZE_DYNAMIC**コントロールバーは動的です。

- **CBRS_SIZE_FIXED**コントロールバーが固定されています。

サイズの動的なスタイルを使用すると、ユーザーは固定されている間は固定されている間はツールバーのサイズを変更できません。 ユーザーが端をドラッグすると、ツール バーは図形を変更する必要がある場合に "折り返し" します。

サイズ固定スタイルは、ツールバーの折り返し状態を保持し、各列のボタンの位置を固定します。 アプリケーションのユーザーは、ツールバーの形状を変更できません。 ツール バーは、ボタン間の区切り記号の位置など、指定された位置で折り返されます。 ツールバーがドッキングされているか浮動であるかにかかわらず、この図形は維持されます。 効果は、ボタンの複数の列を持つ固定パレットです。

[CToolBar::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle)を使用して、ツール バーのボタンの状態とスタイルを返すこともできます。 ボタンのスタイルによって、ボタンの表示方法とユーザー入力への応答が決まります。状態は、ボタンがラップされた状態であるかどうかを示します。

## <a name="setting-wrap-positions-for-a-fixed-style-toolbar"></a><a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a>固定スタイルツールバーの折り返し位置の設定

サイズ固定スタイルのツールバーの場合は、ツールバーが折り返す位置のツールバー ボタンインデックスを指定します。 次のコードは、メイン フレーム ウィンドウの`OnCreate`オーバーライドでこれを行う方法を示しています。

[!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]

MFC の一般的なサンプル[DOCKTOOL](../overview/visual-cpp-samples.md)は、CControlBar および[CToolBar](../mfc/reference/ccontrolbar-class.md)クラスのメンバー関数を使用して、ツール バーの動的レイアウトを管理する方法を示します。 [CToolBar](../mfc/reference/ctoolbar-class.md) ファイルの編集ボックスを参照してください。ドックツールのCPP。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [ツールバーの基本](../mfc/toolbar-fundamentals.md)

- [ツールバーのツールヒント](../mfc/toolbar-tool-tips.md)

- [古い形式のツール バーの使用](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>関連項目

[MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)
