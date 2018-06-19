---
title: アプリケーションの種類、MFC アプリケーション ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.apptype
dev_langs:
- C++
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5708e823c57ecdb8470a398c4192cba1a5b6e411
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353440"
---
# <a name="application-type-mfc-application-wizard"></a>[アプリケーションの種類] \(MFC アプリケーション ウィザード)
このページを使用して、 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)を設計して新しい MFC アプリケーションへの基本的な機能を追加します。  
  
 **アプリケーションの種類**  
 アプリケーションで作成するドキュメントのサポートの種類を指定します。 選択したアプリケーションの種類では、アプリケーションで使用できるユーザー インターフェイスのオプションを決定します。 参照してください[ユーザー インターフェイスの機能、MFC アプリケーション ウィザード](../../mfc/reference/user-interface-features-mfc-application-wizard.md)詳細についてはします。  
  
 ドキュメントの種類の詳細についてを参照してください。  
  
-   [SDI と MDI](../../mfc/sdi-and-mdi.md)  
  
-   [フレーム ウィンドウ](../../mfc/frame-windows.md)  
  
-   [フレーム ウィンドウ クラス](../../mfc/frame-window-classes.md)  
  
-   [ドキュメント、ビュー、フレームワーク](../../mfc/documents-views-and-the-framework.md)  
  
-   [ダイアログ ボックス](../../mfc/dialog-boxes.md)  
  
|オプション|説明|  
|------------|-----------------|  
|**1 つのドキュメント**|ビュー クラスがに基づいては、アプリケーションのシングル ドキュメント インターフェイス (SDI) アーキテクチャを作成[CView クラス](../../mfc/reference/cview-class.md)です。 ビューの基底クラスを変更することができます、[生成されたクラス、MFC アプリケーション ウィザード](../../mfc/reference/generated-classes-mfc-application-wizard.md)ウィザードのページです。 たとえば、フォーム ベースのアプリケーションを作成するを使用して[CFormView クラス](../../mfc/reference/cformview-class.md)ビュー クラスです。<br /><br /> この種のアプリケーションでは、ドキュメントのフレーム ウィンドウは、1 つだけのドキュメントを保持できます。|  
|**複数のドキュメント**|ビュー クラスがに基づいては、アプリケーションの複数ドキュメント インターフェイス (MDI) アーキテクチャを作成`CView`です。 ビューの基底クラスを変更することができます、**生成されたクラス**ウィザードのページです。 たとえば、フォーム ベースのアプリケーションを作成するを使用して`CFormView`ビュー クラスです。<br /><br /> この種のアプリケーションでは、ドキュメントのフレーム ウィンドウできます複数子ウィンドウを保持します。|  
|**タブ付きドキュメント**|別のタブには、各ドキュメントを配置します。|  
|**ダイアログ ベース**|ダイアログ クラスがに基づいて、アプリケーションのダイアログ ベースのアーキテクチャを作成`CDialog`です。 (HTML ダイアログを作成するには、ボックスをオン**を使用して HTML ダイアログ**)。|  
|**HTML ダイアログを使用します。**|ダイアログ ボックスでアプリケーションの場合のみ ダイアログ クラスから派生した[CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)の代わりに[CDialog クラス](../../mfc/reference/cdialog-class.md)です。 このボックスをチェックする場合`CDHtmlDialog`に記載されて、**基底クラス**ボックスに、[生成されたクラス、MFC アプリケーション ウィザード](../../mfc/reference/generated-classes-mfc-application-wizard.md)ウィザードのページです。<br /><br /> A `CDHtmlDialog`-派生 ダイアログ ボックスには、HTML ベースのダイアログ ボックスが表示されます、HTML を使用して交換データを制御し、HTML のイベントを処理します。|  
|**複数のトップレベル ドキュメント**|ビュー クラスがに基づいては、アプリケーションの複数の最上位レベル アーキテクチャを作成`CView`です。<br /><br /> この種のアプリケーション、ユーザーがクリックしたときに**新規**(または**新しいフレーム**) で、**ファイル**] メニューの [アプリケーションがその親は、デスクトップでは暗黙的にウィンドウを作成します。 新しいドキュメント フレームは、タスク バーに表示され、アプリケーション ウィンドウのクライアント領域に限定されません。|  
  
 **ドキュメント/ビュー アーキテクチャのサポート**  
 使用して、アプリケーションのドキュメント/ビュー アーキテクチャを含めるかどうかを指定します、 [CDocument クラス](../../mfc/reference/cdocument-class.md)と[CView クラス](../../mfc/reference/cview-class.md)(既定値)。 非 MFC アプリケーションを移植する場合、またはコンパイル済み実行可能ファイルのサイズを小さく場合は、このチェック ボックスをオフにします。 既定では、ドキュメント/ビュー アーキテクチャを備えていないアプリケーションはから派生[CWinApp クラス](../../mfc/reference/cwinapp-class.md)、というディスク ファイルからドキュメントを開くために MFC サポートは含まれません。  
  
 **リソース言語**  
 リソースの言語を設定します。 一覧は、Visual Studio がインストールされている、システムで使用できる言語を表示します。 システムの言語以外の言語を選択する場合は、その言語の適切なテンプレート フォルダーがインストール既に必要があります。 言語リソースの使用可能な既定値から別のインストールの詳細については、**リソース言語**一覧を参照してください[ウィザードでサポートされるその他の言語](../../ide/wizard-support-for-other-languages.md)します。  
  
 選択した言語に反映されます、**ローカライズ文字列**のオプション、[ドキュメント テンプレート文字列、MFC アプリケーション ウィザード](../../mfc/reference/document-template-strings-mfc-application-wizard.md)ウィザードのページです。  
  
 **Unicode ライブラリを使用します。**  
 Unicode または非 Unicode のバージョンの MFC ライブラリを使用するかどうかを指定します。  
  
 **プロジェクト形式**  
 アプリケーションが、標準 MFC、ファイル エクスプ ローラー、Visual Studio、または Office アーキテクチャおよび表示するかどうかを示します。 詳細については、次を参照してください。[ファイル エクスプ ローラー スタイルの MFC アプリケーションを作成する](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)です。  
  
|オプション|説明|  
|------------|-----------------|  
|**MFC の標準**|標準の MFC アプリケーション アーキテクチャを提供します。|  
|**ファイル エクスプ ローラー**|ここで、左側のペインは分割ウィンドウを使用して、ファイル エクスプ ローラーのようなアプリケーションを実装して、 [CTreeView クラス](../../mfc/reference/ctreeview-class.md)し、右側のウィンドウは、 [CListView クラス](../../mfc/reference/clistview-class.md)です。|  
|**Visual Studio**|次の 4 つのドッキング可能なペインを含む Visual Studio のようなアプリケーションを実装する (**ファイル ビュー**、**クラス ビュー**、**プロパティ**、および**出力**) から派生した[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)から派生したメイン フレーム ウィンドウと[CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)(既定値)。|  
|**Office**|派生するリボンを含む Office のようなアプリケーションを実装する[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)から派生した Outlook バー [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)から派生したキャプション バー[CMFCCaptionBar クラス](../../mfc/reference/cmfccaptionbar-class.md)、およびメイン フレームから派生した[CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)です。|  
  
 **Visual スタイルと色**  
 アプリケーションの visual スタイルを決定します。 次のオプションを使用できます。  
  
-   **Windows ネイティブ/既定**  
  
-   **Office 2003**  
  
-   **Visual Studio 2005**  
  
-   **Office 2007 (青のテーマ)**  
  
-   **Office 2007 (黒のテーマ)**  
  
-   **Office 2007 (銀色のテーマ)**  
  
-   **Office 2007 (水色のテーマ)**  
  
 **Visual スタイルの切り替えを有効にします。**  
 かどうか、ユーザーことができます、視覚スタイルを変更、実行時にアプリケーションの通常メニューまたはリボンから適切な visual スタイルを選択して、指定します。  
  
 **MFC の使用**  
 MFC ライブラリにリンクする方法を指定します。 既定では、MFC は、共有 DLL としてリンクされます。  
  
|オプション|説明|  
|------------|-----------------|  
|**共有 DLL で MFC を使用します。**|MFC ライブラリを共有 DLL としてアプリケーションにリンクします。 アプリケーションは、実行時に、MFC ライブラリへの呼び出しをによりします。 このオプションは、MFC ライブラリを使用する複数の実行可能ファイルで構成されるアプリケーションのディスクとメモリの量を削減します。 Win32 と MFC の両方のアプリケーションが DLL (既定値) の関数を呼び出すことができます。|  
|**スタティック ライブラリで MFC を使用します。**|ビルド時に、MFC のスタティック ライブラリをアプリケーションにリンクします。|  
  
## <a name="see-also"></a>関連項目  
 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)   
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../../ide/file-types-created-for-visual-cpp-projects.md)

