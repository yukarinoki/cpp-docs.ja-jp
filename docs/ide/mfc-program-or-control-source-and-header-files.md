---
title: MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], MFC source and header
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ab1ed04b9890fbed8de8b59354ab36d7be063e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-program-or-control-source-and-header-files"></a>MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル
Visual Studio で作成したプロジェクトに対して選択したオプションによって、MFC プロジェクトを作成するときに、次のファイルが作成されます。 たとえば、プロジェクトが含まれている*Projname*dlg.cpp と*Projname*dlg.h ファイル ダイアログ ベースのプロジェクトまたはクラスを作成する場合にのみです。  
  
 これらすべてのファイル内にある、 *Projname*ディレクトリ、およびヘッダー ファイル (.h) フォルダーまたはソリューション エクスプ ローラーでフォルダーをソース ファイル (.cpp ファイル) のいずれか。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|*Projname*.h|プログラムまたは DLL の主要なインクルード ファイル。 すべてのグローバル シンボルが含まれていると`#include`他のヘッダー ファイルのディレクティブ。 派生して、`CPrjnameApp`クラス`CWinApp`を宣言し、`InitInstance`メンバー関数。 コントロールに対して、`CPrjnameApp`クラスから派生して`COleControlModule`です。|  
|*Projname*.cpp|メイン プログラムのソース ファイルです。 クラスの 1 つのオブジェクトを作成`CPrjnameApp`から派生した`CWinApp`、オーバーライドして、`InitInstance`メンバー関数。<br /><br /> 実行可能ファイル、`CPrjnameApp::InitInstance`いくつかの操作です。 登録すると、ドキュメントとビュー間の接続として使用できるドキュメント テンプレートメイン フレーム ウィンドウ; を作成します空のドキュメントを作成する (またはドキュメントを開くと、アプリケーションのコマンドライン引数として指定されている場合)。<br /><br /> Dll および ActiveX (OLE 以前) をコントロール`CProjNameApp::InitInstance`を呼び出して ole コントロールのオブジェクト ファクトリを登録`COleObjectFactory::RegisterAll`への呼び出しと`AfxOLEInit`です。 さらに、このメンバー関数は`CProjNameApp::ExitInstance`、コントロールを呼び出してメモリからアンロードするために使用**AfxOleTerm**です。<br /><br /> このファイルも登録し、実装することによって Windows の登録情報データベース内のコントロールの登録を解除、`DllRegisterServer`と`DllUnregisterServer`関数。|  
|*Projname*ctrl.h、 *Projname*ctrl.cpp|宣言し、実装、`CProjnameCtrl`クラスです。 `CProjnameCtrl` 派生した`COleControl`、一部のメンバー関数のスケルトンの実装が定義されて初期化、描画、およびシリアル化して (読み込みおよび保存) コントロールです。 メッセージ、イベント、およびディスパッチ マップも定義されています。|  
|*Projname*dlg.cpp、 *Projname*dlg.h|ダイアログ ベースのアプリケーションを選択した場合に作成されます。 ファイルが派生してをという名前のダイアログ クラスの実装`CProjnameDlg`ダイアログの初期化し、ダイアログ データ エクス (チェンジ DDX) の実行をスケルトンのメンバー関数が含まれるとします。 情報 ダイアログ クラスはこれらのファイルではなく配置も*Projname*.cpp です。|  
|Dlgproxy.cpp、Dlgproxy.h|ダイアログ ベース プログラム、実装、およびヘッダー ファイルにメイン ダイアログ ボックスのプロジェクトのオートメーション プロキシ クラスに適用します。 オートメーションのサポートを選択した場合にのみ使用します。|  
|*Projname*doc.cpp、 *Projname*doc.h|派生し、という名前のドキュメント クラスを実装する`CProjnameDoc`、するには、ドキュメントの初期化、シリアル化のスケルトンのメンバー関数を含めると (の保存し、読み込み) ドキュメント、および診断のデバッグを実装します。|  
|*Projname*set.h/.cpp|データベースをサポートし、レコード セット クラスが含まれているプログラムを作成する場合は作成します。|  
|*Projname*view.cpp、 *Projname*view.h|派生し、という名前のビュー クラスを実装する`CProjnameView`、表示または印刷するドキュメントのデータに使用されます。 `CProjnameView`クラスは、次の MFC クラスのいずれかから派生します。<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> プロジェクトのビュー クラスには、ビューの描画や診断のデバッグを実装するスケルトン メンバー関数が含まれています。 印刷用のサポートを有効にした場合は、メッセージ マップ エントリは、印刷、印刷のセットアップに追加され、印刷プレビュー コマンド メッセージ。 これらのエントリは、ビューの基底クラスの対応するメンバー関数を呼び出します。|  
|*Projname*PropPage.h、 *Projname*PropPage.cpp|宣言し、実装、`CProjnamePropPage`クラスです。 `CProjnamePropPage` 派生した`COlePropertyPage`とスケルトンのメンバー関数、 `DoDataExchange`、データ交換と検証の実装を提供します。|  
|IPframe.cpp、IPframe.h|アプリケーション ウィザードの ミニ サーバーまたはフル サーバー オプションが選択されている場合は作成**自動化オプション**ページ (手順 3 の 6)。 ファイルは派生し、埋め込み先フレーム ウィンドウ クラスを実装する、という名前**元**サーバーがコンテナー プログラムによってアクティブ化を使用します。|  
|Mainfrm.cpp、Mainfrm.h|派生、 **CMainFrame**からいずれかのクラスを[CFrameWnd](../mfc/reference/cframewnd-class.md) (の SDI アプリケーション) または[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) (ため MDI アプリケーション)。 **CMainFrame**クラスは、アプリケーションのウィザードで、対応するオプションが選択されている場合、ツールバーのボタンとステータス バーの作成を処理**アプリケーション オプション** ページ (手順 6)。 使用方法について**CMainFrame**を参照してください[、フレーム ウィンドウ クラスによって作成されたアプリケーションのウィザード](../mfc/frame-window-classes-created-by-the-application-wizard.md)です。|  
|Childfrm.cpp、Childfrm.h|派生、 **CChildFrame**クラス[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)です。 **CChildFrame**のため MDI ドキュメント フレーム ウィンドウ クラスを使用します。 MDI オプションを選択した場合、これらのファイルが常に作成します。|  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/atl-program-or-control-source-and-header-files.md)   
 [CLR プロジェクト](../ide/files-created-for-clr-projects.md)