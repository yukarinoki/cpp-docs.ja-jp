---
title: ドッキングとフローティング ツールバー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 430af2344888696e3cbf053677ef59c7249b50bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="docking-and-floating-toolbars"></a>ツール バーのドッキングとフローティング
Microsoft Foundation Class ライブラリでは、ドッキング可能ツールバーをサポートします。 ドッキング可能ツールバーをアタッチ、または、その親ウィンドウの任意の辺に、ドッキングされていることができます、またはデタッチ、または独自のミニフレーム ウィンドウで、フロートことができます。 この記事では、アプリケーションでドッキング可能ツールバーを使用する方法について説明します。  
  
 アプリケーションのスケルトンを生成するアプリケーションのウィザードを使用する場合は、ドッキング可能ツールバーを使用するかを選択する必要があります。 既定では、アプリケーションのウィザードには、アプリケーションにドッキング可能ツールバーを配置するために必要な 3 つのアクションを実行するコードが生成されます。  
  
-   [フレーム ウィンドウをドッキング可能に](#_core_enabling_docking_in_a_frame_window)です。  
  
-   [ツールバーのドッキング可能に](#_core_enabling_docking_for_a_toolbar)です。  
  
-   [(フレーム ウィンドウ) にツールバーをドッキング](#_core_docking_the_toolbar)です。  
  
 これらの手順のいずれかが存在しない場合、アプリケーションには標準ツールバーが表示されます。 各ドッキング可能なツールバー、アプリケーションでの最後の 2 つの手順を実行する必要があります。  
  
 この記事で取り上げているその他のトピックは次のとおりです。  
  
-   [ツールバーのフローティング](#_core_floating_the_toolbar)  
  
-   [ツールバーのサイズを動的に変更](#_core_dynamically_resizing_the_toolbar)  
  
-   [固定スタイルのツールバーの折り返しの場所を設定](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)  
  
 MFC 標準サンプルを参照してください[DOCKTOOL](../visual-cpp-samples.md)例についてはします。  
  
##  <a name="_core_enabling_docking_in_a_frame_window"></a> フレーム ウィンドウのドッキング可能にします。  
 フレーム ウィンドウにツールバーをドッキングするのにはフレーム ウィンドウ (または変換先) を有効にドッキング可能です。 これを使用して、 [CFrameWnd::EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking)関数で、1 つ取って`DWORD`スタイルのセットであるパラメーターのフレーム ウィンドウのどちらの側では、ドッキングが受け入れるを示すビットします。 渡されたパラメーターがツールバーをドッキングし、ドッキングする複数の辺に示された辺`EnableDocking`は次の順序で使用されます: top、bottom、left、right です。 ドッキング コントロール バーの任意の場所できる場合は、渡す`CBRS_ALIGN_ANY`に`EnableDocking`です。  
  
##  <a name="_core_enabling_docking_for_a_toolbar"></a> ツールバーのドッキング可能にします。  
 ドッキング先が準備できたら、同様の方法でツールバー (またはソース) を準備する必要があります。 呼び出す[CControlBar::EnableDocking](../mfc/reference/ccontrolbar-class.md#enabledocking)ドッキングする各ツールバーのツールバーをドッキングする必要がある辺、変換先を指定します。 呼び出しで指定した辺の`CControlBar::EnableDocking`フレーム ウィンドウにドッキングできる辺が一致し、ツールバーをドッキングことはできません: に変化します。 フローティング状態されて、フローティング ツールバー、フレーム ウィンドウにドッキングするのにはできません。 そのままとなります。  
  
 目的の効果が完全にフローティング ツールバーの場合は、呼び出す`EnableDocking`0 のパラメーターを使用します。 呼び出す[切り離すには](../mfc/reference/cframewnd-class.md#floatcontrolbar)します。 ツールバーは、フローティング、任意の場所にドッキングするのにはできません。 完全には残ります。  
  
##  <a name="_core_docking_the_toolbar"></a> ツールバーをドッキングします。  
 フレームワークによって[CFrameWnd::DockControlBar](../mfc/reference/cframewnd-class.md#dockcontrolbar)ユーザーがツールバーがドッキングされるフレーム ウィンドウの一辺にドロップしようとしたときにします。  
  
 さらに、フレーム ウィンドウにコントロール バーをドッキングするには、いつでもこの関数を呼び出すことができます。 これは通常、初期化中に行います。 複数のツールバーは、フレーム ウィンドウの特定の辺にドッキングされることができます。  
  
##  <a name="_core_floating_the_toolbar"></a> ツールバーのフローティング  
 フレーム ウィンドウからドッキング可能ツールバーをデタッチすると、ツールバーのフローティング、呼び出されます。 呼び出す[切り離すには](../mfc/reference/cframewnd-class.md#floatcontrolbar)これを行う。 フロートするか、ツールバー、それを格納する場所、ポイントとフローティング ツールバーが水平または垂直方向かどうかを決定する配置スタイルを指定します。  
  
 フレームワークは、ユーザーがツールバーをドッキング位置からドラッグ ドッキングされていない有効になっている位置にドロップしたときに、この関数を呼び出します。 フレーム ウィンドウの内外どこでも指定できます。 同様に`DockControlBar`初期化中にもこの関数を呼び出すことができます。  
  
 ドッキング可能ツールバーの MFC 実装では、ドッキング可能ツールバーをサポートする一部のアプリケーションでの拡張機能のいくつか用意されていません。 カスタマイズ可能なツールバーなどの機能が指定されていません。  
  
##  <a name="_core_dynamically_resizing_the_toolbar"></a> ツールバーのサイズを動的に変更  
 Visual C バージョン 4.0 の時点で行うことが考えられるフローティング ツールバーのサイズを動的に変更するアプリケーションのユーザーのできます。 通常、ツールバーには、long、線形図形、水平方向に表示します。 ツールバーの向き、その図形を変更することができます。 たとえば、ユーザーは、フレーム ウィンドウの縦方向のいずれかのツールバーをドッキング、ときに、図形を垂直レイアウトに変更します。 ボタンの複数の行を含む四角形に、ツールバーの形状を変更することもできます。  
  
 次の操作を行うことができます。  
  
-   ツールバーの特徴としては、動的なサイズ変更を指定します。  
  
-   ツールバーの特性として固定サイズを指定します。  
  
 このサポートを提供するには、次の 2 つの新しいツール バー スタイルの呼び出しで使用するため、[用意されて](../mfc/reference/ctoolbar-class.md#create)メンバー関数。 それらは次のとおりです。  
  
-   **CBRS_SIZE_DYNAMIC**コントロール バーは動的です。  
  
-   **CBRS_SIZE_FIXED**コントロール バーを固定します。  
  
 サイズの動的なスタイルでは、浮動小数点型、ドッキングされている間にありませんが、ツールバーのサイズ、ユーザーを許可します。 ツールバー「ラップ」ように、ユーザーの端をドラッグした図形の変更に必要な場所です。  
  
 スタイルの固定サイズでは、各列内のボタンの位置を修正して、ツールバーの折り返しの状態が保持されます。 アプリケーションのユーザーには、ツールバーの形状を変更できません。 ツールバーは、ボタンの間の区切り記号の位置など、指定した場所でラップします。 ツールバーをドッキングまたはフローティングかどうかは、この図形を維持します。 ボタンの複数の列を持つ固定されたパレットになります。  
  
 使用することも[CToolBar::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle)をツールバーの状態とボタンのスタイルを返します。 ボタンのスタイルを決定ボタンの表示方法と、ユーザーの入力に応答する方法状態は、ボタンは、ラップされた状態にするかどうかを示します。  
  
##  <a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a> 固定スタイルのツールバーの折り返しの場所を設定  
 スタイルの固定サイズで、ツールバーのツールバーにツールバーをラップするボタンのインデックスを指定します。 次のコードはこれを行う方法、メイン フレーム ウィンドウの `OnCreate`をオーバーライドします。  
  
 [!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]  
  
 MFC 標準サンプル[DOCKTOOL](../visual-cpp-samples.md)クラスのメンバー関数を使用する方法を示します[CControlBar](../mfc/reference/ccontrolbar-class.md)と[CToolBar](../mfc/reference/ctoolbar-class.md)ツールバーの動的レイアウトを管理します。 EDITBAR ファイルを参照してください。DOCKTOOL で CPP です。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ツールバーに関する基本事項](../mfc/toolbar-fundamentals.md)  
  
-   [ツールバーのツール ヒント](../mfc/toolbar-tool-tips.md)  
  
-   [古いツールバーの使用方法](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)

