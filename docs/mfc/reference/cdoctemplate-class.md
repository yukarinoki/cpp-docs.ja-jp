---
title: CDocTemplate クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 3b2d84af9be8e5c606cde8794b51e12207dcdec9
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426073"
---
# <a name="cdoctemplate-class"></a>CDocTemplate クラス

ドキュメント テンプレートの基本的な機能を定義する抽象基底クラスです。

## <a name="syntax"></a>構文

```
class CDocTemplate : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|Name|Description|
|----------|-----------------|
|[CDocTemplate:: CDocTemplate](#cdoctemplate)|`CDocTemplate` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CDocTemplate:: AddDocument](#adddocument)|テンプレートにドキュメントを追加します。|
|[CDocTemplate:: CloseAllDocuments](#closealldocuments)|このテンプレートに関連付けられているすべてのドキュメントを閉じます。|
|[CDocTemplate:: CreateNewDocument](#createnewdocument)|新しいドキュメントを作成します。|
|[CDocTemplate:: CreateNewFrame](#createnewframe)|ドキュメントとビューを含む新しいフレームウィンドウを作成します。|
|[CDocTemplate:: CreateOleFrame](#createoleframe)|OLE 対応のフレームウィンドウを作成します。|
|[CDocTemplate:: Createプレビューフレーム](#createpreviewframe)|リッチプレビューに使用する子フレームを作成します。|
|[CDocTemplate:: GetDocString](#getdocstring)|ドキュメントの種類に関連付けられている文字列を取得します。|
|[CDocTemplate:: GetFirstDocPosition](#getfirstdocposition)|このテンプレートに関連付けられている最初のドキュメントの位置を取得します。|
|[CDocTemplate:: GetNextDoc](#getnextdoc)|ドキュメントと次のドキュメントの位置を取得します。|
|[CDocTemplate:: InitialUpdateFrame](#initialupdateframe)|フレームウィンドウを初期化し、必要に応じて表示します。|
|[CDocTemplate:: LoadTemplate](#loadtemplate)|指定された `CDocTemplate` または派生クラスのリソースを読み込みます。|
|[CDocTemplate:: MatchDocType](#matchdoctype)|ドキュメントの種類とこのテンプレートの一致の信頼度を決定します。|
|[CDocTemplate:: OpenDocumentFile](#opendocumentfile)|パス名で指定されたファイルを開きます。|
|[CDocTemplate:: RemoveDocument](#removedocument)|テンプレートからドキュメントを削除します。|
|[CDocTemplate:: SaveAllModified](#saveallmodified)|このテンプレートに関連付けられている、変更されたすべてのドキュメントを保存します。|
|[CDocTemplate:: SetContainerInfo](#setcontainerinfo)|埋め込み先 OLE 項目を編集するときに、OLE コンテナーのリソースを決定します。|
|[CDocTemplate:: SetDefaultTitle](#setdefaulttitle)|ドキュメントウィンドウのタイトルバーに既定のタイトルを表示します。|
|[CDocTemplate:: SetPreviewInfo](#setpreviewinfo)|プロセスプレビューハンドラーが不足しています。|
|[CDocTemplate:: SetServerInfo](#setserverinfo)|サーバードキュメントが埋め込まれているか、埋め込み先で編集されている場合に、リソースとクラスを決定します。|

## <a name="remarks"></a>解説

通常、アプリケーションの `InitInstance` 関数の実装には、1つまたは複数のドキュメントテンプレートを作成します。 ドキュメントテンプレートでは、次の3種類のクラス間のリレーションシップを定義します。

- `CDocument`から派生するドキュメントクラス。

- ビュークラス。上に一覧表示されているドキュメントクラスのデータを表示します。 このクラスは、`CView`、`CScrollView`、`CFormView`、または `CEditView`から派生できます。 (`CEditView` 直接使用することもできます)。

- ビューを含むフレームウィンドウクラス。 シングルドキュメントインターフェイス (SDI) アプリケーションの場合は、`CFrameWnd`からこのクラスを派生させます。 マルチドキュメントインターフェイス (MDI) アプリケーションの場合は、`CMDIChildWnd`からこのクラスを派生させます。 フレームウィンドウの動作をカスタマイズする必要がない場合は、独自のクラスを派生させずに、`CFrameWnd` または `CMDIChildWnd` を直接使用できます。

アプリケーションには、サポートするドキュメントの種類ごとに1つのドキュメントテンプレートがあります。 たとえば、アプリケーションがスプレッドシートとテキストドキュメントの両方をサポートしている場合、アプリケーションには2つのドキュメントテンプレートオブジェクトがあります。 各ドキュメントテンプレートは、その種類のすべてのドキュメントの作成と管理を行います。

ドキュメントテンプレートには、ドキュメント、ビュー、およびフレームウィンドウクラスの `CRuntimeClass` オブジェクトへのポインターが格納されます。 これらの `CRuntimeClass` オブジェクトは、ドキュメントテンプレートを構築するときに指定します。

ドキュメントテンプレートには、ドキュメントの種類 (メニュー、アイコン、アクセラレータテーブルリソースなど) で使用されるリソースの ID が含まれています。 ドキュメントテンプレートには、そのドキュメントの種類に関する追加情報を含む文字列も含まれています。 これには、ドキュメントの種類の名前 ("ワークシート" など) とファイル拡張子 (".xls" など) が含まれます。 必要に応じて、アプリケーションのユーザーインターフェイス、Windows ファイルマネージャー、およびオブジェクトのリンクと埋め込み (OLE) のサポートによって使用される他の文字列を含めることができます。

アプリケーションが OLE コンテナーまたはサーバーである場合、ドキュメントテンプレートでは、埋め込み先でのアクティブ化時に使用されるメニューの ID も定義されます。 アプリケーションが OLE サーバーである場合、ドキュメントテンプレートは、埋め込み先でのアクティブ化時に使用されるツールバーとメニューの ID を定義します。 これらの追加の OLE リソースを指定するには、`SetContainerInfo` と `SetServerInfo`を呼び出します。

`CDocTemplate` は抽象クラスであるため、クラスを直接使用することはできません。 一般的なアプリケーションでは、SDI を実装する Microsoft Foundation Class ライブラリ: `CSingleDocTemplate`によって提供される2つの `CDocTemplate`派生クラス、および MDI を実装する `CMultiDocTemplate`を使用します。 ドキュメントテンプレートの使用方法の詳細については、これらのクラスを参照してください。

アプリケーションで、SDI または MDI とは基本的に異なるユーザーインターフェイスパラダイムが必要な場合は、`CDocTemplate`から独自のクラスを派生させることができます。

`CDocTemplate`の詳細については、「[ドキュメントテンプレート」と「ドキュメント/ビューの作成プロセス](../../mfc/document-templates-and-the-document-view-creation-process.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocTemplate`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="adddocument"></a>CDocTemplate:: AddDocument

テンプレートにドキュメントを追加するには、この関数を使用します。

```
virtual void AddDocument(CDocument* pDoc);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
追加するドキュメントへのポインター。

### <a name="remarks"></a>解説

派生クラス[CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)と[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)は、この関数をオーバーライドします。 `CDocTemplate`から独自のドキュメントテンプレートクラスを派生させる場合は、派生クラスでこの関数をオーバーライドする必要があります。

##  <a name="cdoctemplate"></a>CDocTemplate:: CDocTemplate

`CDocTemplate` オブジェクトを構築します。

```
CDocTemplate (
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>パラメーター

*nIDResource*<br/>
ドキュメントの種類で使用されるリソースの ID を指定します。 これには、メニュー、アイコン、アクセラレータテーブル、および文字列リソースが含まれます。

文字列リソースは、' \n ' 文字で区切られた最大7つの部分文字列で構成されます (部分文字列が含まれていない場合、' \n ' 文字はプレースホルダーとして必要です)。ただし、末尾の ' \n ' 文字は必要ありません)。これらの部分文字列は、ドキュメントの種類を記述します。 部分文字列の詳細については、「 [GetDocString](#getdocstring)」を参照してください。 この文字列リソースは、アプリケーションのリソースファイルにあります。 次に例を示します。

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

文字列の先頭が ' \n ' 文字であることに注意してください。これは、最初の部分文字列が MDI アプリケーションで使用されていないためです。したがって、は含まれていません。 この文字列は、文字列エディターを使用して編集できます。文字列全体は、7つの個別のエントリとしてではなく、文字列エディターに単一のエントリとして表示されます。

*pDocClass*<br/>
ドキュメントクラスの `CRuntimeClass` オブジェクトを指します。 このクラスは、ドキュメントを表すために定義する `CDocument`派生クラスです。

*pFrameClass*<br/>
フレームウィンドウクラスの `CRuntimeClass` オブジェクトをポイントします。 このクラスは、`CFrameWnd`派生クラスにすることができます。また、メインフレームウィンドウに既定の動作が必要な場合は、それ自体 `CFrameWnd` できます。

*pViewClass*<br/>
ビュークラスの `CRuntimeClass` オブジェクトをポイントします。 このクラスは、ドキュメントを表示するために定義する `CView`派生クラスです。

### <a name="remarks"></a>解説

`CDocTemplate` オブジェクトを構築するには、このメンバー関数を使用します。 `CDocTemplate` オブジェクトを動的に割り当て、アプリケーションクラスの `InitInstance` メンバー関数から[CWinApp::、adddoctemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate)に渡します。

##  <a name="closealldocuments"></a>CDocTemplate:: CloseAllDocuments

開いているすべてのドキュメントを閉じるには、このメンバー関数を呼び出します。

```
virtual void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>パラメーター

*bEndSession*<br/>
使用されていません。

### <a name="remarks"></a>解説

このメンバー関数は、通常、File Exit コマンドの一部として使用されます。 この関数の既定の実装では、 [CDocument::D eletecontents](../../mfc/reference/cdocument-class.md#deletecontents)メンバー関数を呼び出してドキュメントのデータを削除した後、ドキュメントに関連付けられているすべてのビューのフレームウィンドウを閉じます。

ドキュメントを閉じる前に、ユーザーに特別なクリーンアップ処理を実行させる必要がある場合は、この関数をオーバーライドします。 たとえば、ドキュメントがデータベース内のレコードを表している場合は、この関数をオーバーライドしてデータベースを閉じることができます。

##  <a name="createnewdocument"></a>CDocTemplate:: CreateNewDocument

このメンバー関数を呼び出して、このドキュメントテンプレートに関連付けられている型の新しいドキュメントを作成します。

```
virtual CDocument* CreateNewDocument();
```

### <a name="return-value"></a>戻り値

新しく作成されたドキュメントへのポインター。エラーが発生した場合は NULL。

##  <a name="createnewframe"></a>CDocTemplate:: CreateNewFrame

ドキュメントとビューを含む新しいフレームウィンドウを作成します。

```
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,
    CFrameWnd* pOther);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
新しいフレームウィンドウが参照するドキュメント。 NULL にすることができます。

*その他*<br/>
新しいフレームウィンドウの基になるフレームウィンドウ。 NULL にすることができます。

### <a name="return-value"></a>戻り値

新しく作成されたフレームウィンドウへのポインター。エラーが発生した場合は NULL。

### <a name="remarks"></a>解説

`CreateNewFrame` は、コンストラクターに渡された `CRuntimeClass` オブジェクトを使用して、ビューとドキュメントが添付された新しいフレームウィンドウを作成します。 *Pdoc*パラメーターが NULL の場合、フレームワークはトレースメッセージを出力します。

*Popoparameter*は、Window New コマンドを実装するために使用されます。 新しいフレームウィンドウをモデル化するためのフレームウィンドウが用意されています。 通常、新しいフレームウィンドウは非表示で作成されます。 File New および File Open の標準フレームワークの実装の外部でフレームウィンドウを作成するには、この関数を呼び出します。

##  <a name="createoleframe"></a>CDocTemplate:: CreateOleFrame

OLE フレームウィンドウを作成します。

```
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,
    CDocument* pDoc,
    BOOL bCreateView);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
フレームの親ウィンドウへのポインター。

*pDoc*<br/>
新しい OLE フレームウィンドウが参照するドキュメントへのポインター。

*bCreateView*<br/>
ビューをフレームと共に作成するかどうかを決定します。

### <a name="return-value"></a>戻り値

成功した場合は、フレームウィンドウへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

*BCreateView*が0の場合、空のフレームが作成されます。

##  <a name="getdocstring"></a>CDocTemplate:: GetDocString

ドキュメントの種類に関連付けられている文字列を取得します。

```
virtual BOOL GetDocString(
    CString& rString,
    enum DocStringIndex index) const;
```

### <a name="parameters"></a>パラメーター

*rString*<br/>
関数が返されたときに文字列を格納する `CString` オブジェクトへの参照。

*インデックス*<br/>
ドキュメントの種類を記述する文字列から取得される部分文字列のインデックス。 このパラメーターには、次のいずれかの値を指定できます。

- アプリケーションウィンドウのタイトルバーに表示される `CDocTemplate::windowTitle` 名 (たとえば、"Microsoft Excel")。 SDI アプリケーションのドキュメントテンプレートにのみ存在します。

- 既定のドキュメント名 (たとえば、"シート") のルートを `CDocTemplate::docName` します。 このルートと数値は、ユーザーが [ファイル] メニューから新しいコマンドを選択するたびに、この種類の新しいドキュメントの既定の名前として使用されます (たとえば、"Sheet1" や "Sheet2")。 指定しない場合は、"無題" が既定値として使用されます。

- このドキュメントの種類の `CDocTemplate::fileNewName` 名。 アプリケーションで複数の種類のドキュメントがサポートされている場合、この文字列は [ファイル] [新規] ダイアログボックス ("ワークシート" など) に表示されます。 指定しない場合、ファイルの New コマンドを使用してドキュメントの種類にアクセスすることはできません。

- ドキュメントの種類の説明と、この種類のドキュメントに一致するワイルドカードフィルターを `CDocTemplate::filterName` します。 この文字列は、[ファイルを開く] ダイアログボックスの [種類のファイルの一覧表示] ドロップダウンリストに表示されます (例: "ワークシート (* .xls)")。 指定されていない場合、[ファイルを開く] コマンドを使用してドキュメントの種類にアクセスすることはできません。

- この種類のドキュメントの `CDocTemplate::filterExt` 拡張機能 (例 ".xls")。 指定されていない場合、[ファイルを開く] コマンドを使用してドキュメントの種類にアクセスすることはできません。

- Windows によって管理される登録データベースに格納されるドキュメントの種類の `CDocTemplate::regFileTypeId` 識別子。 この文字列は内部でのみ使用されます (たとえば、"ExcelWorksheet")。 指定しない場合、ドキュメントの種類を Windows ファイルマネージャーに登録できません。

- 登録データベースに格納されるドキュメントの種類の名前を `CDocTemplate::regFileTypeName` します。 この文字列は、登録データベースにアクセスするアプリケーション (たとえば、"Microsoft Excel ワークシート") のダイアログボックスに表示される場合があります。

### <a name="return-value"></a>戻り値

指定した部分文字列が見つかった場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

ドキュメントの種類を記述する特定の部分文字列を取得するには、この関数を呼び出します。 これらの部分文字列を含む文字列は、ドキュメントテンプレートに格納され、アプリケーションのリソースファイル内の文字列から派生します。 フレームワークは、この関数を呼び出して、アプリケーションのユーザーインターフェイスに必要な文字列を取得します。 アプリケーションのドキュメントのファイル名拡張子を指定した場合は、Windows 登録データベースにエントリを追加するときに、フレームワークによってこの関数も呼び出されます。これにより、Windows ファイルマネージャーからドキュメントを開くことができます。

`CDocTemplate`から独自のクラスを派生させる場合にのみ、この関数を呼び出します。

##  <a name="getfirstdocposition"></a>CDocTemplate:: GetFirstDocPosition

このテンプレートに関連付けられている最初のドキュメントの位置を取得します。

```
virtual POSITION GetFirstDocPosition() const = 0;
```

### <a name="return-value"></a>戻り値

このドキュメントテンプレートに関連付けられているドキュメントの一覧を反復処理するために使用できる位置の値。リストが空の場合は NULL。

### <a name="remarks"></a>解説

このテンプレートに関連付けられているドキュメントのリスト内の最初のドキュメントの位置を取得するには、この関数を使用します。 このテンプレートに関連付けられているドキュメントの一覧を反復処理するには、値を[CDocTemplate:: GetNextDoc](#getnextdoc)の引数として使用します。

[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)と[CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)は、どちらもこの純粋仮想関数をオーバーライドします。 `CDocTemplate` から派生したクラスも、この関数をオーバーライドする必要があります。

##  <a name="getnextdoc"></a>CDocTemplate:: GetNextDoc

*Rpo*によって識別されるリスト要素を取得し、 *rpo*をリスト内の次のエントリの位置の値に設定します。

```
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;
```

### <a name="return-value"></a>戻り値

このテンプレートに関連付けられているドキュメントの一覧にある次のドキュメントへのポインター。

### <a name="parameters"></a>パラメーター

*求める*<br/>
[Getfirstdocposition](#getfirstdocposition)または `GetNextDoc`への前回の呼び出しによって返された位置の値への参照。

### <a name="remarks"></a>解説

取得した要素がリスト内の最後の要素である場合、 *rpo*の新しい値は NULL に設定されます。

[Getfirstdocposition](#getfirstdocposition)の呼び出しを使用して初期位置を設定した場合は、前方反復ループで `GetNextDoc` を使用できます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

##  <a name="initialupdateframe"></a>CDocTemplate:: InitialUpdateFrame

フレームウィンドウを初期化し、必要に応じて表示します。

```
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,
    CDocument* pDoc,
    BOOL bMakeVisible = TRUE);
```

### <a name="parameters"></a>パラメーター

*pFrame*<br/>
初期更新が必要なフレームウィンドウ。

*pDoc*<br/>
フレームが関連付けられているドキュメント。 NULL にすることができます。

*bMakeVisible*<br/>
フレームが表示されアクティブになるかどうかを示します。

### <a name="remarks"></a>解説

`CreateNewFrame`を使用して新しいフレームを作成した後、`IntitialUpdateFrame` を呼び出します。 この関数を呼び出すと、そのフレームウィンドウ内のビューが `OnInitialUpdate` 呼び出しを受け取るようになります。 また、以前にアクティブなビューがない場合は、フレームウィンドウのプライマリビューがアクティブになります。プライマリビューは、AFX_IDW_PANE_FIRST の子 ID を持つビューです。 最後に、 *Bmakevisible*が0以外の場合、フレームウィンドウが表示されます。 *Bmakevisible*がゼロの場合、フレームウィンドウの現在のフォーカスと可視状態は変更されません。

フレームワークの File New と File Open の実装を使用する場合は、この関数を呼び出す必要はありません。

##  <a name="loadtemplate"></a>CDocTemplate:: LoadTemplate

指定された `CDocTemplate` または派生クラスのリソースを読み込みます。

```
virtual void LoadTemplate();
```

### <a name="remarks"></a>解説

このメンバー関数は、指定された `CDocTemplate` または派生クラスのリソースを読み込むために、フレームワークによって呼び出されます。 通常、テンプレートがグローバルに構築されている場合を除き、構築時に呼び出されます。 この場合、`LoadTemplate` の呼び出しは、 [CWinApp::、adddoctemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate)が呼び出されるまで遅延されます。

##  <a name="matchdoctype"></a>CDocTemplate:: MatchDocType

ドキュメントの種類とこのテンプレートの一致の信頼度を決定します。

```
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,
    CDocument*& rpDocMatch);
```

### <a name="parameters"></a>パラメーター

*lpszPathName*<br/>
型を確認するファイルのパス名。

*"Rpq Docmatch"*<br/>
*Lpszpathname*によって指定されたファイルが既に開いている場合、一致するドキュメントが割り当てられているドキュメントへのポインター。

### <a name="return-value"></a>戻り値

**信頼**の列挙の値。次のように定義されています。

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

### <a name="remarks"></a>解説

ファイルを開くために使用するドキュメントテンプレートの種類を決定するには、この関数を使用します。 たとえば、アプリケーションで複数のファイルの種類がサポートされている場合、この関数を使用すると、各テンプレートの `MatchDocType` を呼び出し、返された信頼度に従ってテンプレートを選択することで、特定のファイルに適したドキュメントテンプレートを特定できます。

*Lpszpathname*によって指定されたファイルが既に開いている場合、この関数は `CDocTemplate::yesAlreadyOpen` を返し、ファイルの `CDocument` オブジェクトをオブジェクトに*コピーします。*

ファイルが開かれていなくても、 *Lpszpathname*の拡張子が `CDocTemplate::filterExt`で指定された拡張子と一致する場合、この関数は `CDocTemplate::yesAttemptNative` を返し、[*の設定] を NULL*にします。 `CDocTemplate::filterExt`の詳細については、「 [CDocTemplate:: GetDocString](#getdocstring)」を参照してください。

どちらのケースも true でない場合、関数は `CDocTemplate::yesAttemptForeign`を返します。

既定の実装では、`CDocTemplate::maybeAttemptForeign` も `CDocTemplate::maybeAttemptNative`も返されません。 この関数をオーバーライドして、アプリケーションに適した型一致ロジックを実装します。たとえば、**信頼**の列挙体からのこれら2つの値を使用します。

##  <a name="opendocumentfile"></a>CDocTemplate:: OpenDocumentFile

パスで指定されたファイルを開きます。

```
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;

virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU) = 0;
```

### <a name="parameters"></a>パラメーター

*lpszPathName*<br/>
から開くドキュメントを含むファイルのパスへのポインター。

*bAddToMRU*<br/>
からTRUE は、ドキュメントが最新のファイルの1つであることを示します。FALSE は、ドキュメントが最新のファイルの1つではないことを示します。

### <a name="return-value"></a>戻り値

ファイル名が*Lpszpathname*; であるドキュメントへのポインター失敗した場合は NULL です。

### <a name="remarks"></a>解説

*Lpszpathname*によって指定されたパスを持つファイルを開きます。 *Lpszpathname*が NULL の場合、このテンプレートに関連付けられている種類のドキュメントを含む新しいファイルが作成されます。

##  <a name="removedocument"></a>CDocTemplate:: RemoveDocument

このテンプレートに関連付けられているドキュメントの一覧から、 *Pdoc*が指すドキュメントを削除します。

```
virtual void RemoveDocument(CDocument* pDoc);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
削除するドキュメントへのポインター。

### <a name="remarks"></a>解説

派生クラス `CMultiDocTemplate` と `CSingleDocTemplate` はこの関数をオーバーライドします。 `CDocTemplate`から独自のドキュメントテンプレートクラスを派生させる場合は、派生クラスでこの関数をオーバーライドする必要があります。

##  <a name="saveallmodified"></a>CDocTemplate:: SaveAllModified

変更されたすべてのドキュメントを保存します。

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>戻り値

成功した場合は0以外。それ以外の場合は0です。

##  <a name="setcontainerinfo"></a>CDocTemplate:: SetContainerInfo

埋め込み先 OLE 項目を編集するときに、OLE コンテナーのリソースを決定します。

```
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```

### <a name="parameters"></a>パラメーター

*nIDOleInPlaceContainer*<br/>
埋め込みオブジェクトがアクティブになったときに使用されるリソースの ID。

### <a name="remarks"></a>解説

OLE オブジェクトが埋め込み先でアクティブになっているときに使用されるリソースを設定するには、この関数を呼び出します。 これらのリソースには、メニューとアクセラレータテーブルが含まれる場合があります。 この関数は、通常、アプリケーションの[CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)関数で呼び出されます。

*NIDOleInPlaceContainer*に関連付けられているメニューには、アクティブ化されたインプレース項目のメニューをコンテナーアプリケーションのメニューとマージできるようにするための区切り記号が含まれています。 サーバーメニューとコンテナーメニューのマージの詳細については、「[メニューとリソース (OLE)](../../mfc/menus-and-resources-ole.md)」を参照してください。

##  <a name="setdefaulttitle"></a>CDocTemplate:: SetDefaultTitle

この関数を呼び出して、ドキュメントの既定のタイトルを読み込み、ドキュメントのタイトルバーに表示します。

```
virtual void SetDefaultTitle(CDocument* pDocument) = 0;
```

### <a name="parameters"></a>パラメーター

*pDocument*<br/>
タイトルが設定されるドキュメントへのポインター。

### <a name="remarks"></a>解説

既定のタイトルの詳細については、「 [CDocTemplate:: GetDocString](#getdocstring)の `CDocTemplate::docName` の説明を参照してください。

##  <a name="setserverinfo"></a>CDocTemplate:: SetServerInfo

サーバードキュメントが埋め込まれているか、埋め込み先で編集されている場合に、リソースとクラスを決定します。

```
void SetServerInfo(
    UINT nIDOleEmbedding,
    UINT nIDOleInPlaceServer = 0,
    CRuntimeClass* pOleFrameClass = NULL,
    CRuntimeClass* pOleViewClass = NULL);
```

### <a name="parameters"></a>パラメーター

*nIDOleEmbedding*<br/>
埋め込みオブジェクトが別のウィンドウで開かれたときに使用されるリソースの ID です。

*nIDOleInPlaceServer*<br/>
埋め込みオブジェクトがインプレースでアクティブ化されるときに使用されるリソースの ID。

*pOleFrameClass*<br/>
インプレースアクティブ化が発生したときに作成されるフレームウィンドウオブジェクトのクラス情報を含む[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。

*pOleViewClass*<br/>
インプレースアクティブ化が発生したときに作成されるビューオブジェクトのクラス情報を格納している `CRuntimeClass` 構造体へのポインター。

### <a name="remarks"></a>解説

ユーザーが埋め込みオブジェクトのアクティベーションを要求したときに、サーバーアプリケーションによって使用されるリソースを識別するには、このメンバー関数を呼び出します。 これらのリソースは、メニューとアクセラレータテーブルで構成されています。 この関数は、通常、アプリケーションの `InitInstance` で呼び出されます。

*NIDOleInPlaceServer*に関連付けられているメニューには、サーバーメニューをコンテナーのメニューとマージできるようにするための区切り記号が含まれています。 サーバーメニューとコンテナーメニューのマージの詳細については、「[メニューとリソース (OLE)](../../mfc/menus-and-resources-ole.md)」を参照してください。

##  <a name="createpreviewframe"></a>CDocTemplate:: Createプレビューフレーム

リッチプレビューに使用する子フレームを作成します。

```
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,
    CDocument* pDoc);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
親ウィンドウへのポインター (通常はシェルによって提供される)。

*pDoc*<br/>
コンテンツがプレビューされるドキュメントオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

`CFrameWnd` オブジェクトへの有効なポインター。作成に失敗した場合は NULL。

### <a name="remarks"></a>解説

##  <a name="setpreviewinfo"></a>CDocTemplate:: SetPreviewInfo

アウトプロセスプレビューハンドラーを設定します。

```
void SetPreviewInfo(
    UINT nIDPreviewFrame,
    CRuntimeClass* pPreviewFrameClass = NULL,
    CRuntimeClass* pPreviewViewClass = NULL);
```

### <a name="parameters"></a>パラメーター

*nIDPreviewFrame*<br/>
プレビューフレームのリソース ID を指定します。

*Pプレビュー Frameclass*<br/>
プレビューフレームのランタイムクラス情報構造体へのポインターを指定します。

*Pプレビュー Viewclass*<br/>
プレビュービューのランタイムクラス情報構造体へのポインターを指定します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CSingleDocTemplate クラス](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CScrollView クラス](../../mfc/reference/cscrollview-class.md)<br/>
[CEditView クラス](../../mfc/reference/ceditview-class.md)<br/>
[CFormView クラス](../../mfc/reference/cformview-class.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)
