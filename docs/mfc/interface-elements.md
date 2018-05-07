---
title: インターフェイス要素の |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- architecture [MFC], MFC Feature Pack
- MFC Feature Pack, architecture
ms.assetid: eead6827-9602-40a3-8038-8986e8207385
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25f9de4ab5f7d12d240625e0fdf5f857563e8ce2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="interface-elements"></a>インターフェイス要素
導入されたインターフェイス要素について説明[!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)]SP1、およびライブラリの以前のバージョンとの違いについても説明します。  
  
 次の図は、新しいインターフェイス要素を使用してビルドされたアプリケーションを示します。  
  
 ![MFC Feature Pack のアプリケーション例](../mfc/media/mfc_featurepack.png "mfc_featurepack")  
  
## <a name="window-docking"></a>ウィンドウのドッキング  
 ウィンドウの機能をドッキングするドッキング ウィンドウのようになります、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]グラフィカル ユーザー インターフェイスを使用します。  
  
## <a name="control-bars-are-now-panes"></a>コントロール バーがウィンドウようになりました  
 コントロール バーは今すぐウィンドウと呼ばから派生した[CBasePane クラス](../mfc/reference/cbasepane-class.md)です。 コントロール バーの基本クラスが MFC の以前のバージョンで`CControlBar`です。  
  
 アプリケーションのメイン フレーム ウィンドウがによって表される通常、 [CFrameWndEx クラス](../mfc/reference/cframewndex-class.md)または[CMDIFrameWndEx クラス](../mfc/reference/cmdiframewndex-class.md)です。 メイン フレームが呼び出された、*ドッキング サイト*です。 ウィンドウには、3 種類の親の 1 つ持つことができます: ドッキング サイト、ドッキング バー、またはミニフレーム ウィンドウです。  
  
 ペインの 2 種類があります。 サイズを変更およびサイズを変更します。 ステータス バーとツールバーなどのサイズ変更可能なウィンドウの分割またはスライダーを使用してサイズを変更できます。 サイズ変更可能なペインには、コンテナーを (それらの間の分割を作成する別のペインには 1 つのペインをドッキングできます) を形成できます。 ただし、サイズ変更可能なウィンドウは、(ドッキングされている) バーをドッキングするのにはアタッチできません。  
  
 アプリケーションでは、サイズを変更できないウィンドウを使用する場合は派生から[CPane クラス](../mfc/reference/cpane-class.md)です。  アプリケーションでは、サイズ変更可能なペインを使用する場合は派生から[CDockablePane クラス](../mfc/reference/cdockablepane-class.md)  
  
## <a name="dock-site"></a>ドッキング サイト  
 ドッキング サイト (またはメイン フレーム ウィンドウ) には、すべてのウィンドウやアプリケーションでミニフレーム ウィンドウが所有しています。 ドッキング サイトに含まれる、 [CDockingManager](../mfc/reference/cdockingmanager-class.md)メンバー。 このメンバーは、ドッキング サイトに属しているすべてのウィンドウの一覧を保持します。 リストの順序は、ドッキング サイトの外側のエッジに作成され、ペインは、リストの先頭に配置できるようにします。 フレームワークには、ドッキング サイトが再描画、ときにこの一覧をループ処理し、ドッキング サイトの現在の外接する四角形を含めるには、各ウィンドウのレイアウトを調整します。 呼び出すことができます`AdjustDockingLayout`または`RecalcLayout`ドッキング レイアウトを調整する必要があるし、フレームワークは、ドッキング マネージャーにこの呼び出しをリダイレクトします。  
  
## <a name="dock-bars"></a>ドッキング バー  
 各メイン フレーム ウィンドウ位置を調整できます*バーをドッキング*境界線に沿ったです。 ドッキング バーは、ウィンドウが属している、 [CDockSite クラス](../mfc/reference/cdocksite-class.md)です。 派生したオブジェクトを受け入れることができるドッキング バー [CPane](../mfc/reference/cpane-class.md)、ツールバーなどです。 メイン フレーム ウィンドウが初期化されたときに、ドッキング バーを作成するには、呼び出す`EnableDocking`です。 自動非表示バーを有効にするを呼び出す`EnableAutoHideBars`です。 `EnableAutoHideBars` 作成[CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md)オブジェクト、および各ドッキング バーの隣に配置します。  
  
 各ドッキング バーは、ドッキング行に分割されます。 ドッキング行がによって表される、 [CDockingPanesRow クラス](../mfc/reference/cdockingpanesrow-class.md)です。 ドッキングの各行には、ツールバーの一覧が含まれています。 場合は、ユーザーは、ツールバーをドッキングしたり、1 つの行から同じドッキング バー内の別に、ツールバーを移動、フレームワークが新しい行を作成し、それに応じてドッキング バーのサイズを変更または、既存の行にツールバーを配置します。  
  
## <a name="mini-frame-windows"></a>ミニフレーム ウィンドウ  
 フローティング ウィンドウは、ミニフレーム ウィンドウに存在します。 ミニフレーム ウィンドウは 2 つのクラスによって表されます。 [CMDITabInfo クラス](../mfc/reference/cmditabinfo-class.md)(これは、1 つのペインを含めることができます) と[CMultiPaneFrameWnd クラス](../mfc/reference/cmultipaneframewnd-class.md)(これは、いくつかのペインを含めることができます)。 コードでは、ペインをフローティング、呼び出す[CBasePane::FloatPane](../mfc/reference/cbasepane-class.md#floatpane)です。 ペインがフローティング状態になった後は、フレームワークは、ミニフレーム ウィンドウを自動的に作成し、ミニフレーム ウィンドウのフローティング ウィンドウの親になります。 フローティング ペインをドッキングすると、フレームワークが、その親でをリセットし、フローティング ペイン (ツールバー) 用のドッキング バーまたはドッキング サイト (サイズ変更可能なペイン) になります。  
  
## <a name="pane-dividers"></a>ペイン分割バー  
 ペインの区分線 (スライダーまたは分割ウィンドウとも呼ばれます) がによって表される、 [CPaneDivider クラス](../mfc/reference/cpanedivider-class.md)です。 ユーザーは、ペインをドッキング、ときに、フレームワークは、ドック サイトまたは別のペインで、ペインはドッキングするかどうかに関係なく、ペインの区分線を作成します。 ペインをドッキング サイトにドッキング、ペイン分割バーが呼び出されます、*ペイン分割バーを既定*です。 既定ペイン分割バーは、ドッキング サイトのすべてのドッキング ウィンドウのレイアウトを担当します。 ドッキング マネージャーは、ペインの一覧と既定ペインの区分線の一覧を保持します。 ドッキング マネージャーは、すべてのドッキング ウィンドウのレイアウトを担当します。  
  
## <a name="containers"></a>コンテナー  
 すべてのサイズを変更できるウィンドウ、互いにドッキングされているときは、コンテナーに保持されます。 コンテナーがによって表される、 [CPaneContainer クラス](../mfc/reference/cpanecontainer-class.md)です。 各コンテナーには、左と右の部分の間で、左側のペイン、右側のペイン、左のサブコンテナー、右辺のサブ コンテナーと分割線へのポインター。 (*左*と*右*物理辺を参照していませんではなくツリー構造の分岐を識別します)。この方法でウィンドウ、分割ウィンドウのツリーを構築したりしたがって一緒にサイズを変更できるウィンドウの複雑なレイアウトを実現できます。 `CPaneContainer`クラスはコンテナーのツリーを保持; のウィンドウおよびスライダーこのツリー内に存在する 2 つのリストも保持します。 ウィンドウのコンテナー マネージャーは通常、既定のスライダーと複数のペインを実行するミニフレーム ウィンドウに埋め込まれます。  
  
## <a name="auto-hide-control-bars"></a>自動非表示コントロール バー  
 既定では、各`CDockablePane`は自動的に隠す機能をサポートします。 キャプションに暗証番号 (pin) ボタンをクリックすると、`CDockablePane`フレームワークは、ウィンドウを自動非表示モードに切り替えます。 クリックを処理するために、フレームワークを作成、 [CMFCAutoHideBar クラス](../mfc/reference/cmfcautohidebar-class.md)と[CMFCAutoHideButton クラス](../mfc/reference/cmfcautohidebutton-class.md)に関連付けられている、`CMFCAutoHideBar`オブジェクト。 フレームワークにより、新しい`CMFCAutoHideBar`上、 [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md)です。 フレームワークにも添付、`CMFCAutoHideButton`ツールバーにします。 [CDockingManager クラス](../mfc/reference/cdockingmanager-class.md)保持、`CDockablePane`です。  
  
## <a name="tabbed-control-bars-and-outlook-bars"></a>タブ付きのコントロール バーや Outlook バー  
 [CMFCBaseTabCtrl クラス](../mfc/reference/cmfcbasetabctrl-class.md)切り離し可能なタブを持つタブ付きウィンドウの基本機能を実装します。 使用する、`CMFCBaseTabCtrl`オブジェクト、初期化、 [CBaseTabbedPane クラス](../mfc/reference/cbasetabbedpane-class.md)アプリケーションでします。 `CBaseTabbedPane` 派生した`CDockablePane`へのポインターを保持し、`CMFCBaseTabCtrl`オブジェクト。 `CBaseTabbedPane`にドッキングしてタブ形式のコントロール バーのサイズを変更できます。 使用して[cdockablepane::attachtotabwnd](../mfc/reference/cdockablepane-class.md#attachtotabwnd)はドッキングされ、タブを含むコントロール バーを動的に作成します。  
  
 Outlook バー コントロールは、タブ付きのバーにも基づいています。 [CMFCOutlookBar クラス](../mfc/reference/cmfcoutlookbar-class.md)から派生した`CBaseTabbedPane`です。 Outlook バーを使用する方法の詳細については、次を参照してください。 [CMFCOutlookBar クラス](../mfc/reference/cmfcoutlookbar-class.md)です。  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)

