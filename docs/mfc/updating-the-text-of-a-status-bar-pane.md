---
title: ステータス バー ペインのテキストの更新 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aa04fdee2b63f9d91d2bdd7dfd62100b3e32a2c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393322"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>ステータス バー ペインのテキストの更新

この記事では、MFC ステータス バー ペインに表示されるテキストを変更する方法について説明します。 ステータス バー、クラスのウィンドウ オブジェクト[CStatusBar](../mfc/reference/cstatusbar-class.md) : いくつか「ウィンドウ」が含まれています 各ペインは、情報を表示するのに使用できるステータス バーの四角形の領域です。 たとえば、アプリケーションの多くは、右端のウィンドウで CAPS LOCK、NUM LOCK、およびその他のキーの状態を表示します。 アプリケーションも多くの場合、「メッセージ ウィンドウ」とも呼ばれます (ウィンドウ 0) の一番左のウィンドウでわかりやすいテキストを表示します。 たとえば、既定の MFC ステータス バーは、現在選択されているメニュー項目またはツール バー ボタンを説明する文字列を表示するのにメッセージ ウィンドウを使用します。 図に[ステータス バー](../mfc/status-bar-implementation-in-mfc.md)アプリケーション ウィザードで作成した MFC アプリケーションからのステータス バーが表示されます。

既定では、MFC 有効にしません、`CStatusBar`ウィンドウのウィンドウの作成時にします。 ウィンドウをアクティブ化するには、ON_UPDATE_COMMAND_UI マクロを使用して、ステータス バーには、各ウィンドウのおよびペインを更新する必要があります。 ウィンドウは WM_COMMAND メッセージを送信しないためです (そうでないツール バー ボタンなど)、コードを手動で入力する必要があります。

たとえば、1 つのペインが`ID_INDICATOR_PAGE`ドキュメントでは、現在のページ番号が含まれていると、コマンド識別子として。 次の手順では、ステータス バーで、新しいウィンドウを作成する方法について説明します。

### <a name="to-make-a-new-pane"></a>新しいペインを作成するには

1. 定義ウィンドウのコマンド id。

     **ビュー**  メニューのをクリックして**リソース ビュー**します。 プロジェクト リソースを右クリックし、をクリックして**リソース シンボル**します。 [リソース シンボル] ダイアログ ボックスで、`New`します。 コマンド ID の名前を入力します。 たとえば、`ID_INDICATOR_PAGE`します。 では、ID の値を指定するか、[リソース シンボル] ダイアログ ボックスで提案された値を使用します。 たとえば、`ID_INDICATOR_PAGE`既定値をそのまま使用します。 リソース シンボル ダイアログ ボックスを閉じます。

1. ウィンドウに表示する既定の文字列を定義します。

     リソース ビューを開き、ダブルクリック**ストリング テーブル**アプリケーションのリソースの種類を一覧表示するウィンドウ。 **ストリング テーブル**エディターを開き、選択**新しい文字列**から、**挿入**メニュー。 文字列のプロパティ ウィンドウで、ウィンドウのコマンド ID を選択します (たとえば、 `ID_INDICATOR_PAGE`)「ページ」など、既定の文字列値を入力します。 文字列エディターを閉じます。 (既定の文字列が、コンパイラ エラーを回避するために必要)。

1. ウィンドウを追加、*インジケーター*配列。

     ファイルします。CPP、検索、*インジケーター*配列。 この配列は、左から右への順序で、ステータス バーのインジケーターのすべてのコマンド Id を一覧表示します。 配列の適切な時点に示すように、ウィンドウのコマンド ID を入力`ID_INDICATOR_PAGE`:

     [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

呼び出すことをウィンドウにテキストを表示する推奨される方法です、`SetText`クラスのメンバー関数`CCmdUI`でウィンドウの更新ハンドラー関数。 整数型の変数を設定するなど、 *m_nPage*使用と現在のページ数を格納している`SetText`ペインのテキストをその数値の文字列形式に設定します。

> [!NOTE]
>  `SetText`アプローチをお勧めします。 呼び出すことにより若干低いレベルでは、このタスクを実行することは、`CStatusBar`メンバー関数は`SetPaneText`します。 そうであっても、更新ハンドラーも必要があります。 せず、ウィンドウのハンドラーがこのような MFC 自動的に無効にウィンドウで、その内容を消去します。

次の手順では、更新ハンドラー関数を使用して、ウィンドウでテキストを表示する方法を示します。

#### <a name="to-make-a-pane-display-text"></a>テキストの表示ウィンドウ

1. コマンドのコマンド更新ハンドラーを追加します。

     次に示すように、ハンドラーのプロトタイプを手動で追加`ID_INDICATOR_PAGE`(でします。H):

     [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. 適切な。CPP ファイルに示すように、ハンドラーの定義を追加`ID_INDICATOR_PAGE`(でします。CPP):

     [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

     このハンドラーの最後の 3 つの行は、テキストを表示するコードです。

1. 適切なメッセージ マップに示すように、ON_UPDATE_COMMAND_UI マクロを追加`ID_INDICATOR_PAGE`(でします。CPP):

     [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

値を定義すると、 *m_nPage*メンバー変数 (クラスの`CMainFrame`)、この手法により、アプリケーションが他のインジケーターを更新するのと同様に、アイドル状態の処理中に、ウィンドウに表示するページ番号。 場合*m_nPage*の変更、表示が次のアイドル ループの中に変更します。

### <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [ユーザー インターフェイス オブジェクト (プログラムの条件の変更として、ツールバーのボタンとメニュー項目を更新する方法) を更新します。](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>関連項目

[MFC でのステータス バーの実装](../mfc/status-bar-implementation-in-mfc.md)<br/>
[CStatusBar クラス](../mfc/reference/cstatusbar-class.md)
