---
title: ファイル エクスプ ローラー スタイルの MFC アプリケーションの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcexplorer.project
dev_langs:
- C++
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5b0f5d4bdabc987d4f4177f616ce756c351b8b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>エクスプローラー形式の MFC アプリケーションの作成
多くの Windows システム アプリケーションは、ファイル エクスプ ローラーのユーザー インターフェイス (UI) を使用します。 ファイル エクスプ ローラーを開始するときになど、表示、垂直方向に分割分割バー クライアント領域を持つアプリケーション。 クライアント領域の左側にあるナビゲーションと参照の機能を提供し、クライアント領域の右側にある詳細が表示されます、選択範囲を左ペインでします。 ユーザーには、左側のウィンドウ内の項目がクリックすると、アプリケーションには、右側のウィンドウが再作成されます。 MDI アプリケーションでのコマンドを使用することができます、**ビュー**  メニューの右側のウィンドウに表示される詳細情報の量を変更します。 (SDI またはマルチ トップレベル ドキュメント アプリケーションでは、ツールバーのボタンのみを使用して詳細を変更できます)。  
  
 ペインの内容は、アプリケーションによって異なります。 ブラウザーで、ファイル システムは、左側のウィンドウは、フォルダー、個々 のファイルまたはマシン、および詳細が右のペインが表示されている間にディレクトリ、コンピューター、またはコンピューター グループの階層ビューを示します。 内容は必ずしもありませんファイルであります。 これらは、電子メール メッセージ、エラー レポート、またはその他のデータベースのアイテムで、可能性があります。  
  
 ウィザードでは、次のクラスを作成します。  
  
-   **CLeftView**クラスは、クライアント領域の左側のウィンドウを定義します。 常に由来[CTreeView](../../mfc/reference/ctreeview-class.md)です。  
  
-   C*ProjName*ビュー クラスがクライアント領域の右側のウィンドウを定義します。 既定では、派生は[CListView](../../mfc/reference/clistview-class.md)から指定したクラスによってビューの他の種類を指定できますが、**基底クラス**一覧に、[生成されたクラス](../../mfc/reference/generated-classes-mfc-application-wizard.md)のページ、ウィザード。  
  
 生成されたアプリケーションには、シングル ドキュメント インターフェイス (SDI)、マルチ ドキュメント インターフェイス (MDI)、または複数の最上位のドキュメントのアーキテクチャを持つことができます。 使用して、アプリケーションを作成各フレーム ウィンドウが垂直方向に分割[CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)です。 このアプリケーションの種類をコーディングすることは、この種類のアプリケーションがある各分割ペイン内の個別のコントロール ビューする点を除いて、スプリッターを使用する標準の MFC アプリケーションをコーディングに似ています。  
  
 右側のウィンドウで既定のリスト ビューを使用する場合、ウィザードは、大きいアイコン、小さいアイコン、リスト、および詳細モード間で、ビューのスタイルを切り替えるには、追加のメニューの選択肢 (MDI アプリケーションの場合のみ) とツール バー ボタンを作成します。  
  
### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>ファイル エクスプ ローラー スタイルの MFC の実行可能ファイルを作成するのには  
  
1.  指示に従い[MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)です。  
  
2.  MFC アプリケーション ウィザードで[アプリケーションの種類](../../mfc/reference/application-type-mfc-application-wizard.md)] ページで、[、**ファイル エクスプ ローラー**プロジェクトのスタイル。  
  
3.  ウィザードの他のページで、希望するその他のオプションを設定します。  
  
4.  をクリックして**完了**スケルトン アプリケーションを生成します。  
  
 詳細については次を参照してください:  
  
-   [複数のドキュメント タイプ、ビュー、フレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [派生ビュー クラス](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [アプリケーションのデザイン上の検討事項](../../mfc/application-design-choices.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)   
 [Web ブラウザー形式の MFC アプリケーションを作成します。](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)   
 [フォーム ベースの MFC アプリケーションの作成](../../mfc/reference/creating-a-forms-based-mfc-application.md)

