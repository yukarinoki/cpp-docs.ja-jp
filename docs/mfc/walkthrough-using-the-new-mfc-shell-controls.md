---
title: 'チュートリアル: 新しい Mfc シェルのコントロール |Microsoft Docs'
ms.custom: ''
ms.date: 09/20/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e1cffc9d1231cd9e8e91b445f05eb7dbbbc4ce4
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169620"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>チュートリアル : 新しい MFC シェル コントロールの使用

このチュートリアルでは、ファイル エクスプローラーのような外観のアプリケーションを作成します。 ここでは、2 つのペインのあるウィンドウを作成します。 左側のウィンドウには、 [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md)階層ビューで、デスクトップを表示するオブジェクト。 右側のウィンドウには、 [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md)左側のウィンドウで選択されているフォルダーにファイルを表示します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルでは、使用する Visual Studio を設定して**汎用開発設定**します。 さまざまな開発設定を使用している場合は、このチュートリアルで使用する一部の Visual Studio ウィンドウは、既定では表示されません。

### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードを使用して新しい MFC アプリケーションを作成するには

1. 使用して、 **MFC アプリケーション ウィザード**新しい MFC アプリケーションを作成します。 ウィザードを実行する、**ファイル**メニューの **新規**、し、**プロジェクト**します。 **新しいプロジェクト** ダイアログ ボックスが表示されます。

1. **新しいプロジェクト** ダイアログ ボックスで、展開、 **Visual C**内のノード、**プロジェクトの種類**ペイン**MFC**します。 次に、**テンプレート**ペインで、 **MFC アプリケーション**します。 など、プロジェクトの名前を入力`MFCShellControls` をクリック**OK**します。 後**MFC アプリケーション ウィザード**が表示されたら、次のオプションを使用します。

    1. **アプリケーションの種類** ウィンドウで、**アプリケーションの種類**チェック ボックスをオフ、**タブ付きドキュメント**オプション。 次に、選択**1 つのドキュメント**選択**ドキュメント/ビュー アーキテクチャ サポート**します。 **スタイル プロジェクト**を選択します**Visual Studio**との間、**視覚スタイルと色**一覧選択ドロップダウン**Office 2007 (青のテーマ)**. 

    1. **複合ドキュメント サポート**ペインで、 **None**します。

    1. 変更を加えないでください、**ドキュメント テンプレート文字列**ウィンドウ。

    1. **データベース サポート**ペイン (Visual Studio 2015 以前) を選択**None**このアプリケーションでは、データベースが使用されないためです。 

    1. **ユーザー インターフェイス機能**ウィンドウで、ことを確認します、**メニュー バーとツールバーを使用して、** オプションを選択します。 その他のオプションはそのままにします。 

    1. **高度な機能**ウィンドウで、**機能を高度な**、のみを選択します**ActiveX コントロール**と**コモン コントロール マニフェスト**。 **フレーム ウィンドウを高度な**、のみを選択、**ナビゲーション ウィンドウ**オプション。 これにより、ウィンドウの左側に、`CMFCShellTreeCtrl` が埋め込まれた状態でナビゲーション ウィンドウが作成されます。 

    1. 変更を加えることはできません、**生成されたクラス**ウィンドウ。 そのため、をクリックして**完了**新しい MFC プロジェクトを作成します。

1. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションを構築する、**ビルド**メニューの **ソリューションのビルド**します。 アプリケーションが正常にビルドする場合を選択してアプリケーションを実行**デバッグの開始**から、**デバッグ**メニュー。

   ウィンドウの左側に標準のメニュー バー、標準ツールバー、標準ステータス バー、および Outlook バーを持つアプリケーションを自動的に作成、**フォルダー**ビューと**カレンダー**ビュー.

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>シェル リスト コントロールをドキュメント ビューに追加するには

1. ここでは、ウィザードによって作成されたビューに `CMFCShellListCtrl` のインスタンスを追加します。 ビューのヘッダー ファイルをダブルクリックして開きます**MFCShellControlsView.h**で、**ソリューション エクスプ ローラー**します。

   ヘッダー ファイルの先頭部分にある `#pragma once` ディレクティブを探します。 その直後に、次のコードを追加して、`CMFCShellListCtrl` のヘッダー ファイルをインクルードします。

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   次に、`CMFCShellListCtrl` 型のメンバー変数を追加します。 最初に、ヘッダー ファイルで次のコメントを探します。

   ```cpp
   // Generated message map functions
   ```

   そのコメントの直前に、次のコードを追加します。

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

1. **MFC アプリケーション ウィザード**既に作成されて、`CMFCShellTreeCtrl`オブジェクト、`CMainFrame`クラスが、保護されたメンバーであります。 後で、このオブジェクトにアクセスします。 したがって、ここでアクセサーを作成します。 ダブルクリックして、MainFrm.h ヘッダー ファイルを開き、**ソリューション エクスプ ローラー**します。 次のコメントを探します。

   ```cpp
   // Attributes
   ```

   この直後に、次のメソッド宣言を追加します。

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   次に、ダブルクリックして MainFrm.cpp ソース ファイルを開き、**ソリューション エクスプ ローラー**します。 このファイルの末尾に、次のメソッド定義を追加します。

   ```cpp
   CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()
   {
        return m_wndTree;
   }
   ```

1. `CMFCShellControlsView` Windows メッセージを処理するように `WM_CREATE` クラスを更新します。 開く、**クラス ビュー**ウィンドウと選択、`CMFCShellControlsView`クラス。 右クリックして**プロパティ**します。

    次に、**プロパティ**ウィンドウで、をクリックして、**メッセージ**アイコン。 スクロール ダウンして `WM_CREATE` メッセージを探します。 横のリスト ドロップダウンから`WM_CREATE`、 **\<追加 > OnCreate**します。 これにより、メッセージ ハンドラーが作成され、MFC メッセージ マップが自動的に更新されます。

   `OnCreate` メソッドで、独自の `CMFCShellListCtrl` オブジェクトを作成します。 MFCShellControlsView.cpp ソース ファイルで `OnCreate` メソッド定義を探し、その実装を次のコードに置き換えます。

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

1. `WM_SIZE` メッセージについて、前の手順を繰り返します。 これにより、ユーザーがアプリケーション ウィンドウのサイズを変更するたびにアプリケーションのビューが再描画されるようになります。 `OnSize` メソッドの定義を次のコードに置き換えます。

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

1. 最後の手順が接続するには、`CMFCShellTreeCtrl`と`CMFCShellListCtrl`オブジェクトを使用して、 [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist)メソッド。 このメソッドを呼び出すと、`CMFCShellListCtrl` で選択された項目の内容が自動的に `CMFCShellTreeCtrl` に表示されます。 行いますが、`OnActivateView`からオーバーライドされるメソッドは、 [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview)します。

   MFCShellControlsView.h ヘッダー ファイルの `CMFCShellControlsView` クラス宣言に、次のメソッド宣言を追加します。

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   次に、このメソッドの定義を MFCShellControlsView.cpp ソース ファイルに追加します。

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

   `CMainFrame` クラスのメソッドを呼び出すため、MFCShellControlsView.cpp ソース ファイルの先頭部分に次の `#include` ディレクティブを追加する必要があります。

    ```cpp
    #include "MainFrm.h"
    ```

1. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションを構築する、**ビルド**メニューの **ソリューションのビルド**します。 場合は、アプリケーションが正常にビルド、実行を選択して**デバッグの開始**から、**デバッグ**メニュー。

   `CMFCShellTreeCtrl` で選択されている項目の詳細が、ビュー ペインに表示されるようになりました。 `CMFCShellTreeCtrl` でノードをクリックすると、`CMFCShellListCtrl` が自動的に更新されます。 また、`CMFCShellListCtrl` でフォルダーをダブルクリックすると、`CMFCShellTreeCtrl` が自動的に更新されます。

   ツリー コントロールまたはリスト コントロールの任意の項目を右クリックします。 実際を使用していた場合、同じコンテキスト メニューを取得することに注意してください。**ファイル エクスプ ローラー**します。

## <a name="next-steps"></a>次の手順

- ウィザードでは、両方で Outlook バーが作成された、**フォルダー**ウィンドウと**カレンダー**ウィンドウ。 おそらくは無意味に、**カレンダー**ペインで、**エクスプ ローラー**ウィンドウ。 したがって、このペインを削除します。

- `CMFCShellListCtrl`の異なるモードでファイルの表示をサポート**大きいアイコン**、**小さいアイコン**、**一覧**、および**詳細**します。 アプリケーションを更新して、この機能を実装します。 ヒント: を参照してください[Visual C のサンプル](../visual-cpp-samples.md)します。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)
