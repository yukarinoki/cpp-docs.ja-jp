---
description: 詳細については、「アプリケーションの種類、MFC アプリケーションウィザード」を参照してください。
title: '[アプリケーションの種類] (MFC アプリケーション ウィザード)'
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.apptype
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
ms.openlocfilehash: 178e9c1319b17e356273fc3e59d2133c8d4aa54c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322786"
---
# <a name="application-type-mfc-application-wizard"></a>[アプリケーションの種類] (MFC アプリケーション ウィザード)

[Mfc アプリケーションウィザード](../../mfc/reference/mfc-application-wizard.md)のこのページを使用すると、基本的な機能をデザインし、新しい mfc アプリケーションに追加できます。

- **アプリケーションの種類**

  アプリケーションで作成するドキュメントサポートの種類を指定します。 アプリケーションで使用できるユーザーインターフェイスオプションは、選択したアプリケーションの種類によって決まります。 詳細については [、「[ユーザーインターフェイスの機能] (MFC アプリケーションウィザード)](../../mfc/reference/user-interface-features-mfc-application-wizard.md) 」を参照してください。

   ドキュメントの種類の詳細については、以下を参照してください。

  - [SDI と MDI](../../mfc/sdi-and-mdi.md)

  - [フレームウィンドウ](../../mfc/frame-windows.md)

  - [フレームウィンドウクラス](../../mfc/frame-window-classes.md)

  - [ドキュメント、ビュー、フレームワーク](../../mfc/documents-views-and-the-framework.md)

  - [ダイアログボックス](../../mfc/dialog-boxes.md)

  |オプション|説明|
  |------------|-----------------|
  |**1 つのドキュメント**|アプリケーションのためのシングルドキュメントインターフェイス (SDI) アーキテクチャを作成します。このアーキテクチャでは、ビュークラスは [CView クラス](../../mfc/reference/cview-class.md)に基づいています。 ウィザードの [ [生成されたクラス] (MFC アプリケーションウィザード)](../../mfc/reference/generated-classes-mfc-application-wizard.md) ページで、ビューの基本クラスを変更できます。 たとえば、フォームベースのアプリケーションを作成するには、ビュークラスに [CFormView クラス](../../mfc/reference/cformview-class.md) を使用します。<br /><br /> この種類のアプリケーションでは、ドキュメントのフレームウィンドウはドキュメントを1つだけ保持できます。|
  |**複数のドキュメント**|アプリケーションのマルチドキュメントインターフェイス (MDI) アーキテクチャを作成します。ビュークラスは、に基づいて `CView` います。 ウィザードの [ **生成されたクラス** ] ページで、ビューの基本クラスを変更できます。 たとえば、フォームベースのアプリケーションを作成するには、 `CFormView` ビュークラスにを使用します。<br /><br /> この種類のアプリケーションでは、ドキュメントのフレームウィンドウに複数の子ウィンドウを含めることができます。|
  |**[タブ付きドキュメント]**|各ドキュメントを別のタブに配置します。|
  |**ダイアログベース**|ダイアログクラスの基になるアプリケーションのダイアログベースのアーキテクチャを作成し `CDialog` ます。 (HTML ダイアログを作成するには、[ **html ダイアログを使用** する] チェックボックスをオンにします)。|
  |**HTML ダイアログの使用**|ダイアログボックスアプリケーションの場合のみ。 [CDialog](../../mfc/reference/cdialog-class.md)クラスではなく、 [CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)からダイアログクラスを派生させます。 このチェックボックスをオンにすると、 `CDHtmlDialog` ウィザードの [[生成されたクラス] (MFC アプリケーションウィザード)](../../mfc/reference/generated-classes-mfc-application-wizard.md)ページの [**基底クラス**] ボックスにが表示されます。<br /><br /> `CDHtmlDialog`から派生したダイアログボックスには、html ベースのダイアログボックスが表示されます。また、html コントロールとデータを交換し、html イベントを処理します。|
  |**複数のトップレベルドキュメント**|ビュークラスの基になっているアプリケーションに対して、複数のトップレベルアーキテクチャを作成し `CView` ます。<br /><br /> この種類のアプリケーションでは、ユーザーが [**ファイル**] メニューの [**新規**] (または [**新しいフレーム**]) をクリックすると、アプリケーションによって、親が暗黙的にデスクトップとなるウィンドウが作成されます。 新しいドキュメントフレームはタスクバーに表示され、アプリケーションウィンドウのクライアント領域に制限されません。|

- **ドキュメント/ビューアーキテクチャのサポート**

  アプリケーションに、 [CDocument クラス](../../mfc/reference/cdocument-class.md) と [CView クラス](../../mfc/reference/cview-class.md) (既定値) を使用してドキュメント/ビューアーキテクチャを含めるかどうかを指定します。 非 MFC アプリケーションを移植する場合、またはコンパイルされた実行可能ファイルのサイズを小さくする場合は、このチェックボックスをオフにします。 既定では、ドキュメント/ビューアーキテクチャのないアプリケーションは、 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)から派生しています。また、ディスクファイルからドキュメントを開くための MFC のサポートは含まれていません。

- **リソース言語**

  リソースの言語を設定します。 一覧には、Visual Studio によってインストールされたシステムで使用可能な言語が表示されます。 システム言語以外の言語を選択する場合は、その言語の適切なテンプレートフォルダーが既にインストールされている必要があります。

  選択した言語は、ウィザードの [[ドキュメントテンプレート文字列] の [MFC アプリケーションウィザード](../../mfc/reference/document-template-strings-mfc-application-wizard.md)] ページにある [ローカライズされた **文字列**] オプションに反映されます。

- **Unicode ライブラリを使用する**

  MFC ライブラリの Unicode または非 Unicode バージョンを使用するかどうかを指定します。

- **プロジェクトスタイル**

  アプリケーションに標準の MFC、エクスプローラー、Visual Studio、または Office のアーキテクチャと表示があるかどうかを示します。 詳細については、「 [MFC アプリケーション Explorer-Style のファイルの作成](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)」を参照してください。

  |オプション|説明|
  |------------|-----------------|
  |**MFC 標準**|標準の MFC アプリケーションアーキテクチャを提供します。|
  |**エクスプローラー**|左ペインが [CTreeView クラス](../../mfc/reference/ctreeview-class.md) で、右側のペインが [CListView クラス](../../mfc/reference/clistview-class.md)であるスプリッターウィンドウを使用して、エクスプローラーのようなアプリケーションを実装します。|
  |**Visual Studio**|[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)から派生した4つのドッキング可能なペイン (**ファイルビュー**、**クラスビュー**、**プロパティ**、**出力**) と、 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)から派生したメインフレームウィンドウ (既定値) を含む、Visual Studio のようなアプリケーションを実装します。|
  |**Office**|[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)から派生したリボン、 [Cmfcoutlookbar クラス](../../mfc/reference/cmfcoutlookbar-class.md)から派生した Outlook バー、 [CMFCCaptionBar クラス](../../mfc/reference/cmfccaptionbar-class.md)から派生したキャプションバー、 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)から派生したメインフレームを含む、Office と同様のアプリケーションを実装します。|

- **視覚スタイルと色**

  アプリケーションの視覚スタイルを決定します。 次のオプションを使用できます。

  - **Windows ネイティブ/既定**

  - **Office 2003**

  - **Visual Studio 2005**

  - **Office 2007 (青のテーマ)**

  - **Office 2007 (黒のテーマ)**

  - **Office 2007 (シルバーテーマ)**

  - **Office 2007 (水色のテーマ)**

- **視覚スタイルの切り替えを有効にする**

  ユーザーが実行時にアプリケーションの視覚スタイルを変更できるかどうかを指定します。通常は、メニューまたはリボンから適切な視覚スタイルを選択します。

- **MFC の使用法**

  MFC ライブラリにリンクする方法を指定します。 既定では、MFC は共有 DLL としてリンクされています。

  |オプション|説明|
  |------------|-----------------|
  |**共有 DLL で MFC を使用する**|MFC ライブラリを共有 DLL としてアプリケーションにリンクします。 アプリケーションは、実行時に MFC ライブラリへの呼び出しを行います。 このオプションを選択すると、MFC ライブラリを使用する複数の実行可能ファイルで構成されるアプリケーションのディスクとメモリの要件が軽減されます。 Win32 と MFC の両方のアプリケーションで、DLL 内の関数を呼び出すことができます (既定)。|
  |**スタティックライブラリで MFC を使用する**|ビルド時にアプリケーションを静的 MFC ライブラリにリンクします。|

## <a name="see-also"></a>関連項目

[MFC アプリケーションウィザード](../../mfc/reference/mfc-application-wizard.md)<br/>
[Visual Studio の C++ プロジェクトに対して作成されるファイルの種類](../../build/reference/file-types-created-for-visual-cpp-projects.md)
