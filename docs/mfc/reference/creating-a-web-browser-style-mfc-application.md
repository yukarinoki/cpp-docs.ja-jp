---
description: 詳細については、「Web Browser-Style MFC アプリケーションの作成」を参照してください。
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
ms.openlocfilehash: 0ee8250be20b53979c2a3e059d83237389091e72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301283"
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Web ブラウザー形式の MFC アプリケーションの作成

Web ブラウザースタイルのアプリケーションは、インターネット (HTML や active ドキュメントなど)、イントラネット、およびローカルファイルシステムおよびネットワーク上のフォルダーから情報にアクセスできます。 アプリケーションのビュークラスを [CHtmlView](../../mfc/reference/chtmlview-class.md)から派生させることにより、ビューに WebBrowser コントロールを提供することで、アプリケーションを Web ブラウザーにすることができます。

## <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC のドキュメント/ビューアーキテクチャに基づいて Web ブラウザーアプリケーションを作成するには

1. 「 [MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)」の指示に従います。

1. MFC アプリケーションウィザードの [ [アプリケーションの種類](../../mfc/reference/application-type-mfc-application-wizard.md) ] ページで、[ **ドキュメント/ビューアーキテクチャ** ] ボックスが選択されていることを確認します。 ( **1 つのドキュメント** または **複数のドキュメント** を選択できますが、 **ダイアログベース** では選択できません)。

1. [ [生成されたクラスの確認](../../mfc/reference/generated-classes-mfc-application-wizard.md) ] ページで、[ **基本クラス** ] ドロップダウンメニューを使用してを選択し `CHtmlView` ます。

1. スケルトンアプリケーションに組み込むその他のオプションを選択します。

1. **[完了]** をクリックします。

WebBrowser コントロールは、ハイパーリンクを使用した Web 閲覧と Uniform Resource Locator (URL) のナビゲーションをサポートしています。 このコントロールは、ユーザーが以前に参照したサイト、フォルダー、およびドキュメントを前方または後方に参照できるようにする、履歴リストを保持します。 コントロールは、ナビゲーション、ハイパーリンク、履歴リスト、お気に入り、およびセキュリティを直接処理します。 アプリケーションは、WebBrowser コントロールをアクティブドキュメントコンテナーとして使用して、アクティブドキュメントもホストできます。 そのため、Microsoft Excel スプレッドシートや Word 文書などの高度に書式設定されたドキュメントを WebBrowser コントロール内から開いて編集できます。 また、WebBrowser コントロールは、activex コントロールをホストできる ActiveX コントロールコンテナーでもあります。

> [!NOTE]
> WebBrowser ActiveX コントロール (および `CHtmlView` ) は、Internet Explorer 4.0 以降がインストールされている Windows バージョンで実行されているアプリケーションに対してのみ使用できます。

`CHtmlView`は単に Microsoft Web ブラウザーコントロールを実装しているため、印刷のサポートは、他の[CView](../../mfc/reference/cview-class.md)派生クラスとは同じではありません。 代わりに、WebBrowser コントロールは、プリンターのユーザーインターフェイスと印刷を実装します。 このため、 `CHtmlView` は印刷プレビューをサポートしていません。また、他の MFC アプリケーションで使用できる、 [cview:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)、 [cview:: OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)、および [cview:: OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)などの他の印刷サポート機能を提供しません。

`CHtmlView` web ブラウザーコントロールのラッパーとして機能します。これにより、アプリケーションは Web ページまたは HTML ページにビューが表示されます。 このウィザードでは、view クラスの [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) 関数のオーバーライドを作成し、Microsoft Visual C++ の Web サイトへのナビゲーションリンクを提供します。

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

このサイトは、独自のものに置き換えることも、 [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) メンバー関数を使用して、プロジェクトのリソーススクリプトに存在する HTML ページをビューの既定のコンテンツとして開くこともできます。 次に例を示します。

```cpp
void CWebView::OnInitialUpdate()
{
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.
    LoadFromResource(IDR_HTML1);
}
```

## <a name="see-also"></a>関連項目

[MFC サンプル MFCIE](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/internet)<br/>
[MFC アプリケーションウィザード](../../mfc/reference/mfc-application-wizard.md)<br/>
[コンパイラとビルドのプロパティの設定](../../build/working-with-project-properties.md)<br/>
[[プロパティ ページ]](../../build/reference/property-pages-visual-cpp.md)<br/>
[コンパイラとビルドのプロパティの設定](../../build/working-with-project-properties.md)
