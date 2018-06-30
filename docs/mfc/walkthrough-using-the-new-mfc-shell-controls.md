---
title: 'チュートリアル: 新しい MFC を使用してコントロールをシェル |Microsoft ドキュメント'
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
ms.openlocfilehash: eebfc98af109bbcdb0e5c1b3b2b3bf517dd8b076
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122099"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>チュートリアル : 新しい MFC シェル コントロールの使用

このチュートリアルでは、ファイル エクスプローラーのような外観のアプリケーションを作成します。 ここでは、2 つのペインのあるウィンドウを作成します。 左側のウィンドウには、 [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md)を階層ビューで、デスクトップを表示するオブジェクト。 右側のペインには、 [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md)左側のペインで選択されているフォルダー内のファイルを表示します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを設定することが前提としています。[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]を使用する**全般的な開発設定**です。 別の開発設定を使用している場合は、このチュートリアルで使用する一部の [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ウィンドウが既定で表示されないことがあります。

### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードを使用して新しい MFC アプリケーションを作成するには

1. 使用して、 **MFC アプリケーション ウィザード**新しい MFC アプリケーションを作成します。 ウィザードを実行する、**ファイル**メニュー選択**新規**、し、**プロジェクト**です。 **新しいプロジェクト** ダイアログ ボックスが表示されます。

2. **新しいプロジェクト** ダイアログ ボックスで、展開、 **Visual C**内のノード、**プロジェクトの種類**ペイン**MFC**です。 次に、**テンプレート**ペインで、 **MFC アプリケーション**です。 プロジェクトの名前を入力します。 `MFCShellControls`  をクリック**OK**です。 **MFC アプリケーション ウィザード**が表示されます。

3. **MFC アプリケーション ウィザード**ダイアログ ボックスで、をクリックして**次**です。 **アプリケーションの種類**ウィンドウが表示されます。

4. **アプリケーションの種類**ペイン、下にある**アプリケーションの種類**チェック ボックスをオフ、**タブ付きドキュメント**オプション。 次に、選択**1 つのドキュメント**選択**ドキュメント/ビュー アーキテクチャ サポート**です。 **スタイルをプロジェクト** **Visual Studio**との間、 **Visual スタイルと色**ドロップ ダウン リストを**Office 2007 (青のテーマ)**. その他のオプションはそのままにします。 をクリックして**次**を表示する、**複合ドキュメント サポート**ウィンドウです。

5. **複合ドキュメント サポート**ペインで、 **None**です。 をクリックして**次**を表示する、**ドキュメント テンプレート文字列**ウィンドウです。

6. 変更を加えないで、**ドキュメント テンプレート文字列**ウィンドウです。 をクリックして**次**を表示する、**データベース サポート**ウィンドウです。

7. **データベース サポート**ペインで、 **None**このアプリケーションは、データベースが使用されないためです。 をクリックして**次**を表示する、**ユーザー インターフェイスの機能**ウィンドウです。

8. **ユーザー インターフェイス機能** ウィンドウで、ことを確認して、**メニュー バーとツールバーを使用して**オプションを選択します。 その他のオプションはそのままにします。 をクリックして**次**を表示する、**高度な機能**ウィンドウです。

9. **高度な機能**ペイン、下にある**拡張機能**、のみを選択**ActiveX コントロール**と**コモン コントロール マニフェスト**です。 **フレーム ペインを高度な**、のみを選択、**ナビゲーション ウィンドウ**オプション。 これにより、ウィンドウの左側に、`CMFCShellTreeCtrl` が埋め込まれた状態でナビゲーション ウィンドウが作成されます。 をクリックして**次**を表示する、**生成されたクラス**ウィンドウです。

10. 何も変更しようとしていない、**生成されたクラス**ウィンドウです。 したがってをクリックして**完了**新しい MFC プロジェクトを作成します。

11. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションを構築する、**ビルド**メニュー選択**ソリューションのビルド**です。 アプリケーションが正常にビルドされたアプリケーションを実行 を選択して**デバッグの開始**から、**デバッグ**メニュー。

   ウィザードのウィンドウの左側に標準のメニュー バー、標準ツールバー、標準ステータス バー、および Outlook バーを持つアプリケーションを自動的に作成する、**フォルダー**ビューおよび**カレンダー**ビュー.

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>シェル リスト コントロールをドキュメント ビューに追加するには

1. ここでは、ウィザードによって作成されたビューに `CMFCShellListCtrl` のインスタンスを追加します。 ビュー ヘッダー ファイルを開くで MFCShellControlsView.h をダブルクリックすると、**ソリューション エクスプ ローラー**です。

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

2. **MFC アプリケーション ウィザード**既に作成されて、`CMFCShellTreeCtrl`内のオブジェクト、`CMainFrame`クラスが保護されたメンバー。 後で、このオブジェクトにアクセスします。 したがって、ここでアクセサーを作成します。 ダブルクリックしてで MainFrm.h ヘッダー ファイルを開き、**ソリューション エクスプ ローラー**です。 次のコメントを探します。

   ```cpp
   // Attributes
   ```

   この直後に、次のメソッド宣言を追加します。

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   次をダブルクリックしてで MainFrm.cpp ソース ファイルを開く、**ソリューション エクスプ ローラー**です。 このファイルの末尾に、次のメソッド定義を追加します。

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

   次に、**プロパティ**ウィンドウで、をクリックして、**メッセージ**アイコン。 見つかるまで下へスクロール、 **WM_CREATE**メッセージ。 ドロップダウン リストに**WM_CREATE** **\<追加 > OnCreate**です。 これにより、メッセージ ハンドラーが作成され、MFC メッセージ マップが自動的に更新されます。

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

5. 最後の手順が接続するには、`CMFCShellTreeCtrl`と`CMFCShellListCtrl`オブジェクトを使用して、 [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist)メソッドです。 このメソッドを呼び出すと、`CMFCShellListCtrl` で選択された項目の内容が自動的に `CMFCShellTreeCtrl` に表示されます。 この作業を行うは、`OnActivateView`からは、オーバーライドするメソッド[CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview)です。

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

6. アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションを構築する、**ビルド**メニュー選択**ソリューションのビルド**です。 アプリケーションが正常にビルドされた場合は実行を選択して**デバッグの開始**から、**デバッグ**メニュー。

   `CMFCShellTreeCtrl` で選択されている項目の詳細が、ビュー ペインに表示されるようになりました。 `CMFCShellTreeCtrl` でノードをクリックすると、`CMFCShellListCtrl` が自動的に更新されます。 また、`CMFCShellListCtrl` でフォルダーをダブルクリックすると、`CMFCShellTreeCtrl` が自動的に更新されます。

   ツリー コントロールまたはリスト コントロールの任意の項目を右クリックします。 ファイル エクスプローラーを使用している場合と同じようなコンテキスト メニューが表示されます。

## <a name="next-steps"></a>次の手順

- ウィザードでは、両方のある Outlook バーが作成された、**フォルダー**ペインおよび**カレンダー**ウィンドウです。 おそらくは言えませんがなければ意味、**カレンダー**エクスプ ローラー ウィンドウ内のウィンドウ。 したがって、このペインを削除します。

- `CMFCShellListCtrl`などさまざまなモードでファイルを表示をサポート**大きいアイコン**、**小さいアイコン**、**リスト**、および**詳細**です。 アプリケーションを更新して、この機能を実装します。 ヒント: を参照してください[Visual C のサンプル](../visual-cpp-samples.md)です。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)  
