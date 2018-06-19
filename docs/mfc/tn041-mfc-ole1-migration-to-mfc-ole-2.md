---
title: 'TN041: MFC ole 2 MFC OLE1 移行 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE1 [MFC]
- migrating OLE1 to OLE2
- migration [MFC], OLE1 to OLE2
- OLE2 [MFC]
- porting OLE1 to OLE2
- converting OLE1 to OLE2
- upgrading Visual C++ applications [MFC], OLE1 to OLE2
- TN041
ms.assetid: 67f55552-4b04-4ddf-af0b-4d9eaf5da957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78faa19263ff0ea03aac891c9be3a6114f7f9a48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385405"
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>テクニカル ノート 41: MFC/OLE1 から MFC/OLE 2 への移植
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
## <a name="general-issues-relating-to-migration"></a>移行に関連する一般的な問題  
 (以降) MFC 2.5 では、OLE 2 クラスの設計目標の 1 つは、MFC 2.0 では OLE 1.0 のサポートのために、同じアーキテクチャの多くを維持するでした。 その結果、多くの MFC 2.0 では同じ OLE クラス内に残ったままこのバージョンの MFC (`COleDocument`、 `COleServerDoc`、 `COleClientItem`、 `COleServerItem`)。 さらに、これらのクラスの Api の多くはまったく同じです。 ただし、OLE 2 は OLE 1.0 から大幅に異なる詳細の一部が変更できるようにします。 を MFC 2.0 OLE1 をサポートしている場合思う自宅で MFC の 2.0 をサポートします。  
  
 既存の MFC/OLE1 アプリケーションを実行し、OLE 2 の機能を追加している場合は、この注意を最初に読み取る必要があります。 このノート カバーの一般的な問題をいくつかを OLE1 MFC/OLE 2 への機能を移植するときに発生し、MFC 2.0 に含まれる 2 つのアプリケーションを移植するときに検出された問題について説明します MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md)と。[HIERSVR](../visual-cpp-samples.md)です。  
  
## <a name="mfc-documentview-architecture-is-important"></a>MFC ドキュメント/ビュー アーキテクチャは、重要  
 アプリケーションが MFC のドキュメント/ビュー アーキテクチャを使用していないアプリケーションに OLE 2 のサポートを追加する場合は、ここで、ドキュメント/ビューに移動する時間です。 MFC の OLE 2 クラスの利点の多くがのみ構成されるか組み込みのアーキテクチャと MFC のコンポーネント、アプリケーションが使用するとします。  
  
 MFC アーキテクチャを使用せず、サーバーまたはコンテナーを実装することが可能であれば、推奨されません。  
  
## <a name="use-mfc-implementation-instead-of-your-own"></a>はなく、独自の MFC 実装を使用します。  
 などのクラスの実装を MFC「固定」 `CToolBar`、 `CStatusBar`、および`CScrollView`OLE 2 のサポートの組み込みの特殊なケース コードがあります。 そのため、アプリケーションでこれらのクラスを使用することができる場合メリットが得られますときの作業を行うようにする OLE に注意してください。 可能であれば「ロール-独自」のクラスは、ここに、目的のためのもお勧めできません。 同様の機能を実装する必要がある場合は、(特にする際に、インプレース アクティブ化)、OLE の細かい点の一部を処理するための優れた参考文献は MFC のソース コードです。  
  
## <a name="examine-the-mfc-sample-code"></a>MFC のサンプル コードを調べる  
 OLE の機能を含む MFC サンプルの数があります。 それぞれのアプリケーションには、異なる角度から OLE を実装します。  
  
- [HIERSVR](../visual-cpp-samples.md)ほとんどの場合、サーバー アプリケーションとして使用するためのものです。 MFC/OLE1 アプリケーションとしての MFC 2.0 に含まれていたとがされて MFC/OLE 2 に移植し、OLE 2 で使用できる多くの OLE 機能を実装できるように拡張されます。  
  
- [OCLIENT](../visual-cpp-samples.md)これは、コンテナーの観点から OLE の機能の多くを示すために意図したもので、コンテナーをスタンドアロン アプリケーションです。 MFC 2.0 から移植された OLE の高度な機能、カスタムのクリップボード形式や埋め込みアイテムへのリンクなどの多くをサポートするために拡張します。  
  
- [DRAWCLI](../visual-cpp-samples.md)このアプリケーション サポートを実装して OLE コンテナーはるか OCLIENT と同様、既存のオブジェクト指向の描画プログラムのフレームワーク内で処理が実行する点が異なります。 OLE コンテナーのサポートを実装および既存のアプリケーションに統合する方法を示します。  
  
- [SUPERPAD](../visual-cpp-samples.md)このアプリケーションだけでなく正常のスタンドアロン アプリケーションでは、OLE サーバーではもです。 実装するサーバーのサポートは、限です。 特に関心があるは、データをクリップボードにコピーする OLE クリップボード サービスの使用方法しますが、クリップボードの貼り付けの機能を実装する Windows"edit"コントロールに組み込まれた機能を使用します。 新しい OLE Api との統合だけでなく、従来の Windows API の使用状況の興味深い組み合わせが表示されます。  
  
 サンプル アプリケーションの詳細については、MFC サンプルのヘルプ」を参照してください。  
  
## <a name="case-study-oclient-from-mfc-20"></a>MFC 2.0 からのケース スタディ: OCLIENT  
 前述したように、 [OCLIENT](../visual-cpp-samples.md) MFC 2.0 に含まれていた、MFC/OLE1 を使用して OLE を実装します。 このアプリケーションが最初に変換された MFC/OLE 2 クラスを使用する手順は次のとおりです。 初期のポートが、MFC/OLE クラスをより深く説明するために完了した後、さまざまな機能が追加されました。 これらの機能はここでは説明しません詳細については、これらの高度な機能、サンプル アプリケーションを参照してください。  
  
> [!NOTE]
>  コンパイラ エラーおよび段階的なプロセスは、Visual C 2.0 で作成されました。 特定のエラー メッセージと場所は、Visual C 4.0 に変更可能性がありますが、概念に関する情報は有効です。  
  
## <a name="getting-it-up-and-running"></a>取得しを実行しています。  
 MFC/OLE へ oclient をポートに採用されているアプローチでは、ビルドし、原因となる明らかなコンパイラ エラーを修正して開始します。 Oclient MFC 2.0 からこのバージョンの MFC でコンパイルすると、それほど多くのエラーを解決するのにはないことがあります。 これらが発生した順序でエラーは次のとおりです。  
  
## <a name="compile-and-fix-errors"></a>コンパイルとエラーの修正  
  
```  
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters  
```  
  
 最初のエラーに関する注意事項`COleClientItem::Draw`です。 MFC/OLE1 MFC/OLE バージョンより多くのパラメーターをかかりました。 余分なパラメーターでした。 多くの場合、必要であり、通常、(この例では) のように NULL。 このバージョンの MFC に描画されている CDC メタファイル DC は、ときに、lpWBounds の値が自動的に判断できます。 さらに、"属性 DC から"に渡された pDC のいずれかと、フレームワークは構築ため pFormatDC パラメーターは必要なくなりました。 2 つの削除だけでこの問題を修正するように余分な描画呼び出しのパラメーターは NULL です。  
  
```  
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier  
\oclient\mainview.cpp(273) : error C2057: expected constant expression  
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
```  
  
 結果のファクトを上記のエラーをすべての**COleClientItem::CreateXXXX** MFC/OLE1 内の関数に必要な項目を表す一意の名前が渡されることです。 これは、基になる OLE API の要件です。 これは、機能は、たとえば OLE 2 では、DDE (名前は、DDE メッセージ交換で使用された) 基になる通信メカニズムとして使用しないため MFC/OLE 2 では必要ありません。 この問題を解決するには削除、 **CreateNewName**への参照がすべてだけでなく機能します。 どのような各 MFC/OLE 関数が受け取るこのバージョンでの呼び出しでカーソルを置き、F1 キーを押すだけで調べる簡単です。  
  
 大きく異なる別の領域は、OLE 2 クリップボード処理です。 OLE1 とクリップボードを Windows クリップボード Api 操作を使用します。 OLE 2 これは、別のメカニズムです。 MFC/OLE1 Api は、コピーする前に、クリップボードが開いていると見なされます、`COleClientItem`クリップボード オブジェクト。 これは必要なくなりましたなり、すべて MFC/OLE クリップボード操作が失敗します。 依存関係を削除するコードを編集するときに**CreateNewName**Windows のクリップボードを開いたり閉じたりするコードを削除することも必要があります。  
  
```  
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier  
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function  
\oclient\mainview.cpp(344) : error C2057: expected constant expression  
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'  
```  
  
 これらのエラーの結果から、 **CMainView::OnInsertObject**ハンドラー。 「オブジェクトの挿入」コマンドの処理は、別の領域で変更された少しです。 この場合は、単に新しい OLE コンテナー アプリケーションに対して AppWizard によって提供される元の実装をマージする最も簡単なは。 実際には、これは、他のアプリケーションを移植するときに適用可能な手法です。 呼び出して「オブジェクトの挿入」ダイアログの表示で MFC/OLE1 **AfxOleInsertDialog**関数。 構築するこのバージョンでは、**インクルード**ダイアログ オブジェクトと呼び出し`DoModal`です。 新しい OLE 項目をさらに、作成、 **CLSID** classname 文字列の代わりにします。 次のように、最終的な結果になります  
  
```  
COleInsertDialog dlg;  
if (dlg.DoModal() != IDOK)  
    return; 
 
BeginWaitCursor();

 
CRectItem* pItem = NULL;  
TRY  
{ *// First create the C++ object  
    pItem = GetDocument()->CreateItem();
ASSERT_VALID(pItem);

 *// Initialize the item from the dialog data.  
    if (!dlg.CreateItem(pItem))  
    AfxThrowMemoryException();
*// any exception will do  
    ASSERT_VALID(pItem);

 *// run the object if appropriate  
    if (dlg.GetSelectionType() == 
    COleInsertDialog::createNewItem) 
    pItem->DoVerb(OLEIVERB_SHOW,
    this);

 *// update right away  
    pItem->UpdateLink();
pItem->UpdateItemRectFromServer();

 *// set selection to newly inserted item  
    SetSelection(pItem);

 pItem->Invalidate();

}  
CATCH (CException,
    e)  
{ *// clean up item  
    if (pItem != NULL)  
    GetDocument()->DeleteItem(pItem);

 
    AfxMessageBox(IDP_FAILED_TO_CREATE);

} 
END_CATCH  
 
EndWaitCursor();
```  
  
> [!NOTE]
>  新しいオブジェクトの挿入があります、アプリケーションによって異なる)。  
  
 含める必要も\<afxodlgs.h > の宣言が含まれています、**インクルード**ダイアログ クラスと MFC によって提供される他の標準のダイアログ。  
  
```  
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier  
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters  
```  
  
 これらのエラーは、概念的に同じですが、にもかかわらずに OLE 2 で一部の OLE1 定数が変更されているという事実が原因です。 ここでは**例**に変更された`OLEIVERB_PRIMARY`です。 OLE1 と OLE 2 の両方で主動詞は通常、実行されるコンテナーによって、ユーザーが項目をダブルクリックするとします。  
  
 さらに、`DoVerb`で追加のパラメーターを受け取るようになりました: ビューへのポインター (`CView`*)。 このパラメーターは「ビジュアル編集」(または、インプレース アクティブ化) を実装するのみ使用します。 用今すぐこの時点でこの機能を実装していないために、NULL の場合にそのパラメーターを設定します。  
  
 オーバーライドする必要がありますを確認すること、framework インプレース試行をアクティブにしないで`COleClientItem::CanActivate`次のようにします。  
  
```  
BOOL CRectItem::CanActivate()  
{  
    return FALSE;  
}  
 
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier  
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function  
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier  
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function  
```  
  
 MFC/OLE1 で**COleClientItem::GetBounds**と**SetBounds**クエリおよび項目の範囲を操作するために使用された (、**左**と**上部**メンバーが 0 では常に)。 MFC/OLE 2 でより直接的でサポートされる`COleClientItem::GetExtent`と`SetExtent`、対処する、**サイズ**または`CSize`代わりにします。  
  
 コードを新しい SetItemRectToServer UpdateItemRectFromServer 呼び出しが次のように検索。  
  
```  
BOOL CRectItem::UpdateItemRectFromServer()  
{  
    ASSERT(m_bTrackServerSize);

 CSize size;  
    if (!GetExtent(&size))  
    return FALSE;    // blank  
 *// map from HIMETRIC to screen coordinates  
 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.LPtoDP(&size);

 } *// just set the item size  
    if (m_rect.Size() != size)  
 { *// invalidate the old size/position  
    Invalidate();
m_rect.right = m_rect.left + size.cx;  
    m_rect.bottom = m_rect.top + size.cy; *// as well as the new size/position  
    Invalidate();

 }  
    return TRUE;  
}  
 
BOOL CRectItem::SetItemRectToServer()  
{ *// set the official bounds for the embedded item  
    CSize size = m_rect.Size();

 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.DPtoLP(&size);

 }  
    TRY 
 {  
    SetExtent(size);
*// may do a wait  
 }  
    CATCH(CException, e)  
 {  
    return FALSE;  // links will not allow SetBounds  
 }  
    END_CATCH 
    return TRUE;  
}  
 
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'  
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier  
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function  
```  
  
 コンテナーからサーバーへの呼び出しでは、MFC/OLE1 同期 API が*シミュレーション*OLE1 が多くの場合は本質的に非同期であるため、します。 ユーザーからのコマンドを処理する前に進行中の非同期呼び出しを確認する必要があります。 指定された MFC/OLE1、 **COleClientItem::InWaitForRelease**これを行うための関数。 MFC/OLE 2 でこの必要はありません、CMainFrame で OnCommand の上書きをすべて同時に削除することができます。  
  
 この時点で OCLIENT のコンパイルし、リンクします。  
  
## <a name="other-necessary-changes"></a>その他の必要な変更  
 いくつかの点を実行しないことが保持する OCLIENT の実行、ただしもあります。 以降ではなく今すぐ問題を解決することをお勧めします。  
  
 OLE ライブラリを初期化するために必要な場合は最初に、です。 これは、呼び出すことで**AfxOleInit**から`InitInstance`:  
  
```  
if (!AfxOleInit())  
{  
    AfxMessageBox("Failed to initialize OLE libraries");

    return FALSE;  
}  
```  
  
 仮想関数のパラメーター リストの変更を確認することをお勧めします。 このような機能の 1 つ`COleClientItem::OnChange`、MFC/OLE コンテナー アプリケーションでオーバーライドします。 オンライン ヘルプを見ると、によって、余分な 'DWORD について' が追加されたことが表示されます。 新しい CRectItem::OnChange は次のようになります。  
  
```  
void   
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)  
{  
    if (m_bTrackServerSize&& 
 !UpdateItemRectFromServer())  
 { *// Blank object  
    if (wNotification == OLE_CLOSED)  
 { *// no data received for the object - destroy it  
    ASSERT(!IsVisible());

 GetDocument()->DeleteItem(this);

    return; // no update (item is gone now)  
 }  
 }  
    if (wNotification != OLE_CLOSED)  
    Dirty();
Invalidate();
*// any change will cause a redraw  
}  
```  
  
 コンテナー アプリケーションでは、MFC/OLE1 からドキュメント クラスの派生**COleClientDoc**です。 MFC/OLE 2 でこのクラスが削除されに置き換えられました`COleDocument`(この新しい組織をやすくコンテナー/サーバー アプリケーションの構築) します。 `#define`マップされる**COleClientDoc**に`COleDocument`OCLIENT など、MFC/OLE 2 への MFC/OLE1 アプリケーションの移植を簡単にします。 提供されない機能の 1 つ`COleDocument`によって指定された**COleClientDoc**標準コマンド メッセージ マップ エントリです。 これは、これを使用しても、そのサーバー アプリケーション`COleDocument`(間接的に) を含まないにこれらのコマンド ハンドラーのオーバーヘッド コンテナー/サーバー アプリケーションでない限り、します。 このため CMainDoc メッセージ マップに、次のエントリを追加する必要があります。  
  
```  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE,
    OnUpdatePasteMenu)  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK,
    OnUpdatePasteLinkMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS,
    OnUpdateEditLinksMenu)  
ON_COMMAND(ID_OLE_EDIT_LINKS,
    COleDocument::OnEditLinks)  
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST,
    OnUpdateObjectVerbMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT,
    OnUpdateObjectVerbMenu)  
ON_COMMAND(ID_OLE_EDIT_CONVERT,
    OnEditConvert)  
```  
  
 これらのコマンドのすべての実装は`COleDocument`、これは、ドキュメントの基底クラスです。  
  
 この時点では、OCLIENT は機能の OLE コンテナー アプリケーションです。 (OLE1 または OLE 2) の任意の型の項目を挿入することができます。 インプレース アクティブ化を有効にするために必要なコードは実装されていませんので OLE1 と同じように別のウィンドウで項目が編集します。 次のセクションでは、インプレース編集 (「ビジュアル編集」と呼ばれることもあります) を有効にするために必要な変更について説明します。  
  
## <a name="adding-visual-editing"></a>「ビジュアル編集」を追加します。  
 OLE の最も一般的な機能の 1 つは、インプレース アクティブ化 (「ビジュアル編集」) です。 この機能は、コンテナーのユーザー インターフェイスの一部のユーザーのシームレスな編集インターフェイスを提供する場合に、サーバー アプリケーションを使用します。 OCLIENT する、インプレース アクティブ化を実装するのには、特別なリソースをいくつか追加のコードだけでなく、追加する必要があります。 これらのリソースと、コードが通常提供されるに対して AppWizard によって、実際には、多くのコードをここでは「コンテナー」サポートを含む新しい AppWizard アプリケーションから直接借用しました。  
  
 まず、インプレース アクティブであるアイテムがある場合に使用するメニュー リソースを追加する必要があります。 IDR_OCLITYPE リソースをコピーしてファイルとウィンドウのポップアップを削除して、Visual C でこの追加のメニュー リソースを作成できます。 グループの分離を示すためにファイルとウィンドウのポップアップは 2 つの区分線に挿入 (のようになります: ファイル&#124;&#124;ウィンドウ)。 これらの区切り文字の意味し、サーバーとコンテナーのメニューにマージする方法の詳細についてを参照してください「メニューとリソース:: メニューのマージ」 *OLE 2 クラス*です。  
  
 これらのメニューを作成した後は、フレームワークには、認識させる必要があります。 これは、呼び出すことで`CDocTemplate::SetContainerInfo`に対してドキュメント テンプレートの一覧に追加する前に、ドキュメント テンプレートのです。 ドキュメント テンプレートを登録する新しいコードは、次のようになります。  
  
```  
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE, 
    RUNTIME_CLASS(CMainDoc), 
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame  
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```   
  
 IDR_OLECLITYPE_INPLACE リソースが、特別なインプレースで Visual C で作成します。  
  
 インプレース アクティブ化を有効にすることがありますの両方を変更する必要がある、`CView`を派生クラスだけでなく`COleClientItem`行うクラスを派生します。 AppWizard によって提供されるすべてのこれらのオーバーライドおよび実装の大部分が既定の AppWizard アプリケーションから直接取得されます。  
  
 このポートの最初の手順では、インプレース アクティブ化がオーバーライドする完全によって無効に`COleClientItem::CanActivate`です。 インプレース アクティブ化を許可するには、この上書きを削除してください。 さらに、NULL は、すべての呼び出しに渡された`DoVerb`(はそのうち 2 つ)、ビューを提供することはのみが、インプレース アクティブ化に必要なためです。 適切なビューを通過する必要が、インプレース アクティブ化を完全に実装するには、`DoVerb`呼び出します。 これらの呼び出しのいずれかが**CMainView::OnInsertObject**:  
  
```  
pItem->DoVerb(OLEIVERB_SHOW, this);
```  
  
 他にも**もう 1 つ**:  
  
```  
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```  
  
 オーバーライドする必要がある`COleClientItem::OnGetItemPosition`です。 これは、サーバーに、アイテムが、インプレース アクティブ化されたコンテナーのウィンドウの基準とした、ウィンドウを配置する場所を示しています。 OCLIENT、実装は単純です。  
  
```  
void CRectItem::OnGetItemPosition(CRect& rPosition)  
{  
    rPosition = m_rect;  
}  
```  
  
 ほとんどのサーバーが「インプレースのサイズを変更します」と呼ばれるものを実装しても これにより、サーバー ウィンドウの決まり、ユーザーがアイテムの編集中に移動します。 コンテナーは、位置とサイズ、コンテナー ドキュメント自体内を移動するか、通常、ウィンドウのサイズ変更に影響するためこの操作に参加する必要があります。 OCLIENT の実装では、新しい位置とサイズでなしで管理されている内部の四角形を同期します。  
  
```  
BOOL CRectItem::OnChangeItemPosition(const CRect& rectPos)  
{  
    ASSERT_VALID(this);

 
    if (!COleClientItem::OnChangeItemPosition(rectPos))  
    return FALSE;  
 
    Invalidate();
m_rect = rectPos;  
    Invalidate();
GetDocument()->SetModifiedFlag();

 
    return TRUE;  
}  
```  
  
 この時点では、インプレース アクティブ化して、サイズ変更と、アクティブである場合の項目の移動を処理するアイテムを許可するための十分なコードがあるけれども、コードはユーザーに許可なしの編集セッションを終了するには 一部のサーバーはこの機能が自体は、esc キーを処理することによっては、コンテナーがアイテムを非アクティブ化する 2 つの方法を提供することをお勧めします。 (1) 外側をクリックし、項目、および (2) キーを押すと、エスケープします。  
  
 ESC キーのコマンドを VK_ESCAPE キーにマップする Visual C でアクセラレータを追加、ID_CANCEL_EDIT がリソースに追加します。 このコマンドのハンドラーは、次に示します。  
  
```  
// The following command handler provides the standard  
// keyboard user interface to cancel an in-place  
// editing session.void CMainView::OnCancelEdit()  
{ *// Close any in-place active item on this view.  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->Close();
ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);

}  
```  
  
 ユーザーがアイテムの外側をクリックするケースを処理するための先頭に次のコードを追加する**ときの処理**:  
  
```  
if (pNewSel != m_pSelection || pNewSel == NULL)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& pActiveItem != pNewSel)  
    pActiveItem->Close();

} 
 
```  
  
 アイテムが、インプレース アクティブのとき、フォーカスが必要です。 このようなことを確認するには、フォーカスは、ビューがフォーカスを受け取ったとき、常にアクティブな項目を転送できるように OnSetFocus を処理します。  
  
```  
// Special handling of OnSetFocus and OnSize are required   
// when an object is being edited in-place.  
void CMainView::OnSetFocus(CWnd* pOldWnd)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& 
    pActiveItem->GetItemState() == COleClientItem::activeUIState)  
 { *// need to set focus to this item if it is same view  
    CWnd* pWnd = pActiveItem->GetInPlaceWindow();
if (pWnd != NULL)  
 {  
    pWnd->SetFocus();
*// don't call the base class  
    return; 
 }  
 }  
 
    CView::OnSetFocus(pOldWnd);

} 
```  
  
 ビューのサイズが変更されるときに、アクティブな項目のクリッピング四角形が変更されたことを通知する必要があります。 ハンドラーを指定してこれを行う`OnSize`:  
  
```  
void CMainView::OnSize(UINT nType,
    int cx,
    int cy)  
{  
    CView::OnSize(nType,
    cx,
    cy);

    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->SetItemRects();

} 
```  
  
## <a name="case-study-hiersvr-from-mfc-20"></a>MFC 2.0 からのケース スタディ: HIERSVR  
 [HIERSVR](../visual-cpp-samples.md) MFC 2.0 にも含まれますが、MFC/OLE1 を使用して OLE を実装します。 このメモでこのアプリケーションが最初に変換された MFC/OLE 2 クラスを使用して手順について簡単に説明します。 初期のポートが MFC/OLE 2 クラスをより深く説明するために完了した後、さまざまな機能が追加されました。 これらの機能はここでは説明しません詳細については、これらの高度な機能、サンプル アプリケーションを参照してください。  
  
> [!NOTE]
>  コンパイラ エラーおよび段階的なプロセスは、Visual C 2.0 で作成されました。 特定のエラー メッセージと場所は、Visual C 4.0 に変更可能性がありますが、概念に関する情報は有効です。  
  
## <a name="getting-it-up-and-running"></a>取得しを実行しています。  
 移植する hiersvr MFC/OLE を採用されているアプローチでは、ビルドし、原因となる明らかなコンパイラ エラーを修正して開始します。 MFC 2.0 から HIERSVR サンプルを取得してコンパイルするにはこのバージョンの MFC の下にある場合 (ただし、oclient が複数ある) を解決するのには多くのエラーがないことがあります。 通常行われる順序でエラーは次のとおりです。  
  
## <a name="compile-and-fix-errors"></a>コンパイルとエラーの修正  
  
```  
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'  
```  
  
 この最初のエラーに大きな問題を示して、`InitInstance`サーバー用の関数。 OLE サーバーに必要な初期化は、MFC/OLE1 アプリケーションを実行していることをする必要があります、最も大きな変更のいずれかで、可能性があります。 最もよい方法は、AppWizard が OLE サーバーの作成を確認し、適切なコードを変更します。 ここでは、点に注意してください。  
  
 呼び出して OLE ライブラリを初期化する必要がある**AfxOleInit**  
  
 サーバーのリソース ハンドルとでは設定できないランタイム クラス情報を設定するドキュメント テンプレート オブジェクトの SetServerInfo を呼び出して、`CDocTemplate`コンス トラクターです。  
  
 コマンドラインで/Embedding がある場合、アプリケーションのメイン ウィンドウを表示しません。  
  
 必要があります、 **GUID**ドキュメントにします。 これは、ドキュメントの種類 (128 ビット) の一意の識別子です。 AppWizard を作成する — ためここで説明した手法を使用する場合は、新しい AppWizard が生成されるサーバー アプリケーションから新しいコードをコピーすることができます単に「盗む」そのアプリケーションから取得した GUID です。 それ以外の場合は、GUIDGEN を使用することができます。BIN ディレクトリ内の EXE ユーティリティです。  
  
 「接続」する必要がある、`COleTemplateServer`オブジェクトを呼び出すことによって、ドキュメント テンプレートに`COleTemplateServer::ConnectTemplate`です。  
  
 アプリケーションは、スタンドアロンの実行時に、システム レジストリを更新します。 これにより、ユーザーが移動した場合、します。アプリケーションの EXE には、新しい場所を指す Windows システム登録データベースを更新、新しい場所から実行されます。  
  
 すべての AppWizard を作成するのに基づくこれらの変更を適用した後に`InitInstance`、 `InitInstance` (および関連する GUID) の HIERSVR が次のように読み取る必要があります。  
  
```  
// this is the GUID for HIERSVR documents  
static const GUID BASED_CODE clsid = 
 { 0xA0A16360L,
    0xC19B,
    0x101A, { 0x8C,
    0xE5,
    0x00,
    0xDD,
    0x01,
    0x11,
    0x3F,
    0x12 } };  
 
/////////////////////////////////////////////////////////////////////////////  
// COLEServerApp initialization  
 
BOOL COLEServerApp::InitInstance()  
{ *// OLE 2 initialization  
    if (!AfxOleInit())  
 {  
    AfxMessageBox("Initialization of the OLE failed!");

    return FALSE;  
 }  
 *// Standard initialization  
    LoadStdProfileSettings();

// Load standard INI file options   
 *// Register document templates  
    CDocTemplate* pDocTemplate;  
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,  
    RUNTIME_CLASS(CServerDoc), 
    RUNTIME_CLASS(CMDIChildWnd), 
    RUNTIME_CLASS(CServerView));

 pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);

    AddDocTemplate(pDocTemplate);

 *// create main MDI Frame window  
    CMainFrame* pMainFrame = new CMainFrame;  
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))  
    return FALSE;  
    m_pMainWnd = pMainFrame;  
 
    SetDialogBkColor();
*// gray look  
 *// enable file manager drag/drop and DDE Execute open  
    m_pMainWnd->DragAcceptFiles();
EnableShellOpen();

 
    m_server.ConnectTemplate(clsid,
    pDocTemplate,
    FALSE);

    COleTemplateServer::RegisterAll();

 *// try to launch as an OLE server  
    if (RunEmbedded())  
 { *// "short-circuit" initialization -- run as server!  
    return TRUE;  
 }  
    m_server.UpdateRegistry();
RegisterShellFileTypes();

 *// not run as OLE server,
    so show the main window  
    if (m_lpCmdLine[0] == '\0')  
 { *// create a new (empty) document  
    OnFileNew();

 }  
    else 
 { *// open an existing document  
    OpenDocumentFile(m_lpCmdLine);

 }  
 
    pMainFrame->ShowWindow(m_nCmdShow);

 pMainFrame->UpdateWindow();

 
    return TRUE;  
}  
```  
  
 上記のコードが、次のように新しいリソース ID IDR_HIERSVRTYPE_SRVR_EMB を指すことがわかります。 これは、別のコンテナーに埋め込まれているドキュメントを編集する際に使用するメニュー リソースです。 MFC/OLE1 埋め込みアイテムの編集に固有のメニュー項目がその場で変更されました。 ファイル ベースのドキュメントを編集する代わりに埋め込みアイテムの編集時に、まったく別のメニュー構造を使用するとは 2 つのモードを別のユーザー インターフェイスを提供するより簡単です。 わかる後で、埋め込みオブジェクトには、一括編集するときに、まったく別のメニュー リソースが使用されます。  
  
 このリソースを作成するには、リソース スクリプトを Visual C に読み込むし、既存の IDR_HIERSVRTYPE メニュー リソースをコピーします。 (これは、AppWizard を使用する同じ名前付け規則) IDR_HIERSVRTYPE_SRVR_EMB に新しいリソースの名前を変更します。 次に「ファイルの更新」に「ファイルの保存」を変更します。コマンド ID を付けます**ID_FILE_UPDATE**です。 "ファイルのコピーを付けて保存する";「付けて」変更もコマンド ID を付けます**ID_FILE_SAVE_COPY_AS**です。 フレームワークは、これらのコマンドの両方の実装を提供します。  
  
```  
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations  
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers  
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'  
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'  
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers  
```  
  
 オーバーライドによるエラーの数がある`OnSetData`を参照しているため、 **OLESTATUS**型です。 **OLESTATUS** OLE1 にエラーが返される方法でした。 これは、動作が変更を`HRESULT`OLE 2 で MFC が通常に変換しますが、`HRESULT`に、`COleException`エラーを含むです。 ここでは特定のオーバーライド`OnSetData`を行うには最も簡単な方法はそれを削除するために必要がなくなりました。  
  
```  
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters  
```  
  
 `COleServerItem`コンス トラクターは、余分な 'BOOL' パラメーターを受け取ります。 このフラグは、上のメモリ管理の方法を決定、`COleServerItem`オブジェクト。 TRUE に設定することは、によって、フレームワークではこれらのオブジェクトのメモリ管理を行います。-必要でなくなったときに、それらを削除します。 HIERSVR を使用して**よう**(から派生した`COleServerItem`) ため、このフラグを FALSE に設定をそのネイティブのデータの一部としてオブジェクト。 Hiersvr の各サーバーのアイテムが削除されたときを判断します。  
  
```  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
```  
  
 これらのエラーがあるようにオーバーライドされていない一部の ' 純粋仮想関数。 ほとんどの場合これは OnDraw のパラメーター リストが変更されたというにより発生します。 このエラーを解決するには、次のように変更します。**修正**次のように (およびに宣言)。  
  
```  
BOOL CServerItem::OnDraw(CDC* pDC,
    CSize& rSize)  
{ *// request from OLE to draw node  
    pDC->SetMapMode(MM_TEXT);

// always in pixels  
    return DoDraw(pDC,
    CPoint(0,
    0),
    FALSE);

}  
```  
  
 新しいパラメーターは、'rSize' です。 これにより、描画のサイズを入力できる便利な場合です。 このサイズは内で指定する必要があります**HIMETRIC**です。 この場合、便利ではありませんでは、この値を入力する、フレームワーク`OnGetExtent`範囲を取得します。 そのため、実装する必要があります`OnGetExtent`:  
  
```  
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect,
    CSize& rSize)  
{  
    if (dwDrawAspect != DVASPECT_CONTENT)  
    return COleServerItem::OnGetExtent(dwDrawAspect,
    rSize);

 
    rSize = CalcNodeSize();
return TRUE;  
}  
 
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier  
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type  
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'  
```  
  
 CServerItem::CalcNodeSize 関数では、アイテムのサイズに変換されます**HIMETRIC**で保存され**m_rectBounds**です。 記載されていない '**m_rectBounds**' のメンバー`COleServerItem`存在しません (これは部分的に置き換えられました`m_sizeExtent`、OLE 2 でこのメンバーよりも若干異なる、使用法が**m_rectBounds**OLE1 ででした)。 設定ではなく、 **HIMETRIC**サイズこのメンバー変数に、それが返すされます。 この戻り値が使用される`OnGetExtent`、以前に実装されています。  
  
```  
CSize CServerItem::CalcNodeSize()  
{  
    CClientDC dcScreen(NULL);

 
    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,  
    m_strDescription.GetLength());

 m_sizeNode += CSize(CX_INSET* 2,
    CY_INSET* 2);

 *// set suggested HIMETRIC size  
    CSize size(m_sizeNode.cx,
    m_sizeNode.cy);

    dcScreen.SetMapMode(MM_HIMETRIC);

 dcScreen.DPtoLP(&size);

    return size;  
}  
```  
  
 ようもオーバーライド**COleServerItem::OnGetTextData**です。 この関数は、MFC/OLE 残されているし、別のメカニズムは置き換えられます。 MFC 3.0 バージョンの MFC OLE サンプル[HIERSVR](../visual-cpp-samples.md)オーバーライドすることでこの機能を実装して`COleServerItem::OnRenderFileData`です。 OnGetTextData オーバーライドを削除することができますので、この機能はこの基本的なポートの重要ではありません。  
  
 多数のエラー svritem.cpp で対処していないことがあります。 「現実の」エラーではありません-以前のエラーが原因で、エラーのみです。  
  
```  
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters  
```  
  
 `COleServerItem::CopyToClipboard` 'bIncludeNative' フラグをサポートしていません。 ネイティブのデータ (サーバー項目のシリアル化の関数によって書き込まれます) は、最初のパラメーターを削除するように常にコピーします。 さらに、 `CopyToClipboard` FALSE を返す代わりにエラーが発生時に例外がスローされます。 CServerView::OnEditCopy の以下のコードを変更します。  
  
```  
void CServerView::OnEditCopy()  
{  
    if (m_pSelectedNode == NULL)  
    AfxThrowNotSupportedException();

 
    TRY 
 {  
    m_pSelectedNode->CopyToClipboard(TRUE);

 }  
    CATCH_ALL(e) 
 {  
    AfxMessageBox("Copy to clipboard failed");

 }  
    END_CATCH_ALL 
}  
```  
  
 HIERSVR の MFC 2.0 バージョンのコンパイル結果として得られる OCLIENT の同じバージョンのよりも多くのエラーがありましたがあった少ない実際に変更します。  
  
 この時点で HIERSVR はコンパイルしリンクし、次で実装されている一括編集機能せず、OLE サーバーとして機能します。  
  
## <a name="adding-visual-editing"></a>「ビジュアル編集」を追加します。  
 このサーバー アプリケーションには、「ビジュアル編集」(またはをインプレース アクティブ化) を追加するにはのみ、いくつかのように注意する必要があります。  
  
-   項目が、インプレース アクティブなときに使用される特殊なメニュー リソースを必要とします。  
  
-   ツールバー (上記で説明したメニュー リソースに一致)、サーバーから使用できるメニュー コマンドを一致するように、標準ツールバーのサブセットだけを使用する必要がありますので、このアプリケーションは、ツールバーを持ちます。  
  
-   派生する新しいクラスを作成する必要があります`COleIPFrameWnd`インプレースでのユーザー インターフェイスを提供する (から派生した CMainFrame とほぼ同様に`CMDIFrameWnd`、MDI ユーザー インターフェイスを提供)。  
  
-   これらの特殊なリソースやクラスは、フレームワークに指示する必要があります。  
  
 メニュー リソースが簡単に作成します。 Visual C を実行、IDR_HIERSVRTYPE_SRVR_IP と呼ばれるメニュー リソースを IDR_HIERSVRTYPE メニュー リソースをコピーします。 メニューを変更して、編集およびヘルプ] メニューの [ポップアップのままにするようにします。 2 つの区切り記号 メニューを追加、編集およびヘルプ メニューの間 (のようになります: 編集&#124;&#124;役立ちます)。 これらの区切り文字の意味し、サーバーとコンテナーのメニューにマージする方法の詳細についてを参照してください「メニューとリソース:: メニューのマージ」 *OLE 2 クラス*です。  
  
 サブセットのツールバーのビットマップは、"Server"オプションがオンで新規生成 AppWizard アプリケーションから 1 つをコピーすることによって簡単に作成できます。 このビットマップは、Visual C にインポートすることができます。 必ず、ビットマップの ID の IDR_HIERSVRTYPE_SRVR_IP を付与してください。  
  
 クラスから派生する`COleIPFrameWnd`server のサポートも使用して AppWizard が生成されたアプリケーションからコピーできます。 IPFRAME の両方のファイルをコピーします。CPP と IPFRAME です。H、プロジェクトに追加します。 確認して、`LoadBitmap`呼び出しは IDR_HIERSVRTYPE_SRVR_IP、前の手順で作成されるビットマップを参照します。  
  
 これですべての新しいリソースやクラスを作成するは、必要なコードを追加して、これらを教える (および今すぐこのアプリケーションがインプレース編集をサポートしていることを知っている) フレームワークようにします。 によって複数のパラメーターを追加することによってこれは、`SetServerInfo`で呼び出し、`InitInstance`関数。  
  
```  
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,  
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```  
  
 インプレースでを実行する準備ができました、インプレース アクティブ化をサポートする任意のコンテナーにします。 しかし、残さコードは、1 つの軽微なバグがあります。 HIERSVR には、ユーザーがマウスの右ボタンを押したときに表示される、コンテキスト メニューがサポートしています。 このメニューは動作 HIERSVR が完全にオープンで、その場合、埋め込み先編集時に機能しません。 理由は、CServerView::OnRButtonDown 内のコードの単一行にピン留めすることができます。  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```  
  
 参照に注意してください**ここ**です。 サーバーが、インプレース アクティブ化の場合は、メイン ウィンドウがあると m_pMainWnd を設定するが通常表示されていません。 さらに、このウィンドウを指す、*メイン*アプリケーションのウィンドウで、サーバーは完全なときに表示される MDI フレーム ウィンドウを開く、またはスタンドアロンで実行します。 アクティブなフレーム ウィンドウには参照されません-ときに、インプレース アクティブ化は、フレーム ウィンドウから派生された`COleIPFrameWnd`です。 一括編集するには、このバージョンの MFC は、新しい関数を追加するときにも正しいのアクティブなウィンドウを取得する`AfxGetMainWnd`です。 一般に、この関数の代わりを使用する必要があります**ここ**です。 このコードは、次のように変更する必要があります。  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetMainWnd());
```  
  
 これで、インプレース アクティブ化の機能の有効な最小 OLE サーバーがあります。 まだあります多くの機能で使用できたいない MFC/OLE1 MFC/OLE 2 で使用できます。 詳細については HIERSVR サンプルを参照して、機能を実装することができます。 HIERSVR を実装する機能の一部を次に示します。  
  
-   ズーム機能のコンテナーとして使用します。  
  
-   ドラッグ アンド ドロップし、カスタムのクリップボード形式です。  
  
-   選択範囲としてコンテナー ウィンドウのスクロールが変更されます。  
  
 また、MFC 3.0 で HIERSVR サンプルは、そのサーバーのアイテムのデザインが多少異なりますを使用します。 これは、メモリを節約でき、リンクより柔軟です。 HIERSVR の 2.0 バージョンで、ツリー内の各ノード*は a* `COleServerItem`です。 `COleServerItem` これらのノードごとに必ずしも必要ではよりもオーバーヘッドがもう少しが、`COleServerItem`のアクティブなリンクが必要です。 特定の時点で、非常にアクティブなリンクがあります、ほとんどの場合。 このバージョンの MFC で HIERSVR をより効率的に行うをするには、間のノードから、`COleServerItem`です。 両方 CServerNode と**よう**クラスです。 **よう**(から派生した`COleServerItem`) のみが必要に応じて作成します。 コンテナー (またはコンテナー) は、特定のノードをその特定のリンクを使用してを停止、CServerNode に関連付けられているようオブジェクトは削除されます。 この設計より効率的かつ柔軟です。 その柔軟性は、複数のリンクを選択範囲を処理する場合にします。 複数の選択をサポートして HIERSVR これら 2 つのバージョンのどちらが簡単に追加する (およびそのような選択項目にリンクをサポートする) ことが、MFC 3.0 のバージョンと HIERSVR、ので、`COleServerItem`はネイティブのデータから分離します。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

