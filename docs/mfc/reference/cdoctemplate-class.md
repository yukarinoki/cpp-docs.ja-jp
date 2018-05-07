---
title: CDocTemplate クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocTemplate
- AFXWIN/CDocTemplate
- AFXWIN/CDocTemplate::CDocTemplate
- AFXWIN/CDocTemplate::AddDocument
- AFXWIN/CDocTemplate::CloseAllDocuments
- AFXWIN/CDocTemplate::CreateNewDocument
- AFXWIN/CDocTemplate::CreateNewFrame
- AFXWIN/CDocTemplate::CreateOleFrame
- AFXWIN/CDocTemplate::CreatePreviewFrame
- AFXWIN/CDocTemplate::GetDocString
- AFXWIN/CDocTemplate::GetFirstDocPosition
- AFXWIN/CDocTemplate::GetNextDoc
- AFXWIN/CDocTemplate::InitialUpdateFrame
- AFXWIN/CDocTemplate::LoadTemplate
- AFXWIN/CDocTemplate::MatchDocType
- AFXWIN/CDocTemplate::OpenDocumentFile
- AFXWIN/CDocTemplate::RemoveDocument
- AFXWIN/CDocTemplate::SaveAllModified
- AFXWIN/CDocTemplate::SetContainerInfo
- AFXWIN/CDocTemplate::SetDefaultTitle
- AFXWIN/CDocTemplate::SetPreviewInfo
- AFXWIN/CDocTemplate::SetServerInfo
dev_langs:
- C++
helpviewer_keywords:
- CDocTemplate [MFC], CDocTemplate
- CDocTemplate [MFC], AddDocument
- CDocTemplate [MFC], CloseAllDocuments
- CDocTemplate [MFC], CreateNewDocument
- CDocTemplate [MFC], CreateNewFrame
- CDocTemplate [MFC], CreateOleFrame
- CDocTemplate [MFC], CreatePreviewFrame
- CDocTemplate [MFC], GetDocString
- CDocTemplate [MFC], GetFirstDocPosition
- CDocTemplate [MFC], GetNextDoc
- CDocTemplate [MFC], InitialUpdateFrame
- CDocTemplate [MFC], LoadTemplate
- CDocTemplate [MFC], MatchDocType
- CDocTemplate [MFC], OpenDocumentFile
- CDocTemplate [MFC], RemoveDocument
- CDocTemplate [MFC], SaveAllModified
- CDocTemplate [MFC], SetContainerInfo
- CDocTemplate [MFC], SetDefaultTitle
- CDocTemplate [MFC], SetPreviewInfo
- CDocTemplate [MFC], SetServerInfo
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7674e9a25f4794d40a977fce914ab6ac0131de25
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdoctemplate-class"></a>CDocTemplate クラス
ドキュメント テンプレートの基本的な機能を定義する抽象基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDocTemplate::CDocTemplate](#cdoctemplate)|`CDocTemplate` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocTemplate::AddDocument](#adddocument)|テンプレートにドキュメントを追加します。|  
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|このテンプレートに関連付けられているすべてのドキュメントを閉じます。|  
|[CDocTemplate::CreateNewDocument](#createnewdocument)|新しいドキュメントを作成します。|  
|[CDocTemplate::CreateNewFrame](#createnewframe)|ドキュメントとビューを含む新しいフレーム ウィンドウを作成します。|  
|[CDocTemplate::CreateOleFrame](#createoleframe)|OLE が有効なフレーム ウィンドウを作成します。|  
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|リッチ プレビューに使用する子フレームを作成します。|  
|[CDocTemplate::GetDocString](#getdocstring)|ドキュメントの種類に関連付けられている文字列を取得します。|  
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|このテンプレートに関連付けられている最初のドキュメントの位置を取得します。|  
|[CDocTemplate::GetNextDoc](#getnextdoc)|ドキュメントと、次の位置を取得します。|  
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|フレーム ウィンドウを初期化し、必要に応じて表示にします。|  
|[CDocTemplate::LoadTemplate](#loadtemplate)|リソースを読み込み、指定された`CDocTemplate`またはその派生クラス。|  
|[CDocTemplate::MatchDocType](#matchdoctype)|ドキュメントの種類とテンプレートの間の一致で信頼度を決定します。|  
|[CDocTemplate::OpenDocumentFile](#opendocumentfile)|パス名で指定されたファイルを開きます。|  
|[CDocTemplate::RemoveDocument](#removedocument)|テンプレートからドキュメントを削除します。|  
|[CDocTemplate::SaveAllModified](#saveallmodified)|変更されたこのテンプレートに関連付けられているすべてのドキュメントを保存します。|  
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|インプレースで OLE 項目を編集する場合は、OLE コンテナーのリソースを決定します。|  
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|ドキュメント ウィンドウのタイトル バーには、既定のタイトルを表示します。|  
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|プロセス外の設定は、ハンドラーをプレビューします。|  
|[CDocTemplate::SetServerInfo](#setserverinfo)|サーバー ドキュメントが埋め込まれているまたはインプレースを編集するときに、リソースやクラスを決定します。|  
  
## <a name="remarks"></a>コメント  
 通常、アプリケーションの実装では 1 つまたは複数のドキュメント テンプレートを作成する`InitInstance`関数。 ドキュメント テンプレートには、3 種類のクラス間のリレーションシップを定義します。  
  
-   派生するドキュメント クラス**CDocument**です。  
  
-   ビュー クラス上に示したドキュメント クラスのデータを表示します。 このクラスから派生できます`CView`、 `CScrollView`、 `CFormView`、または`CEditView`です。 (使用することも`CEditView`直接)。  
  
-   ビューを含むフレーム ウィンドウ クラスです。 シングル ドキュメント インターフェイス (SDI) アプリケーションの場合からこのクラスを派生`CFrameWnd`です。 このクラスからの派生、マルチ ドキュメント インターフェイス (MDI) アプリケーションの`CMDIChildWnd`します。 使用することができる場合は、フレーム ウィンドウの動作をカスタマイズする必要はありません、`CFrameWnd`または`CMDIChildWnd`独自のクラスを派生することがなく、直接です。  
  
 アプリケーションでは、サポートされているドキュメントの種類ごとに 1 つのドキュメント テンプレートを持ちます。 たとえば、アプリケーションは、スプレッドシートやテキスト ドキュメントの両方をサポートする場合、アプリケーションには、2 つのドキュメント テンプレート オブジェクトがあります。 各ドキュメント テンプレートを作成して、その型のすべてのドキュメントの管理を担当します。  
  
 ドキュメント テンプレートへのポインターを格納する、`CRuntimeClass`ドキュメント、ビュー、フレーム ウィンドウ クラスのオブジェクト。 これら`CRuntimeClass`ドキュメント テンプレートを構築するときに、オブジェクトが指定されています。  
  
 ドキュメント テンプレートには、(メニュー、アイコン、アクセラレータ テーブル リソースなど) のドキュメントの種類で使用するリソースの ID が含まれています。 ドキュメント テンプレートには、そのドキュメントの種類に関する追加情報を含む文字列もあります。 これらには、ドキュメントの種類 (たとえば、「ワークシート」) とファイル拡張子 (たとえば、".xls"など) の名前が含まれます。 必要に応じて、アプリケーションのユーザー インターフェイス、Windows ファイル マネージャー、およびオブジェクトのリンクおよび Embedding (OLE) サポートで使用されるその他の文字列を格納できます。  
  
 アプリケーションが OLE コンテナーやサーバーの場合は、ドキュメント テンプレートは、インプレース アクティブ化時に使用するメニューの ID も定義します。 アプリケーションが OLE サーバーの場合は、ドキュメント テンプレートは、インプレース アクティブ化時に使用するメニューのツールバーの ID を定義します。 呼び出すことによってこれらの追加 OLE リソースを指定する`SetContainerInfo`と`SetServerInfo`です。  
  
 `CDocTemplate`抽象クラスでは、クラスを直接使用することはできません。 一般的なアプリケーションを使用して、2 つのいずれかの`CDocTemplate`-Microsoft Foundation Class ライブラリが提供するクラスを派生: `CSingleDocTemplate`、SDI を実装して`CMultiDocTemplate`MDI を実装します。 ドキュメント テンプレートの使用に関する詳細については、これらのクラスを参照してください。  
  
 独自のクラスを派生させることができる場合は、アプリケーションは、基本的に異なります SDI または MDI のどちらであるユーザー インターフェイスのパラダイムを必要とする`CDocTemplate`です。  
  
 詳細については`CDocTemplate`を参照してください[ドキュメント テンプレートとドキュメント/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="adddocument"></a>  CDocTemplate::AddDocument  
 テンプレートにドキュメントを追加するのにには、この関数を使用します。  
  
```  
virtual void AddDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDoc`  
 追加するドキュメントへのポインター。  
  
### <a name="remarks"></a>コメント  
 派生クラス[CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)と[関数](../../mfc/reference/csingledoctemplate-class.md)この関数をオーバーライドします。 独自のドキュメント テンプレート クラスを派生させるかどうか`CDocTemplate`、派生クラスは、この関数をオーバーライドする必要があります。  
  
##  <a name="cdoctemplate"></a>  CDocTemplate::CDocTemplate  
 `CDocTemplate` オブジェクトを構築します。  
  
```  
CDocTemplate (
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDResource`  
 ドキュメントの種類で使用するリソースの ID を指定します。 これには、メニューのアイコン、アクセラレータ テーブル、および文字列リソースが含まれます。  
  
 文字列リソースは、'\n' 文字で区切られた最大 7 つの部分文字列で構成されます (部分文字列が含まれていない場合、プレース ホルダーとして '\n' 文字が必要ですただし、末尾の '\n' 文字は必要ありません;)。これらの部分文字列では、ドキュメントの種類について説明します。 詳細については、部分文字列は、次を参照してください。 [GetDocString](#getdocstring)です。 この文字列リソースについては、アプリケーションのリソース ファイルにあります。 例えば:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 文字列は"\n"文字で始まることに注意してください。これは、最初の部分文字列が MDI アプリケーションで実行されていない、したがってが含まれていないためです。 ストリング エディターを使用してこの文字列を編集することができます。文字列全体は、7 つの独立したエントリとしてではなく文字列エディターで、1 つのエントリとして表示されます。  
  
 `pDocClass`  
 指す、`CRuntimeClass`ドキュメント クラスのオブジェクト。 このクラスは、 **CDocument**のドキュメントを表すために定義するクラスを派生します。  
  
 `pFrameClass`  
 指す、`CRuntimeClass`フレーム ウィンドウ クラスのオブジェクト。 このクラスにすることができます、 `CFrameWnd`-派生クラスにすることもできます`CFrameWnd`自体、メイン フレーム ウィンドウの既定の動作をする場合。  
  
 `pViewClass`  
 指す、`CRuntimeClass`ビュー クラスのオブジェクト。 このクラスは、 `CView`-、ドキュメントを表示を定義するクラスを派生します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用して構築するために、`CDocTemplate`オブジェクト。 動的に割り当てる、`CDocTemplate`オブジェクトに渡すと[とき](../../mfc/reference/cwinapp-class.md#adddoctemplate)から、`InitInstance`アプリケーション クラスのメンバー関数。  
  
##  <a name="closealldocuments"></a>  CDocTemplate::CloseAllDocuments  
 開いているすべてのドキュメントを閉じるには、このメンバー関数を呼び出します。  
  
```  
virtual void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEndSession`  
 セッションが終了されているかどうかを指定します。 **TRUE**セッションがそれ以外の終了されている場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は通常、ファイルの終了 コマンドの一部として使用されます。 この関数の既定の実装、[のに](../../mfc/reference/cdocument-class.md#deletecontents)ドキュメントのデータとし、閉じる、ドキュメントにアタッチされているすべてのビューのフレーム ウィンドウを削除するメンバー関数。  
  
 ユーザーがドキュメントを閉じる前に、特別なクリーンアップ処理を実行する必要をする場合は、この関数をオーバーライドします。 たとえば、ドキュメントでは、データベース内のレコードを表す、場合、データベースを終了するには、この関数をオーバーライドします。  
  
##  <a name="createnewdocument"></a>  CDocTemplate::CreateNewDocument  
 このドキュメント テンプレートに関連付けられている型の新しいドキュメントを作成するには、このメンバー関数を呼び出します。  
  
```  
virtual CDocument* CreateNewDocument();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたドキュメントへのポインターまたは**NULL**場合は、エラーが発生します。  
  
##  <a name="createnewframe"></a>  CDocTemplate::CreateNewFrame  
 ドキュメントとビューを含む新しいフレーム ウィンドウを作成します。  
  
```  
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,  
    CFrameWnd* pOther);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDoc`  
 新しいフレーム ウィンドウを参照するドキュメントです。 指定できます**NULL**です。  
  
 `pOther`  
 新しいフレーム ウィンドウに基づいているフレーム ウィンドウです。 指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたフレーム ウィンドウへのポインターまたは**NULL**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 `CreateNewFrame` 使用して、`CRuntimeClass`オブジェクトを表示と添付されたドキュメントを使用して、新しいフレーム ウィンドウを作成するコンス トラクターに渡されます。 場合、`pDoc`パラメーターは**NULL**フレームワークは、トレース メッセージを出力します。  
  
 `pOther`新しいウィンドウのコマンドを実装するパラメーターを使用します。 新しいフレーム ウィンドウをモデル化するフレーム ウィンドウを提供します。 新しいフレーム ウィンドウを非表示には、通常は作成されます。 新しいファイルとファイルを開くの標準的なフレームワークの実装の外部のフレーム ウィンドウを作成するには、この関数を呼び出します。  
  
##  <a name="createoleframe"></a>  CDocTemplate::CreateOleFrame  
 OLE のフレーム ウィンドウを作成します。  
  
```  
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc,  
    BOOL bCreateView);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 フレームの親ウィンドウへのポインター。  
  
 `pDoc`  
 新しい OLE フレーム ウィンドウを参照するドキュメントへのポインター。  
  
 `bCreateView`  
 フレームとビューを作成するかどうかを判断します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、フレーム ウィンドウへのポインターそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 場合`bCreateView`0 の場合は、空のフレームを作成します。  
  
##  <a name="getdocstring"></a>  CDocTemplate::GetDocString  
 ドキュメントの種類に関連付けられている文字列を取得します。  
  
```  
virtual BOOL GetDocString(
    CString& rString,  
    enum DocStringIndex index) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rString`  
 参照、`CString`関数が戻るときに、文字列を格納するオブジェクト。  
  
 *index*  
 ドキュメントの種類を説明する文字列から取得する部分文字列のインデックス。 このパラメーターには、次のいずれかの値を指定できます。  
  
- **CDocTemplate::windowTitle**アプリケーション ウィンドウのタイトル バーの (たとえば、"Excel") に表示される名前です。 SDI アプリケーションのドキュメント テンプレートにのみ存在します。  
  
- **CDocTemplate::docName** (たとえば、「シート」) の既定のドキュメント名のルートです。 このルートと、多くは (たとえば、「シート 1」または「シート 2」など) は、ファイル メニューから新規作成 を選択するたびにこの種類の新しいドキュメントの既定の名前に使用されます。 指定しない場合、「無題」は、既定値として使用します。  
  
- **CDocTemplate::fileNewName**このドキュメントの種類の名前。 アプリケーションでは、ドキュメントの 1 つ以上の型をサポートする場合は、新しいファイル ダイアログ ボックス (たとえば、「ワークシート」) でこの文字列が表示されます。 指定しない場合、ドキュメントの種類がファイルの新規作成 コマンドを使用してアクセスできません。  
  
- **CDocTemplate::filterName**ドキュメントの種類と一致するドキュメントのこの型のワイルドカード フィルターの説明。 この文字列は、ファイルを開く ダイアログ ボックス (「ワークシート (*.xls)」など) でファイルの種類のドロップダウン リストに表示されます。 指定しない場合、ドキュメントの種類がファイルを開くコマンドを使用してアクセスできません。  
  
- **CDocTemplate::filterExt**この型 (たとえば、".xls"など) のドキュメントの拡張子。 指定しない場合、ドキュメントの種類がファイルを開くコマンドを使用してアクセスできません。  
  
- **CDocTemplate::regFileTypeId** Windows によって管理される登録データベースに格納されるドキュメントの種類の識別子。 この文字列は内部の使用のみ (たとえば、「したりできます」) です。 指定しない場合、ドキュメントの種類は Windows ファイル マネージャーに登録できません。  
  
- **CDocTemplate::regFileTypeName**登録データベースに格納されるドキュメントの種類の名前。 この文字列は、登録情報データベース (たとえば、「Microsoft Excel ワークシート」) にアクセスするアプリケーションのダイアログ ボックスに表示される可能性があります。  
  
### <a name="return-value"></a>戻り値  
 指定された部分文字列が見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ドキュメント型を記述する特定の部分文字列を取得するには、この関数を呼び出します。 これらの部分文字列を含む文字列では、ドキュメント テンプレートに格納され、アプリケーションのリソース ファイル内の文字列から派生します。 フレームワークは、アプリケーションのユーザー インターフェイスに必要な文字列を取得するには、この関数を呼び出します。 アプリケーションのドキュメントのファイル名拡張子を指定した場合、またフレームワーク Windows 登録データベースにエントリを追加するときにこれにより、ドキュメントを Windows ファイル マネージャーから開きます。  
  
 独自のクラスから派生する場合にのみ、この関数を呼び出す`CDocTemplate`です。  
  
##  <a name="getfirstdocposition"></a>  CDocTemplate::GetFirstDocPosition  
 このテンプレートに関連付けられている最初のドキュメントの位置を取得します。  
  
```  
virtual POSITION GetFirstDocPosition() const = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**ドキュメント テンプレートに関連付けられたドキュメントのリストを反復処理に使用できる値または**NULL**リストが空の場合。  
  
### <a name="remarks"></a>コメント  
 このテンプレートに関連付けられているドキュメントのリスト内の最初のドキュメントの位置を取得するのにには、この関数を使用します。 使用して、**位置**への引数として値[CDocTemplate::GetNextDoc](#getnextdoc)テンプレートに関連付けられているドキュメントのリストを反復処理します。  
  
 [関数](../../mfc/reference/csingledoctemplate-class.md)と[CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)両方純粋仮想関数をオーバーライドします。 任意のクラスから派生した`CDocTemplate`も、この関数をオーバーライドしなければなりません。  
  
##  <a name="getnextdoc"></a>  CDocTemplate::GetNextDoc  
 によって識別されるリストの要素を取得`rPos`を設定し、`rPos`を**位置**一覧の次のエントリの値。  
  
```  
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 このテンプレートに関連付けられているドキュメントの一覧で、次のドキュメントへのポインター。  
  
### <a name="parameters"></a>パラメーター  
 `rPos`  
 参照、**位置**を以前の呼び出しによって返される値[GetFirstDocPosition](#getfirstdocposition)または`GetNextDoc`です。  
  
### <a name="remarks"></a>コメント  
 場合は、取得した最後の要素を一覧での新しい値`rPos`に設定されている**NULL**です。  
  
 使用することができます`GetNextDoc`への呼び出しに最初の位置を確立する場合は、順方向の反復ループで[GetFirstDocPosition](#getfirstdocposition)です。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
##  <a name="initialupdateframe"></a>  CDocTemplate::InitialUpdateFrame  
 フレーム ウィンドウを初期化し、必要に応じて表示にします。  
  
```  
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,  
    CDocument* pDoc,  
    BOOL bMakeVisible = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrame`  
 最初の更新を必要があるフレーム ウィンドウです。  
  
 `pDoc`  
 フレームが関連付けられているドキュメントです。 指定できます**NULL**です。  
  
 `bMakeVisible`  
 フレームが表示され、アクティブになる必要があるかどうかを示します。  
  
### <a name="remarks"></a>コメント  
 呼び出す**IntitialUpdateFrame**で新しいフレームを作成した後`CreateNewFrame`です。 受信するには、そのフレーム ウィンドウのビューには、この関数を呼び出すと、`OnInitialUpdate`呼び出しです。 またがない場合以前、アクティブなビュー、フレーム ウィンドウのプライマリ ビューがアクティブになります。プライマリ ビューの子の ID を持つビュー **AFX_IDW_PANE_FIRST**です。 フレーム ウィンドウが表示されます。 最後に、場合`bMakeVisible`は 0 以外。 場合`bMakeVisible`0、現在のフォーカスとフレーム ウィンドウの表示の状態は変更されません。  
  
 新しいファイルとファイルを開くのフレームワークの実装を使用する場合は、この関数を呼び出す必要はありません。  
  
##  <a name="loadtemplate"></a>  CDocTemplate::LoadTemplate  
 リソースを読み込み、指定された`CDocTemplate`またはその派生クラス。  
  
```  
virtual void LoadTemplate();
```  
  
### <a name="remarks"></a>コメント  
 リソースを読み込むために、フレームワークによって呼び出されます、指定された`CDocTemplate`またはその派生クラス。 通常ときに呼び出されます、構築時に除く、テンプレートがグローバルに構築されます。 その場合への呼び出しで`LoadTemplate`まで遅延[とき](../../mfc/reference/cwinapp-class.md#adddoctemplate)と呼びます。  
  
##  <a name="matchdoctype"></a>  CDocTemplate::MatchDocType  
 ドキュメントの種類とテンプレートの間の一致で信頼度を決定します。  
  
```  
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,  
    CDocument*& rpDocMatch);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPathName`  
 型を決定するファイルのパス名。  
  
 `rpDocMatch`  
 ファイルが指定されている場合、一致するドキュメントが割り当てられているドキュメントへのポインター`lpszPathName`は既に開かれています。  
  
### <a name="return-value"></a>戻り値  
 値、**信頼**列挙体は、次のように定義されています。  
  
```  
enum Confidence  
    {  
    noAttempt,
    maybeAttemptForeign,
    maybeAttemptNative,
    yesAttemptForeign,
    yesAttemptNative,
    yesAlreadyOpen
    };  
```  
  
### <a name="remarks"></a>コメント  
 ファイルを開くに使用するのにドキュメント テンプレートの種類を確認するのにには、この関数を使用します。 アプリケーションでは、複数のファイルの種類をサポートする場合など、できますこの関数を使用する特定する使用可能なドキュメント テンプレートには呼び出すことによって、指定されたファイルの適切な`MatchDocType`を有効にしてによるとテンプレートを選択するのには、各テンプレートの信頼度の値が返されます。  
  
 ファイルが指定された場合`lpszPathName`が既に開いている、この関数を返します**CDocTemplate::yesAlreadyOpen**ファイルのコピーと**CDocument**でオブジェクトにオブジェクト`rpDocMatch`です。  
  
 ファイルが、拡張機能が開いていない場合`lpszPathName`によって指定された拡張子と一致する**CDocTemplate::filterExt**、この関数を返します**CDocTemplate::yesAttemptNative** の設定`rpDocMatch`に**NULL**です。 詳細については**CDocTemplate::filterExt**を参照してください[CDocTemplate::GetDocString](#getdocstring)です。  
  
 この関数を返しますのかどうかは、どちらの場合は true、**とき**です。  
  
 既定の実装を返さない**CDocTemplate::maybeAttemptForeign**または**CDocTemplate::maybeAttemptNative**です。 などからこれらの 2 つの値を使用して、アプリケーションに適したの型が一致するロジックを実装するには、この関数をオーバーライドして、**信頼**列挙します。  
  
##  <a name="opendocumentfile"></a>  CDocTemplate::OpenDocumentFile  
 パスで指定されたファイルを開きます。  
  
```  
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;  
 
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszPathName`  
 開かれるドキュメントを含むファイルのパスへのポインター。  
  
 [入力] `bAddToMRU`  
 `TRUE` このドキュメントは、最新のファイルのいずれかを示します`FALSE`ドキュメントが最新のファイルの 1 つでないことを示します。  
  
### <a name="return-value"></a>戻り値  
 ファイルの名前は、ドキュメントへのポインター`lpszPathName`です。`NULL`失敗した場合。  
  
### <a name="remarks"></a>コメント  
 パスを持つには、指定されたファイルを開きます`lpszPathName`です。 場合`lpszPathName`は`NULL`、このテンプレートに関連付けられている型のドキュメントを含む新しいファイルを作成します。  
  
##  <a name="removedocument"></a>  CDocTemplate::RemoveDocument  
 によって示されるドキュメントが削除`pDoc`このテンプレートに関連付けられているドキュメントの一覧からです。  
  
```  
virtual void RemoveDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDoc`  
 削除するドキュメントへのポインター。  
  
### <a name="remarks"></a>コメント  
 派生クラス`CMultiDocTemplate`と`CSingleDocTemplate`この関数をオーバーライドします。 独自のドキュメント テンプレート クラスを派生させるかどうか`CDocTemplate`、派生クラスは、この関数をオーバーライドする必要があります。  
  
##  <a name="saveallmodified"></a>  CDocTemplate::SaveAllModified  
 変更されているすべてのドキュメントを保存します。  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="setcontainerinfo"></a>  CDocTemplate::SetContainerInfo  
 インプレースで OLE 項目を編集する場合は、OLE コンテナーのリソースを決定します。  
  
```  
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDOleInPlaceContainer`  
 埋め込みオブジェクトがアクティブになったときに使用されているリソースの ID。  
  
### <a name="remarks"></a>コメント  
 OLE オブジェクトは、インプレース アクティブ化されたときに使用されるリソースを設定するには、この関数を呼び出します。 これらのリソースには、メニューとアクセラレータ テーブルを含めることがあります。 通常、この関数は呼び出されます。、[場合は](../../mfc/reference/cwinapp-class.md#initinstance)、アプリケーションの関数。  
  
 関連付けられたメニュー`nIDOleInPlaceContainer`コンテナー アプリケーションのメニューにマージするアクティブ化されたインプレースで項目のメニューを許可する区切り記号が含まれています。 サーバーとコンテナーのメニューのマージに関する詳細については、記事を参照してください。[メニューとリソース (OLE)](../../mfc/menus-and-resources-ole.md)です。  
  
##  <a name="setdefaulttitle"></a>  CDocTemplate::SetDefaultTitle  
 ドキュメントの既定のタイトルを読み込んで、ドキュメントのタイトル バーに表示するには、この関数を呼び出します。  
  
```  
virtual void SetDefaultTitle(CDocument* pDocument) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pDocument*  
 タイトルを設定するドキュメントへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定のタイトルの詳細については、の説明を参照してください。 **CDocTemplate::docName**で[CDocTemplate::GetDocString](#getdocstring)です。  
  
##  <a name="setserverinfo"></a>  CDocTemplate::SetServerInfo  
 サーバー ドキュメントが埋め込まれているまたはインプレースを編集するときに、リソースやクラスを決定します。  
  
```  
void SetServerInfo(
    UINT nIDOleEmbedding,  
    UINT nIDOleInPlaceServer = 0,  
    CRuntimeClass* pOleFrameClass = NULL,  
    CRuntimeClass* pOleViewClass = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDOleEmbedding*  
 埋め込みオブジェクトが別のウィンドウで開かれたときに使用されているリソースの ID。  
  
 `nIDOleInPlaceServer`  
 埋め込みオブジェクトが使用されているリソースの ID では、インプレース アクティブ化されます。  
  
 *pOleFrameClass*  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)インプレース アクティブ化が発生したときに作成されるフレーム ウィンドウ オブジェクトのクラスの情報を含む構造体。  
  
 *pOleViewClass*  
 ポインター、`CRuntimeClass`インプレース アクティブ化が発生したときに作成されるビュー オブジェクトのクラスの情報を含む構造体。  
  
### <a name="remarks"></a>コメント  
 ユーザーは、埋め込みオブジェクトのアクティブ化を要求したときに、サーバー アプリケーションによって使用されるリソースを識別するには、このメンバー関数を呼び出します。 これらのリソースは、メニューとアクセラレータ テーブルで構成されます。 通常、この関数は呼び出されます。、 `InitInstance` 、アプリケーションのです。  
  
 関連付けられたメニュー`nIDOleInPlaceServer`コンテナーのメニューで [サーバー] メニューをマージするを許可する区切り記号が含まれています。 サーバーとコンテナーのメニューのマージに関する詳細については、記事を参照してください。[メニューとリソース (OLE)](../../mfc/menus-and-resources-ole.md)です。  
  
##  <a name="createpreviewframe"></a>  CDocTemplate::CreatePreviewFrame  
 リッチ プレビューに使用する子フレームを作成します。  
  
```  
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 (通常は、シェルによって提供される) の親ウィンドウへのポインター。  
  
 `pDoc`  
 内容をプレビューは、ドキュメント オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 有効なポインター、`CFrameWnd`オブジェクト、または`NULL`作成が失敗した場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpreviewinfo"></a>  CDocTemplate::SetPreviewInfo  
 プロセスのプレビュー ハンドラーの出力を設定します。  
  
```  
void SetPreviewInfo(
    UINT nIDPreviewFrame,  
    CRuntimeClass* pPreviewFrameClass = NULL,  
    CRuntimeClass* pPreviewViewClass = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDPreviewFrame`  
 プレビュー フレームのリソース ID を指定します。  
  
 `pPreviewFrameClass`  
 プレビュー フレームのランタイム クラス情報構造体へのポインターを指定します。  
  
 `pPreviewViewClass`  
 プレビュー ビューのランタイム クラス情報構造体へのポインターを指定します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数クラス](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CScrollView クラス](../../mfc/reference/cscrollview-class.md)   
 [CEditView クラス](../../mfc/reference/ceditview-class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)
