---
title: MFC クラス追加ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9560dec12a7710076f752d5329269c844f0d3a8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-add-class-wizard"></a>MFC クラス追加ウィザード
このコード ウィザードを使用して、既存の MFC プロジェクトにクラスを追加または MFC をサポートする ATL プロジェクトにクラスを追加します。 MFC がサポートされている Win32 プロジェクトに MFC クラスを追加することもできます。 プロジェクトの作成時に指定した機能は、このダイアログ ボックスで使用可能なオプションを決定します。  
  
## <a name="names"></a>名前  
 このページで、クラス名、基本クラス、および、新しいクラスのファイル名を指定します。  
  
 **クラス名**  
 新しいクラスの名前を指定し、Id とこのページ上のファイルの名前の既定の単位を提供します。 したがって、たとえば、""が「が付きます」のように、C++ のクラスは通常"C"で開始します。  
  
 **基本クラス**  
 新しいクラスの基底クラスの名前を指定します。 基本クラスは、既定では、 [CWnd](../../mfc/reference/cwnd-class.md)です。 選択した基本クラスでは、このページの他のボックスがアクティブかどうかを判断します。  
  
 基本クラスでは、ダイアログの ID またはリソース id です。 クラスがあるかどうかを決定するように設定するクラスの種類 クラスの一般的な種類は次のとおりです。  
  
-   などのクラス[CButton](../../mfc/reference/cbutton-class.md)、 [CWnd](../../mfc/reference/cwnd-class.md)、または[CDocument](../../mfc/reference/cdocument-class.md)、ダイアログ ボックスが不要 ID またはリソース id です。 これらのクラスは、ダイアログまたはリソース ID を使用しないでください。 基本クラスのこれらのクラスのいずれかを選択した場合、**ダイアログ ID**ボックスおよび**DHTML リソース ID**ボックスは淡色表示になります。  
  
-   などのクラス[CDialog](../../mfc/reference/cdialog-class.md)、 [CFormView](../../mfc/reference/cformview-class.md)、または[CPropertyPage](../../mfc/reference/cpropertypage-class.md)ダイアログの ID を必要とします。  
  
-   クラス[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)、これは、ダイアログの ID、DHTML リソース ID、および HTML ファイル名が必要です。  
  
 ダイアログの ID が必要なクラス、した方がより効果的に使用、[リソース エディター](../../windows/resource-editors.md)ダイアログ リソースを作成するには、その ID を割り当てる、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、し、関連付けられているクラスを作成そのリソース ID に置き換えます。 参照してください[ ダイアログ ボックスの新規作成](../../windows/creating-a-new-dialog-box.md)の詳細については、標準の Windows ダイアログ ボックスを作成する方法です。  
  
> [!NOTE]
>  最初ダイアログ リソースを作成してから、新しいクラスを派生させるかどうか`CDHtmlDialog`、Windows の標準の削除**ok**と**キャンセル**既定 ダイアログ ボックスに表示されるボタン。 DHTML フォームがそれ自体をホストする Windows の標準のダイアログ ボックス**OK**と**キャンセル**ボタン。  
  
 ダイアログ ボックスには、Windows のコントロールと DHTML コントロールの両方を含めることができますは推奨されません。  
  
 **ダイアログの ID**  
 選択した場合に、ダイアログの ID を指定する`CDialog`、 `CFormView`、 `CPropertyPage`、または`CDHtmlDialog`として、**基底クラス**です。  
  
 **.h ファイル**  
 新しいオブジェクトのクラスのヘッダー ファイルの名前を設定します。 既定では、この名前は、名に基づいて内に指定した**クラス名**です。 ファイル名を任意の場所に保存するか、既存のファイルに、クラスの宣言を追加する、省略記号ボタンをクリックします。 既存のファイルを選択すると場合、ウィザードは保存されません、選択した場所にするまで をクリック**完了**ウィザード。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードの指示に従って、クラス宣言が、ファイルの内容に追加されるかどうかを指定するようにします。 をクリックして**はい**; ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
 **.cpp ファイル**  
 新しいオブジェクトのクラスの実装ファイルの名前を設定します。 既定では、この名前は、名に基づいて内に指定した**クラス名**です。 ファイル名を任意の場所に保存する、省略記号ボタンをクリックします。 クリックするまで、選択した場所にファイルが保存されません**完了**ウィザード。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードの指示に従って、クラスの実装が、ファイルの内容に追加されるかどうかを指定するようにします。 をクリックして**はい**; ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
 **アクティブなユーザー補助機能**  
 MFC の Active Accessibility のサポートを有効に呼び出すことによって[EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility)コンス トラクターでします。 このオプションから派生したクラスの使用可能な[CWnd](../../mfc/reference/cwnd-class.md)です。  
  
 **DHTML リソース ID**  
 派生したクラスに適用されます`CDHtmlDialog`のみです。 DHTML ダイアログ ボックスのリソース ID を指定します。 リソース ID は、HTML ダイアログ ボックスのファイル名と共に、プロジェクトの .rc ファイルの HTML セクションに表示されます。 によって識別されるダイアログ ボックスによってホストされる DHTML リソースは、この ID によって識別される**ダイアログ ID**です。  
  
 **.HTM ファイル**  
 派生したクラスに適用されます`CDHtmlDialog`のみです。 DHTML ダイアログ ボックスの HTML ファイルの名前を設定します。 既定では、このファイル名をクラス名に基づきます。 HTML」DHTML ダイアログ ボックスのリソース ID と、プロジェクトの .rc ファイルのファイル名が表示されます。  
  
 **オートメーション**  
 サポートのクラス レベルを設定[オートメーション](../../mfc/automation.md)です。 クラス レベルでの自動化はオートメーションをサポートするすべてのクラスを使用できます。 オートメーションのサポートで作成したプロジェクトの利用もできます。 つまり、いずれか、MFC プロジェクトを[ATL サポート](../../atl/reference/mfc-support-in-atl-projects.md)、または選択した MFC プロジェクト、**オートメーション** チェック ボックス、[高度な機能](../../mfc/reference/advanced-features-mfc-application-wizard.md)MFC のページアプリケーション ウィザードです。  
  
|オプション|説明|  
|------------|-----------------|  
|**None**|クラスにオートメーションのサポートがないことを示します。|  
|**オートメーション**|クラスがオートメーションをサポートしていることを示します。 このオプションを選択する場合、新しく作成されたクラスは、Microsoft Visual Basic や Microsoft Excel などのオートメーション クライアント アプリケーションでのプログラミング可能なオブジェクトとして使用可能なです。 このオプションでは、この表の後に記載されている基本クラスを使用できません。|  
|**タイプ ID で作成可能**|クラスとプロジェクトの両方がオートメーションを使用してこのクラスのオブジェクトを作成する他のアプリケーションをサポートすることを示します。 このオプションを使用して、オートメーション クライアントはオートメーション オブジェクトを直接作成できます。 作成するオブジェクトを指定するクライアント アプリケーションで、テキスト ボックスに、型 ID が使用されます。システム全体と、一意である必要があります。 このオプションでは、この表の後に記載されている基本クラスを使用できません。|  
  
 オートメーションのサポートは、次の基本クラスを使用できません。  
  
-   `CAsyncMonitorFile`  
  
-   `CAsyncSocket`  
  
-   `CCachedDataPathProperty`  
  
-   `CConnectionPoint`  
  
-   `CDatabase`  
  
-   `CDataPathProperty`  
  
-   `CHttpFilter`  
  
-   `CHttpServer`  
  
-   `CInternetSession`  
  
-   `CObject`  
  
-   `CSocket`  
  
 **種類 ID**  
 クラスの型 ID を設定します。 **タイプ ID**ボックスには、次のようにする、プロジェクト名と新しいクラスの名前が連結: *MFCProj.MFCClass*です。 この ID を変更できるは、選択した場合にのみ、**オートメーション**オプション**タイプ ID で作成可能**です。  
  
 **ドキュメント テンプレート リソースを生成します。**  
 ドキュメント テンプレート リソースをアプリケーションで作成したドキュメントがあることを示します。 このチェック ボックスをアクティブ化するプロジェクトが MFC ドキュメント/ビュー アーキテクチャをサポートし、このクラスの基本クラスである必要があります[CFormView](../../mfc/reference/cformview-class.md)です。  
  
 参照してください[ドキュメント テンプレートとドキュメント/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [MFC クラス](../../mfc/reference/adding-an-mfc-class.md)   
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)
