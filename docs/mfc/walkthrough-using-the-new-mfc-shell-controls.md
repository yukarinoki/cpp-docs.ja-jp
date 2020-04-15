---
title: 'チュートリアル : 新しい MFC シェル コントロールの使用'
ms.date: 04/25/2019
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
ms.openlocfilehash: 5786fbbf7ec9f31e7d895a96dae27b8fc95abda1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360211"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>チュートリアル : 新しい MFC シェル コントロールの使用

このチュートリアルでは、エクスプローラーのようなアプリケーションを作成します。 2 つのウィンドウを含むウィンドウを作成します。 左側のウィンドウには、階層ビューにデスクトップを表示する[CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトが表示されます。 右側のウィンドウには、左側のウィンドウで選択されているフォルダー内のファイルを表示する[CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md)が表示されます。

## <a name="prerequisites"></a>前提条件

- Visual Studio 2017 以降では、MFC サポートはオプションのコンポーネントです。 インストールするには、Windows の [スタート] メニューから Visual Studio インストーラーを開きます。 使用している Visual Studio のバージョンを検索し、[**変更**] ボタンを選択します。 **[C++ でデスクトップ開発]** タイルがオンになっていることを確認します。 [**オプション コンポーネント]** の **[MFC サポート**] ボタンをオンにします。

- このチュートリアルでは、Visual Studio が **[一般的な開発設定]** を使用するように設定されていることを前提としています。 別の開発設定を使用している場合、このチュートリアルで使用する Visual Studio の一部のウィンドウが既定で表示されないことがあります。

## <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードを使用して新しい MFC アプリケーションを作成するには

これらの手順は、使用している Visual Studio のバージョンによって異なります。 Visual Studio の優先バージョンのドキュメントを表示するには、**バージョン**セレクター コントロールを使用します。 このページの目次の上部に表示されます。

::: moniker range="vs-2019"

### <a name="to-create-an-mfc-project-in-visual-studio-2019"></a>2019 年の VISUAL Studio で MFC プロジェクトを作成するには

1. メイン メニューで、**[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択して、**[新しいプロジェクトの作成]** ダイアログ ボックスを開きます。

1. 上部の検索ボックスに **「MFC」** と入力し、結果の一覧から **[MFC アプリ**] を選択します。

1. **[次へ]** をクリックします。 次のページで、プロジェクトの名前を入力し、必要に応じてプロジェクトの場所を指定します。

1. **[作成]** ボタンをクリックしてプロジェクトを作成します。

   **MFC アプリケーション ウィザード**が表示されたら、次のオプションを使用します。

   1. 左側の [**アプリケーションの種類]** を選択します。 次に、[**単一のドキュメント**] を選択し、[**ドキュメント/ビュー アーキテクチャ サポート**] を選択します。 [**プロジェクト スタイル**] の **[Visual Studio]** を選択し、[**表示スタイルと色**] ドロップダウン リストから **[Office 2007 (青のテーマ)]** を選択します。

   1. [**複合ドキュメント サポート**] ウィンドウで、[**なし**] を選択します。

   1. **[ドキュメント テンプレートのプロパティ]** ウィンドウは変更しないでください。

   1. [**ユーザー インターフェイス機能]** ウィンドウで、[**メニュー バーとツール バーを使用**する] オプションが選択されていることを確認します。 その他のオプションはそのままにします。

   1. [**拡張機能**] ウィンドウで **、[ActiveX コントロール**]、[**コモン コントロール マニフェスト**]、[**ナビゲーション ウィンドウ]** の各オプションを選択します。 他のすべてをそのままにしておきます。 **[ナビゲーション ウィンドウ]** オプションを使用すると、ウィンドウの左側に`CMFCShellTreeCtrl`ウィンドウが作成され、ウィンドウが既に埋め込まれています。

   1. **[生成されたクラス**] ウィンドウに変更を加えるつもりはないため、[完了]**を**クリックして新しい MFC プロジェクトを作成します。

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-an-mfc-project-in-visual-studio-2017-or-earlier"></a>2017 年以前のバージョンで MFC プロジェクトを作成するには

1. MFC**アプリケーション ウィザード**を使用して、新しい MFC アプリケーションを作成します。 ウィザードを実行するには、[**ファイル]** メニューの [**新規作成**] をクリックし、[**プロジェクト**] をクリックします。 [**新しいプロジェクト**] ダイアログ ボックスが表示されます。

1. [**新しいプロジェクト**] ダイアログ ボックスの [**プロジェクトの種類**] ペインで **[Visual C++]** ノードを展開し **、[MFC]** を選択します。 次に、[**テンプレート]** ペインで **[MFC アプリケーション**] を選択します。 プロジェクト`MFCShellControls`の名前を入力し **、[OK]** をクリックします。

   **MFC アプリケーション ウィザード**が表示されたら、次のオプションを使用します。

   1. [**アプリケーションの種類]** ウィンドウの [**アプリケーションの種類]** で、[**タブ付きドキュメント**] オプションをオフにします。 次に、[**単一のドキュメント**] を選択し、[**ドキュメント/ビュー アーキテクチャ サポート**] を選択します。 [**プロジェクト スタイル**] の **[Visual Studio]** を選択し、[**表示スタイルと色**] ドロップダウン リストから **[Office 2007 (青のテーマ)]** を選択します。

   1. [**複合ドキュメント サポート**] ウィンドウで、[**なし**] を選択します。

   1. **[ドキュメント テンプレート文字列**] ウィンドウは変更しないでください。

   1. [**データベース サポート**] ウィンドウ (Visual Studio 2015 以前) で、アプリケーションはデータベースを使用しないため、[**なし]** を選択します。

   1. [**ユーザー インターフェイス機能]** ウィンドウで、[**メニュー バーとツール バーを使用**する] オプションが選択されていることを確認します。 その他のオプションはそのままにします。

   1. [**拡張機能**] ウィンドウの [**高度な機能**] で **、[ActiveX コントロール**] と **[コモン コントロール マニフェスト**] のみを選択します。 [**詳細フレーム ペイン**] で、[**ナビゲーション ウィンドウ**] オプションのみを選択します。 これにより、ウィンドウの左側にウィンドウが作成され、`CMFCShellTreeCtrl`既に埋め込まれています。

   1. **[生成されたクラス**] ウィンドウに変更を加えるつもりはないため、[完了]**を**クリックして新しい MFC プロジェクトを作成します。

::: moniker-end

アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションをビルドするには、[**ビルド**] メニューの [**ソリューションのビルド**] をクリックします。 アプリケーションが正常にビルドされた場合は、[**デバッグ**] メニューの **[デバッグの開始**] を選択してアプリケーションを実行します。

ウィザードは、標準のメニュー バー、標準のツールバー、標準のステータス バー、**およびフォルダ**ビューと予定表ビューを使用して、ウィンドウの左側に Outlook バーを持つアプリケーションを自動的に作成**します**。

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>シェル リスト コントロールをドキュメント ビューに追加するには

1. このセクションでは、ウィザードが作成したビューに`CMFCShellListCtrl`のインスタンスを追加します。 **ソリューション エクスプローラー**で**MFCShellControlsView.h**をダブルクリックして、ビュー ヘッダー ファイルを開きます。

   ヘッダー ファイルの先頭部分にある `#pragma once` ディレクティブを探します。 その直後に、次のコードを追加して、`CMFCShellListCtrl` のヘッダー ファイルをインクルードします。

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   次に、`CMFCShellListCtrl` 型のメンバー変数を追加します。 最初に、ヘッダー ファイルで次のコメントを探します。

   ```cpp
   // Generated message map functions
   ```

   コメントのすぐ上に、次のコードを追加します。

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

1. **MFC アプリケーション ウィザード**は、`CMFCShellTreeCtrl`クラス内に`CMainFrame`既にオブジェクトを作成していますが、そのオブジェクトは保護されたメンバーです。 後でオブジェクトにアクセスするので、ここでアクセサーを作成します。 **ソリューション エクスプローラ**で MainFrm.h ヘッダー ファイルをダブルクリックして開きます。 次のコメントを探します。

   ```cpp
   // Attributes
   ```

   この直後に、次のメソッド宣言を追加します。

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   次に、**ソリューション エクスプローラ**で MainFrm.cpp ソース ファイルをダブルクリックして開きます。 このファイルの末尾に、次のメソッド定義を追加します。

   ```cpp
   CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()
   {
        return m_wndTree;
   }
   ```

1. `CMFCShellControlsView` Windows メッセージを処理するように `WM_CREATE` クラスを更新します。 **[クラス ビュー]** ウィンドウを`CMFCShellControlsView`開き、クラスを選択します。 右クリックし、**[プロパティ]** を選択します。

   次に、[クラス ウィザード](reference/mfc-class-wizard.md)で、[**メッセージ**] タブをクリック`WM_CREATE`します。 の横にあるドロップダウン リストで`WM_CREATE`、[ ** \<>の追加**] を選択します。 このコマンドは、メッセージ ハンドラーを作成し、MFC メッセージ マップを自動的に更新します。

   メソッドでは`OnCreate`、次にオブジェクトを`CMFCShellListCtrl`作成します。 MFCShellControlsView.cpp ソース ファイルで `OnCreate` メソッド定義を探し、その実装を次のコードに置き換えます。

    ```cpp
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)
    {
        if (CView::OnCreate(lpCreateStruct) == -1)
            return -1;

        CRect rectDummy (0, 0, 0, 0);

        m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,
            rectDummy, this, 1);

        return 0;
    }
    ```

1. `WM_SIZE` メッセージについて、前の手順を繰り返します。 これにより、ユーザーがアプリケーション ウィンドウのサイズを変更するたびに、アプリケーション ビューが再描画されます。 `OnSize` メソッドの定義を次のコードに置き換えます。

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

1. 最後の手順は、メソッドを`CMFCShellTreeCtrl`使用`CMFCShellListCtrl`して オブジェクトと[オブジェクトを接続することです](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist)。 を呼び`CMFCShellTreeCtrl::SetRelatedList`出すと`CMFCShellListCtrl`、 で選択した項目の内容が 自動的`CMFCShellTreeCtrl`に表示されます。 `OnActivateView`[メソッド](../mfc/reference/cview-class.md#onactivateview)内のオブジェクトを接続します。

   MFCShellControlsView.h ヘッダー ファイルの `CMFCShellControlsView` クラス宣言に、次のメソッド宣言を追加します。

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   次に、メソッドの定義を MFCShellControlsView.cpp ソース ファイルに追加します。

    ```cpp
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView)
    {
        if (bActivate&& AfxGetMainWnd() != NULL)
        {
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);
        }

        CView::OnActivateView(bActivate,
            pActivateView,
            pDeactiveView);
    }
    ```

   クラスからメソッドを`CMainFrame`呼び出すため、MFCShellControlsView.cpp ソース ファイルの先頭に`#include`ディレクティブを追加する必要があります。

    ```cpp
    #include "MainFrm.h"
    ```

1. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションをビルドするには、[**ビルド**] メニューの [**ソリューションのビルド**] をクリックします。 アプリケーションが正常にビルドされた場合は、[**デバッグ**] メニューの **[デバッグの開始**] を選択して実行します。

   `CMFCShellTreeCtrl` で選択されている項目の詳細が、ビュー ペインに表示されるようになりました。 `CMFCShellTreeCtrl` でノードをクリックすると、`CMFCShellListCtrl` が自動的に更新されます。 また、`CMFCShellListCtrl` でフォルダーをダブルクリックすると、`CMFCShellTreeCtrl` が自動的に更新されます。

   ツリー コントロールまたはリスト コントロール内の任意の項目を右クリックします。 実際のエクスプローラー を使用している場合と同じコンテキスト メニューが表示**されます**。

## <a name="next-steps"></a>次のステップ

- **ウィザードは、フォルダ**ウィンドウと**予定表**ウィンドウの両方を含む Outlook バーを作成しました。 **エクスプローラ**ウィンドウに **[予定表**] ウィンドウを表示しても意味がない可能性があります。

- `CMFCShellListCtrl`**大きいアイコン**、**小さい**アイコン、**リスト**、**および詳細**など、さまざまなモードでのファイルの表示をサポートしています。 アプリケーションを更新して、この機能を実装します。 ヒント: [「Visual C++ のサンプル](../overview/visual-cpp-samples.md)」を参照してください。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)
