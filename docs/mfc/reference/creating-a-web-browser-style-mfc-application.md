---
title: Web ブラウザー形式の MFC アプリケーションの作成
ms.date: 06/25/2018
f1_keywords:
- vc.appwiz.mfcweb.project
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
ms.openlocfilehash: d928d8de34c6caab0f86e9205d0aea45b5ed737c
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079441"
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Web ブラウザー形式の MFC アプリケーションの作成

Web ブラウザースタイルのアプリケーションは、インターネット (HTML や active ドキュメントなど)、イントラネット、およびローカルファイルシステムおよびネットワーク上のフォルダーから情報にアクセスできます。 アプリケーションのビュークラスを[CHtmlView](../../mfc/reference/chtmlview-class.md)から派生させることにより、ビューに WebBrowser コントロールを提供することで、アプリケーションを Web ブラウザーにすることができます。

### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC のドキュメント/ビューアーキテクチャに基づいて Web ブラウザーアプリケーションを作成するには

1. 「 [MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)」の指示に従います。

1. MFC アプリケーションウィザードの [[アプリケーションの種類](../../mfc/reference/application-type-mfc-application-wizard.md)] ページで、 **[ドキュメント/ビューアーキテクチャ]** ボックスが選択されていることを確認します。 ( **1 つのドキュメント**または**複数のドキュメント**を選択できますが、**ダイアログベース**では選択できません)。

1. [[生成されたクラスの確認](../../mfc/reference/generated-classes-mfc-application-wizard.md)] ページで、 **[基本クラス]** ドロップダウンメニューを使用して [`CHtmlView`] を選択します。

1. スケルトンアプリケーションに組み込むその他のオプションを選択します。

1. **[完了]** をクリックします。

WebBrowser コントロールは、ハイパーリンクを使用した Web 閲覧と Uniform Resource Locator (URL) のナビゲーションをサポートしています。 このコントロールは、ユーザーが以前に参照したサイト、フォルダー、およびドキュメントを前方または後方に参照できるようにする、履歴リストを保持します。 コントロールは、ナビゲーション、ハイパーリンク、履歴リスト、お気に入り、およびセキュリティを直接処理します。 アプリケーションは、WebBrowser コントロールをアクティブドキュメントコンテナーとして使用して、アクティブドキュメントもホストできます。 そのため、Microsoft Excel スプレッドシートや Word 文書などの高度に書式設定されたドキュメントを WebBrowser コントロール内から開いて編集できます。 また、WebBrowser コントロールは、activex コントロールをホストできる ActiveX コントロールコンテナーでもあります。

> [!NOTE]
>  WebBrowser ActiveX コントロール (および `CHtmlView`) は、Internet Explorer 4.0 以降がインストールされている Windows バージョンで実行されているアプリケーションに対してのみ使用できます。

`CHtmlView` は Microsoft Web ブラウザーコントロールを実装するだけなので、印刷のサポートは、他の[CView](../../mfc/reference/cview-class.md)派生クラスとは同じではありません。 代わりに、WebBrowser コントロールは、プリンターのユーザーインターフェイスと印刷を実装します。 その結果、`CHtmlView` は印刷プレビューをサポートしておらず、他の MFC アプリケーションで使用できる、 [cview:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)、 [Cview:: OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)、および[cview:: OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)などの他の印刷サポート機能を提供しません。

`CHtmlView` は、web ブラウザーコントロールのラッパーとして機能します。これにより、アプリケーションは Web ページまたは HTML ページにビューが表示されます。 このウィザードでは、view クラスの[OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate)関数のオーバーライドを作成し、Microsoft Visual C++ Web サイトへのナビゲーションリンクを提供します。

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    Navigate2(_T("http://www.docs.microsoft.com/"),
        NULL,
        NULL);
}
```

このサイトは、独自のものに置き換えることも、 [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource)メンバー関数を使用して、プロジェクトのリソーススクリプトに存在する HTML ページをビューの既定のコンテンツとして開くこともできます。 次に例を示します。

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    LoadFromResource(IDR_HTML1);
}
```

## <a name="see-also"></a>参照

[MFC サンプル MFCIE](https://github.com/Microsoft/VCSamples)<br/>
[MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)<br/>
[コンパイラとビルドのプロパティの設定](../../build/working-with-project-properties.md)<br/>
[プロパティ ページ](../../build/reference/property-pages-visual-cpp.md)<br/>
[コンパイラとビルドのプロパティの設定](../../build/working-with-project-properties.md)
