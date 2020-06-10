---
title: MDI タブ付きグループ
ms.date: 11/04/2016
helpviewer_keywords:
- mdi [MFC], tabbed groups
- tabbed grous [MFC]
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
ms.openlocfilehash: 0c1bf925003d5081b2cdc837012a57585b1ace60
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624357"
---
# <a name="mdi-tabbed-groups"></a>MDI タブ付きグループ

マルチドキュメントインターフェイス (MDI) のタブ付きグループ機能を使用すると、マルチドキュメントインターフェイス (mdi) アプリケーションで、MDI クライアント領域に1つ以上のタブ付きウィンドウ (タブ付き*グループ*と呼ばれる) を表示できます。 タブ付きウィンドウは、垂直方向または水平方向に配置できます。 アプリケーションが複数の MDI タブ付きグループをホストしている場合は、分割されたグループが分割されます。

## <a name="features"></a>特徴

MDI タブ付きグループの機能を次に示します。

- アプリケーションでは、タブ付きウィンドウを動的に作成できます。

- アプリケーションでは、タブ付きウィンドウを水平方向または垂直方向に配置できます。

- タブ付きウィンドウのグループはスプリッターで区切られます。 ユーザーはスプリッターを使用して、タブ付きグループのサイズを変更できます。

- ユーザーは、グループ間で個々のタブをドラッグできます。

- ユーザーは、個々のタブをドラッグして新しいグループを作成できます。

- ユーザーは、ショートカットメニューを使用してタブを移動したり、新しいグループを作成したりできます。

- アプリケーションでは、タブ付きウィンドウのレイアウトを保存して読み込むことができます。

- アプリケーションでは、MDI ドキュメントの一覧を保存して読み込むことができます。

- アプリケーションは、個々のタブ付きグループにアクセスし、パラメーターを変更できます。

### <a name="using-mdi-tabbed-groups"></a>MDI タブ付きグループの使用

MDI タブ付きグループで一般的に実行されるタスクを次に示します。

- メインフレームウィンドウの MDI タブ付きグループを有効にするには、 [CMDIFrameWndEx:: EnableMDITabbedGroups](reference/cmdiframewndex-class.md#enablemditabbedgroups)を呼び出します。 このメソッドの2番目のパラメーターは、クラスのインスタンスです `CMDITabInfo` 。 を呼び出す前に、既定のパラメーターを使用することも、変更することもでき `CMDIFrameWndEx::EnableMDITabbedGroups` ます。

- 実行時に MDI タブ付きグループのプロパティを変更するには、オブジェクトを作成または変更 `CMDITabInfo` して、を再度呼び出します。 `CMDIFrameWndEx::EnableMDITabbedGroups`

- MDI タブ付きウィンドウの一覧を取得するには、を呼び出し `CMDIFrameWndEx::GetMDITabGroups` ます。

- アクティブなタブ付きグループの横に新しい MDI タブ付きグループを作成するには、を呼び出し `CMDIFrameWndEx::MDITabNewGroup` ます。

- タブ付きグループの前または次のウィンドウに入力フォーカスを移動するには、を呼び出し `CMDIFrameWndEx::MDITabMoveToNextGroup` ます。

- ウィンドウが MDI タブ付きグループ呼び出しのメンバーであるかどうかを確認する場合は `CMDIFrameWndEx::IsMemberOfMDITabGroup` 。

- メインフレームウィンドウに対して MDI タブまたは MDI タブ付きグループが有効になっているかどうかを確認するには、を呼び出し `CMDIFrameWndEx::AreMDITabs` ます。 MDI タブ付きグループが有効かどうかを判断するには、を呼び出し `CMDIFrameWndEx::IsMDITabbedGroup` ます。

- ユーザーがタブをクリックしたとき、または別の MDI タブ付きグループにドラッグしたときにショートカットメニューを表示するには、の `CMDIFrameWndEx::OnShowMDITabContextMenu` 派生クラスでをオーバーライドし `CMDIFrameWndEx` ます。 このメソッドを実装しない場合、アプリケーションではショートカットメニューが表示されません。

- アプリケーションで MDI タブ付きグループのレイアウトを保存するには、を呼び出し `CMDIFrameWndEx::SaveMDIState` ます。 以前に保存した MDI タブ付きグループプロファイルを読み込むには、を呼び出し `CMDIFrameWndEx::LoadMDIState` ます。 また、これらのメソッドを呼び出して、開いているドキュメントの一覧を MDI アプリケーションに読み込んだり、保存したりすることもできます。 MDI 状態の保存と読み込みの詳細については、「 [CMDIFrameWndEx:: LoadMDIState](reference/cmdiframewndex-class.md#loadmdistate)」を参照してください。

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](user-interface-elements-mfc.md)<br/>
[CMDIFrameWndEx クラス](reference/cmdiframewndex-class.md)<br/>
[CMDIChildWndEx クラス](reference/cmdichildwndex-class.md)<br/>
[CMDITabInfo クラス](reference/cmditabinfo-class.md)
