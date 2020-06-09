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
ms.openlocfilehash: f40d8860f2e514bf3c9e9364a664326250c9627a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615831"
---
# <a name="docking-and-floating-toolbars"></a>ツール バーのドッキングとフローティング

Microsoft Foundation Class ライブラリは、ドッキング可能ツールバーをサポートします。 ドッキング可能なツールバーは、親ウィンドウの任意の辺にアタッチしたりドッキングしたりすることができます。または、独自のミニフレームウィンドウでデタッチまたはフローティングできます。 この記事では、アプリケーションでドッキング可能ツールバーを使用する方法について説明します。

アプリケーションウィザードを使用してアプリケーションのスケルトンを生成する場合は、ドッキング可能なツールバーを使用するかどうかを選択するように求められます。 既定では、アプリケーションウィザードによって、アプリケーションにドッキング可能なツールバーを配置するために必要な次の3つの操作を実行するコードが生成されます。

- [フレームウィンドウでのドッキングを有効に](#_core_enabling_docking_in_a_frame_window)します。

- [ツールバーのドッキングを有効に](#_core_enabling_docking_for_a_toolbar)します。

- [ツールバーをフレームウィンドウにドッキング](#_core_docking_the_toolbar)します。

これらの手順のいずれかが存在しない場合は、アプリケーションに標準のツールバーが表示されます。 アプリケーションのドッキング可能な各ツールバーについて、最後の2つの手順を実行する必要があります。

この記事で説明するその他のトピックは次のとおりです。

- [ツールバーのフローティング](#_core_floating_the_toolbar)

- [ツールバーのサイズを動的に変更する](#_core_dynamically_resizing_the_toolbar)

- [固定スタイルのツールバーの折り返し位置の設定](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)

例については、MFC の一般的なサンプル[DOCKTOOL](../overview/visual-cpp-samples.md)を参照してください。

## <a name="enabling-docking-in-a-frame-window"></a><a name="_core_enabling_docking_in_a_frame_window"></a>フレームウィンドウでのドッキングの有効化

フレームウィンドウにツールバーをドッキングするには、ドッキングを許可するためにフレームウィンドウ (または変換先) を有効にする必要があります。 これを行うには、 [CFrameWnd:: EnableDocking](reference/cframewnd-class.md#enabledocking)関数を使用します。この関数は、1つの*DWORD*パラメーターを受け取ります。これは、フレームウィンドウのどの側がドッキングを受け入れるかを示す一連のスタイルビットです。 ツールバーをドッキングしようとしているときに、ドッキングできる複数の辺がある場合、に渡されるパラメーターで示される辺 `EnableDocking` は、top、bottom、left、right の順序で使用されます。 コントロールバーを任意の場所にドッキングできるようにするには、 **CBRS_ALIGN_ANY**をに渡し `EnableDocking` ます。

## <a name="enabling-docking-for-a-toolbar"></a><a name="_core_enabling_docking_for_a_toolbar"></a>ツールバーのドッキングの有効化

ドッキング先の準備が完了したら、同様の方法でツールバー (またはソース) を準備する必要があります。 ドッキングするツールバーごとに[CControlBar:: EnableDocking](reference/ccontrolbar-class.md#enabledocking)を呼び出して、ツールバーがドッキングされる対象の辺を指定します。 フレームウィンドウでドッキングが有効になっている辺と一致する辺が、の呼び出しで指定されていない場合 `CControlBar::EnableDocking` 、ツールバーをドッキングすることはできません。 フローティング状態になると、フローティングツールバーのままになり、フレームウィンドウにドッキングできなくなります。

必要な効果が永続的なツールバーの場合は、 `EnableDocking` パラメーター0を指定してを呼び出します。 次に、 [CFrameWnd:: FloatControlBar](reference/cframewnd-class.md#floatcontrolbar)を呼び出します。 ツールバーはフローティング状態のままで、任意の場所にドッキングすることはできません。

## <a name="docking-the-toolbar"></a><a name="_core_docking_the_toolbar"></a>ツールバーのドッキング

フレームワークは、ユーザーがドッキングを可能にするフレームウィンドウの辺にツールバーをドロップしようとしたときに、 [CFrameWnd::D ockcontrolbar](reference/cframewnd-class.md#dockcontrolbar)を呼び出します。

さらに、この関数をいつでも呼び出して、コントロールバーをフレームウィンドウにドッキングできます。 通常、これは初期化中に行われます。 複数のツールバーは、フレームウィンドウの特定の辺にドッキングできます。

## <a name="floating-the-toolbar"></a><a name="_core_floating_the_toolbar"></a>ツールバーのフローティング

ドッキング可能なツールバーをフレームウィンドウから取り外すことを、ツールバーにフローティングと呼びます。 これを行うには、 [CFrameWnd:: FloatControlBar](reference/cframewnd-class.md#floatcontrolbar)を呼び出します。 フローティングツールバーを配置する位置と、フローティングツールバーが水平と垂直のどちらであるかを決定する配置スタイルを指定します。

フレームワークは、ユーザーがツールバーをドッキング位置からドラッグし、ドッキングが有効になっていない場所にドロップすると、この関数を呼び出します。 これは、フレームウィンドウの内側または外側の任意の場所に配置できます。 と同様に `DockControlBar` 、初期化中にこの関数を呼び出すこともできます。

ドッキング可能なツールバーの MFC 実装には、ドッキング可能なツールバーをサポートする一部のアプリケーションの拡張機能の一部が用意されていません。 カスタマイズ可能なツールバーなどの機能は用意されていません。

## <a name="dynamically-resizing-the-toolbar"></a><a name="_core_dynamically_resizing_the_toolbar"></a>ツールバーのサイズを動的に変更する

Visual C++ バージョン4.0 では、アプリケーションのユーザーがフローティングツールバーのサイズを動的に変更できるようになります。 通常、ツールバーには、水平方向に表示される長い線形図形があります。 ただし、ツールバーの向きとその形状を変更することはできます。 たとえば、ユーザーがフレームウィンドウの垂直方向のいずれかにツールバーをドッキングすると、図形は垂直レイアウトに変わります。 また、複数行のボタンを使用して、ツールバーを四角形に変えることもできます。

次のようにすることができます。

- 動的なサイズ変更をツールバーの特性として指定します。

- 固定サイズ設定をツールバーの特性として指定します。

このサポートを提供するために、 [CToolBar:: Create](reference/ctoolbar-class.md#create)メンバー関数の呼び出しで使用する新しいツールバースタイルが2つあります。 これらは次のとおりです。

- **CBRS_SIZE_DYNAMIC**コントロールバーは動的です。

- **CBRS_SIZE_FIXED**コントロールバーは固定されています。

サイズ動的スタイルを使用すると、ユーザーはフローティング中にツールバーのサイズを変更できますが、ドッキングされている間は変更できません。 ツールバーは、ユーザーが図形の端をドラッグしたときに、形状を変更するために必要な場所をラップします。

サイズ固定スタイルは、ツールバーの折り返しの状態を保持し、各列のボタンの位置を修正します。 アプリケーションのユーザーは、ツールバーの形状を変更することはできません。 ツールバーは、ボタン間の区切り記号の位置など、指定された場所でラップされます。 この図形は、ツールバーがドッキングされているか、フローティング状態であるかを維持します。 効果は、ボタンの複数の列を持つ固定パレットです。

また、 [CToolBar:: GetButtonStyle](reference/ctoolbar-class.md#getbuttonstyle)を使用して、ツールバーのボタンの状態とスタイルを返すこともできます。 ボタンのスタイルによって、ボタンの表示方法とユーザー入力に対する応答方法が決まります。状態は、ボタンがラップされた状態であるかどうかを示します。

## <a name="setting-wrap-positions-for-a-fixed-style-toolbar"></a><a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a>固定スタイルのツールバーの折り返し位置の設定

固定スタイルのサイズのツールバーの場合は、ツールバーが折り返されるツールバーボタンのインデックスを指定します。 次のコードは、メインフレームウィンドウのオーバーライドでこれを行う方法を示してい `OnCreate` ます。

[!code-cpp[NVC_MFCDocViewSDI#10](codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]

MFC の一般的なサンプル[DOCKTOOL](../overview/visual-cpp-samples.md)は、 [CControlBar](reference/ccontrolbar-class.md)と[CToolBar](reference/ctoolbar-class.md)クラスのメンバー関数を使用して、ツールバーの動的レイアウトを管理する方法を示しています。 ファイルの EDITBAR を参照してください。DOCKTOOL の CPP。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ツールバーの基礎](toolbar-fundamentals.md)

- [ツールバーのツールヒント](toolbar-tool-tips.md)

- [古い形式のツール バーの使用](using-your-old-toolbars.md)

## <a name="see-also"></a>関連項目

[MFC ツール バーの実装](mfc-toolbar-implementation.md)
