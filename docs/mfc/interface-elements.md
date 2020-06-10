---
title: インターフェイス要素
ms.date: 11/19/2018
helpviewer_keywords:
- architecture [MFC], MFC Feature Pack
- MFC Feature Pack, architecture
ms.assetid: eead6827-9602-40a3-8038-8986e8207385
ms.openlocfilehash: 4d4d81287cb30a7d3608025085cdb3f9a208147a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619990"
---
# <a name="interface-elements"></a>インターフェイス要素

このドキュメントでは、Visual Studio 2008 SP1 で導入されたインターフェイス要素について説明します。また、以前のバージョンのライブラリとの違いについても説明します。

次の図は、新しいインターフェイス要素を使用して作成されたアプリケーションを示しています。

![MFC Feature Pack のアプリケーション例](../mfc/media/mfc_featurepack.png "MFC Feature Pack のアプリケーション例")

## <a name="window-docking"></a>ウィンドウのドッキング

ウィンドウのドッキング機能は、Visual Studio のグラフィカルユーザーインターフェイスで使用されるウィンドウのドッキングに似ています。

## <a name="control-bars-are-now-panes"></a>コントロールバーがペインになりました

コントロールバーは、ウィンドウと呼ばれ、 [Cbasepane クラス](reference/cbasepane-class.md)から派生したものです。 以前のバージョンの MFC では、コントロールバーの基本クラスはでした `CControlBar` 。

アプリケーションのメインフレームウィンドウは、通常、 [CFrameWndEx クラス](reference/cframewndex-class.md)または[CMDIFrameWndEx クラス](reference/cmdiframewndex-class.md)によって表されます。 メインフレームは、 *dock サイト*と呼ばれます。 ペインには、ドッキングサイト、ドッキングバー、またはミニフレームウィンドウの3種類の親があります。

2種類のペインがあります。サイズ変更不可能で、サイズを変更できます。 ステータスバーやツールバーなどのサイズ変更可能なウィンドウは、スプリッターまたはスライダーを使用してサイズを変更できます。 サイズ変更可能なウィンドウでは、コンテナーを形成できます (あるウィンドウを別のウィンドウにドッキングし、それらの間にスプリッターを作成できます)。 ただし、サイズ変更可能ペインはドッキングバーに装着 (ドッキング) できません。

アプリケーションでサイズ変更できないウィンドウを使用する場合は、 [CPane クラス](reference/cpane-class.md)から派生させます。  アプリケーションでサイズ変更可能なウィンドウを使用する場合は、 [CDockablePane クラス](reference/cdockablepane-class.md)から派生させます。

## <a name="dock-site"></a>サイトのドッキング

Dock サイト (またはメインフレームウィンドウ) は、アプリケーション内のすべてのペインとミニフレームウィンドウを所有します。 Dock サイトには、 [CDockingManager](reference/cdockingmanager-class.md)メンバーが含まれています。 このメンバーは、dock サイトに属しているすべてのウィンドウの一覧を保持します。 リストは、ドッキングサイトの外縁で作成されたペインがリストの先頭に配置されるように並べ替えられます。 フレームワークは、ドッキングサイトを再描画するときに、この一覧をループし、各ペインのレイアウトを調整して、ドッキングサイトの現在の外接する四角形を含めます。 `AdjustDockingLayout`ドッキングレイアウトを調整する必要があるときにまたはを呼び出すことができ、 `RecalcLayout` フレームワークはこの呼び出しをドッキングマネージャーにリダイレクトします。

## <a name="dock-bars"></a>ドッキングバー

各メインフレームウィンドウは、*ドッキングバー*を境界線に沿って配置できます。 ドッキングバーは、 [CDockSite クラス](reference/cdocksite-class.md)に属するペインです。 ドッキングバーは、ツールバーなどの[CPane](reference/cpane-class.md)から派生したオブジェクトを受け入れることができます。 メインフレームウィンドウが初期化されたときにドッキングバーを作成するには、を呼び出し `EnableDocking` ます。 自動非表示バーを有効にするには、を呼び出し `EnableAutoHideBars` ます。 `EnableAutoHideBars`[CAutoHideDockSite](reference/cautohidedocksite-class.md)オブジェクトを作成し、各ドックバーの横に配置します。

各 dock バーは、ドッキング行に分割されます。 Dock 行は、 [CDockingPanesRow クラス](reference/cdockingpanesrow-class.md)によって表されます。 各 dock 行には、ツールバーの一覧が含まれています。 ユーザーがツールバーをドッキングするか、同じドッキングバー内のある行から別の行にツールバーを移動すると、フレームワークは新しい行を作成し、それに応じてドッキングバーのサイズを変更するか、または既存の行にツールバーを配置します。

## <a name="mini-frame-windows"></a>ミニフレームウィンドウ

フローティングペインはミニフレームウィンドウに存在します。 ミニフレームウィンドウは、 [CMDITabInfo クラス](reference/cmditabinfo-class.md)(1 つのペインのみを含めることができます) と[CMultiPaneFrameWnd クラス](reference/cmultipaneframewnd-class.md)(複数のペインを含むことができます) で表されます。 コード内でペインをフローティングするには、 [Cbasepane:: FloatPane](reference/cbasepane-class.md#floatpane)を呼び出します。 ペインがフローティング状態になると、フレームワークによってミニフレームウィンドウが自動的に作成され、ミニフレームウィンドウがフローティングペインの親になります。 フローティングペインがドッキングされると、フレームワークによって親がリセットされ、フローティングペインがドッキングバー (ツールバーの場合) または dock サイト (サイズ変更可能なウィンドウの場合) になります。

## <a name="pane-dividers"></a>ペインの区分線

ペインの区切り線 (名前付きスライダーまたはスプリッター) は、 [Cpanedivider クラス](reference/cpanedivider-class.md)によって表されます。 ユーザーがペインをドッキングすると、ペインがドッキングサイトにドッキングされているか、別のペインにドッキングされているかに関係なく、フレームワークによってペインの区切り線が作成されます。 ペインがドッキングサイトにドッキングされている場合、ペインの区分線は*既定のペインの区分線*と呼ばれます。 既定のペインの区分線は、ドッキングサイトのすべてのドッキングウィンドウのレイアウトを担当します。 Dock マネージャーでは、既定のペインの区切り線の一覧と、ウィンドウの一覧が保持されます。 ドッキングマネージャーは、すべてのドッキングウィンドウのレイアウトを担当します。

## <a name="containers"></a>Containers

相互にドッキングされているすべてのサイズ変更可能なウィンドウは、コンテナーに保持されます。 コンテナーは[Cpanecontainer クラス](reference/cpanecontainer-class.md)によって表されます。 各コンテナーには、左ペイン、右ペイン、左サブコンテナー、右サブコンテナー、および左側と右側の部分の分割線へのポインターがあります。 (*左*と*右*は、物理的な側を参照せず、ツリー構造の分岐を識別します)。このようにして、ウィンドウとスプリッターのツリーを作成することができます。これにより、複数のウィンドウのサイズを変更できる複雑なレイアウトが実現されます。 クラスは、 `CPaneContainer` コンテナーのツリーを保持します。また、このツリーに存在するペインとスライダーの2つのリストも保持します。 ペインコンテナーマネージャーは、通常、複数のウィンドウを表示する既定のスライダーとミニフレームウィンドウに埋め込まれます。

## <a name="auto-hide-control-bars"></a>コントロールバーの自動非表示

既定では、 `CDockablePane` は自動的に隠す機能をサポートしています。 ユーザーがのキャプションの [ピン留め] ボタンをクリックすると、フレームワークによって `CDockablePane` ウィンドウが自動的に非表示モードに切り替わります。 このクリックを処理するために、フレームワークは、オブジェクトに関連付けられた[Cmfcautohidebar クラス](reference/cmfcautohidebar-class.md)と[Cmfcautohidebar クラス](reference/cmfcautohidebutton-class.md)を作成し `CMFCAutoHideBar` ます。 フレームワークは、新しいを `CMFCAutoHideBar` [CAutoHideDockSite](reference/cautohidedocksite-class.md)に配置します。 フレームワークは、を `CMFCAutoHideButton` ツールバーにもアタッチします。 [CDockingManager クラス](reference/cdockingmanager-class.md)はを保持し `CDockablePane` ます。

## <a name="tabbed-control-bars-and-outlook-bars"></a>タブ付きコントロールバーと Outlook バー

[CMFCBaseTabCtrl クラス](reference/cmfcbasetabctrl-class.md)は、切り離し可能なタブを持つタブ付きウィンドウの基本機能を実装します。 オブジェクトを使用するには `CMFCBaseTabCtrl` 、アプリケーションで[CBaseTabbedPane クラス](reference/cbasetabbedpane-class.md)を初期化します。 `CBaseTabbedPane`はから派生 `CDockablePane` し、オブジェクトへのポインターを保持し `CMFCBaseTabCtrl` ます。 を `CBaseTabbedPane` 使用すると、ユーザーはタブ付きコントロールバーをドッキングしたり、サイズを変更したりできます。 [CDockablePane:: AttachToTabWnd](reference/cdockablepane-class.md#attachtotabwnd)を使用して、ドッキングされたコントロールバーとタブを動的に作成します。

Outlook バーコントロールは、タブ付きバーにも基づいています。 [Cmfcoutlookbar クラス](reference/cmfcoutlookbar-class.md)はから派生 `CBaseTabbedPane` しています。 Outlook バーの使用方法の詳細については、「 [Cmfcoutlookbar クラス](reference/cmfcoutlookbar-class.md)」を参照してください。

## <a name="see-also"></a>関連項目

[概念](mfc-concepts.md)
