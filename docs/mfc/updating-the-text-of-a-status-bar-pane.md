---
description: 詳細については、Status-Bar ペインのテキストの更新に関するページを参照してください。
title: ステータス バー ペインのテキストの更新
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- ON_UPDATE_COMMAND_UI macro [MFC]
- user interface objects [MFC], updating
- text, status bar
- CStatusBar class [MFC], updating
- SetText method [MFC]
- panes, status bar
- status bars [MFC], updating
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
ms.openlocfilehash: 2c3a922072fe117719c1cea803b16ca9c998ce1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263726"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>ステータス バー ペインのテキストの更新

この記事では、MFC ステータスバーペインに表示されるテキストを変更する方法について説明します。 ステータスバー ( [CStatusBar](../mfc/reference/cstatusbar-class.md) クラスのウィンドウオブジェクト) には、いくつかの "ペイン" が含まれています。 各ペインは、ステータスバーの四角形の領域で、情報を表示するために使用できます。 たとえば、多くのアプリケーションでは、右端のウィンドウの CAPS LOCK、NUM LOCK、およびその他のキーの状態が表示されます。 また、多くの場合、アプリケーションでは、左端のウィンドウ (ペイン 0) に情報のテキストが表示されます ("メッセージウィンドウ" と呼ばれることもあります)。 たとえば、既定の MFC ステータスバーでは、メッセージペインを使用して、現在選択されているメニュー項目またはツールバーボタンを説明する文字列を表示します。 [ステータスバー](../mfc/status-bar-implementation-in-mfc.md)の図は、アプリケーションウィザードで作成された MFC アプリケーションのステータスバーを示しています。

既定では、ペインの作成時に、MFC はペインを有効にしません `CStatusBar` 。 ペインをアクティブにするには、ステータスバーの各ペインの ON_UPDATE_COMMAND_UI マクロを使用して、ペインを更新する必要があります。 ペインは WM_COMMAND メッセージを送信しないため (ツールバーボタンのようなものではありません)、手動でコードを入力する必要があります。

たとえば、1つのペインに `ID_INDICATOR_PAGE` コマンド識別子があり、ドキュメント内の現在のページ番号が含まれているとします。 次の手順では、ステータスバーに新しいウィンドウを作成する方法について説明します。

### <a name="to-make-a-new-pane"></a>新しいウィンドウを作成するには

1. ペインのコマンド ID を定義します。

   [ **表示** ] メニューの [ **リソースビュー**] をクリックします。 プロジェクトリソースを右クリックし、[ **リソースシンボル**] をクリックします。 [リソースシンボル] ダイアログボックスで、をクリックし `New` ます。 コマンド ID 名を入力します (例:) `ID_INDICATOR_PAGE` 。 ID の値を指定するか、[リソースシンボル] ダイアログボックスで提示された値をそのまま使用します。 たとえば、の場合は、 `ID_INDICATOR_PAGE` 既定値をそのまま使用します。 [リソースシンボル] ダイアログボックスを閉じます。

1. ペインに表示する既定の文字列を定義します。

   リソースビュー開いた状態で、アプリケーションのリソースの種類を一覧表示するウィンドウの [ **文字列テーブル** ] をダブルクリックします。 **文字列テーブル** エディターを開いた状態で、[**挿入**] メニューの [**新しい文字列**] をクリックします。 ペインのコマンド ID (たとえば) を選択 `ID_INDICATOR_PAGE` し、"Page" などの既定の文字列値を入力します。 文字列エディターを閉じます。 (コンパイラエラーを回避するには、既定の文字列が必要です)。

1. *インジケーター* 配列にペインを追加します。

   ファイル MAINFRM.CPP にあります。CPP で、 *インジケーター* の配列を探します。 この配列は、ステータスバーのすべてのインジケーターのコマンド Id を左から右へ順に一覧表示します。 配列内の適切な位置に、次に示すように、ペインのコマンド ID を入力し `ID_INDICATOR_PAGE` ます。

   [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

ペインにテキストを表示するには、 `SetText` ペインの更新ハンドラー関数でクラスのメンバー関数を呼び出すことをお勧めし `CCmdUI` ます。 たとえば、現在のページ番号を含む *m_nPage* 整数変数を設定し、を使用して、 `SetText` その数値の文字列バージョンにペインのテキストを設定することができます。

> [!NOTE]
> この `SetText` 方法をお勧めします。 メンバー関数を呼び出すことによって、このタスクを少し低いレベルで実行することができ `CStatusBar` `SetPaneText` ます。 それでも、更新ハンドラーが必要です。 ペインのハンドラーがないと、MFC はウィンドウを自動的に無効にし、その内容を消去します。

次の手順は、更新ハンドラー関数を使用してテキストをペインに表示する方法を示しています。

#### <a name="to-make-a-pane-display-text"></a>ペインにテキストを表示するには

1. コマンドのコマンド更新ハンドラーを追加します。

   (MAINFRM.CPP の) のように、ハンドラーのプロトタイプを手動で追加し `ID_INDICATOR_PAGE` ます。H):

   [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. 適切なで。CPP ファイルで、(MAINFRM.CPP の) のように、ハンドラーの定義を追加し `ID_INDICATOR_PAGE` ます。CPP):

   [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

   このハンドラーの最後の3行は、テキストを表示するコードです。

1. 適切なメッセージマップで、(MAINFRM.CPP の) のように ON_UPDATE_COMMAND_UI マクロを追加し `ID_INDICATOR_PAGE` ます。CPP):

   [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

*M_nPage* メンバー変数 (クラス) の値を定義すると `CMainFrame` 、この手法により、アプリケーションが他のインジケーターを更新するのと同じ方法で、アイドル処理中にページ番号がウィンドウに表示されます。 *M_nPage* 変更されると、次のアイドルループ中に表示が変更されます。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ユーザーインターフェイスオブジェクトの更新 (プログラムの条件の変更に応じてツールバーのボタンとメニュー項目を更新する方法)](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>関連項目

[MFC でのステータスバーの実装](../mfc/status-bar-implementation-in-mfc.md)<br/>
[CStatusBar クラス](../mfc/reference/cstatusbar-class.md)
