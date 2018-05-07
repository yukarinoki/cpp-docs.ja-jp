---
title: ステータス バー ペインのテキストの更新 |Microsoft ドキュメント
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
ms.openlocfilehash: dbb2f14f274be3c7282a897c271049fe46434f3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>ステータス バー ペインのテキストの更新
この記事では、MFC ステータス バー ペインに表示されるテキストを変更する方法について説明します。 ステータス バー — クラスの window オブジェクト[CStatusBar](../mfc/reference/cstatusbar-class.md) — 複数「ペインです」が含まれています。 各ペインは、情報を表示する使用できるステータス バーの四角形の領域です。 たとえば、多くのアプリケーションは、一番右のペインに表示、CAPSLOCK、NUMLOCK、およびその他のキーの状態を表示します。 アプリケーションも多くの場合、テキストを表示役に立つ、一番左のウィンドウ (0)、「メッセージ ウィンドウ」とも呼ばれます。 たとえば、既定の MFC ステータス バーは、現在選択されているメニュー項目またはツール バー ボタンを説明する文字列を表示するのにメッセージ ウィンドウを使用します。 図に[ステータス バー](../mfc/status-bar-implementation-in-mfc.md)アプリケーション ウィザードで作成した MFC アプリケーションから、ステータス バーが表示されます。  
  
 既定では、MFC 有効にしません、`CStatusBar`ウィンドウのウィンドウの作成時にします。 ウィンドウをアクティブにする必要がありますを使用して、`ON_UPDATE_COMMAND_UI`状態に各ペインのマクロ バーおよびペインを更新します。 ウィンドウを送信しないため**WM_COMMAND**メッセージ (そうでないツール バー ボタンなど)、コードを手動で入力する必要があります。  
  
 たとえば、1 つのペインが`ID_INDICATOR_PAGE`ドキュメントでは、現在のページ番号が含まれていることと、コマンド識別子として。 次の手順では、ステータス バーで新しいウィンドウを作成する方法について説明します。  
  
### <a name="to-make-a-new-pane"></a>新しいペインを作成するには  
  
1.  ペインのコマンド ID を定義します  
  
     **ビュー**  メニューのをクリックして**リソース ビュー**です。 プロジェクト リソースを右クリックし、をクリックして**リソース シンボル**です。 [リソース シンボル] ダイアログ ボックス`New`です。 コマンド ID の名前を入力します。 たとえば、`ID_INDICATOR_PAGE`です。 ID の値を指定するか、[リソース シンボル] ダイアログ ボックスで表示された値を受け入れます。 たとえば、`ID_INDICATOR_PAGE`既定値をそのまま使用します。 リソース シンボル ダイアログ ボックスを閉じます。  
  
2.  ウィンドウに表示する既定の文字列を定義します。  
  
     リソース ビューを開きをダブルクリックして**ストリング テーブル**アプリケーションのリソースの種類を一覧表示されたウィンドウでします。 **ストリング テーブル**エディターを開く を選択して**新しい文字列**から、**挿入**メニュー。 文字列のプロパティ ウィンドウで、ペインのコマンド ID を選択 (たとえば、 `ID_INDICATOR_PAGE`)「ページ」などの既定の文字列値を入力します。 文字列エディターを閉じます。 (必要なコンパイラ エラーを回避するための既定の文字列です。)  
  
3.  ウィンドウを追加、**インジケーター**配列。  
  
     ファイルします。CPP、検索、**インジケーター**配列。 この配列には、左から右の順に、ステータス バーのインジケーターのすべてのコマンド Id が一覧表示します。 次に示すように配列に適切な時点では、ペインのコマンド ID を入力してください`ID_INDICATOR_PAGE`:  
  
     [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]  
  
 呼び出すには、ペインにテキストを表示することをお勧め、 **SetText**クラスのメンバー関数`CCmdUI`ウィンドウの更新プログラム ハンドラー関数にします。 整数型の変数を設定するなど、 `m_nPage` 、現在のページ番号および使用を含む**SetText**ペインのテキストをその数値の文字列形式に設定します。  
  
> [!NOTE]
>  **SetText**アプローチをお勧めします。 呼び出すことによってより若干少なくレベルでは、このタスクを実行することは、`CStatusBar`メンバー関数は、`SetPaneText`です。 その場合でも、更新ハンドラーも必要があります。 ウィンドウのハンドラーがこのようなを使用せず MFC 自動的に無効にウィンドウで、その内容が消去されます。  
  
 次の手順では、更新ハンドラー関数を使用して、テキスト、ウィンドウに表示する方法を示します。  
  
#### <a name="to-make-a-pane-display-text"></a>テキストを表示 ウィンドウを作成するには  
  
1.  コマンドのコマンド更新ハンドラーを追加します。  
  
     次に示すように、ハンドラーのプロトタイプを手動で追加`ID_INDICATOR_PAGE`でします。H):  
  
     [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]  
  
2.  適切な。CPP ファイルに追加し、ハンドラーの定義を次に示すように`ID_INDICATOR_PAGE`でします。CPP):  
  
     [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]  
  
     このハンドラーの最後の 3 つの行は、テキストを表示するコードです。  
  
3.  適切なメッセージ マップの追加、`ON_UPDATE_COMMAND_UI`マクロを次に示すように`ID_INDICATOR_PAGE`でします。CPP):  
  
     [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]  
  
 値を定義すると、`m_nPage`メンバー変数 (クラスの`CMainFrame`)、この手法により、アプリケーションが他のインジケーターを更新する同じ方法でアイドル状態の処理中に、ウィンドウに表示するページ番号です。 場合`m_nPage`の変更、次のアイドル ループ時に表示が変更されます。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ユーザー インターフェイス オブジェクト (プログラムの条件の変更として、ツールバーのボタンとメニュー項目を更新する方法) を更新します。](../mfc/how-to-update-user-interface-objects.md)  
  
## <a name="see-also"></a>関連項目  
 [ステータス バーの実装 (MFC の)](../mfc/status-bar-implementation-in-mfc.md)   
 [CStatusBar クラス](../mfc/reference/cstatusbar-class.md)
