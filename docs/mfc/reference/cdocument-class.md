---
title: CDocument クラス
ms.date: 11/04/2016
f1_keywords:
- CDocument
- AFXWIN/CDocument
- AFXWIN/CDocument::CDocument
- AFXWIN/CDocument::AddView
- AFXWIN/CDocument::BeginReadChunks
- AFXWIN/CDocument::CanCloseFrame
- AFXWIN/CDocument::ClearChunkList
- AFXWIN/CDocument::ClearPathName
- AFXWIN/CDocument::DeleteContents
- AFXWIN/CDocument::FindChunk
- AFXWIN/CDocument::GetAdapter
- AFXWIN/CDocument::GetDocTemplate
- AFXWIN/CDocument::GetFile
- AFXWIN/CDocument::GetFirstViewPosition
- AFXWIN/CDocument::GetNextView
- AFXWIN/CDocument::GetPathName
- AFXWIN/CDocument::GetThumbnail
- AFXWIN/CDocument::GetTitle
- AFXWIN/CDocument::InitializeSearchContent
- AFXWIN/CDocument::IsModified
- AFXWIN/CDocument::IsSearchAndOrganizeHandler
- AFXWIN/CDocument::LoadDocumentFromStream
- AFXWIN/CDocument::OnBeforeRichPreviewFontChanged
- AFXWIN/CDocument::OnChangedViewList
- AFXWIN/CDocument::OnCloseDocument
- AFXWIN/CDocument::OnCreatePreviewFrame
- AFXWIN/CDocument::OnDocumentEvent
- AFXWIN/CDocument::OnDrawThumbnail
- AFXWIN/CDocument::OnLoadDocumentFromStream
- AFXWIN/CDocument::OnNewDocument
- AFXWIN/CDocument::OnOpenDocument
- AFXWIN/CDocument::OnPreviewHandlerQueryFocus
- AFXWIN/CDocument::OnPreviewHandlerTranslateAccelerator
- AFXWIN/CDocument::OnRichPreviewBackColorChanged
- AFXWIN/CDocument::OnRichPreviewFontChanged
- AFXWIN/CDocument::OnRichPreviewSiteChanged
- AFXWIN/CDocument::OnRichPreviewTextColorChanged
- AFXWIN/CDocument::OnSaveDocument
- AFXWIN/CDocument::OnUnloadHandler
- AFXWIN/CDocument::PreCloseFrame
- AFXWIN/CDocument::ReadNextChunkValue
- AFXWIN/CDocument::ReleaseFile
- AFXWIN/CDocument::RemoveChunk
- AFXWIN/CDocument::RemoveView
- AFXWIN/CDocument::ReportSaveLoadException
- AFXWIN/CDocument::SaveModified
- AFXWIN/CDocument::SetChunkValue
- AFXWIN/CDocument::SetModifiedFlag
- AFXWIN/CDocument::SetPathName
- AFXWIN/CDocument::SetTitle
- AFXWIN/CDocument::UpdateAllViews
- AFXWIN/CDocument::OnFileSendMail
- AFXWIN/CDocument::OnUpdateFileSendMail
- AFXWIN/CDocument::m_bGetThumbnailMode
- AFXWIN/CDocument::m_bPreviewHandlerMode
- AFXWIN/CDocument::m_bSearchMode
- AFXWIN/CDocument::m_clrRichPreviewBackColor
- AFXWIN/CDocument::m_clrRichPreviewTextColor
- AFXWIN/CDocument::m_lfRichPreviewFont
helpviewer_keywords:
- CDocument [MFC], CDocument
- CDocument [MFC], AddView
- CDocument [MFC], BeginReadChunks
- CDocument [MFC], CanCloseFrame
- CDocument [MFC], ClearChunkList
- CDocument [MFC], ClearPathName
- CDocument [MFC], DeleteContents
- CDocument [MFC], FindChunk
- CDocument [MFC], GetAdapter
- CDocument [MFC], GetDocTemplate
- CDocument [MFC], GetFile
- CDocument [MFC], GetFirstViewPosition
- CDocument [MFC], GetNextView
- CDocument [MFC], GetPathName
- CDocument [MFC], GetThumbnail
- CDocument [MFC], GetTitle
- CDocument [MFC], InitializeSearchContent
- CDocument [MFC], IsModified
- CDocument [MFC], IsSearchAndOrganizeHandler
- CDocument [MFC], LoadDocumentFromStream
- CDocument [MFC], OnBeforeRichPreviewFontChanged
- CDocument [MFC], OnChangedViewList
- CDocument [MFC], OnCloseDocument
- CDocument [MFC], OnCreatePreviewFrame
- CDocument [MFC], OnDocumentEvent
- CDocument [MFC], OnDrawThumbnail
- CDocument [MFC], OnLoadDocumentFromStream
- CDocument [MFC], OnNewDocument
- CDocument [MFC], OnOpenDocument
- CDocument [MFC], OnPreviewHandlerQueryFocus
- CDocument [MFC], OnPreviewHandlerTranslateAccelerator
- CDocument [MFC], OnRichPreviewBackColorChanged
- CDocument [MFC], OnRichPreviewFontChanged
- CDocument [MFC], OnRichPreviewSiteChanged
- CDocument [MFC], OnRichPreviewTextColorChanged
- CDocument [MFC], OnSaveDocument
- CDocument [MFC], OnUnloadHandler
- CDocument [MFC], PreCloseFrame
- CDocument [MFC], ReadNextChunkValue
- CDocument [MFC], ReleaseFile
- CDocument [MFC], RemoveChunk
- CDocument [MFC], RemoveView
- CDocument [MFC], ReportSaveLoadException
- CDocument [MFC], SaveModified
- CDocument [MFC], SetChunkValue
- CDocument [MFC], SetModifiedFlag
- CDocument [MFC], SetPathName
- CDocument [MFC], SetTitle
- CDocument [MFC], UpdateAllViews
- CDocument [MFC], OnFileSendMail
- CDocument [MFC], OnUpdateFileSendMail
- CDocument [MFC], m_bGetThumbnailMode
- CDocument [MFC], m_bPreviewHandlerMode
- CDocument [MFC], m_bSearchMode
- CDocument [MFC], m_clrRichPreviewBackColor
- CDocument [MFC], m_clrRichPreviewTextColor
- CDocument [MFC], m_lfRichPreviewFont
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
ms.openlocfilehash: 2d87ff67000fb5b70c0a5c965638875e6f50b22c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424459"
---
# <a name="cdocument-class"></a>CDocument クラス

ユーザーが定義するドキュメント クラスの基本機能が用意されています。

## <a name="syntax"></a>構文

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDocument:: CDocument](#cdocument)|`CDocument` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDocument:: AddView](#addview)|ビューをドキュメントに添付します。|
|[CDocument:: BeginReadChunks](#beginreadchunks)|チャンク読み取りを初期化します。|
|[CDocument:: CanCloseFrame](#cancloseframe)|高度なオーバーライド可能。このドキュメントを表示しているフレームウィンドウを閉じる前に呼び出されます。|
|[CDocument::ClearChunkList](#clearchunklist)|チャンクリストをクリアします。|
|[CDocument::ClearPathName](#clearpathname)|ドキュメントオブジェクトのパスをクリアします。|
|[CDocument::D eleteContents](#deletecontents)|ドキュメントのクリーンアップを実行するために呼び出されます。|
|[CDocument:: FindChunk](#findchunk)|指定された GUID を持つチャンクを検索します。|
|[CDocument:: GetAdapter](#getadapter)|`IDocument` インターフェイスを実装するオブジェクトへのポインターを返します。|
|[CDocument:: GetDocTemplate](#getdoctemplate)|ドキュメントの種類を記述するドキュメントテンプレートへのポインターを返します。|
|[CDocument::GetFile](#getfile)|目的の `CFile` オブジェクトへのポインターを返します。|
|[CDocument:: GetFirstViewPosition](#getfirstviewposition)|ビューのリスト内の最初のの位置を返します。反復処理を開始するために使用されます。|
|[CDocument:: GetNextView](#getnextview)|ドキュメントに関連付けられているビューの一覧を反復処理します。|
|[CDocument::GetPathName](#getpathname)|ドキュメントのデータファイルのパスを返します。|
|[CDocument:: GetThumbnail](#getthumbnail)|サムネイルを表示するためにサムネイルプロバイダーによって使用されるビットマップを作成するために呼び出されます。|
|[CDocument:: GetTitle](#gettitle)|ドキュメントのタイトルを返します。|
|[CDocument:: InitializeSearchContent](#initializesearchcontent)|検索ハンドラーの検索コンテンツを初期化するために呼び出されます。|
|[CDocument:: IsModified](#ismodified)|ドキュメントが最後に保存されてから変更されたかどうかを示します。|
|[CDocument:: IsSearchAndOrganizeHandler](#issearchandorganizehandler)|`CDocument` オブジェクトのこのインスタンスが検索 & 編成ハンドラーに作成されたかどうかを示します。|
|[CDocument:: LoadDocumentFromStream](#loaddocumentfromstream)|ストリームからドキュメントデータを読み込むために呼び出されます。|
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|リッチプレビューフォントが変更される前に呼び出されます。|
|[CDocument::OnChangedViewList](#onchangedviewlist)|ドキュメントに対してビューの追加または削除を行った後に呼び出されます。|
|[CDocument:: OnCloseDocument](#onclosedocument)|ドキュメントを閉じるために呼び出されます。|
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|リッチプレビュー用のプレビューフレームを作成する必要があるときにフレームワークによって呼び出されます。|
|[CDocument::OnDocumentEvent](#ondocumentevent)|ドキュメントイベントへの応答としてフレームワークによって呼び出されます。|
|[CDocument:: OnDrawThumbnail](#ondrawthumbnail)|派生クラスでこのメソッドをオーバーライドして、サムネイルの内容を描画します。|
|[CDocument:: OnLoadDocumentFromStream](#onloaddocumentfromstream)|ストリームからドキュメントデータを読み込む必要があるときに、フレームワークによって呼び出されます。|
|[CDocument::OnNewDocument](#onnewdocument)|新しいドキュメントを作成するために呼び出されます。|
|[CDocument::OnOpenDocument](#onopendocument)|既存のドキュメントを開くために呼び出されます。|
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|GetFocus 関数の呼び出しから HWND を返すように、プレビューハンドラーに指示します。|
|[CDocument:: OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|プレビューハンドラーが、プレビューハンドラーが実行されているプロセスのメッセージポンプから渡されたキーストロークを処理するように指示します。|
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|リッチプレビューの背景色が変更されたときに呼び出されます。|
|[CDocument:: OnRichPreviewFontChanged](#onrichpreviewfontchanged)|リッチプレビューフォントが変更されたときに呼び出されます。|
|[CDocument:: OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|リッチプレビューサイトが変更されたときに呼び出されます。|
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|リッチプレビューテキストの色が変更されたときに呼び出されます。|
|[CDocument::OnSaveDocument](#onsavedocument)|ドキュメントをディスクに保存するために呼び出されます。|
|[CDocument:: OnUnloadHandler](#onunloadhandler)|プレビューハンドラーがアンロードされるときにフレームワークによって呼び出されます。|
|[CDocument::PreCloseFrame](#precloseframe)|フレームウィンドウが閉じる前に呼び出されます。|
|[CDocument:: ReadNextChunkValue](#readnextchunkvalue)|次のチャンク値を読み取ります。|
|[CDocument::ReleaseFile](#releasefile)|ファイルを解放して、他のアプリケーションで使用できるようにします。|
|[CDocument::RemoveChunk](#removechunk)|指定された GUID を持つチャンクを削除します。|
|[CDocument:: RemoveView](#removeview)|ドキュメントからビューをデタッチします。|
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|高度なオーバーライド可能。例外が発生したために、開いているまたは保存操作を完了できないときに呼び出されます。|
|[CDocument:: SaveModified](#savemodified)|高度なオーバーライド可能。ドキュメントを保存する必要があるかどうかをユーザーに確認するために呼び出されます。|
|[CDocument:: SetChunkValue](#setchunkvalue)|チャンク値を設定します。|
|[CDocument:: SetModifiedFlag](#setmodifiedflag)|ドキュメントが最後に保存されてから変更されたことを示すフラグを設定します。|
|[CDocument:: SetPathName](#setpathname)|ドキュメントによって使用されるデータファイルのパスを設定します。|
|[CDocument:: SetTitle](#settitle)|ドキュメントのタイトルを設定します。|
|[CDocument:: UpdateAllViews](#updateallviews)|ドキュメントが変更されたことをすべてのビューに通知します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CDocument:: OnFileSendMail](#onfilesendmail)|添付されたドキュメントを使用してメールメッセージを送信します。|
|[CDocument:: OnUpdateFileSendMail](#onupdatefilesendmail)|メールサポートが存在する場合は、[メールを送信] コマンドを有効にします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CDocument:: m_bGetThumbnailMode](#m_bgetthumbnailmode)|`CDocument` オブジェクトがサムネイル用に dllhost によって作成されたことを指定します。 `CView::OnDraw`でチェックインする必要があります。|
|[CDocument:: m_bPreviewHandlerMode](#m_bpreviewhandlermode)|`CDocument` オブジェクトが `Rich Preview`用に prevhost によって作成されたことを示します。 `CView::OnDraw`でチェックインする必要があります。|
|[CDocument:: m_bSearchMode](#m_bsearchmode)|`CDocument` オブジェクトがインデクサーまたはその他の検索アプリケーションによって作成されたことを示します。|
|[CDocument:: m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|リッチプレビューウィンドウの背景色を指定します。 この色はホストによって設定されます。|
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|リッチプレビューウィンドウの前景色を指定します。 この色はホストによって設定されます。|
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|リッチプレビューウィンドウのテキストフォントを指定します。 このフォント情報はホストによって設定されます。|

## <a name="remarks"></a>Remarks

ドキュメントは、通常、ファイルを開くコマンドを使用してユーザーが開くデータの単位を表し、[ファイル] [保存] コマンドを使用して保存します。

`CDocument` は、ドキュメントの作成、読み込み、保存などの標準的な操作をサポートしています。 フレームワークは、`CDocument`によって定義されたインターフェイスを使用してドキュメントを操作します。

アプリケーションでは、複数の種類のドキュメントをサポートできます。たとえば、アプリケーションでスプレッドシートとテキストドキュメントの両方がサポートされている場合があります。 ドキュメントの種類ごとに、関連付けられたドキュメントテンプレートがあります。ドキュメントテンプレートでは、その種類のドキュメントに使用されるリソース (メニュー、アイコン、アクセラレータテーブルなど) を指定します。 各ドキュメントには、関連付けられた `CDocTemplate` オブジェクトへのポインターが含まれています。

ユーザーは、関連付けられている[CView](../../mfc/reference/cview-class.md)オブジェクトを使用してドキュメントを操作します。 ビューは、ドキュメントのイメージをフレームウィンドウに表示し、ユーザーの入力をドキュメントに対する操作として解釈します。 ドキュメントには、複数のビューを関連付けることができます。 ユーザーがドキュメント上のウィンドウを開くと、フレームワークによってビューが作成され、ドキュメントにアタッチされます。 ドキュメントテンプレートでは、各種類のドキュメントを表示するために使用されるビューとフレームウィンドウの種類を指定します。

ドキュメントはフレームワークの標準のコマンドルーティングの一部であり、その結果、標準的なユーザーインターフェイスコンポーネント ([ファイル] [保存] メニュー項目など) からコマンドを受け取ることができます。 ドキュメントは、アクティブなビューによって転送されたコマンドを受け取ります。 ドキュメントが特定のコマンドを処理しない場合は、そのコマンドを管理するドキュメントテンプレートにコマンドを転送します。

ドキュメントのデータが変更されると、それぞれのビューにその変更が反映される必要があります。 `CDocument` には、このような変更をビューに通知するための[UpdateAllViews](#updateallviews)メンバー関数が用意されているので、必要に応じてビュー自体を再描画できます。 また、フレームワークは、変更されたファイルを閉じる前に保存するようにユーザーに求めます。

一般的なアプリケーションでドキュメントを実装するには、次の操作を行う必要があります。

- ドキュメントの種類ごとに `CDocument` からクラスを派生させます。

- 各ドキュメントのデータを格納するためのメンバー変数を追加します。

- ドキュメントのデータを読み取って変更するためのメンバー関数を実装します。 ドキュメントのビューは、これらのメンバー関数の最も重要なユーザーです。

- ドキュメントクラスの[CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize)メンバー関数をオーバーライドして、ディスクとの間でドキュメントのデータを読み書きします。

`CDocument` は、メールサポート (MAPI) が存在する場合にメールを使用したドキュメントの送信をサポートしています。 「 [MFC で](../../mfc/mapi-support-in-mfc.md)の[mapi](../../mfc/mapi.md)および mapi のサポート」を参照してください。

`CDocument`の詳細については、「[シリアル化](../../mfc/serialization-in-mfc.md)」、「[ドキュメント/ビューアーキテクチャのトピック](../../mfc/document-view-architecture.md)」、および「[ドキュメント/ビューの作成](../../mfc/document-view-creation.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

##  <a name="cdocumentaddview"></a><a name="addview"></a>  CDocument::AddView

この関数を呼び出して、ドキュメントにビューをアタッチします。

```
void AddView(CView* pView);
```

### <a name="parameters"></a>パラメーター

*pView*<br/>
追加するビューをポイントします。

### <a name="remarks"></a>Remarks

この関数は、ドキュメントに関連付けられているビューの一覧に、指定されたビューを追加します。また、この関数は、ビューのドキュメントポインターをこのドキュメントに設定します。 フレームワークは、新しく作成されたビューオブジェクトをドキュメントにアタッチするときに、この関数を呼び出します。これは、File New、File Open、または New Window コマンドに応答して、またはスプリッターウィンドウが分割されたときに発生します。

ビューを手動で作成してアタッチする場合にのみ、この関数を呼び出します。 通常は、ドキュメントクラス、ビュークラス、およびフレームウィンドウクラスを関連付けるために、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクトを定義して、フレームワークがドキュメントとビューを接続できるようにします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

##  <a name="cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>  CDocument::BeginReadChunks

チャンク読み取りを初期化します。

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentcancloseframe"></a><a name="cancloseframe"></a>CDocument:: CanCloseFrame

ドキュメントを表示しているフレームウィンドウが閉じられる前に、フレームワークによって呼び出されます。

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>パラメーター

*pFrame*<br/>
ドキュメントにアタッチされているビューのフレームウィンドウを指します。

### <a name="return-value"></a>戻り値

フレームウィンドウを安全に閉じることができる場合は0以外の場合は。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

既定の実装では、ドキュメントを表示している他のフレームウィンドウがあるかどうかを確認します。 指定されたフレームウィンドウがドキュメントを表示する最後のウィンドウである場合は、ドキュメントが変更されている場合、この関数はドキュメントを保存するようにユーザーに求めます。 フレームウィンドウが閉じているときに特別な処理を実行する場合は、この関数をオーバーライドします。 これは高度なオーバーライド可能です。

##  <a name="cdocumentcdocument"></a><a name="cdocument"></a>CDocument:: CDocument

`CDocument` オブジェクトを構築します。

```
CDocument();
```

### <a name="remarks"></a>Remarks

ドキュメントの作成は、フレームワークによって処理されます。 [OnNewDocument](#onnewdocument)メンバー関数をオーバーライドして、ドキュメントごとに初期化を実行します。これは、シングルドキュメントインターフェイス (SDI) アプリケーションでは特に重要です。

##  <a name="cdocumentclearchunklist"></a><a name="clearchunklist"></a>  CDocument::ClearChunkList

チャンクリストをクリアします。

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentclearpathname"></a><a name="clearpathname"></a>  CDocument::ClearPathName

ドキュメントオブジェクトのパスをクリアします。

```
virtual void ClearPathName();
```

### <a name="remarks"></a>Remarks

`CDocument` オブジェクトからパスをクリアすると、ドキュメントが次に保存されるときに、アプリケーションによってユーザーに対してプロンプトが表示されます。 これにより、**保存**コマンドは、**名前を付けて保存**コマンドと同じように動作します。

##  <a name="cdocumentdeletecontents"></a><a name="deletecontents"></a>  CDocument::DeleteContents

`CDocument` オブジェクト自体を破棄せずに、ドキュメントのデータを削除するためにフレームワークによって呼び出されます。

```
virtual void DeleteContents();
```

### <a name="remarks"></a>Remarks

ドキュメントが破棄される直前に呼び出されます。 また、ドキュメントが再利用される前に空であることを確認するためにも呼び出されます。 これは、1つのドキュメントのみを使用する SDI アプリケーションでは特に重要です。ドキュメントは、ユーザーが別のドキュメントを作成または開いたときに再利用されます。 この関数を呼び出して、すべてのドキュメントのデータを削除する "Clear All を編集" または同様のコマンドを実装します。 この関数の既定の実装は、何も行いません。 ドキュメント内のデータを削除するには、この関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

##  <a name="cdocumentfindchunk"></a><a name="findchunk"></a>  CDocument::FindChunk

指定した GUID を持つチャンクを検索します。

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>パラメーター

*guid*<br/>
検索するチャンクの GUID を指定します。

*pid*<br/>
検索するチャンクの PID を指定します。

### <a name="return-value"></a>戻り値

成功した場合は、内部チャンクリスト内の位置。 それ以外の場合は NULL。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentgetadapter"></a><a name="getadapter"></a>  CDocument::GetAdapter

`IDocument` インターフェイスを実装するオブジェクトへのポインターを返します。

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>戻り値

`IDocument` インターフェイスを実装するオブジェクトへのポインター。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>  CDocument::GetDocTemplate

このドキュメントの種類のドキュメントテンプレートへのポインターを取得するには、この関数を呼び出します。

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>戻り値

このドキュメントの種類のドキュメントテンプレートへのポインター。ドキュメントがドキュメントテンプレートで管理されていない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

##  <a name="cdocumentgetfile"></a><a name="getfile"></a>  CDocument::GetFile

`CFile` オブジェクトへのポインターを取得するには、このメンバー関数を呼び出します。

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>パラメーター

*lpszFileName*<br/>
目的のファイルへのパスを表す文字列。 相対パスまたは絶対パスを指定できます。

*pError*<br/>
操作の完了ステータスを示す既存のファイル例外オブジェクトへのポインター。

*Noペンフラグ*<br/>
共有とアクセスモード。 ファイルを開くときに実行するアクションを指定します。 ビットごとの OR (&#124;) 演算子を使用すると、cfile コンストラクター [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) に一覧表示されているオプションを組み合わせることができます。 1つのアクセス許可と1つの共有オプションが必要です。`modeCreate` モードと `modeNoInherit` モードは省略可能です。

### <a name="return-value"></a>戻り値

`CFile` オブジェクトへのポインター。

##  <a name="cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>  CDocument::GetFirstViewPosition

この関数を呼び出して、ドキュメントに関連付けられているビューのリスト内の最初のビューの位置を取得します。

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>戻り値

[GetNextView](#getnextview)メンバー関数を使用した反復処理に使用できる位置の値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="cdocumentgetnextview"></a><a name="getnextview"></a>  CDocument::GetNextView

ドキュメントのすべてのビューを反復処理するには、この関数を呼び出します。

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*rPosition*<br/>
`GetNextView` または[Getfirstviewposition](#getfirstviewposition)メンバー関数への前回の呼び出しによって返された位置の値への参照。 この値を NULL にすることはできません。

### <a name="return-value"></a>戻り値

*RPosition*によって識別されるビューへのポインター。

### <a name="remarks"></a>Remarks

関数は、 *rPosition*によって識別されるビューを返し、 *rPosition*をリスト内の次のビューの位置の値に設定します。 取得したビューが一覧の最後のビューである場合、 *rPosition*は NULL に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="cdocumentgetpathname"></a><a name="getpathname"></a>  CDocument::GetPathName

ドキュメントのディスクファイルの完全修飾パスを取得します。

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>戻り値

ドキュメントの完全修飾パス。 ドキュメントが保存されていない場合、またはドキュメントにディスクファイルが関連付けられていない場合、この文字列は空になります。

##  <a name="cdocumentgetthumbnail"></a><a name="getthumbnail"></a>  CDocument::GetThumbnail

サムネイルを表示するためにサムネイルプロバイダーによって使用されるビットマップを作成します。

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>パラメーター

*cx*<br/>
ビットマップの幅と高さを指定します。

*phbmp*<br/>
関数が正常に返された場合に、ビットマップへのハンドルを格納します。

*pdwAlpha*<br/>
関数が正常に返されたときに、アルファチャネル値を指定する DWORD を格納します。

### <a name="return-value"></a>戻り値

サムネイルのビットマップが正常に作成された場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentgettitle"></a><a name="gettitle"></a>  CDocument::GetTitle

ドキュメントのタイトルを取得するには、この関数を呼び出します。通常は、ドキュメントのファイル名から派生します。

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>戻り値

ドキュメントのタイトル。

##  <a name="cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>  CDocument::InitializeSearchContent

検索ハンドラーの検索コンテンツを初期化するために呼び出されます。

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>Remarks

派生クラスでこのメソッドをオーバーライドして、検索コンテンツを初期化します。 コンテンツは、";" で区切られた部分を含む文字列である必要があります。 たとえば、"point;四角形ole 項目 "。

##  <a name="cdocumentismodified"></a><a name="ismodified"></a>  CDocument::IsModified

ドキュメントが最後に保存されてから変更されたかどうかを確認するには、この関数を呼び出します。

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>戻り値

ドキュメントが最後に保存されてから変更された場合は0以外の。それ以外の場合は0です。

##  <a name="cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>CDocument:: IsSearchAndOrganizeHandler

`CDocument` のこのインスタンスが検索 & 整理ハンドラーに対して作成されたかどうかを示します。

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>戻り値

この `CDocument` のインスタンスが検索 & 整理ハンドラーに対して作成された場合に TRUE を返します。

### <a name="remarks"></a>Remarks

現在、この関数は、アウトプロセスサーバーに実装されている豊富なプレビューハンドラーに対してのみ TRUE を返します。 アプリケーションレベルで適切なフラグ (m_bPreviewHandlerMode、m_bSearchMode、m_bGetThumbnailMode) を設定して、この関数が TRUE を返すようにすることができます。

##  <a name="cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>CDocument:: LoadDocumentFromStream

ストリームからドキュメントデータを読み込むために呼び出されます。

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>パラメーター

*pStream*<br/>
ストリームへのポインター。 このストリームはシェルによって提供されます。

*dwGrfMode*<br/>
ストリームへのアクセスモード。

### <a name="return-value"></a>戻り値

読み込み操作が成功した場合は S_OK、それ以外の場合はエラーコードを返します。

### <a name="remarks"></a>Remarks

派生クラスでこのメソッドをオーバーライドすると、ストリームからデータを読み込む方法をカスタマイズできます。

##  <a name="cdocumentm_bgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>CDocument:: m_bGetThumbnailMode

`CDocument` オブジェクトがサムネイル用に dllhost によって作成されたことを示します。 `CView::OnDraw`でチェックインする必要があります。

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>Remarks

`TRUE` は、ドキュメントがサムネイル用に dllhost によって作成されたことを示します。

##  <a name="cdocumentm_bpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>  CDocument::m_bPreviewHandlerMode

`CDocument` オブジェクトがリッチプレビュー用に prevhost によって作成されたことを示します。 `CView::OnDraw`でチェックインする必要があります。

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>Remarks

TRUE は、ドキュメントがリッチプレビュー用に prevhost によって作成されたことを示します。

##  <a name="cdocumentm_bsearchmode"></a><a name="m_bsearchmode"></a>  CDocument::m_bSearchMode

`CDocument` オブジェクトがインデクサーまたは別の検索アプリケーションによって作成されたことを示します。

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>Remarks

`TRUE` は、ドキュメントがインデクサーまたは別の検索アプリケーションによって作成されたことを示します。

##  <a name="cdocumentm_clrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>  CDocument::m_clrRichPreviewBackColor

リッチプレビューウィンドウの背景色を指定します。 この色はホストによって設定されます。

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentm_clrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>  CDocument::m_clrRichPreviewTextColor

リッチプレビューウィンドウの前景色を指定します。 この色はホストによって設定されます。

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentm_lfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>  CDocument::m_lfRichPreviewFont

リッチプレビューウィンドウのテキストフォントを指定します。 このフォント情報はホストによって設定されます。

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>  CDocument::OnBeforeRichPreviewFontChanged

リッチプレビューフォントが変更される前に呼び出されます。

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>  CDocument::OnChangedViewList

ビューがドキュメントに追加された後、またはドキュメントから削除された後に、フレームワークによって呼び出されます。

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>Remarks

この関数の既定の実装では、最後のビューが削除されているかどうかがチェックされ、存在する場合はドキュメントが削除されます。 フレームワークがビューを追加または削除するときに特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、関連付けられているビューがない場合でもドキュメントを開いたままにする場合は、この関数をオーバーライドします。

##  <a name="cdocumentonclosedocument"></a><a name="onclosedocument"></a>  CDocument::OnCloseDocument

ドキュメントが閉じられたときにフレームワークによって呼び出されます。通常は、File Close コマンドの一部として呼び出されます。

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>Remarks

この関数の既定の実装は、ドキュメントを表示するために使用されるすべてのフレームを破棄し、ビューを閉じて、ドキュメントの内容をクリーンアップしてから、 [DeleteContents](#deletecontents)メンバー関数を呼び出してドキュメントのデータを削除します。

フレームワークがドキュメントを閉じるときに特別なクリーンアップ処理を実行する場合は、この関数をオーバーライドします。 たとえば、ドキュメントがデータベース内のレコードを表している場合は、この関数をオーバーライドしてデータベースを閉じることができます。 オーバーライドから、この関数の基本クラスバージョンを呼び出す必要があります。

##  <a name="cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>  CDocument::OnCreatePreviewFrame

リッチプレビュー用のプレビューフレームを作成する必要があるときにフレームワークによって呼び出されます。

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>戻り値

フレームが正常に作成された場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentondocumentevent"></a><a name="ondocumentevent"></a>  CDocument::OnDocumentEvent

ドキュメントイベントへの応答としてフレームワークによって呼び出されます。

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>パラメーター

*deEvent*<br/>
からイベントの種類を示す列挙データ型。

### <a name="remarks"></a>Remarks

ドキュメントイベントは、複数のクラスに影響を与える可能性があります。 このメソッドは、 [CDocument クラス](../../mfc/reference/cdocument-class.md)以外のクラスに影響するドキュメントイベントの処理を行います。 現時点では、ドキュメントイベントに応答する必要がある唯一のクラスは、 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)です。 `CDocument` クラスには、`CDocument`への影響の処理を担当する他の上書き可能なメソッドがあります。

次の表に、 *Deevent*に使用できる値と、その値が対応するイベントの一覧を示します。

|[値]|対応するイベント|
|-----------|-------------------------|
|`onAfterNewDocument`|新しいドキュメントが作成されました。|
|`onAfterOpenDocument`|新しいドキュメントが開かれました。|
|`onAfterSaveDocument`|ドキュメントが保存されました。|
|`onAfterCloseDocument`|ドキュメントが閉じられました。|

##  <a name="cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>CDocument:: OnDrawThumbnail

派生クラスでこのメソッドをオーバーライドしてサムネイルを描画します。

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>パラメーター

*dc*<br/>
デバイスコンテキストへの参照。

*lprcBounds*<br/>
サムネイルを描画する領域の外接する四角形を指定します。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>  CDocument::OnFileSendMail

常駐メールホスト (存在する場合) を介してメッセージを添付ファイルとして送信します。

```
void OnFileSendMail();
```

### <a name="remarks"></a>Remarks

`OnFileSendMail` は、 [Onsavedocument](#onsavedocument)を呼び出して、無題のドキュメントと変更されたドキュメントを一時ファイルにシリアル化 (保存) し、電子メールで送信します。 ドキュメントが変更されていない場合、一時ファイルは必要ありません。元のが送信されます。 `OnFileSendMail` は MAPI32.DLL を読み込みます。DLL がまだ読み込まれていない場合は、DLL です。

[COleDocument](../../mfc/reference/coledocument-class.md)の `OnFileSendMail` の特別な実装は、複合ファイルを正しく処理します。

`CDocument` は、メールサポート (MAPI) が存在する場合にメールを使用したドキュメントの送信をサポートしています。 記事「 [MFC での](../../mfc/mapi-support-in-mfc.md) [mapi のトピック](../../mfc/mapi.md)と mapi のサポート」を参照してください。

##  <a name="cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>  CDocument::OnLoadDocumentFromStream

ストリームからドキュメントデータを読み込む必要がある場合に、フレームワークによって呼び出されます。

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>パラメーター

*pStream*<br/>
受信ストリームへのポインター。

*grfMode*<br/>
ストリームへのアクセスモード。

### <a name="return-value"></a>戻り値

読み込みが成功した場合は S_OK します。それ以外の場合は、エラーコード。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonnewdocument"></a><a name="onnewdocument"></a>  CDocument::OnNewDocument

ファイルの New コマンドの一部としてフレームワークによって呼び出されます。

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>戻り値

ドキュメントが正常に初期化された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

この関数の既定の実装は、 [DeleteContents](#deletecontents)メンバー関数を呼び出して、ドキュメントが空であることを確認してから、新しいドキュメントをクリーンとしてマークします。 新しいドキュメントのデータ構造を初期化するには、この関数をオーバーライドします。 オーバーライドから、この関数の基本クラスバージョンを呼び出す必要があります。

ユーザーが SDI アプリケーションで [ファイル] [新規作成] コマンドを選択した場合、フレームワークはこの関数を使用して、新しいドキュメントを作成するのではなく、既存のドキュメントを再初期化します。 ユーザーがマルチドキュメントインターフェイス (MDI) アプリケーションで [ファイル] [新規] を選択した場合、フレームワークは毎回新しいドキュメントを作成し、この関数を呼び出して初期化します。 SDI アプリケーションで有効になるように、File New コマンドのコンストラクターではなく、この関数に初期化コードを配置する必要があります。

`OnNewDocument` が2回呼び出される場合があることに注意してください。 このエラーは、ドキュメントが ActiveX ドキュメントサーバーとして埋め込まれている場合に発生します。 関数は、(`COleObjectFactory`派生クラスによって公開された) `CreateInstance` メソッドによって呼び出され、`InitNew` メソッド (`COleServerDoc`派生クラスによって公開される) によって2回目に呼び出されます。

### <a name="example"></a>例

次の例は、ドキュメントオブジェクトを初期化する別の方法を示しています。

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

##  <a name="cdocumentonopendocument"></a><a name="onopendocument"></a>  CDocument::OnOpenDocument

File Open コマンドの一部としてフレームワークによって呼び出されます。

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>パラメーター

*lpszPathName*<br/>
開くドキュメントのパスを指します。

### <a name="return-value"></a>戻り値

ドキュメントが正常に読み込まれた場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

この関数の既定の実装は、指定されたファイルを開き、 [DeleteContents](#deletecontents)メンバー関数を呼び出してドキュメントが空であることを確認し、 [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize)を呼び出してファイルの内容を読み取り、ドキュメントをクリーンとしてマークします。 アーカイブ機構またはファイル機構以外のものを使用する場合は、この関数をオーバーライドします。 たとえば、ドキュメントが個別のファイルではなくデータベースのレコードを表すアプリケーションを作成できます。

ユーザーが SDI アプリケーションで [ファイルを開く] コマンドを選択した場合、フレームワークはこの関数を使用して、新しいオブジェクトを作成するのではなく、既存の `CDocument` オブジェクトを再初期化します。 ユーザーが MDI アプリケーションで [ファイルを開く] を選択した場合、フレームワークは毎回新しい `CDocument` オブジェクトを構築し、次にこの関数を呼び出して初期化します。 SDI アプリケーションでは、File Open コマンドを有効にするコンストラクターではなく、この関数に初期化コードを配置する必要があります。

### <a name="example"></a>例

次の例は、ドキュメントオブジェクトを初期化する別の方法を示しています。

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

##  <a name="cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>  CDocument::OnPreviewHandlerQueryFocus

`GetFocus` 関数の呼び出しから取得した HWND を返すようにプレビューハンドラーに指示します。

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>パラメーター

*phwnd*<br/>
入出力このメソッドから制御が戻るときに、プレビューハンドラーのフォアグラウンドスレッドから `GetFocus` 関数の呼び出しから返された HWND へのポインターを格納します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返します。それ以外の場合は、エラー値。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>  CDocument::OnPreviewHandlerTranslateAccelerator

プレビューハンドラーが、プレビューハンドラーが実行されているプロセスのメッセージポンプから渡されたキーストロークを処理するように指示します。

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>パラメーター

*pmsg*<br/>
からウィンドウメッセージへのポインター。

### <a name="return-value"></a>戻り値

キーストロークメッセージをプレビューハンドラーで処理できる場合、ハンドラーはそれを処理して S_OK を返します。 プレビューハンドラーがキーストロークメッセージを処理できない場合は、`IPreviewHandlerFrame::TranslateAccelerator`経由でホストに提供します。 ホストがメッセージを処理する場合、このメソッドは S_OK を返します。 ホストがメッセージを処理しない場合、このメソッドは S_FALSE を返します。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>  CDocument::OnRichPreviewBackColorChanged

リッチプレビューの背景色が変更されたときに呼び出されます。

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>  CDocument::OnRichPreviewFontChanged

リッチプレビューフォントが変更されたときに呼び出されます。

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>  CDocument::OnRichPreviewSiteChanged

リッチプレビューサイトが変更されたときに呼び出されます。

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>  CDocument::OnRichPreviewTextColorChanged

リッチプレビューテキストの色が変更されたときに呼び出されます。

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonsavedocument"></a><a name="onsavedocument"></a>  CDocument::OnSaveDocument

[ファイル名を付けて保存] コマンドまたは [ファイル名を付けて保存] コマンドの一部としてフレームワークによって呼び出されます。

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>パラメーター

*lpszPathName*<br/>
ファイルの保存先の絶対パスを指します。

### <a name="return-value"></a>戻り値

ドキュメントが正常に保存された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

この関数の既定の実装では、指定されたファイルを開き、 [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize)を呼び出してドキュメントのデータをファイルに書き込んだ後、ドキュメントをクリーンとしてマークします。 フレームワークがドキュメントを保存するときに特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、ドキュメントが個別のファイルではなくデータベースのレコードを表すアプリケーションを作成できます。

##  <a name="cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>CDocument:: OnUnloadHandler

プレビューハンドラーがアンロードされるときにフレームワークによって呼び出されます。

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>Remarks

##  <a name="cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>  CDocument::OnUpdateFileSendMail

メールサポート (MAPI) が存在する場合は、ID_FILE_SEND_MAIL コマンドを有効にします。

```
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*pCmdUI*<br/>
ID_FILE_SEND_MAIL コマンドに関連付けられている[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>Remarks

それ以外の場合、この関数はメニュー項目の上または下にある区切り記号を含めて、メニューから ID_FILE_SEND_MAIL コマンドを削除します。 MAPI32.DLL の場合、MAPI が有効になります。DLL は、WIN の [Mail] セクションのパスとに存在します。INI ファイル、MAPI = 1。 ほとんどのアプリケーションは、[ファイル] メニューにこのコマンドを配置します。

`CDocument` は、メールサポート (MAPI) が存在する場合にメールを使用したドキュメントの送信をサポートしています。 記事「 [MFC での](../../mfc/mapi-support-in-mfc.md) [mapi のトピック](../../mfc/mapi.md)と mapi のサポート」を参照してください。

##  <a name="cdocumentprecloseframe"></a><a name="precloseframe"></a>  CDocument::PreCloseFrame

このメンバー関数は、フレームウィンドウが破棄される前にフレームワークによって呼び出されます。

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>パラメーター

*pFrame*<br/>
関連付けられている `CDocument` オブジェクトを保持する[CFrameWnd](../../mfc/reference/cframewnd-class.md)へのポインター。

### <a name="remarks"></a>Remarks

カスタムクリーンアップを提供するようにオーバーライドできますが、基本クラスも必ず呼び出してください。

`PreCloseFrame` の既定では、`CDocument`では何も実行されません。 `CDocument`派生クラスは、このメンバー[関数を](../../mfc/reference/cricheditdoc-class.md)[使用します](../../mfc/reference/coledocument-class.md)。

##  <a name="cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>  CDocument::ReadNextChunkValue

次のチャンク値を読み取ります。

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>パラメーター

*ppValue*<br/>
入出力関数から制御が戻ったときに、 *Ppvalue*に読み取られた値が含まれます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentreleasefile"></a><a name="releasefile"></a>  CDocument::ReleaseFile

このメンバー関数は、ファイルを解放して他のアプリケーションで使用できるようにするために、フレームワークによって呼び出されます。

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>パラメーター

*pFile*<br/>
解放される CFile オブジェクトへのポインター。

*bAbort*<br/>
`CFile::Close` または `CFile::Abort`のいずれかを使用してファイルを解放するかどうかを指定します。 ファイルが[CFile:: Close](../../mfc/reference/cfile-class.md#close)を使用して解放される場合は FALSE。ファイルが[CFile:: Abort](../../mfc/reference/cfile-class.md#abort)を使用して解放される場合は TRUE。

### <a name="remarks"></a>Remarks

*Babort*が TRUE の場合、`ReleaseFile` は `CFile::Abort`を呼び出し、ファイルが解放されます。 `CFile::Abort` は例外をスローしません。

*Babort*が FALSE の場合、`ReleaseFile` は `CFile::Close` を呼び出し、ファイルが解放されます。

このメンバー関数をオーバーライドして、ファイルが解放される前にユーザーがアクションを要求するようにします。

##  <a name="cdocumentremovechunk"></a><a name="removechunk"></a>  CDocument::RemoveChunk

指定した GUID を持つチャンクを削除します。

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>パラメーター

*Guid*<br/>
削除するチャンクの GUID を指定します。

*Pid*<br/>
削除するチャンクの PID を指定します。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentremoveview"></a><a name="removeview"></a>  CDocument::RemoveView

この関数を呼び出して、ドキュメントからビューをデタッチします。

```
void RemoveView(CView* pView);
```

### <a name="parameters"></a>パラメーター

*pView*<br/>
削除するビューを指します。

### <a name="remarks"></a>Remarks

この関数は、ドキュメントに関連付けられているビューの一覧から、指定されたビューを削除します。また、ビューのドキュメントポインターを NULL に設定します。 この関数は、フレームウィンドウが閉じられたとき、または分割ウィンドウのペインが閉じられたときにフレームワークによって呼び出されます。

ビューを手動でデタッチする場合にのみ、この関数を呼び出します。 通常は、ドキュメントクラス、ビュークラス、およびフレームウィンドウクラスを関連付けるために、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクトを定義して、フレームワークにドキュメントとビューをデタッチさせます。

サンプル実装については、「 [Addview](#addview) 」の例を参照してください。

##  <a name="cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>  CDocument::ReportSaveLoadException

ドキュメントの保存または読み込み中に例外がスローされた場合 (通常は[CFileException](../../mfc/reference/cfileexception-class.md)または[cアーカイブ例外](../../mfc/reference/carchiveexception-class.md)) に呼び出されます。

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>パラメーター

*lpszPathName*<br/>
保存または読み込み中のドキュメントの名前を指します。

*e*<br/>
スローされた例外を指します。 NULL の場合もあります。

*bSaving*<br/>
実行中の操作を示すフラグです。ドキュメントが保存されていた場合は0以外、ドキュメントが読み込まれていた場合は0。

*nIDPDefault*<br/>
関数がより具体的なものを指定していない場合に表示されるエラーメッセージの識別子。

### <a name="remarks"></a>Remarks

既定の実装では、例外オブジェクトが調べられ、その原因を具体的に説明するエラーメッセージが検索されます。 特定のメッセージが見つからない場合、または*e*が NULL の場合は、 *nIDPDefault*パラメーターで指定された一般的なメッセージが使用されます。 次に、この関数は、エラーメッセージを含むメッセージボックスを表示します。 カスタマイズされた追加のエラーメッセージを提供する場合は、この関数をオーバーライドします。 これは高度なオーバーライド可能です。

##  <a name="cdocumentsavemodified"></a><a name="savemodified"></a>CDocument:: SaveModified

変更されたドキュメントを閉じる前に、フレームワークによって呼び出されます。

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>戻り値

続行してドキュメントを閉じることが安全な場合は0以外の。ドキュメントを閉じない場合は0。

### <a name="remarks"></a>Remarks

この関数の既定の実装では、ドキュメントが作成されている場合に、変更を保存するかどうかをユーザーに確認するメッセージボックスが表示されます。 プログラムで別のプロンプト手順が必要な場合は、この関数をオーバーライドします。 これは高度なオーバーライド可能です。

##  <a name="cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>  CDocument::SetChunkValue

チャンク値を設定します。

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>パラメーター

*pValue*<br/>
設定するチャンク値を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

##  <a name="cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>  CDocument::SetModifiedFlag

ドキュメントに変更を加えた後に、この関数を呼び出します。

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>パラメーター

*bModified*<br/>
ドキュメントが変更されたかどうかを示すフラグです。

### <a name="remarks"></a>Remarks

この関数を一貫して呼び出すことにより、ユーザーがドキュメントを閉じる前に変更を保存するように求めるメッセージが表示されます。 通常は、 *Bmodified*パラメーターに対して既定値の TRUE を使用する必要があります。 ドキュメントをクリーン (未変更) としてマークするには、この関数を FALSE の値で呼び出します。

##  <a name="cdocumentsetpathname"></a><a name="setpathname"></a>  CDocument::SetPathName

ドキュメントのディスクファイルの完全修飾パスを指定するには、この関数を呼び出します。

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszPathName*<br/>
ドキュメントのパスとして使用される文字列を指します。

*bAddToMRU*<br/>
ファイル名が最近使用した (MRU) ファイルリストに追加されているかどうかを判断します。 TRUE の場合、ファイル名が追加されます。FALSE の場合、追加されません。

### <a name="remarks"></a>Remarks

*Baddtomru*の値によっては、アプリケーションによって管理される MRU リストにパスが追加されるか、追加されません。 一部のドキュメントは、ディスクファイルに関連付けられていないことに注意してください。 フレームワークによって使用されるファイルを開いたり保存したりするための既定の実装をオーバーライドする場合にのみ、この関数を呼び出します。

##  <a name="cdocumentsettitle"></a><a name="settitle"></a>CDocument:: SetTitle

ドキュメントのタイトル (フレームウィンドウのタイトルバーに表示される文字列) を指定するには、この関数を呼び出します。

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>パラメーター

*lpszTitle*<br/>
ドキュメントのタイトルとして使用される文字列を指します。

### <a name="remarks"></a>Remarks

この関数を呼び出すと、ドキュメントを表示するすべてのフレームウィンドウのタイトルが更新されます。

##  <a name="cdocumentupdateallviews"></a><a name="updateallviews"></a>CDocument:: UpdateAllViews

ドキュメントが変更された後に、この関数を呼び出します。

```
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>パラメーター

*pSender*<br/>
ドキュメントを変更したビューを指します。すべてのビューを更新する場合は NULL です。

*lHint*<br/>
変更に関する情報を格納します。

*pHint*<br/>
変更に関する情報を格納しているオブジェクトを指します。

### <a name="remarks"></a>Remarks

[SetModifiedFlag](#setmodifiedflag)メンバー関数を呼び出した後に、この関数を呼び出す必要があります。 この関数は、ドキュメントにアタッチされている各ビューを通知します。ただし、 *Psender*によって指定されたビューは、ドキュメントが変更されていることを前提としています。 通常、ビューを使用してユーザーがドキュメントを変更した後、この関数をビュークラスから呼び出します。

この関数は、送信ビュー、 *Phint* 、 *lhint*を除く各ドキュメントのビューに対して、 [CView:: OnUpdate](../../mfc/reference/cview-class.md#onupdate)メンバー関数を呼び出します。 これらのパラメーターを使用して、ドキュメントに加えられた変更に関する情報をビューに渡します。 *Lhint*を使用して情報をエンコードしたり、 [CObject](../../mfc/reference/cobject-class.md)から派生したクラスを定義して変更に関する情報を格納したり、 *phint*を使用してそのクラスのオブジェクトを渡したりすることができます。 [CView](../../mfc/reference/cview-class.md)派生クラスの `CView::OnUpdate` メンバー関数をオーバーライドして、渡された情報に基づいてビューの表示の更新を最適化します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>関連項目

[MFC のサンプル MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル NPP](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)
