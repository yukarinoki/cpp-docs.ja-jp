---
title: フォーム ベースの MFC アプリケーションの作成
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcforms.project
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
ms.openlocfilehash: 6810a6c7fce91865a92d048129da29305e22abc1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291250"
---
# <a name="creating-a-forms-based-mfc-application"></a>フォーム ベースの MFC アプリケーションの作成

フォームとは、ユーザーがデータのアクセスや変更に使用できる、コントロール付きのダイアログ ボックスです。 フォームをユーザーが選択できるアプリケーションを開発することもできます。 一般的には、フォーム ベースのアプリケーションにより、ユーザーのアクセス フォームのクリックによって**新規**から、**ファイル**メニュー。 ユーザーへのアクセスを許可しないはダイアログ ベースのアプリケーション、**新規**オプション、**ファイル** メニューは、フォーム ベースのアプリケーションもと見なされます。

シングル ドキュメント インターフェイス (SDI: Single Document Interface) のフォーム ベースのアプリケーションでは、一度に実行できるフォームのインスタンスは 1 つだけです。 新しいフォームを選択して、SDI フォーム ベースのアプリケーションから同時にさまざまなフォームを実行することは、**新規**オプション、**ファイル**メニュー。

マルチ ドキュメント インターフェイス (MDI: Multiple Document Interface) のフォーム ベースのアプリケーションを作成すると、同一フォームの複数のインスタンスをアプリケーションでサポートできます。

マルチ トップレベル ドキュメントをサポートするアプリケーションを作成すると、デスクトップがそのドキュメントの暗黙の親となり、ドキュメントのフレームがアプリケーションのクライアント領域に限定されることはありません。 ドキュメントの複数のインスタンスを開くことができます。各インスタンスにはフレーム、メニュー、タスク バー アイコンが含まれます。 選択した場合は、ドキュメントの後続のインスタンスを個別に閉じることができます、**終了**オプションを**ファイル** メニューの最初のインスタンスでは、アプリケーションのすべてのインスタンスを閉じます。

SDI、MDI、およびマルチ トップレベル ドキュメント アプリケーションはすべてフォーム ベースであり、ドキュメント/ビュー アーキテクチャを使用します。

定義上は、ダイアログ ベースのアプリケーションもすべてフォーム ベースになります。 ダイアログ ベースのアプリケーションでは、ドキュメント/ビュー アーキテクチャが使用されないため、独自の追加フォームの作成およびそのアクセス方法は自分で管理する必要があります。

フォーム ベースのアプリケーションの基本クラスは[CFormView](../../mfc/reference/cformview-class.md)します。 アプリケーションでデータベースをサポートする場合は、`CFormView` の任意の派生クラスも選択できます。 フォームとは、`CFormView` から派生するウィンドウ、または `CFormView` から継承されたクラスから派生するウィンドウです。

基本クラスを使用する場合でも[CView](../../mfc/reference/cview-class.md)、行うことができます後で、アプリケーションでフォームに基づく[MFC クラスの追加](../../mfc/reference/adding-an-mfc-class.md)から派生した`CFormView`とチェック、**ドキュメント テンプレートの生成リソース**でチェック ボックスをオン、 [MFC クラス ウィザード](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md)します。

ウィザードを終了するとプロジェクトが開きます。基底クラスとして `CFormView` (または `CFormView` から継承されたクラス) を選択した場合、あるいはダイアログ ベースのアプリケーションを作成した場合は、Visual C++ によってダイアログ エディターが開かれます。 これで最初のフォームをデザインする準備が整いました。

### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>フォーム ベースの MFC アプリケーションの作成を開始するには

1. 指示に従って[MFC アプリケーションを作成する](../../mfc/reference/creating-an-mfc-application.md)します。

1. MFC アプリケーション ウィザードで[アプリケーションの種類](../../mfc/reference/application-type-mfc-application-wizard.md)] ページで、[、**ドキュメント/ビュー アーキテクチャ サポート**チェック ボックスをオンします。

1. 選択**1 つのドキュメント**、**複数のドキュメント**、または**複数のトップレベル ドキュメント**します。

    > [!NOTE]
    >  既定では、SDI、MDI、または複数のトップレベル ドキュメント インターフェイス アプリケーションを選択した場合`CView`で、アプリケーションのビューの基底クラスとして設定されて、[生成されたクラス](../../mfc/reference/generated-classes-mfc-application-wizard.md)ウィザードのページ。 フォーム ベースのアプリケーションを作成するには、アプリケーションのビューの基底クラスとして `CFormView` を選択する必要があります。 ウィザードは、フォーム ベースのアプリケーションの印刷はサポートしていません。

1. ウィザードのその他のページで、必要なプロジェクト オプションを設定します。

1. クリックして**完了**スケルトン アプリケーションを生成します。

詳細については次を参照してください:

- [派生ビュー クラス](../../mfc/derived-view-classes-available-in-mfc.md)

- [ドキュメント/ビュー アーキテクチャの代替手段](../../mfc/alternatives-to-the-document-view-architecture.md)

- [アプリケーションのデザイン上の検討事項](../../mfc/application-design-choices.md)

## <a name="see-also"></a>関連項目

[MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)<br/>
[フォーム ビュー](../../mfc/form-views-mfc.md)<br/>
[エクスプローラー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)<br/>
[Web ブラウザー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)
