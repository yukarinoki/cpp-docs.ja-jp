---
title: 'チュートリアル: 新しい Mfc シェルのコントロール |Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
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
ms.openlocfilehash: 6fbf10ef749df0ce5e5984ac773e0d2c00106b82
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42538529"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>チュートリアル : 新しい MFC シェル コントロールの使用

このチュートリアルでは、ファイル エクスプローラーのような外観のアプリケーションを作成します。 ここでは、2 つのペインのあるウィンドウを作成します。 左側のウィンドウには、 [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md)階層ビューで、デスクトップを表示するオブジェクト。 右側のウィンドウには、 [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md)左側のウィンドウで選択されているフォルダーにファイルを表示します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルでは、使用する Visual Studio を設定して**汎用開発設定**します。 さまざまな開発設定を使用している場合は、このチュートリアルで使用する一部の Visual Studio ウィンドウは、既定では表示されません。

### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードを使用して新しい MFC アプリケーションを作成するには

1. 使用して、 **MFC アプリケーション ウィザード**新しい MFC アプリケーションを作成します。 ウィザードを実行する、**ファイル**メニューの **新規**、し、**プロジェクト**します。 **新しいプロジェクト** ダイアログ ボックスが表示されます。

2. **新しいプロジェクト** ダイアログ ボックスで、展開、 **Visual C**内のノード、**プロジェクトの種類**ペイン**MFC**します。 次に、**テンプレート**ペインで、 **MFC アプリケーション**します。 など、プロジェクトの名前を入力`MFCShellControls` をクリック**OK**します。 **MFC アプリケーション ウィザード**が表示されます。

3. **MFC アプリケーション ウィザード**ダイアログ ボックスで、をクリックして**次**します。 **アプリケーションの種類**ペインが表示されます。

4. **アプリケーションの種類** ウィンドウで、**アプリケーションの種類**チェック ボックスをオフ、**タブ付きドキュメント**オプション。 次に、選択**1 つのドキュメント**選択**ドキュメント/ビュー アーキテクチャ サポート**します。 **スタイル プロジェクト**を選択します**Visual Studio**との間、**視覚スタイルと色**一覧選択ドロップダウン**Office 2007 (青のテーマ)**. その他のオプションはそのままにします。 クリックして**次**を表示する、**複合ドキュメント サポート**ウィンドウ。

5. **複合ドキュメント サポート**ペインで、 **None**します。 クリックして**次**を表示する、**ドキュメント テンプレート文字列**ウィンドウ。

6. 変更を加えないでください、**ドキュメント テンプレート文字列**ウィンドウ。 をクリックして**次**を表示する、**データベース サポート**ウィンドウ。

7. **データベース サポート**ペインで、 **None**このアプリケーションでは、データベースが使用されないためです。 をクリックして**次**を表示する、**ユーザー インターフェイス機能**ウィンドウ。

8. **ユーザー インターフェイス機能**ウィンドウで、ことを確認します、**メニュー バーとツールバーを使用して、** オプションを選択します。 その他のオプションはそのままにします。 をクリックして**次**を表示する、**高度な機能**ウィンドウ。

9. **高度な機能**ウィンドウで、**機能を高度な**、のみを選択します**ActiveX コントロール**と**コモン コントロール マニフェスト**。 **フレーム ウィンドウを高度な**、のみを選択、**ナビゲーション ウィンドウ**オプション。 これにより、ウィンドウの左側に、`CMFCShellTreeCtrl` が埋め込まれた状態でナビゲーション ウィンドウが作成されます。 をクリックして**次**を表示する、**生成されたクラス**ウィンドウ。

10. 変更を加えることはできません、**生成されたクラス**ウィンドウ。 そのため、をクリックして**完了**新しい MFC プロジェクトを作成します。

11. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションを構築する、**ビルド**メニューの **ソリューションのビルド**します。 アプリケーションが正常にビルドする場合を選択してアプリケーションを実行**デバッグの開始**から、**デバッグ**メニュー。

   ウィンドウの左側に標準のメニュー バー、標準ツールバー、標準ステータス バー、および Outlook バーを持つアプリケーションを自動的に作成、**フォルダー**ビューと**カレンダー**ビュー.

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>シェル リスト コントロールをドキュメント ビューに追加するには

1. ここでは、ウィザードによって作成されたビューに `CMFCShellListCtrl` のインスタンスを追加します。 MFCShellControlsView.h をダブルクリックして、ビューのヘッダー ファイルを開き、**ソリューション エクスプ ローラー**します。

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

2. **MFC アプリケーション ウィザード**既に作成されて、`CMFCShellTreeCtrl`オブジェクト、`CMainFrame`クラスが、保護されたメンバーであります。 後で、このオブジェクトにアクセスします。 したがって、ここでアクセサーを作成します。 ダブルクリックして、MainFrm.h ヘッダー ファイルを開き、**ソリューション エクスプ ローラー**します。 次のコメントを探します。

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

3. 更新、`CMFCShellControlsView`を処理するクラス、 **WM_CREATE** windows メッセージ。 MFCShellControlsView.h ヘッダー ファイルを開き、次のコード行をクリックします。

    ```cpp
    class CMFCShellControlsView : public CView
    ```

   次に、**プロパティ**ウィンドウで、をクリックして、**メッセージ**アイコン。 表示されるまで下にスクロール、 **WM_CREATE**メッセージ。 横のリスト ドロップダウンから**WM_CREATE**、 **\<追加 > OnCreate**します。 これにより、メッセージ ハンドラーが作成され、MFC メッセージ マップが自動的に更新されます。

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

4. 前の手順を繰り返しますが、 **WM_SIZE**メッセージ。 これにより、ユーザーがアプリケーション ウィンドウのサイズを変更するたびにアプリケーションのビューが再描画されるようになります。 `OnSize` メソッドの定義を次のコードに置き換えます。

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

5. 最後の手順が接続するには、`CMFCShellTreeCtrl`と`CMFCShellListCtrl`オブジェクトを使用して、 [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist)メソッド。 このメソッドを呼び出すと、`CMFCShellListCtrl` で選択された項目の内容が自動的に `CMFCShellTreeCtrl` に表示されます。 行いますが、`OnActivateView`からオーバーライドされるメソッドは、 [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview)します。

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

6. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションを構築する、**ビルド**メニューの **ソリューションのビルド**します。 場合は、アプリケーションが正常にビルド、実行を選択して**デバッグの開始**から、**デバッグ**メニュー。

   `CMFCShellTreeCtrl` で選択されている項目の詳細が、ビュー ペインに表示されるようになりました。 `CMFCShellTreeCtrl` でノードをクリックすると、`CMFCShellListCtrl` が自動的に更新されます。 また、`CMFCShellListCtrl` でフォルダーをダブルクリックすると、`CMFCShellTreeCtrl` が自動的に更新されます。

   ツリー コントロールまたはリスト コントロールの任意の項目を右クリックします。 ファイル エクスプローラーを使用している場合と同じようなコンテキスト メニューが表示されます。

## <a name="next-steps"></a>次の手順

- ウィザードでは、両方で Outlook バーが作成された、**フォルダー**ウィンドウと**カレンダー**ウィンドウ。 おそらくは無意味に、**カレンダー**エクスプ ローラー ウィンドウのウィンドウ。 したがって、このペインを削除します。

- `CMFCShellListCtrl`の異なるモードでファイルの表示をサポート**大きいアイコン**、**小さいアイコン**、**一覧**、および**詳細**します。 アプリケーションを更新して、この機能を実装します。 ヒント: を参照してください[Visual C のサンプル](../visual-cpp-samples.md)します。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)  
