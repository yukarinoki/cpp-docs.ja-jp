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
ms.openlocfilehash: ceae20c89d9a6d3f4393f838b3594938107785f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353571"
---
# <a name="control-bars"></a>コントロール バー

"コントロール バー" は、ツールバー、ステータス バー、およびダイアログ バーの一般名です。 MFC`CToolBar`クラス`CStatusBar` `CDialogBar` `COleResizeBar`、、、`CReBar`およびクラス[CControlBar](../mfc/reference/ccontrolbar-class.md)から派生します。

コントロール バーは、ユーザーがオプションを選択したり、コマンドを実行したり、プログラム情報を取得したりできるコントロールの行を表示するウィンドウです。 コントロール バーの種類には、ツールバー、ダイアログ バー、ステータス バーなどがあります。

- [CToolBar](../mfc/reference/ctoolbar-class.md)クラスのツールバー

- ステータス バー (クラス[CStatusBar)](../mfc/reference/cstatusbar-class.md)

- クラス[CDialogBar](../mfc/reference/cdialogbar-class.md)のダイアログ バー

- Rebar(クラス[CReBar内)](../mfc/reference/crebar-class.md)

> [!IMPORTANT]
> MFC バージョン 4.0 では、ツール バー、ステータス バー、およびツール ヒントは、MFC 固有の以前の実装ではなく *、comctl32.dll*に実装されたシステム機能を使用して実装されています。 MFC バージョン 6.0`CReBar`では、 comctl32.dll の機能もラップします。

コントロール バーの種類の簡単な説明を次に示します。 詳細については、以下のリンクを参照してください。

## <a name="control-bars"></a>コントロール バー

コントロール バーは、迅速な 1 ステップのコマンド 操作を提供することで、プログラムの使いやすさを大幅に向上させます。 クラス`CControlBar`はすべてのツールバー、ステータス バー、およびダイアログ バーの共通機能を提供します。 `CControlBar`には、親フレーム ウィンドウにコントロール バーを配置する機能が用意されています。 コントロール バーは通常、親フレーム ウィンドウの子ウィンドウであるため、フレーム ウィンドウのクライアント ビューまたは MDI クライアントの "兄弟" です。 コントロール バー オブジェクトは、親ウィンドウのクライアント四角形に関する情報を使用して、それ自体を配置します。 次に、親の残りのクライアント ウィンドウの四角形を変更して、クライアント ビューまたは MDI クライアント ウィンドウがクライアント ウィンドウの残りの部分を埋めるようにします。

> [!NOTE]
> コントロール バーのボタンに**COMMAND**または**UPDATE_COMMAND_UI**ハンドラーがない場合、フレームワークは自動的にそのボタンを無効にします。

## <a name="toolbars"></a>[ツール バー]

ツールバーは、コマンドを実行するビットマップ ボタンの行を表示するコントロール バーです。 ツールバーボタンを押すと、メニュー項目を選択するのと同じになります。メニュー項目がツール バー ボタンと同じ ID を持つ場合は、メニュー項目にマップされた同じハンドラーを呼び出します。 ボタンは、プッシュボタン、ラジオボタン、またはチェックボックスとして表示および動作するように設定できます。 通常、ツール バーはフレーム ウィンドウの上部に配置されますが、MFC ツール バーは親ウィンドウの任意の辺にドッキングしたり、専用のミニフレーム ウィンドウに浮動したりできます。 ツールバーは「フローティング」も可能で、サイズを変更したり、マウスでドラッグしたりできます。 ツール バーのボタンの上にマウスを移動すると、ツール ヒントを表示することもできます。 ツール ヒントは、ボタンの目的を簡単に説明する小さなポップアップ ウィンドウです。

> [!NOTE]
> MFC バージョン 4.0 では、クラス[CToolBar](../mfc/reference/ctoolbar-class.md)は、Windows ツール バーコモン コントロールを使用します。 には`CToolBar` [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)が含まれています。 ただし、古いツールバーは引き続きサポートされています。 記事[「ツールバー](../mfc/mfc-toolbar-implementation.md)」を参照してください。

## <a name="status-bars"></a>ステータス バー

ステータス バーは、テキスト出力ペイン(インジケータ)を含むコントロール バーです。 出力ペインは、通常、メッセージ行として、およびステータス インジケータとして使用されます。 メッセージ行の例には、MFC アプリケーション ウィザードで作成された既定のステータス バーの左端のペインで、選択したメニューまたはツール バー コマンドを簡単に説明するコマンド ヘルプ メッセージ行が含まれます。 ステータス インジケータの例には、スクロール ロック、NUM LOCK、およびその他のキーが含まれます。 ステータス バーは、通常、フレーム ウィンドウの下部に揃えられます。 クラス[を参照してください。](../mfc/reference/cstatusbar-class.md) [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)

## <a name="dialog-bars"></a>ダイアログ バー

ダイアログ バーは、ダイアログ テンプレート リソースに基づくコントロール バーで、モードレス ダイアログ ボックスの機能を備えています。 ダイアログ バーには、Windows、カスタム コントロール、または ActiveX コントロールを含めることができます。 ダイアログ ボックスと同様に、ユーザーはコントロール間でタブを移動できます。 ダイアログ バーは、フレーム ウィンドウの上下左右の辺に揃えることができ、フレーム ウィンドウ内に浮動することもできます。 クラス[CDialogBar を](../mfc/reference/cdialogbar-class.md)参照してください。

## <a name="rebars"></a>鉄筋

[Rebar](../mfc/using-crebarctrl.md)は、Rebar コントロールのドッキング、レイアウト、状態、および持続性の情報を提供するコントロールバーです。 Rebar オブジェクトには、編集ボックス、ツールバー、リスト ボックスなど、さまざまな子ウィンドウ (通常は他のコントロール) を含めることができます。 Rebar オブジェクトは、指定されたビットマップ上に子ウィンドウを表示できます。 グリッパー バーをクリックまたはドラッグすることで、自動的または手動でサイズ変更できます。 クラス[CReBar](../mfc/reference/crebar-class.md)を参照してください。

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
