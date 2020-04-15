---
title: クラス
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
ms.openlocfilehash: 3376b8febe8ae4586ce649f3f83386875acb678f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375502"
---
# <a name="cdoctemplate-class"></a>クラス

ドキュメント テンプレートの基本的な機能を定義する抽象基底クラスです。

## <a name="syntax"></a>構文

```
class CDocTemplate : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[をクリックします。](#cdoctemplate)|`CDocTemplate` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ドキュメントの追加](#adddocument)|テンプレートに文書を追加します。|
|[ドキュメントテンプレート::すべてのドキュメントを閉じる](#closealldocuments)|このテンプレートに関連付けられているすべてのドキュメントを閉じます。|
|[ドキュメントテンプレート::新しいドキュメントの作成](#createnewdocument)|新しいドキュメントを作成します。|
|[を作成します。](#createnewframe)|ドキュメントとビューを含む新しいフレーム ウィンドウを作成します。|
|[を作成します。](#createoleframe)|OLE 対応のフレーム ウィンドウを作成します。|
|[をクリックします。](#createpreviewframe)|リッチ プレビューに使用する子フレームを作成します。|
|[をクリックします。](#getdocstring)|ドキュメントの種類に関連付けられている文字列を取得します。|
|[をクリックします。](#getfirstdocposition)|このテンプレートに関連付けられている最初の文書の位置を取得します。|
|[次のドキュメントを作成します。](#getnextdoc)|ドキュメントと次のドキュメントの位置を取得します。|
|[初期更新フレーム](#initialupdateframe)|フレーム ウィンドウを初期化し、必要に応じて表示します。|
|[を読み込む](#loadtemplate)|指定`CDocTemplate`されたクラスまたは派生クラスのリソースを読み込みます。|
|[を指定します。](#matchdoctype)|ドキュメント タイプとこのテンプレートの一致の信頼度を決定します。|
|[ドキュメント ファイルを開く](#opendocumentfile)|パス名で指定されたファイルを開きます。|
|[ドキュメントの削除](#removedocument)|テンプレートから文書を削除します。|
|[を変更しました。](#saveallmodified)|このテンプレートに関連付けられている、変更されたすべてのドキュメントを保存します。|
|[を設定します。](#setcontainerinfo)|OLE アイテムを編集するときに OLE コンテナのリソースを決定します。|
|[を設定します。](#setdefaulttitle)|ドキュメント ウィンドウのタイトル バーに既定のタイトルを表示します。|
|[を設定します。](#setpreviewinfo)|プロセス プレビュー ハンドラからセットアップします。|
|[を設定します。](#setserverinfo)|サーバー ドキュメントが埋め込みまたは編集されるときにリソースとクラスを決定します。|

## <a name="remarks"></a>解説

通常、アプリケーションの`InitInstance`関数の実装で 1 つ以上のドキュメント テンプレートを作成します。 ドキュメント テンプレートは、次の 3 種類のクラス間の関係を定義します。

- から派生するドキュメント クラス`CDocument`。

- 上記のドキュメント クラスのデータを表示するビュー クラス。 このクラス`CView`は、 `CScrollView`、 、 `CFormView`、 `CEditView`、 、 から派生できます。 (直接使用`CEditView`することもできます。

- ビューを含むフレーム ウィンドウ クラス。 単一のドキュメント インターフェイス (SDI) アプリケーションの場合は`CFrameWnd`、このクラスを から派生させます。 マルチ ドキュメント インターフェイス (MDI) アプリケーションの場合は、`CMDIChildWnd`このクラスを から派生します。 フレーム ウィンドウの動作をカスタマイズする必要がない場合は、独自のクラスを派生`CFrameWnd`せずに`CMDIChildWnd`使用するか直接使用できます。

アプリケーションでは、サポートするドキュメントの種類ごとに 1 つのドキュメント テンプレートがあります。 たとえば、アプリケーションがスプレッドシートとテキスト ドキュメントの両方をサポートしている場合、アプリケーションには 2 つのドキュメント テンプレート オブジェクトがあります。 各ドキュメント テンプレートは、その種類のすべてのドキュメントを作成および管理します。

ドキュメント テンプレートには、ドキュメント、ビュー `CRuntimeClass` 、およびフレーム ウィンドウクラスのオブジェクトへのポインターが格納されます。 これらの`CRuntimeClass`オブジェクトは、ドキュメント テンプレートを作成するときに指定します。

ドキュメント テンプレートには、ドキュメント タイプで使用されるリソースの ID (メニュー、アイコン、アクセラレータ テーブルリソースなど) が含まれています。 また、ドキュメント テンプレートには、ドキュメントの種類に関する追加情報を含む文字列も含まれています。 ドキュメントの種類 ("ワークシート" など) とファイル拡張子 (".xls" など) の名前が含まれます。 必要に応じて、アプリケーションのユーザー インターフェイス、Windows ファイル マネージャー、およびオブジェクトのリンクと埋め込み (OLE) のサポートで使用される他の文字列を含めることができます。

アプリケーションが OLE コンテナーまたはサーバーである場合、ドキュメント テンプレートは、インプレース アクティブ化の際に使用されるメニューの ID も定義します。 アプリケーションが OLE サーバーの場合、ドキュメント テンプレートは、インプレース アクティブ化の際に使用されるツール バーとメニューの ID を定義します。 これらの追加の OLE リソースは`SetContainerInfo`、`SetServerInfo`および を呼び出して指定します。

抽象`CDocTemplate`クラスであるため、クラスを直接使用することはできません。 一般的なアプリケーションでは、Microsoft `CDocTemplate` `CSingleDocTemplate` `CMultiDocTemplate`Foundation クラス ライブラリによって提供される 2 つの派生クラスのいずれかを使用します。 ドキュメント テンプレートの使用方法の詳細については、これらのクラスを参照してください。

アプリケーションで SDI や MDI とは根本的に異なるユーザー インターフェイス パラダイムが必要な場合は、`CDocTemplate`から独自のクラスを派生させることができます。

の詳細については、「[ドキュメント テンプレートとドキュメント/ビュー作成プロセス](../../mfc/document-templates-and-the-document-view-creation-process.md)」を参照してください。 `CDocTemplate`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocTemplate`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cdoctemplateadddocument"></a><a name="adddocument"></a>ドキュメントの追加

この関数を使用して、テンプレートにドキュメントを追加します。

```
virtual void AddDocument(CDocument* pDoc);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
追加するドキュメントへのポインター。

### <a name="remarks"></a>解説

派生クラス[CMultiDoc テンプレート](../../mfc/reference/cmultidoctemplate-class.md)と[C1Doc テンプレート](../../mfc/reference/csingledoctemplate-class.md)は、この関数をオーバーライドします。 から`CDocTemplate`独自のドキュメント テンプレート クラスを派生させる場合、派生クラスはこの関数をオーバーライドする必要があります。

## <a name="cdoctemplatecdoctemplate"></a><a name="cdoctemplate"></a>をクリックします。

`CDocTemplate` オブジェクトを構築します。

```
CDocTemplate (
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
ドキュメントタイプで使用されるリソースの ID を指定します。 これには、メニュー、アイコン、アクセラレータ テーブル、および文字列リソースが含まれます。

文字列リソースは、'\n' 文字で区切られた最大 7 個の部分文字列で構成されます (部分文字列が含まれていない場合は、"\n" 文字がプレースホルダとして必要になりますが、末尾の '\n' 文字は必要ありません)。これらの部分文字列はドキュメントタイプを記述します。 部分文字列の詳細については、「 [GetDocString](#getdocstring)」を参照してください。 この文字列リソースは、アプリケーションのリソース ファイルにあります。 次に例を示します。

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

文字列は '\n' 文字で始まることに注意してください。これは、最初の部分文字列が MDI アプリケーションで使用されないため、含まれていないためです。 この文字列は、文字列エディタを使用して編集できます。文字列全体が、7 つの個別のエントリではなく、文字列エディタ内の単一のエントリとして表示されます。

*クラス*<br/>
ドキュメント クラス`CRuntimeClass`のオブジェクトへのポイント。 このクラスは、`CDocument`ドキュメントを表すために定義する派生クラスです。

*クラス*<br/>
フレーム ウィンドウ`CRuntimeClass`クラスのオブジェクトへのポイント。 このクラスは`CFrameWnd`、派生クラスにすることも、メイン フレーム`CFrameWnd`ウィンドウの既定の動作を行う場合は、それ自体にすることもできます。

*クラスを表示します。*<br/>
ビュー クラス`CRuntimeClass`のオブジェクトへのポイント。 このクラスは、`CView`ドキュメントを表示するために定義する派生クラスです。

### <a name="remarks"></a>解説

このメンバー関数を使用して、`CDocTemplate`オブジェクトを構築します。 オブジェクトを`CDocTemplate`動的に割り当て、アプリケーション クラスの`InitInstance`メンバー関数から[CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate)に渡します。

## <a name="cdoctemplateclosealldocuments"></a><a name="closealldocuments"></a>ドキュメントテンプレート::すべてのドキュメントを閉じる

開いているすべてのドキュメントを閉じるには、このメンバー関数を呼び出します。

```
virtual void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>パラメーター

*セッション*<br/>
使用されていません。

### <a name="remarks"></a>解説

このメンバー関数は、通常、ファイル終了コマンドの一部として使用されます。 この関数の既定の実装では[、CDocument::DeleteContents メンバー](../../mfc/reference/cdocument-class.md#deletecontents)関数を呼び出してドキュメントのデータを削除し、ドキュメントに添付されているすべてのビューのフレーム ウィンドウを閉じます。

ドキュメントを閉じる前にユーザーに特別なクリーンアップ処理を実行するように要求する場合は、この関数をオーバーライドします。 たとえば、ドキュメントがデータベース内のレコードを表す場合、この関数をオーバーライドしてデータベースを閉じる必要があります。

## <a name="cdoctemplatecreatenewdocument"></a><a name="createnewdocument"></a>ドキュメントテンプレート::新しいドキュメントの作成

このドキュメント テンプレートに関連付けられている種類の新しいドキュメントを作成します。

```
virtual CDocument* CreateNewDocument();
```

### <a name="return-value"></a>戻り値

新しく作成されたドキュメントへのポインター。

## <a name="cdoctemplatecreatenewframe"></a><a name="createnewframe"></a>を作成します。

ドキュメントとビューを含む新しいフレーム ウィンドウを作成します。

```
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,
    CFrameWnd* pOther);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
新しいフレーム ウィンドウが参照するドキュメント。 NULL にすることができます。

*その他*<br/>
新しいフレーム ウィンドウの基になるフレーム ウィンドウ。 NULL にすることができます。

### <a name="return-value"></a>戻り値

新しく作成されたフレーム ウィンドウへのポインター。

### <a name="remarks"></a>解説

`CreateNewFrame`は、`CRuntimeClass`コンストラクターに渡されたオブジェクトを使用して、ビューとドキュメントがアタッチされた新しいフレーム ウィンドウを作成します。 *pDoc*パラメーターが NULL の場合、フレームワークは TRACE メッセージを出力します。

*pOther*パラメーターは、ウィンドウ新規作成コマンドを実装するために使用されます。 新しいフレーム ウィンドウをモデル化するためのフレーム ウィンドウを提供します。 新しいフレーム ウィンドウは、通常は非表示に作成されます。 この関数を呼び出して、標準のフレームワーク実装の [ファイル新規作成] および [ファイルを開く] の外部にフレーム ウィンドウを作成します。

## <a name="cdoctemplatecreateoleframe"></a><a name="createoleframe"></a>を作成します。

OLE フレーム ウィンドウを作成します。

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
新しい OLE フレーム ウィンドウが参照するドキュメントへのポインター。

*ビューを作成します。*<br/>
フレームと共にビューを作成するかどうかを決定します。

### <a name="return-value"></a>戻り値

成功した場合はフレーム ウィンドウへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

*bCreateView*が 0 の場合は、空のフレームが作成されます。

## <a name="cdoctemplategetdocstring"></a><a name="getdocstring"></a>をクリックします。

ドキュメントの種類に関連付けられている文字列を取得します。

```
virtual BOOL GetDocString(
    CString& rString,
    enum DocStringIndex index) const;
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
関数が`CString`返されるときに文字列を格納するオブジェクトへの参照。

*index*<br/>
ドキュメントの種類を記述する文字列から取得される部分文字列のインデックス。 このパラメーターには、次のいずれかの値を指定できます。

- `CDocTemplate::windowTitle`アプリケーション ウィンドウのタイトル バーに表示される名前 ("Excel" など)。 SDI アプリケーションのドキュメント テンプレートにのみ表示されます。

- `CDocTemplate::docName`既定のドキュメント名 ("Sheet" など) のルートです。 ユーザーが [ファイル] メニューの [新規作成] をクリックすると、この種類の新しいドキュメントの既定の名前 ("Sheet1" や "Sheet2" など) に、このルートと数字が使用されます。 指定しない場合は、デフォルトとして「無題」が使用されます。

- `CDocTemplate::fileNewName`このドキュメント タイプの名前。 アプリケーションが複数の種類のドキュメントをサポートしている場合、この文字列は [新規作成] ダイアログ ボックス ("ワークシート" など) に表示されます。 指定しない場合、ファイルの新規作成コマンドを使用してドキュメントタイプにアクセスできません。

- `CDocTemplate::filterName`ドキュメントタイプの説明と、このタイプのドキュメントに一致するワイルドカードフィルタ。 この文字列は、[ファイルを開く] ダイアログ ボックスの [ファイルの種類] ボックスの一覧に表示されます (たとえば、"ワークシート (*.xls)")。 指定しない場合、ファイルを開くコマンドを使用してドキュメントタイプにアクセスできません。

- `CDocTemplate::filterExt`この種類のドキュメントの拡張子 (".xls" など)。 指定しない場合、ファイルを開くコマンドを使用してドキュメントタイプにアクセスできません。

- `CDocTemplate::regFileTypeId`Windows が管理する登録データベースに格納されるドキュメントタイプの識別子。 この文字列は内部使用専用です ("ExcelWorksheet" など)。 指定しない場合、ドキュメントの種類を Windows ファイル マネージャに登録することはできません。

- `CDocTemplate::regFileTypeName`登録データベースに格納するドキュメント タイプの名前。 この文字列は、登録データベースにアクセスするアプリケーションのダイアログ ボックス (たとえば、"Excel ワークシート" など) に表示されます。

### <a name="return-value"></a>戻り値

指定された部分文字列が見つかった場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ドキュメントの種類を記述する特定の部分文字列を取得します。 これらの部分文字列を含む文字列は、ドキュメント テンプレートに格納され、アプリケーションのリソース ファイル内の文字列から派生します。 フレームワークは、アプリケーションのユーザー インターフェイスに必要な文字列を取得するために、この関数を呼び出します。 アプリケーションのドキュメントにファイル名拡張子を指定した場合、Windows 登録データベースにエントリを追加するときに、フレームワークはこの関数を呼び出します。これにより、Windows ファイル マネージャからドキュメントを開けることができます。

から独自のクラスを派生する場合にのみ、この関数を`CDocTemplate`呼び出します。

## <a name="cdoctemplategetfirstdocposition"></a><a name="getfirstdocposition"></a>をクリックします。

このテンプレートに関連付けられている最初の文書の位置を取得します。

```
virtual POSITION GetFirstDocPosition() const = 0;
```

### <a name="return-value"></a>戻り値

このドキュメント テンプレートに関連付けられているドキュメントのリストを反復処理するために使用できる POSITION 値。リストが空の場合は NULL。

### <a name="remarks"></a>解説

この関数を使用して、このテンプレートに関連付けられたドキュメントのリスト内の最初の文書の位置を取得します。 テンプレートに関連付けられたドキュメントのリストを反復処理するには、位置値を[引数](#getnextdoc)として使用します。

[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)この純粋な仮想関数[は](../../mfc/reference/cmultidoctemplate-class.md)どちらもオーバーライドされます。 派生元のクラスも`CDocTemplate`この関数をオーバーライドする必要があります。

## <a name="cdoctemplategetnextdoc"></a><a name="getnextdoc"></a>次のドキュメントを作成します。

*rPos*で識別されるリスト要素を取得し *、rPos*をリスト内の次のエントリの POSITION 値に設定します。

```
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;
```

### <a name="return-value"></a>戻り値

このテンプレートに関連付けられているドキュメントの一覧の次のドキュメントへのポインター。

### <a name="parameters"></a>パラメーター

*Rpos*<br/>
前の呼び出しによって返された位置[値への参照](#getfirstdocposition)`GetNextDoc`。

### <a name="remarks"></a>解説

取得した要素がリストの最後の要素である場合 *、rPos*の新しい値は NULL に設定されます。

初期位置を`GetNextDoc` [GetFirstDocPosition](#getfirstdocposition)の呼び出しで設定する場合は、順方向反復ループで使用できます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

## <a name="cdoctemplateinitialupdateframe"></a><a name="initialupdateframe"></a>初期更新フレーム

フレーム ウィンドウを初期化し、必要に応じて表示します。

```
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,
    CDocument* pDoc,
    BOOL bMakeVisible = TRUE);
```

### <a name="parameters"></a>パラメーター

*フレーム*<br/>
初期更新が必要なフレーム ウィンドウ。

*pDoc*<br/>
フレームが関連付けられているドキュメント。 NULL にすることができます。

*ビクジブル*<br/>
フレームを表示してアクティブにするかどうかを示します。

### <a name="remarks"></a>解説

を`IntitialUpdateFrame`使用して新しいフレームを`CreateNewFrame`作成した後に呼び出す。 この関数を呼び出すと、そのフレーム ウィンドウ内`OnInitialUpdate`のビューが呼び出しを受け取ります。 また、以前アクティブなビューが存在しない場合は、フレーム ウィンドウのプライマリ ビューがアクティブになります。プライマリ ビューは、子 ID が AFX_IDW_PANE_FIRST のビューです。 最後に *、bMakeVisible*が 0 以外の場合、フレーム ウィンドウが表示されます。 *bMakeVisible*が 0 の場合、フレーム ウィンドウの現在のフォーカスと表示状態は変更されません。

フレームワークの File New および File Open の実装を使用する場合は、この関数を呼び出す必要はありません。

## <a name="cdoctemplateloadtemplate"></a><a name="loadtemplate"></a>を読み込む

指定`CDocTemplate`されたクラスまたは派生クラスのリソースを読み込みます。

```
virtual void LoadTemplate();
```

### <a name="remarks"></a>解説

このメンバー関数は、指定された`CDocTemplate`派生クラスのリソースを読み込むために、フレームワークによって呼び出されます。 通常、テンプレートがグローバルに構築されている場合を除き、構築時に呼び出されます。 その場合、呼び出し`LoadTemplate`は[CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate)が呼び出されるまで遅延されます。

## <a name="cdoctemplatematchdoctype"></a><a name="matchdoctype"></a>を指定します。

ドキュメント タイプとこのテンプレートの一致の信頼度を決定します。

```
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,
    CDocument*& rpDocMatch);
```

### <a name="parameters"></a>パラメーター

*パス名*<br/>
タイプが決定されるファイルのパス名。

*一致します。*<br/>
*lpszPathName*で指定されたファイルが既に開かれている場合、一致するドキュメントが割り当てられているドキュメントへのポインター。

### <a name="return-value"></a>戻り値

次のように定義されている**信頼度**列挙体の値。

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

この関数を使用して、ファイルを開くときに使用するドキュメント テンプレートの種類を決定します。 たとえば、アプリケーションで複数のファイルの種類をサポートしている場合、この関数を使用して、各テンプレートを順番に呼び出`MatchDocType`し、返される信頼値に応じてテンプレートを選択することで、特定のファイルに対して使用可能なドキュメント テンプレートのどれが適切かを判断できます。

*lpszPathName*で指定されたファイルが既に開かれている場合、`CDocTemplate::yesAlreadyOpen`この関数は`CDocument`*rpDocMatch*のオブジェクトにファイルのオブジェクトを返し、コピーします。

ファイルが開かれていないが *、lpszPathName*の拡張子が`CDocTemplate::filterExt`で指定された拡張子と一致`CDocTemplate::yesAttemptNative`する場合、この関数は*rpDocMatch*を NULL に戻し、設定します。 `CDocTemplate::filterExt`の詳細については、「[テンプレート::GetDocString](#getdocstring)」を参照してください。

どちらの場合も true の場合、`CDocTemplate::yesAttemptForeign`関数は を返します。

既定の実装では、`CDocTemplate::maybeAttemptForeign`または`CDocTemplate::maybeAttemptNative`が返されません。 この関数をオーバーライドして、**アプリケーション**に適した型一致ロジックを実装します。

## <a name="cdoctemplateopendocumentfile"></a><a name="opendocumentfile"></a>ドキュメント ファイルを開く

パスで指定されたファイルを開きます。

```
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;

virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU) = 0;
```

### <a name="parameters"></a>パラメーター

*パス名*<br/>
[in]開くドキュメントを含むファイルのパスへのポインター。

*ブアドトムル*<br/>
[in]TRUE は、ドキュメントが最新のファイルの 1 つであることを示します。FALSE は、文書が最新のファイルの 1 つではないことを示します。

### <a name="return-value"></a>戻り値

ファイルの名前が*lpszPathName*によって指定されているドキュメントへのポインター。失敗した場合は NULL。

### <a name="remarks"></a>解説

パスが指定されているファイルを*開きます*。 *lpszPathName*が NULL の場合、このテンプレートに関連付けられている種類のドキュメントを含む新しいファイルが作成されます。

## <a name="cdoctemplateremovedocument"></a><a name="removedocument"></a>ドキュメントの削除

このテンプレートに関連付けられているドキュメントの一覧から *、pDoc*によって指されているドキュメントを削除します。

```
virtual void RemoveDocument(CDocument* pDoc);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
削除するドキュメントへのポインター。

### <a name="remarks"></a>解説

派生クラス`CMultiDocTemplate`とこの`CSingleDocTemplate`関数をオーバーライドします。 から`CDocTemplate`独自のドキュメント テンプレート クラスを派生させる場合、派生クラスはこの関数をオーバーライドする必要があります。

## <a name="cdoctemplatesaveallmodified"></a><a name="saveallmodified"></a>を変更しました。

変更されたすべてのドキュメントを保存します。

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合は 0。

## <a name="cdoctemplatesetcontainerinfo"></a><a name="setcontainerinfo"></a>を設定します。

OLE アイテムを編集するときに OLE コンテナのリソースを決定します。

```
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```

### <a name="parameters"></a>パラメーター

*コンテナ*<br/>
埋め込みオブジェクトがアクティブになったときに使用されるリソースの ID。

### <a name="remarks"></a>解説

OLE オブジェクトがインプレース アクティブにされたときに使用されるリソースを設定します。 これらのリソースには、メニューやアクセラレータ テーブルが含まれる場合があります。 この関数は通常、アプリケーションの[CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)関数で呼び出されます。

*nIDOleInPlaceContainer*に関連付けられているメニューには、コンテナー アプリケーションのメニューとマージするアクティブなインプレース項目のメニューを許可する区切り記号が含まれています。 サーバー メニューとコンテナ メニューのマージの詳細については、「[メニューとリソース (OLE)」](../../mfc/menus-and-resources-ole.md)を参照してください。

## <a name="cdoctemplatesetdefaulttitle"></a><a name="setdefaulttitle"></a>を設定します。

ドキュメントの既定のタイトルを読み込み、ドキュメントのタイトル バーに表示します。

```
virtual void SetDefaultTitle(CDocument* pDocument) = 0;
```

### <a name="parameters"></a>パラメーター

*ドキュメント*<br/>
タイトルを設定するドキュメントへのポインター。

### <a name="remarks"></a>解説

既定のタイトルの詳細については、`CDocTemplate::docName`[次](#getdocstring)の説明を参照してください。

## <a name="cdoctemplatesetserverinfo"></a><a name="setserverinfo"></a>を設定します。

サーバー ドキュメントが埋め込みまたは編集されるときにリソースとクラスを決定します。

```
void SetServerInfo(
    UINT nIDOleEmbedding,
    UINT nIDOleInPlaceServer = 0,
    CRuntimeClass* pOleFrameClass = NULL,
    CRuntimeClass* pOleViewClass = NULL);
```

### <a name="parameters"></a>パラメーター

*を埋め込む*<br/>
埋め込みオブジェクトを別のウィンドウで開いたときに使用されるリソースの ID。

*サーバー*<br/>
埋め込みオブジェクトが埋め込みオブジェクトをアクティブにするときに使用されるリソースの ID。

*クラス*<br/>
埋め込み場所でのアクティブ化が発生したときに作成されるフレーム ウィンドウ オブジェクトのクラス情報を含む[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインター。

*クラス*<br/>
埋め込`CRuntimeClass`み場所でのアクティブ化が発生したときに作成されるビュー オブジェクトのクラス情報を格納している構造体へのポインター。

### <a name="remarks"></a>解説

ユーザーが埋め込みオブジェクトのアクティブ化を要求したときにサーバー アプリケーションで使用されるリソースを識別します。 これらのリソースは、メニューとアクセラレータ テーブルで構成されます。 この関数は通常、アプリケーション`InitInstance`で呼び出されます。

*nIDOleInPlaceServer*に関連付けられているメニューには、サーバー メニューをコンテナーのメニューとマージできるようにする区切り記号が含まれています。 サーバー メニューとコンテナ メニューのマージの詳細については、「[メニューとリソース (OLE)」](../../mfc/menus-and-resources-ole.md)を参照してください。

## <a name="cdoctemplatecreatepreviewframe"></a><a name="createpreviewframe"></a>をクリックします。

リッチ プレビューに使用する子フレームを作成します。

```
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,
    CDocument* pDoc);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
親ウィンドウへのポインター (通常はシェルによって提供されます)。

*pDoc*<br/>
コンテンツがプレビューされるドキュメント オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

オブジェクトへの有効な`CFrameWnd`ポインター、 または作成に失敗した場合は NULL。

### <a name="remarks"></a>解説

## <a name="cdoctemplatesetpreviewinfo"></a><a name="setpreviewinfo"></a>を設定します。

プロセス外プレビューハンドラを設定します。

```
void SetPreviewInfo(
    UINT nIDPreviewFrame,
    CRuntimeClass* pPreviewFrameClass = NULL,
    CRuntimeClass* pPreviewViewClass = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
プレビュー フレームのリソース ID を指定します。

*クラスをプレビューします。*<br/>
プレビュー フレームのランタイム クラス情報構造体へのポインターを指定します。

*クラスを表示します。*<br/>
プレビュー ビューのランタイム クラス情報構造体へのポインターを指定します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CSingleDocTemplate クラス](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[CScrollView クラス](../../mfc/reference/cscrollview-class.md)<br/>
[CEditView クラス](../../mfc/reference/ceditview-class.md)<br/>
[クラスを表示します。](../../mfc/reference/cformview-class.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)
