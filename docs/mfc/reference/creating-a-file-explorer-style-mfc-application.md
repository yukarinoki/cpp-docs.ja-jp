---
description: 詳細については、「MFC アプリケーション Explorer-Style ファイルの作成」を参照してください。
title: エクスプローラー形式の MFC アプリケーションの作成
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcexplorer.project
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
ms.openlocfilehash: 9419aae58cf34ec70585b952360cb12702424381
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301322"
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>エクスプローラー形式の MFC アプリケーションの作成

多くの Windows システムアプリケーションでは、エクスプローラー用のユーザーインターフェイス (UI) が使用されています。 たとえば、エクスプローラーを起動すると、クライアント領域を分割する垂直分割バーを持つアプリケーションが表示されます。 クライアント領域の左側にナビゲーション機能と参照機能が用意されています。また、[クライアント] 領域の右側には、左側のウィンドウでの選択に関連する詳細が表示されます。 ユーザーが左側のウィンドウで項目をクリックすると、アプリケーションが右ペインを再表示します。 MDI アプリケーションでは、[ **表示** ] メニューのコマンドを使用して、右ペインに表示される詳細の量を変更できます。 (SDI または複数のトップレベルドキュメントアプリケーションでは、ツールバーのボタンのみを使用して詳細を変更できます)。

ウィンドウの内容は、アプリケーションによって異なります。 ファイルシステムのブラウザーでは、左側のウィンドウには、ディレクトリ、コンピューター、またはコンピューターグループの階層ビューが表示されます。右側のウィンドウには、フォルダー、個々のファイル、またはコンピューターが表示されます。 コンテンツは必ずしもファイルである必要はありません。 これらは、電子メールメッセージ、エラーレポート、またはデータベース内のその他のアイテムである可能性があります。

ウィザードでは、次のクラスが作成されます。

- クラスは、 `CLeftView` クライアント領域の左側のペインを定義します。 常に [CTreeView](../../mfc/reference/ctreeview-class.md)から派生します。

- C *ProjName* View クラスは、クライアント領域の右ペインを定義します。 既定では、 [CListView](../../mfc/reference/clistview-class.md)から派生しますが、ウィザードの [[生成さ](../../mfc/reference/generated-classes-mfc-application-wizard.md)れたクラス] ページの [**基底クラス**] ボックスの一覧から指定したクラスに応じて、別の種類のビューを使用できます。

生成されたアプリケーションは、シングルドキュメントインターフェイス (SDI)、マルチドキュメントインターフェイス (MDI)、または複数のトップレベルドキュメントアーキテクチャを持つことができます。 アプリケーションが作成する各フレームウィンドウは、 [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)を使用して垂直方向に分割されます。 このアプリケーションの種類のコーディングは、スプリッターを使用する通常の MFC アプリケーションのコーディングに似ています。ただし、この種類のアプリケーションでは、分割ペイン内に個別のコントロールビューが用意されています。

右側のペインで既定のリストビューを使用すると、ウィザードによって追加のメニューオプション (MDI アプリケーションの場合のみ) と、ビューのスタイルを大きなアイコン、小さいアイコン、リスト、詳細モードに切り替えるためのツールバーボタンが作成されます。

### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>エクスプローラー形式の MFC 実行可能ファイルの作成を開始するには

1. 「 [MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)」の指示に従います。

1. MFC アプリケーションウィザードの [ [アプリケーションの種類](../../mfc/reference/application-type-mfc-application-wizard.md) ] ページで、 **エクスプローラー** のプロジェクトスタイルを選択します。

1. ウィザードの他のページで必要なその他のオプションを設定します。

1. [ **完了** ] をクリックして、スケルトンアプリケーションを生成します。

詳細については、次を参照してください。

- [複数のドキュメントタイプ、ビュー、フレームウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)

- [MFC で使用できる派生ビュー クラス](../../mfc/derived-view-classes-available-in-mfc.md)

- [アプリケーション設計の選択肢](../../mfc/application-design-choices.md)

## <a name="see-also"></a>関連項目

[MFC アプリケーションウィザード](../../mfc/reference/mfc-application-wizard.md)<br/>
[Web Browser-Style MFC アプリケーションの作成](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)<br/>
[Forms-Based MFC アプリケーションの作成](../../mfc/reference/creating-a-forms-based-mfc-application.md)
