---
title: Web ブラウザー スタイルの MFC アプリケーションの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcweb.project
dev_langs:
- C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1553f7ccc3b22b4e3d76d8c49d94ba2a61c19e97
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122554"
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Web ブラウザー形式の MFC アプリケーションの作成
ネットワークとローカル ファイル システムで Web ブラウザー形式のアプリケーション (HTML またはアクティブ ドキュメント) など、インターネットまたはイントラネットでは、フォルダーから情報にアクセスできます。 アプリケーションのビュー クラスから派生することによって[CHtmlView](../../mfc/reference/chtmlview-class.md)、効果的に WebBrowser コントロールと、ビューを提供することで Web ブラウザー アプリケーションを作成します。  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC ドキュメント/ビュー アーキテクチャに基づいて、Web ブラウザー アプリケーションを作成するには  
  
1.  指示に従い[MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)です。  
  
2.  MFC アプリケーション ウィザードで[アプリケーションの種類](../../mfc/reference/application-type-mfc-application-wizard.md) ページであることを確認、**ドキュメント/ビュー アーキテクチャ**ボックスがオンにします。 (いずれかを選択することができます**1 つのドキュメント**または**複数ドキュメント**、ではなく**ダイアログ ベース**)。  
  
3.  [生成されたクラス](../../mfc/reference/generated-classes-mfc-application-wizard.md) ページで、使用して、**基底クラス**を選択するドロップダウン メニュー`CHtmlView`です。  
  
4.  その他のオプションをスケルトン アプリケーションに組み込まれているを選択します。  
  
5.  **[完了]** をクリックします。  
  
 WebBrowser コントロールは、ハイパーリンクと Uniform Resource Locator (URL) ナビゲーションを通じて Web サイトの参照をサポートします。 コントロールがユーザーが前後に参照できる履歴一覧を保持しを旧バージョンと以前に参照したサイト、フォルダー、およびドキュメント。 コントロールは、ナビゲーション、ハイパーリンク、履歴の一覧、お気に入り、およびセキュリティに直接処理します。 アプリケーションは、ホストのアクティブなドキュメントもへの active ドキュメント コンテナーとして WebBrowser コントロールを使用できます。 したがって、表現力豊かな書式設定された Microsoft Excel スプレッドシートなどまたは Word のドキュメントを開くおよび編集できますから WebBrowser コントロール内で。 WebBrowser コントロールが ActiveX コントロールをホストできる ActiveX コントロール コンテナーもできます。  
  
> [!NOTE]
>  WebBrowser ActiveX コントロール (および`CHtmlView`) 以降がインストールされているか Internet Explorer 4.0 でのバージョンの Windows で実行されるアプリケーションにのみ使用できます。  
  
 `CHtmlView`だけ印刷が他のマイクロソフトの Web ブラウザー コントロールのサポートを実装[CView](../../mfc/reference/cview-class.md)-クラスを派生します。 代わりに、WebBrowser コントロールは、印刷、プリンターのユーザー インターフェイスを実装します。 その結果、`CHtmlView`は印刷プレビューをサポートしていないと、フレームワークは他の印刷のサポート機能を提供しません: たとえば、[き](../../mfc/reference/cview-class.md#onprepareprinting)、[値](../../mfc/reference/cview-class.md#onbeginprinting)、および[CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)、他の MFC アプリケーションで使用可能な。  
  
 `CHtmlView` で、アプリケーションを Web または HTML ページに表示する、Web ブラウザー コントロール用のラッパーとして機能します。 ウィザードでの上書きを作成、[フィルターと並べ替え順序](../../mfc/reference/cview-class.md#oninitialupdate)Microsoft Visual C の Web サイトへのナビゲーション リンクを提供するビュー クラスの関数。  
  
```cpp
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.  
    Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),
        NULL,
        NULL);
}
```

このサイトは、独自のいずれかで置き換えることができますか、使用して、 [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource)メンバー関数、ビューの既定のコンテンツとして、プロジェクトのリソース スクリプトに存在する HTML ページを開きます。 例えば:  
  
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
 [MFC サンプル MFCIE](http://msdn.microsoft.com/en-us/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)   
 [プロジェクトのプロパティの使用](../../ide/working-with-project-properties.md)   
 [プロパティ ページ](../../ide/property-pages-visual-cpp.md)   
 [プロジェクトのプロパティの使用](../../ide/working-with-project-properties.md)   
 [アプリケーションの配置](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

