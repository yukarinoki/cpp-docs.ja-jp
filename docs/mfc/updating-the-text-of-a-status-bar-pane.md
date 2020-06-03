---
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
ms.openlocfilehash: 723046fc1721cc46608e00f19a4431ef081be13d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366688"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>ステータス バー ペインのテキストの更新

この資料では、MFC ステータス バー ペインに表示されるテキストを変更する方法について説明します。 ステータス バーは[、CStatusBar](../mfc/reference/cstatusbar-class.md)クラスのウィンドウ オブジェクトで、いくつかの "ペイン" を含んでいます。 各ペインは、情報を表示するために使用できるステータス バーの四角形の領域です。 たとえば、多くのアプリケーションでは、CapsLock、NumLock、およびその他のキーの状態が右端のペインに表示されます。 アプリケーションでは、一番左側のペイン (ペイン 0) に情報テキストが表示されることがよくあります。 たとえば、既定の MFC ステータス バーでは、メッセージ ペインを使用して、現在選択されているメニュー項目またはツール バー ボタンを説明する文字列が表示されます。 [ステータス バー](../mfc/status-bar-implementation-in-mfc.md)の図は、アプリケーション ウィザードで作成された MFC アプリケーションのステータス バーを示しています。

既定では、MFC では、ペイン`CStatusBar`を作成するときに、ペインを有効にしません。 ペインをアクティブにするには、ステータス バーの各ペインのON_UPDATE_COMMAND_UI マクロを使用して、ペインを更新する必要があります。 ウィンドウはWM_COMMANDメッセージを送信しないため (ツール バー ボタンとは違う)、コードを手動で入力する必要があります。

たとえば、あるペインのコマンド識別子`ID_INDICATOR_PAGE`が、ドキュメント内の現在のページ番号を含む場合を考えます。 次の手順では、ステータス バーに新しいペインを作成する方法について説明します。

### <a name="to-make-a-new-pane"></a>新しいペインを作成するには

1. ペインのコマンド ID を定義します。

   [**表示**] メニューの [**リソース ビュー**] をクリックします。 プロジェクト リソースを右クリックし、 **[ リソース シンボル**] をクリックします。 [リソース シンボル] ダイアログ`New`ボックスで、 をクリックします。 コマンド ID 名を入力`ID_INDICATOR_PAGE`します。 ID の値を指定するか、[リソース シンボル] ダイアログ ボックスで指定した値を受け入れます。 たとえば、 の`ID_INDICATOR_PAGE`場合は、既定値を受け入れます。 [リソース シンボル] ダイアログ ボックスを閉じます。

1. ペインに表示する既定の文字列を定義します。

   リソース ビューを開いた後、アプリケーションのリソースの種類を一覧表示するウィンドウで **[文字列テーブル**] をダブルクリックします。 **文字列テーブル**エディタを開いた後、[**挿入**] メニューの **[新しい文字列**] を選択します。 ペインのコマンド ID (たとえば) を`ID_INDICATOR_PAGE`選択し、"Page" などの既定の文字列値を入力します。 文字列エディタを閉じます。 (コンパイラ エラーを回避するには、既定の文字列が必要です)。

1. インジケータ配列にペイン*を追加します*。

   ファイルの中で、MAINFRM.CPP、指標配列*を*見つけます。 この配列は、ステータス バーのすべてのインジケータのコマンド ID を左から右の順にリストします。 配列の適切な位置で、次に示すように、ペインのコマンド ID を`ID_INDICATOR_PAGE`入力します。

   [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

ペインにテキストを表示する推奨される方法は、ペインの`SetText`更新ハンドラー関数で`CCmdUI`クラスのメンバー関数を呼び出す方法です。 たとえば、現在のページ番号を含む整数変数*m_nPage*を設定し、ペインのテキストをその`SetText`番号の文字列バージョンに設定する場合に使用します。

> [!NOTE]
> この`SetText`方法を推奨します。 メンバ関数`SetPaneText`を呼び出すことで、このタスクを少し低`CStatusBar`いレベルで実行できます。 それでも、更新ハンドラーが必要です。 ウィンドウに対してこのようなハンドラーがない場合、MFC は自動的にペインを無効にし、その内容を削除します。

次の手順では、更新ハンドラー関数を使用してペインにテキストを表示する方法を示します。

#### <a name="to-make-a-pane-display-text"></a>ペインにテキストを表示するには

1. コマンドのコマンド更新ハンドラーを追加します。

   ここで示すように、ハンドラーのプロトタイプを手動で追加します`ID_INDICATOR_PAGE`(MAINFRM で)。H):

   [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. 適切な .CPP ファイルで、(MAINFRM で) に`ID_INDICATOR_PAGE`示すように、ハンドラーの定義を追加します。CPP):

   [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

   このハンドラーの最後の 3 行は、テキストを表示するコードです。

1. 該当するメッセージ・マップに、(MAINFRM で)`ID_INDICATOR_PAGE`に示すように、ON_UPDATE_COMMAND_UI・マクロを追加します。CPP):

   [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

m_nPage*メンバー変数*(クラス`CMainFrame`) の値を定義すると、この手法を使用すると、アプリケーションが他のインジケーターを更新するのと同じ方法で、アイドル処理中にページ番号がペインに表示されます。 *m_nPage*変更すると、次のアイドル ループの間に表示が変更されます。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [ユーザー インターフェイス オブジェクトの更新 (プログラムの状態が変化した場合にツール バー ボタンとメニュー項目を更新する方法)](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>関連項目

[MFC でのステータス バーの実装](../mfc/status-bar-implementation-in-mfc.md)<br/>
[クラス](../mfc/reference/cstatusbar-class.md)
