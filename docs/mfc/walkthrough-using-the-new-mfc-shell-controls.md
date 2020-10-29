---
title: 'チュートリアル : 新しい MFC シェル コントロールの使用'
ms.date: 04/25/2019
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
ms.openlocfilehash: 0d8db9044a64305bd7bb9ef6fe10de9ecef1ce51
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924753"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>チュートリアル : 新しい MFC シェル コントロールの使用

このチュートリアルでは、ファイルエクスプローラーに似たアプリケーションを作成します。 2つのペインを持つウィンドウを作成します。 左側のウィンドウには、デスクトップを階層ビューで表示する [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) オブジェクトが保持されます。 右側のウィンドウに [Cmfcshelllistctrl](../mfc/reference/cmfcshelllistctrl-class.md) が表示され、左側のウィンドウで選択されているフォルダー内のファイルが表示されます。

## <a name="prerequisites"></a>前提条件

- Visual Studio 2017 以降では、MFC のサポートはオプションのコンポーネントです。 インストールするには、Windows の [スタート] メニューから Visual Studio インストーラーを開きます。 使用している Visual Studio のバージョンを見つけて、[ **変更** ] ボタンをクリックします。 [ **C++ によるデスクトップ開発** ] タイルがオンになっていることを確認します。 [ **オプションコンポーネント** ] で、[ **MFC サポート** ] ボタンをオンにします。

- このチュートリアルでは、 **全般的な開発設定** を使用するように Visual Studio を設定していることを前提としています。 別の開発設定を使用している場合は、このチュートリアルで使用している一部の Visual Studio ウィンドウが既定で表示されないことがあります。

## <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードを使用して新しい MFC アプリケーションを作成するには

これらの手順は、使用している Visual Studio のバージョンによって異なります。 優先するバージョンの Visual Studio のドキュメントを表示するには、 **[バージョン]** セレクター コントロールを使用します。 このページの目次の一番上にあります。

::: moniker range="msvc-160"

### <a name="to-create-an-mfc-project-in-visual-studio-2019"></a>Visual Studio 2019 で MFC プロジェクトを作成するには

1. メイン メニューで、 **[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択して、 **[新しいプロジェクトの作成]** ダイアログ ボックスを開きます。

1. 上部の検索ボックスに「 **mfc** 」と入力し、結果の一覧で [ **mfc アプリ** ] を選択します。

1. **[次へ]** をクリックします。 次のページで、プロジェクトの名前を入力し、必要に応じてプロジェクトの場所を指定します。

1. **[作成]** ボタンをクリックしてプロジェクトを作成します。

   **MFC アプリケーションウィザード** が表示されたら、次のオプションを使用します。

   1. 左側で [ **アプリケーションの種類** ] を選択します。 次に、[ **単一ドキュメント** ] を選択し、[ **ドキュメント/ビューアーキテクチャのサポート** ] を選択します。 [ **プロジェクトスタイル** ] で、[ **visual Studio** ] を選択し、[ **visual スタイルと色** ] ドロップダウンリストから [ **Office 2007 (Blue theme)** ] を選択します。

   1. [ **複合ドキュメントサポート** ] ペインで、[ **なし** ] を選択します。

   1. **ドキュメントテンプレートのプロパティ** ペインを変更しないでください。

   1. [ **ユーザーインターフェイス機能** ] ウィンドウで、[ **メニューバーとツールバーを使用する** ] オプションが選択されていることを確認します。 その他のオプションはそのままにします。

   1. [ **高度な機能** ] ウィンドウで、[ **ActiveX コントロール** ]、[ **コモンコントロールマニフェスト** ]、および [ **ナビゲーションウィンドウ** ] オプションを選択します。 そのままにしておきます。 [ **ナビゲーションウィンドウ** ] オプションを選択すると、ウィザードによってウィンドウの左側に、 `CMFCShellTreeCtrl` 既に埋め込まれたウィンドウが作成されます。

   1. **生成さ** れたクラスペインには変更を加えないため、[ **完了** ] をクリックして新しい MFC プロジェクトを作成します。

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-create-an-mfc-project-in-visual-studio-2017-or-earlier"></a>Visual Studio 2017 以前で MFC プロジェクトを作成するには

1. **Mfc アプリケーションウィザード** を使用して、新しい mfc アプリケーションを作成します。 ウィザードを実行するには、[ **ファイル** ] メニューの [ **新規作成** ] をポイントし、[ **プロジェクト** ] をクリックします。 [ **新しいプロジェクト** ] ダイアログボックスが表示されます。

1. [ **新しいプロジェクト** ] ダイアログボックスで、[ **プロジェクトの種類** ] ペインの [ **Visual C++** ] ノードを展開し、[ **MFC** ] をクリックします。 次に、[ **テンプレート** ] ペインで [ **MFC アプリケーション** ] を選択します。 プロジェクトの名前 (など) を入力し、 `MFCShellControls` [ **OK]** をクリックします。

   **MFC アプリケーションウィザード** が表示されたら、次のオプションを使用します。

   1. [ **アプリケーションの種類** ] ウィンドウの [ **アプリケーションの種類** ] で、[ **タブ付きドキュメント** ] オプションをオフにします。 次に、[ **単一ドキュメント** ] を選択し、[ **ドキュメント/ビューアーキテクチャのサポート** ] を選択します。 [ **プロジェクトスタイル** ] で、[ **visual Studio** ] を選択し、[ **visual スタイルと色** ] ドロップダウンリストから [ **Office 2007 (Blue theme)** ] を選択します。

   1. [ **複合ドキュメントサポート** ] ペインで、[ **なし** ] を選択します。

   1. [ **ドキュメントテンプレート文字列** ] ペインには変更を加えないでください。

   1. アプリケーションでデータベースを使用しないため、[ **データベースサポート** ] ウィンドウ (Visual Studio 2015 以前) で [ **なし** ] を選択します。

   1. [ **ユーザーインターフェイス機能** ] ウィンドウで、[ **メニューバーとツールバーを使用する** ] オプションが選択されていることを確認します。 その他のオプションはそのままにします。

   1. [ **高度な機能** ] ウィンドウの [ **高度な機能** ] で、[ **ActiveX コントロール** と **コモンコントロールマニフェスト** のみ] を選択します。 [ **高度なフレームペイン** ] で、[ **ナビゲーションウィンドウ** ] オプションのみを選択します。 これにより、ウィザードによってウィンドウの左側に、 `CMFCShellTreeCtrl` 既に埋め込まれたウィンドウが作成されます。

   1. **生成さ** れたクラスペインには変更を加えないため、[ **完了** ] をクリックして新しい MFC プロジェクトを作成します。

::: moniker-end

アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションをビルドするには、[ **ビルド** ] メニューの [ **ソリューションのビルド** ] をクリックします。 アプリケーションが正常にビルドされた場合は、[ **デバッグ** ] メニューの [ **デバッグ開始** ] をクリックしてアプリケーションを実行します。

ウィザードでは、標準のメニューバー、標準のツールバー、標準のステータスバー、およびウィンドウの左側にある Outlook バー ( **フォルダー** ビューと **予定表** ビュー) を持つアプリケーションが自動的に作成されます。

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>シェル リスト コントロールをドキュメント ビューに追加するには

1. このセクションでは、ウィザードによって `CMFCShellListCtrl` 作成されたビューにのインスタンスを追加します。 **ソリューションエクスプローラー** で [ **mfcshell]** をダブルクリックして、ビューヘッダーファイルを開きます。

   ヘッダー ファイルの先頭部分にある `#pragma once` ディレクティブを探します。 その直後に、次のコードを追加して、`CMFCShellListCtrl` のヘッダー ファイルをインクルードします。

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   次に、`CMFCShellListCtrl` 型のメンバー変数を追加します。 最初に、ヘッダー ファイルで次のコメントを探します。

   ```cpp
   // Generated message map functions
   ```

   そのコメントのすぐ上に、次のコードを追加します。

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

1. **MFC アプリケーションウィザード** では、クラスにオブジェクトが既に作成され `CMFCShellTreeCtrl` てい `CMainFrame` ますが、プロテクトメンバーです。 後でオブジェクトにアクセスするため、ここではアクセサーを作成します。 **ソリューションエクスプローラー** で mainfrm.cpp ヘッダーファイルをダブルクリックして開きます。 次のコメントを探します。

   ```cpp
   // Attributes
   ```

   この直後に、次のメソッド宣言を追加します。

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   次に、 **ソリューションエクスプローラー** でダブルクリックして、mainfrm.cpp ソースファイルを開きます。 このファイルの末尾に、次のメソッド定義を追加します。

   ```cpp
   CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()
   {
        return m_wndTree;
   }
   ```

1. `CMFCShellControlsView` Windows メッセージを処理するように `WM_CREATE` クラスを更新します。 [ **クラスビュー** ] ウィンドウを開き、クラスを選択し `CMFCShellControlsView` ます。 右クリックし、 **[プロパティ]** を選択します。

   次に、 [クラスウィザード](reference/mfc-class-wizard.md)で、[ **メッセージ** ] タブをクリックします。メッセージが見つかるまで下にスクロール `WM_CREATE` します。 の横にあるドロップダウンリストから `WM_CREATE` 、[ **\<Add> OnCreate** ] を選択します。 このコマンドは、メッセージハンドラーを作成し、MFC メッセージマップを自動的に更新します。

   メソッドで `OnCreate` 、ここでオブジェクトを作成 `CMFCShellListCtrl` します。 MFCShellControlsView.cpp ソース ファイルで `OnCreate` メソッド定義を探し、その実装を次のコードに置き換えます。

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

1. `WM_SIZE` メッセージについて、前の手順を繰り返します。 これにより、ユーザーがアプリケーションウィンドウのサイズを変更するたびに、アプリケーションビューが再描画されます。 `OnSize` メソッドの定義を次のコードに置き換えます。

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

1. 最後の手順では、 `CMFCShellTreeCtrl` `CMFCShellListCtrl` [CMFCShellTreeCtrl:: set list](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) メソッドを使用して、オブジェクトとオブジェクトを接続します。 を呼び出すと、 `CMFCShellTreeCtrl::SetRelatedList` `CMFCShellListCtrl` で選択されている項目の内容がによって自動的に表示され `CMFCShellTreeCtrl` ます。 メソッド内のオブジェクトを接続します `OnActivateView` 。これは、 [CView:: Onのアクティブビュー](../mfc/reference/cview-class.md#onactivateview)からオーバーライドされます。

   MFCShellControlsView.h ヘッダー ファイルの `CMFCShellControlsView` クラス宣言に、次のメソッド宣言を追加します。

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   次に、メソッドの定義を Mfcshellのソースファイルに追加します。

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

   クラスからメソッドを呼び出しているため `CMainFrame` 、 `#include` 次のように、mfcshellcontrolsview .cpp ソースファイルの先頭にディレクティブを追加する必要があります。

    ```cpp
    #include "MainFrm.h"
    ```

1. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションをビルドするには、[ **ビルド** ] メニューの [ **ソリューションのビルド** ] をクリックします。 アプリケーションが正常にビルドされた場合は、[ **デバッグ** ] メニューの [ **デバッグ開始** ] をクリックして実行します。

   `CMFCShellTreeCtrl` で選択されている項目の詳細が、ビュー ペインに表示されるようになりました。 `CMFCShellTreeCtrl` でノードをクリックすると、`CMFCShellListCtrl` が自動的に更新されます。 また、`CMFCShellListCtrl` でフォルダーをダブルクリックすると、`CMFCShellTreeCtrl` が自動的に更新されます。

   ツリーコントロールまたはリストコントロール内のいずれかの項目を右クリックします。 実際の **ファイルエクスプローラー** を使用している場合と同じコンテキストメニューが表示されます。

## <a name="next-steps"></a>次の手順

- ウィザードによって、 **フォルダー** ウィンドウと **予定表** ウィンドウの両方を含む Outlook バーが作成されました。 [ **エクスプローラー** ] ウィンドウに **予定表** ウィンドウを表示しても意味がないので、このウィンドウを削除してください。

- は、 `CMFCShellListCtrl` **大きいアイコン** 、 **小さいアイコン** 、 **一覧** 、 **詳細** など、さまざまなモードでファイルを表示することをサポートしています。 アプリケーションを更新して、この機能を実装します。 ヒント: [Visual C++ のサンプル](../overview/visual-cpp-samples.md)を参照してください。

## <a name="see-also"></a>こちらもご覧ください

[チュートリアル](../mfc/walkthroughs-mfc.md)
