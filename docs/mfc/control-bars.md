---
title: コントロール バー
ms.date: 11/04/2016
helpviewer_keywords:
- command bars [MFC], types of
- toolbars [MFC], control bars
- control bars [MFC]
- MFC, control bars
- control bars [MFC], types of
- CDialogBar class [MFC], control bars
- status bars [MFC], control bars
- CControlBar class [MFC], MFC control bars
- dialog bars [MFC], control bars
- CToolBar class [MFC], control bars
- CStatusBar class [MFC], control bars
ms.assetid: 31831910-3d23-4d70-9e71-03cc02f01ec4
ms.openlocfilehash: a2d3683b744493bb5566456b9e1358c1ddc418d4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615975"
---
# <a name="control-bars"></a>コントロール バー

"コントロールバー" は、ツールバー、ステータスバー、およびダイアログバーの一般的な名前です。 MFC クラス `CToolBar` 、、、、およびは、共通の機能を `CStatusBar` `CDialogBar` `COleResizeBar` `CReBar` 実装するクラス[CControlBar](reference/ccontrolbar-class.md)から派生します。

コントロールバーは、ユーザーがオプションを選択したり、コマンドを実行したり、プログラム情報を取得したりできるコントロールの行を表示するウィンドウです。 コントロールバーの種類には、ツールバー、ダイアログバー、ステータスバーなどがあります。

- ツールバー、クラスの[CToolBar](reference/ctoolbar-class.md)

- [CStatusBar](reference/cstatusbar-class.md)クラスのステータスバー

- [CDialogBar](reference/cdialogbar-class.md)クラスのダイアログバー

- [CReBar](reference/crebar-class.md)クラスの rebars

> [!IMPORTANT]
> MFC バージョン4.0 以降では、ツールバー、ステータスバー、およびツールヒントは、MFC 固有の実装ではなく、 *comctl32.dll*に実装されているシステム機能を使用して実装されます。 MFC バージョン6.0 では、 `CReBar` comctl32.dll 機能をラップするも追加されました。

コントロールバーの型について簡単に紹介します。 詳細については、以下のリンクを参照してください。

## <a name="control-bars"></a>コントロール バー

コントロールバーは、簡単なワンステップコマンドアクションを提供することで、プログラムの使いやすさを大幅に向上させます。 クラス `CControlBar` は、すべてのツールバー、ステータスバー、およびダイアログバーの共通機能を提供します。 `CControlBar`親フレームウィンドウにコントロールバーを配置するための機能を提供します。 通常、コントロールバーは親フレームウィンドウの子ウィンドウであるため、フレームウィンドウのクライアントビューまたは MDI クライアントの "兄弟" になります。 コントロールバーオブジェクトは、親ウィンドウのクライアント四角形に関する情報を使用して、それ自体を配置します。 次に、クライアントビューまたは MDI クライアントウィンドウがクライアントウィンドウの残りの部分を埋めるように、親の残りのクライアントウィンドウの四角形を変更します。

> [!NOTE]
> コントロールバーのボタンに**コマンド**または**UPDATE_COMMAND_UI**ハンドラーがない場合は、フレームワークによって自動的にボタンが無効になります。

## <a name="toolbars"></a>[ツール バー]

ツールバーは、コマンドを実行するビットマップボタンの行を表示するコントロールバーです。 ツールバーボタンを押す操作は、メニュー項目を選択するのと同じです。メニュー項目がツールバーボタンと同じ ID を持つ場合、メニュー項目にマップされた同じハンドラーを呼び出します。 ボタンは、プッシュボタン、オプションボタン、またはチェックボックスとして表示および動作するように構成できます。 通常、ツールバーはフレームウィンドウの上部に並べられていますが、MFC ツールバーは親ウィンドウの任意の辺に "ドッキング" できます。また、独自のミニフレームウィンドウでフローティングできます。 ツールバーは、"フローティング" することもできます。また、そのサイズを変更して、マウスでドラッグすることもできます。 ツールバーには、ユーザーがツールバーのボタンの上にマウスを移動したときにツールヒントが表示されることもあります。 ツールヒントは、ボタンの目的を簡単に説明する小さなポップアップウィンドウです。

> [!NOTE]
> MFC バージョン4.0 では、クラス[CToolBar](reference/ctoolbar-class.md)は Windows ツールバーコモンコントロールを使用します。 に `CToolBar` は[CToolBarCtrl](reference/ctoolbarctrl-class.md)が含まれています。 ただし、以前のツールバーは引き続きサポートされます。 記事の[ツールバー](mfc-toolbar-implementation.md)を参照してください。

## <a name="status-bars"></a>ステータス バー

ステータスバーは、テキスト出力ペイン、または "インジケーター" を含むコントロールバーです。 出力ペインは、通常、メッセージ行として、また状態インジケーターとして使用されます。 メッセージ行の例には、MFC アプリケーションウィザードによって作成された既定のステータスバーの左端のウィンドウで選択したメニューまたはツールバーコマンドを簡単に説明するコマンドヘルプメッセージ行が含まれています。 ステータスインジケーターの例には、スクロールロック、NUMLOCK、およびその他のキーが含まれます。 通常、ステータスバーはフレームウィンドウの下部に合わせて調整されます。 「クラス[CStatusBar](reference/cstatusbar-class.md)とクラス[CStatusBarCtrl](reference/cstatusbarctrl-class.md)」を参照してください。

## <a name="dialog-bars"></a>ダイアログ バー

ダイアログバーは、ダイアログテンプレートリソースに基づくコントロールバーで、モードレスダイアログボックスの機能を備えています。 ダイアログバーには、Windows、カスタム、または ActiveX コントロールを含めることができます。 ダイアログボックスと同様に、ユーザーはコントロールの中でタブを使用できます。 ダイアログバーは、フレームウィンドウの上、下、左、または右に配置でき、独自のフレームウィンドウでフローティングすることもできます。 「クラス[CDialogBar](reference/cdialogbar-class.md)」を参照してください。

## <a name="rebars"></a>再バー

[Rebar](using-crebarctrl.md)は、rebar コントロールのドッキング、レイアウト、状態、および永続化に関する情報を提供するコントロールバーです。 Rebar オブジェクトには、さまざまな子ウィンドウを含めることができます。通常は、エディットボックス、ツールバー、リストボックスなどの他のコントロールが含まれます。 Rebar オブジェクトは、指定されたビットマップ上に子ウィンドウを表示できます。 グリップバーをクリックまたはドラッグすると、自動または手動でサイズを変更できます。 「クラス[CReBar](reference/crebar-class.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](user-interface-elements-mfc.md)
