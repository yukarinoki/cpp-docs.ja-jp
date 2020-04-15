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
ms.openlocfilehash: 2f8ba8d0b35bd72efa8f8d63dbefd689e645d768
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374048"
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
|[Cドキュメント::Cドキュメント](#cdocument)|`CDocument` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ドキュメント::ビューの追加](#addview)|ドキュメントにビューを添付します。|
|[ドキュメント::読み取りチャンクを開始](#beginreadchunks)|チャンク読み取りを初期化します。|
|[ドキュメント::フレームを閉じることができる](#cancloseframe)|高度なオーバーライド可能。このドキュメントを表示するフレーム ウィンドウを閉じる前に呼び出されます。|
|[Cドキュメント::クリアチャンクリスト](#clearchunklist)|チャンク リストをクリアします。|
|[Cドキュメント::クリアパス名](#clearpathname)|ドキュメント オブジェクトのパスをクリアします。|
|[ドキュメント::Dの内容](#deletecontents)|ドキュメントのクリーンアップを実行するために呼び出されます。|
|[Cドキュメント::チャンクを見つける](#findchunk)|指定された GUID を持つチャンクを検索します。|
|[Cドキュメント::ゲットアダプタ](#getadapter)|インターフェイスを実装`IDocument`するオブジェクトへのポインターを返します。|
|[ドキュメント::テンプレートを取得します。](#getdoctemplate)|ドキュメントの種類を記述するドキュメント テンプレートへのポインターを返します。|
|[Cドキュメント::ゲットファイル](#getfile)|目的`CFile`のオブジェクトへのポインターを返します。|
|[ドキュメント::最初のビューポジション](#getfirstviewposition)|ビューのリスト内の最初の位置を返します。を使用して反復を開始します。|
|[ドキュメント::次のビューを取得します。](#getnextview)|ドキュメントに関連付けられたビューのリストを反復処理します。|
|[ドキュメント::ゲットパス名](#getpathname)|ドキュメントのデータ ファイルのパスを返します。|
|[Cドキュメント::サムネイルを取得](#getthumbnail)|サムネイルを表示するためにサムネイル プロバイダーが使用するビットマップを作成するために呼び出されます。|
|[ドキュメント::タイトルを取得します。](#gettitle)|ドキュメントのタイトルを返します。|
|[ドキュメント::初期化検索コンテンツ](#initializesearchcontent)|検索ハンドラーの検索コンテンツを初期化するために呼び出されます。|
|[Cドキュメント::イズ修正](#ismodified)|ドキュメントが最後に保存されてから変更されたかどうかを示します。|
|[Cドキュメント::イサーチアンド整理ハンドラ](#issearchandorganizehandler)|検索&整理ハンドラー用`CDocument`にオブジェクトのこのインスタンスが作成されたかどうかを示します。|
|[ストリームから読み込む](#loaddocumentfromstream)|ストリームからドキュメント データを読み込むために呼び出されます。|
|[ドキュメント::オン・ハフォアリッチプレビューフォント変更](#onbeforerichpreviewfontchanged)|リッチ プレビュー のフォントが変更される前に呼び出されます。|
|[ドキュメント::オンリデータビューリスト](#onchangedviewlist)|ビューがドキュメントに追加または削除された後に呼び出されます。|
|[ドキュメント::ドキュメントを閉じる](#onclosedocument)|ドキュメントを閉じるために呼び出されます。|
|[ドキュメント::オンCreateプレビューフレーム](#oncreatepreviewframe)|リッチ プレビューのプレビュー フレームを作成する必要がある場合に、フレームワークによって呼び出されます。|
|[Cドキュメント::オンドキュメントイベント](#ondocumentevent)|ドキュメント イベントに応答して、フレームワークによって呼び出されます。|
|[Cドキュメント::オンドローサムネイル](#ondrawthumbnail)|サムネイルの内容を描画するには、派生クラスでこのメソッドをオーバーライドします。|
|[ストリームからドキュメントを読み取る](#onloaddocumentfromstream)|ストリームからドキュメント データを読み込む必要があるときに、フレームワークによって呼び出されます。|
|[Cドキュメント::オンニュードキュメント](#onnewdocument)|新しいドキュメントを作成するために呼び出されます。|
|[ドキュメント::オンオープンドキュメント](#onopendocument)|既存のドキュメントを開くために呼び出されます。|
|[Cドキュメント::オンプレビューハンドラクエリフォーカス](#onpreviewhandlerqueryfocus)|HwND が GetFocus 関数を呼び出して返すようにプレビュー ハンドラーを指示します。|
|[Cドキュメント::オンプレビューハンドラトランスレートアクセラレータ](#onpreviewhandlertranslateaccelerator)|プレビュー ハンドラが実行されているプロセスのメッセージ ポンプから渡されたキーストロークを処理するように、プレビュー ハンドラに指示します。|
|[ドキュメント::オンリッチプレビューバックカラー変更](#onrichpreviewbackcolorchanged)|リッチ プレビューの背景色が変更されたときに呼び出されます。|
|[ドキュメント::オンリッチプレビューフォント変更](#onrichpreviewfontchanged)|リッチ プレビュー のフォントが変更されたときに呼び出されます。|
|[ドキュメント::オンリッチプレビューサイト変更](#onrichpreviewsitechanged)|リッチ プレビュー サイトが変更されたときに呼び出されます。|
|[ドキュメント::オンリッチプレビューテキスト色を変更しました](#onrichpreviewtextcolorchanged)|リッチ プレビューのテキストの色が変更されたときに呼び出されます。|
|[ドキュメント::保存ドキュメント](#onsavedocument)|ドキュメントをディスクに保存するために呼び出されます。|
|[Cドキュメント::オンアンロードハンドラー](#onunloadhandler)|プレビュー ハンドラがアンロードされるときに、フレームワークによって呼び出されます。|
|[ドキュメント::P閉じるフレーム](#precloseframe)|フレーム ウィンドウを閉じる前に呼び出されます。|
|[ドキュメント::次のチャンク値](#readnextchunkvalue)|次のチャンク値を読み取ります。|
|[Cドキュメント::リリースファイル](#releasefile)|他のアプリケーションで使用できるようにファイルを解放します。|
|[Cドキュメント::チャンクの削除](#removechunk)|指定した GUID を持つチャンクを削除します。|
|[ドキュメント::ビューの削除](#removeview)|ドキュメントからビューを切り離します。|
|[ドキュメント::レポートセーブロード例外](#reportsaveloadexception)|高度なオーバーライド可能。例外が原因でオープン操作または保存操作を完了できない場合に呼び出されます。|
|[Cドキュメント::保存変更](#savemodified)|高度なオーバーライド可能。ドキュメントを保存するかどうかをユーザーに確認するために呼び出されます。|
|[ドキュメント::セットチャンク値](#setchunkvalue)|チャンク値を設定します。|
|[Cドキュメント::セット修正フラグ](#setmodifiedflag)|ドキュメントが最後に保存されてから変更されたことを示すフラグを設定します。|
|[Cドキュメント::セットパス名](#setpathname)|ドキュメントで使用するデータ ファイルのパスを設定します。|
|[Cドキュメント::セットタイトル](#settitle)|ドキュメントのタイトルを設定します。|
|[ドキュメント::すべてのビューを更新します。](#updateallviews)|ドキュメントが変更されたことをすべてのビューに通知します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[Cドキュメント::オンファイル送信メール](#onfilesendmail)|ドキュメントが添付されたメール メッセージを送信します。|
|[Cドキュメント::オンアップデートファイル送信メール](#onupdatefilesendmail)|メールサポートが存在する場合は、[メールの送信] コマンドを有効にします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ドキュメント::m_bGetThumbnailMode](#m_bgetthumbnailmode)|オブジェクトが`CDocument`サムネイル用の dllhost によって作成されたことを指定します。 でチェックインする`CView::OnDraw`必要があります。|
|[ドキュメント::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|`CDocument`の前のホストによってオブジェクトが作成されたことを指定`Rich Preview`します。 でチェックインする`CView::OnDraw`必要があります。|
|[ドキュメント::m_bSearchMode](#m_bsearchmode)|インデ`CDocument`クサーまたは他の検索アプリケーションによってオブジェクトが作成されたことを指定します。|
|[Cドキュメント::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|リッチ プレビュー ウィンドウの背景色を指定します。 この色はホストによって設定されます。|
|[ドキュメント::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|リッチ プレビュー ウィンドウの前景色を指定します。 この色はホストによって設定されます。|
|[ドキュメント::m_lfRichPreviewFont](#m_lfrichpreviewfont)|リッチ プレビュー ウィンドウのテキスト フォントを指定します。 このフォント情報はホストによって設定されます。|

## <a name="remarks"></a>解説

ドキュメントは、ユーザーが通常[ファイルを開く]コマンドで開き、[ファイルを保存]コマンドで保存するデータの単位を表します。

`CDocument`は、ドキュメントの作成、読み込み、保存などの標準操作をサポートします。 フレームワークは、 で定義されたインターフェイスを使用`CDocument`してドキュメントを操作します。

アプリケーションは、複数のタイプのドキュメントをサポートできます。たとえば、アプリケーションはスプレッドシートとテキスト ドキュメントの両方をサポートする場合があります。 ドキュメントの種類ごとに、関連付けられたドキュメント テンプレートがあります。ドキュメント テンプレートは、その種類のドキュメントに使用するリソース (メニュー、アイコン、アクセラレータ テーブルなど) を指定します。 各ドキュメントには、関連付けられた`CDocTemplate`オブジェクトへのポインタが含まれています。

ユーザーは、関連付けられた[CView](../../mfc/reference/cview-class.md)オブジェクトを通じてドキュメントを操作します。 ビューは、フレーム ウィンドウにドキュメントのイメージをレンダリングし、ユーザー入力をドキュメントに対する操作として解釈します。 ドキュメントには、複数のビューを関連付けることができます。 ユーザーがドキュメントのウィンドウを開くと、フレームワークはビューを作成し、ドキュメントにアタッチします。 ドキュメント テンプレートは、ドキュメントの種類ごとに表示するビューとフレーム ウィンドウの種類を指定します。

ドキュメントはフレームワークの標準コマンド ルーティングの一部であり、その結果、標準のユーザー インターフェイス コンポーネント ([ファイルの保存] メニュー項目など) からコマンドを受け取ります。 ドキュメントは、アクティブなビューによって転送されるコマンドを受け取ります。 ドキュメントが特定のコマンドを処理しない場合、そのコマンドを管理するドキュメント テンプレートに転送します。

ドキュメントのデータが変更されると、各ビューにそれらの変更が反映されている必要があります。 `CDocument`は、このような変更のビューを通知するための[UpdateAllViews](#updateallviews)メンバー関数を提供するため、ビューは必要に応じて自分自身を再描画できます。 また、フレームワークは、変更されたファイルを閉じる前に保存するようにユーザーに求めます。

一般的なアプリケーションでドキュメントを実装するには、次の操作を行う必要があります。

- ドキュメントの各タイプ`CDocument`のクラスを派生させます。

- 各ドキュメントのデータを格納するメンバー変数を追加します。

- ドキュメントのデータを読み取り、変更するためのメンバー関数を実装します。 ドキュメントのビューは、これらのメンバー関数の最も重要なユーザーです。

- ドキュメント クラスの[CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)メンバー関数をオーバーライドして、ドキュメントのデータをディスクに書き込んだり、ディスクから読み取りしたりします。

`CDocument`は、メールサポート(MAPI)が存在する場合、メールを介して文書を送信することをサポートします。 MFC での[MAPI](../../mfc/mapi.md)および[MAPI サポートの記事を](../../mfc/mapi-support-in-mfc.md)参照してください。

`CDocument`詳細については、「[シリアル化](../../mfc/serialization-in-mfc.md)、[ドキュメント/ビュー アーキテクチャ のトピック](../../mfc/document-view-architecture.md)、および[ドキュメント/ビューの作成](../../mfc/document-view-creation.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cdocumentaddview"></a><a name="addview"></a>ドキュメント::ビューの追加

ドキュメントにビューを添付します。

```
void AddView(CView* pView);
```

### <a name="parameters"></a>パラメーター

*pビュー*<br/>
追加するビューへのポイント。

### <a name="remarks"></a>解説

この関数は、指定されたビューをドキュメントに関連付けられたビューのリストに追加します。この関数は、ビューのドキュメント ポインタもこのドキュメントに設定します。 フレームワークは、新しく作成されたビュー オブジェクトをドキュメントにアタッチするときにこの関数を呼び出します。これは、ファイル新規作成、ファイルを開く、またはウィンドウの新規作成コマンドに応答して、または分割ウィンドウが分割されているときに発生します。

ビューを手動で作成およびアタッチする場合にのみ、この関数を呼び出します。 通常、フレームワークは、ドキュメント クラス、ビュー クラス、およびフレーム ウィンドウ クラスを関連付ける[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクトを定義することによって、ドキュメントとビューを接続します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

## <a name="cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>ドキュメント::読み取りチャンクを開始

チャンク読み取りを初期化します。

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>解説

## <a name="cdocumentcancloseframe"></a><a name="cancloseframe"></a>ドキュメント::フレームを閉じることができる

ドキュメントを表示するフレーム ウィンドウが閉じられる前に、フレームワークによって呼び出されます。

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>パラメーター

*フレーム*<br/>
ドキュメントにアタッチされているビューのフレーム ウィンドウへの移動。

### <a name="return-value"></a>戻り値

フレーム ウィンドウを閉じても安全な場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

既定の実装では、ドキュメントを表示する他のフレーム ウィンドウがあるかどうかを確認します。 指定したフレーム ウィンドウがドキュメントを最後に表示する場合、ドキュメントが変更されている場合は、ドキュメントを保存するように求めるメッセージが表示されます。 フレーム ウィンドウを閉じたときに特別な処理を実行する場合は、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。

## <a name="cdocumentcdocument"></a><a name="cdocument"></a>Cドキュメント::Cドキュメント

`CDocument` オブジェクトを構築します。

```
CDocument();
```

### <a name="remarks"></a>解説

フレームワークは、ドキュメントの作成を処理します。 [OnNewDocument](#onnewdocument)メンバー関数をオーバーライドして、ドキュメントごとに初期化を実行します。これは、単一ドキュメント インターフェイス (SDI) アプリケーションで特に重要です。

## <a name="cdocumentclearchunklist"></a><a name="clearchunklist"></a>Cドキュメント::クリアチャンクリスト

チャンク リストをクリアします。

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>解説

## <a name="cdocumentclearpathname"></a><a name="clearpathname"></a>Cドキュメント::クリアパス名

ドキュメント オブジェクトのパスをクリアします。

```
virtual void ClearPathName();
```

### <a name="remarks"></a>解説

オブジェクトからパスを`CDocument`クリアすると、アプリケーションは、ドキュメントが次に保存されるときにユーザーにプロンプトを表示します。 これにより、[**名前を付けて保存]** コマンドと同様に **[保存]** コマンドが動作します。

## <a name="cdocumentdeletecontents"></a><a name="deletecontents"></a>ドキュメント::Dの内容

オブジェクト自体を破棄せずにドキュメントのデータを削除するために、フレームワークによって呼`CDocument`び出されます。

```
virtual void DeleteContents();
```

### <a name="remarks"></a>解説

ドキュメントが破棄される直前に呼び出されます。 また、ドキュメントが再利用される前に、ドキュメントが空であることを確認するために呼び出されます。 これは、1 つのドキュメントのみを使用する SDI アプリケーションでは特に重要です。ユーザーが別のドキュメントを作成または開くたびに、ドキュメントが再利用されます。 ドキュメントのすべてのデータを削除する "すべてクリアの編集" または同様のコマンドを実装します。 この関数の既定の実装は、何も行いません。 ドキュメント内のデータを削除するには、この関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

## <a name="cdocumentfindchunk"></a><a name="findchunk"></a>Cドキュメント::チャンクを見つける

指定された GUID を持つチャンクを検索します。

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>パラメーター

*guid*<br/>
検索するチャンクの GUID を指定します。

*Pid*<br/>
検索するチャンクの PID を指定します。

### <a name="return-value"></a>戻り値

成功した場合は、内部チャンク リスト内の位置。 それ以外の場合は NULL。

### <a name="remarks"></a>解説

## <a name="cdocumentgetadapter"></a><a name="getadapter"></a>Cドキュメント::ゲットアダプタ

インターフェイスを実装するオブジェクトへのポインターを`IDocument`返します。

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>戻り値

`IDocument`インターフェイスを実装するオブジェクトへのポインター。

### <a name="remarks"></a>解説

## <a name="cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>ドキュメント::テンプレートを取得します。

このドキュメントの種類のドキュメント テンプレートへのポインターを取得します。

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>戻り値

このドキュメントの種類のドキュメント テンプレートへのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

## <a name="cdocumentgetfile"></a><a name="getfile"></a>Cドキュメント::ゲットファイル

`CFile`オブジェクトへのポインターを取得します。

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
目的のファイルへのパスを表す文字列。 パスは相対パスまたは絶対パスです。

*pError*<br/>
操作の完了状態を示す既存のファイル例外オブジェクトへのポインター。

*フラグを開く*<br/>
共有モードとアクセスモード。 ファイルを開くときに実行するアクションを指定します。 CFile コンストラクター [CFile::CFile](../../mfc/reference/cfile-class.md#cfile)にリストされているオプションを結合するには、ビットごとの OR (&#124;) 演算子を使用します。 アクセス権と共有オプションが 1 つ必要です。と`modeCreate``modeNoInherit`モードはオプションです。

### <a name="return-value"></a>戻り値

`CFile` オブジェクトを指すポインターです。

## <a name="cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>ドキュメント::最初のビューポジション

ドキュメントに関連付けられたビューのリスト内の最初のビューの位置を取得します。

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>戻り値

[メンバー関数を](#getnextview)使用して反復処理に使用できる位置値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetnextview"></a><a name="getnextview"></a>ドキュメント::次のビューを取得します。

ドキュメントのすべてのビューを反復処理します。

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*r位置*<br/>
メンバー関数への以前の呼び出しによって返された位置`GetNextView`値[GetFirstViewPosition](#getfirstviewposition)への参照。 この値は NULL にできません。

### <a name="return-value"></a>戻り値

*rPosition*で識別されるビューへのポインター。

### <a name="remarks"></a>解説

この関数は *、rPosition*で識別されたビューを返し *、rPosition*をリスト内の次のビューの位置値に設定します。 取得したビューがリストの最後のビューである場合 *、rPosition*は NULL に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetpathname"></a><a name="getpathname"></a>ドキュメント::ゲットパス名

ドキュメントのディスク ファイルの絶対パスを取得します。

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>戻り値

ドキュメントの完全修飾パス。 ドキュメントが保存されていない場合、またはディスク ファイルが関連付けられていない場合、この文字列は空です。

## <a name="cdocumentgetthumbnail"></a><a name="getthumbnail"></a>Cドキュメント::サムネイルを取得

サムネイル プロバイダーがサムネイルを表示するために使用するビットマップを作成します。

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>パラメーター

*Cx*<br/>
ビットマップの幅と高さを指定します。

*フmpmp*<br/>
関数が正常に返された場合に、ビットマップへのハンドルを格納します。

*pdw アルファ*<br/>
関数が正常に返された場合に、アルファ チャネル値を指定する DWORD を格納します。

### <a name="return-value"></a>戻り値

サムネイルのビットマップが正常に作成された場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cdocumentgettitle"></a><a name="gettitle"></a>ドキュメント::タイトルを取得します。

通常はドキュメントのファイル名から派生するドキュメントのタイトルを取得します。

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>戻り値

ドキュメントのタイトル。

## <a name="cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>ドキュメント::初期化検索コンテンツ

検索ハンドラーの検索コンテンツを初期化するために呼び出されます。

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>解説

検索コンテンツを初期化するには、派生クラスでこのメソッドをオーバーライドします。 コンテンツは、";" で区切られた部分を持つ文字列である必要があります。 たとえば、"ポイント;長方形;oleアイテム"。

## <a name="cdocumentismodified"></a><a name="ismodified"></a>Cドキュメント::イズ修正

ドキュメントが最後に保存されてから変更されたかどうかを調べます。

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>戻り値

ドキュメントが最後に保存されてから変更された場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>Cドキュメント::イサーチアンド整理ハンドラ

検索&整理ハンドラーに`CDocument`対してこのインスタンスが作成されたかどうかを示します。

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>戻り値

のこのインスタンス`CDocument`が検索&整理ハンドラー用に作成された場合は TRUE を返します。

### <a name="remarks"></a>解説

現在、この関数は、プロセス外のサーバーに実装されているリッチ プレビュー ハンドラに対してのみ TRUE を返します。 アプリケーション レベルで適切なフラグ (m_bPreviewHandlerMode、m_bSearchMode、m_bGetThumbnailMode) を設定すると、この関数が TRUE を返すようにできます。

## <a name="cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>ストリームから読み込む

ストリームからドキュメント データを読み込むために呼び出されます。

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>パラメーター

*pストリーム*<br/>
ストリームへのポインター。 このストリームはシェルによって提供されます。

*ドグラフモード*<br/>
ストリームへのアクセス モード。

### <a name="return-value"></a>戻り値

S_OK読み込み操作が成功した場合は HRESULT エラー コードを返します。

### <a name="remarks"></a>解説

ストリームからデータを読み込む方法をカスタマイズするには、派生クラスでこのメソッドをオーバーライドできます。

## <a name="cdocumentm_bgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>ドキュメント::m_bGetThumbnailMode

オブジェクトがサムネイル`CDocument`用の dllhost によって作成されたことを指定します。 でチェックインする`CView::OnDraw`必要があります。

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>解説

`TRUE`ドキュメントがサムネイル用の dllhost によって作成されたことを示します。

## <a name="cdocumentm_bpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>ドキュメント::m_bPreviewHandlerMode

`CDocument`オブジェクトがリッチ プレビュー用プレブホストによって作成されたことを指定します。 でチェックインする`CView::OnDraw`必要があります。

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>解説

TRUE は、ドキュメントがリッチ プレビューのプレブホストによって作成されたことを示します。

## <a name="cdocumentm_bsearchmode"></a><a name="m_bsearchmode"></a>ドキュメント::m_bSearchMode

オブジェクトがイン`CDocument`デクサーまたは別の検索アプリケーションによって作成されたことを指定します。

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>解説

`TRUE`ドキュメントがインデクサーまたは別の検索アプリケーションによって作成されたことを示します。

## <a name="cdocumentm_clrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>Cドキュメント::m_clrRichPreviewBackColor

リッチ プレビュー ウィンドウの背景色を指定します。 この色はホストによって設定されます。

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>解説

## <a name="cdocumentm_clrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>ドキュメント::m_clrRichPreviewTextColor

リッチ プレビュー ウィンドウの前景色を指定します。 この色はホストによって設定されます。

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>解説

## <a name="cdocumentm_lfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>ドキュメント::m_lfRichPreviewFont

リッチ プレビュー ウィンドウのテキスト フォントを指定します。 このフォント情報はホストによって設定されます。

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>解説

## <a name="cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>ドキュメント::オン・ハフォアリッチプレビューフォント変更

リッチ プレビュー フォントが変更される前に呼び出されます。

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>解説

## <a name="cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>ドキュメント::オンリデータビューリスト

ビューがドキュメントに追加またはドキュメントから削除された後に、フレームワークによって呼び出されます。

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>解説

この関数の既定の実装では、最後のビューが削除されているかどうかを確認し、削除されている場合は、ドキュメントを削除します。 フレームワークがビューを追加または削除するときに特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、ドキュメントにビューがアタッチされていない場合でもドキュメントを開いたままにする場合は、この関数をオーバーライドします。

## <a name="cdocumentonclosedocument"></a><a name="onclosedocument"></a>ドキュメント::ドキュメントを閉じる

ドキュメントが閉じられたときに、通常はファイルを閉じるコマンドの一部として、フレームワークによって呼び出されます。

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>解説

この関数の既定の実装では、ドキュメントの表示に使用されるすべてのフレームが破棄され、ビューが閉じ、ドキュメントの内容がクリーンアップされ[、DeleteContents](#deletecontents)メンバー関数が呼び出されてドキュメントのデータが削除されます。

フレームワークがドキュメントを閉じるときに特別なクリーンアップ処理を実行する場合は、この関数をオーバーライドします。 たとえば、ドキュメントがデータベース内のレコードを表す場合、この関数をオーバーライドしてデータベースを閉じる必要があります。 オーバーライドからこの関数の基本クラス バージョンを呼び出す必要があります。

## <a name="cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>ドキュメント::オンCreateプレビューフレーム

リッチ プレビューのプレビュー フレームを作成する必要がある場合に、フレームワークによって呼び出されます。

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>戻り値

フレームが正常に作成された場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cdocumentondocumentevent"></a><a name="ondocumentevent"></a>Cドキュメント::オンドキュメントイベント

ドキュメント イベントに応答して、フレームワークによって呼び出されます。

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>パラメーター

*デイベント*<br/>
[in]イベントの種類を記述する列挙型。

### <a name="remarks"></a>解説

ドキュメント イベントは、複数のクラスに影響する場合があります。 このメソッドは[、CDocument クラス](../../mfc/reference/cdocument-class.md)以外のクラスに影響を与えるドキュメント イベントを処理します。 現在、ドキュメント イベントに応答する必要がある唯一の[クラスは、 CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)です。 クラス`CDocument`には、 に対する影響を処理する他のオーバーライド可能`CDocument`なメソッドがあります。

次の表に *、deEvent*の値と、対応するイベントの一覧を示します。

|[値]|対応するイベント|
|-----------|-------------------------|
|`onAfterNewDocument`|新しいドキュメントが作成されました。|
|`onAfterOpenDocument`|新しいドキュメントが開かれました。|
|`onAfterSaveDocument`|ドキュメントが保存されました。|
|`onAfterCloseDocument`|ドキュメントは閉じられました。|

## <a name="cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>Cドキュメント::オンドローサムネイル

サムネイルを描画するには、派生クラスでこのメソッドをオーバーライドします。

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>パラメーター

*Dc*<br/>
デバイス コンテキストへの参照。

*lprcBounds*<br/>
サムネイルを描画する領域の外接する四角形を指定します。

### <a name="remarks"></a>解説

## <a name="cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>Cドキュメント::オンファイル送信メール

ドキュメントを添付ファイルとして、常駐メール ホスト経由でメッセージを送信します( 存在する場合)。

```
void OnFileSendMail();
```

### <a name="remarks"></a>解説

`OnFileSendMail`[OnSaveDocument](#onsavedocument)を呼び出して、タイトルのない変更されたドキュメントを一時ファイルにシリアル化 (保存) し、電子メールで送信します。 ドキュメントが変更されていない場合、一時ファイルは必要ありません。オリジナルが送信されます。 `OnFileSendMail`MAPI32 を読み込みます。DLL がまだ読み込まれていない場合。

の特別な実装`OnFileSendMail`[は](../../mfc/reference/coledocument-class.md)、複合ファイルを正しく処理します。

`CDocument`は、メールサポート(MAPI)が存在する場合、メールを介して文書を送信することをサポートします。 MFC の[MAPI トピック](../../mfc/mapi.md)と MAPI[サポートの記事を](../../mfc/mapi-support-in-mfc.md)参照してください。

## <a name="cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>ストリームからドキュメントを読み取る

ストリームからドキュメント データを読み込む必要がある場合に、フレームワークによって呼び出されます。

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>パラメーター

*pストリーム*<br/>
受信ストリームへのポインター。

*グレフモード*<br/>
ストリームへのアクセス モード。

### <a name="return-value"></a>戻り値

ロードが成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

## <a name="cdocumentonnewdocument"></a><a name="onnewdocument"></a>Cドキュメント::オンニュードキュメント

[ファイルの新規作成] コマンドの一部として、フレームワークによって呼び出されます。

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>戻り値

ドキュメントが正常に初期化された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数の既定の実装では[、DeleteContents](#deletecontents)メンバー関数を呼び出して、ドキュメントが空であることを確認し、新しいドキュメントをクリーンとしてマークします。 新しいドキュメントのデータ構造を初期化するには、この関数をオーバーライドします。 オーバーライドからこの関数の基本クラス バージョンを呼び出す必要があります。

ユーザーが SDI アプリケーションで File New コマンドを選択した場合、フレームワークはこの関数を使用して、新しいドキュメントを作成するのではなく、既存のドキュメントを再初期化します。 ユーザーがマルチ ドキュメント インターフェイス (MDI) アプリケーションで [ファイル新規作成] を選択した場合、フレームワークは毎回新しいドキュメントを作成し、この関数を呼び出して初期化します。 SDI アプリケーションで有効にするには、File New コマンドのコンストラクターではなく、初期化コードをこの関数に配置する必要があります。

2回呼び出`OnNewDocument`される場合があることに注意してください。 これは、ドキュメントが ActiveX ドキュメント サーバーとして埋め込まれている場合に発生します。 この関数は、最初`CreateInstance`にメソッドによって呼び出されます`COleObjectFactory`(-derived クラスによって公開される)`InitNew`とメソッドによって 2`COleServerDoc`回目の呼び出し (-derived クラスによって公開されます)。

### <a name="example"></a>例

次の例は、ドキュメント オブジェクトを初期化する別の方法を示しています。

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

## <a name="cdocumentonopendocument"></a><a name="onopendocument"></a>ドキュメント::オンオープンドキュメント

[ファイルを開く] コマンドの一部として、フレームワークによって呼び出されます。

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>パラメーター

*パス名*<br/>
開くドキュメントのパスへのポイント。

### <a name="return-value"></a>戻り値

ドキュメントが正常に読み込まれた場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数の既定の実装では、指定したファイルを開き[、DeleteContents](#deletecontents)メンバー関数を呼び出してドキュメントが空であることを確認し[、CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)を呼び出してファイルの内容を読み取り、ドキュメントをクリーンとしてマークします。 アーカイブ・メカニズムまたはファイル・メカニズム以外のものを使用する場合は、この関数をオーバーライドします。 たとえば、ドキュメントが別々のファイルではなく、データベース内のレコードを表すアプリケーションを作成できます。

ユーザーが SDI アプリケーションで File Open コマンドを選択した場合、フレームワークはこの関数を使用して`CDocument`、新しいオブジェクトを作成するのではなく、既存のオブジェクトを再初期化します。 ユーザーが MDI アプリケーションで File Open を選択した場合、フレームワーク`CDocument`は毎回新しいオブジェクトを作成し、この関数を呼び出して初期化します。 SDI アプリケーションで有効にするには、File Open コマンドのコンストラクターではなく、初期化コードをこの関数に配置する必要があります。

### <a name="example"></a>例

次の例は、ドキュメント オブジェクトを初期化する別の方法を示しています。

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

## <a name="cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>Cドキュメント::オンプレビューハンドラクエリフォーカス

関数の呼び出しから取得した HWND を返`GetFocus`すようにプレビュー ハンドラに指示します。

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>パラメーター

*フーンド*<br/>
[アウト]このメソッドが返されるときに、プレビュー ハンドラのフォアグラウンド スレッドから関数`GetFocus`を呼び出した結果から返される HWND へのポインターを格納します。

### <a name="return-value"></a>戻り値

成功した場合はS_OKを返します。それ以外の場合はエラー値。

### <a name="remarks"></a>解説

## <a name="cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>Cドキュメント::オンプレビューハンドラトランスレートアクセラレータ

プレビュー ハンドラが実行されているプロセスのメッセージ ポンプから渡されたキーストロークを処理するように、プレビュー ハンドラに指示します。

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>パラメーター

*Pmsg*<br/>
[in]ウィンドウ メッセージへのポインター。

### <a name="return-value"></a>戻り値

キー入力メッセージがプレビュー ハンドラで処理できる場合、ハンドラはそれを処理し、S_OK返します。 プレビュー ハンドラがキーストローク メッセージを処理できない場合は、 を使用して`IPreviewHandlerFrame::TranslateAccelerator`ホストに提供します。 ホストがメッセージを処理する場合、このメソッドはS_OKを返します。 ホストがメッセージを処理しない場合、このメソッドはS_FALSEを返します。

### <a name="remarks"></a>解説

## <a name="cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>ドキュメント::オンリッチプレビューバックカラー変更

リッチ プレビューの背景色が変更されたときに呼び出されます。

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>解説

## <a name="cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>ドキュメント::オンリッチプレビューフォント変更

リッチ プレビュー のフォントが変更されたときに呼び出されます。

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>解説

## <a name="cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>ドキュメント::オンリッチプレビューサイト変更

リッチ プレビュー サイトが変更されたときに呼び出されます。

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>解説

## <a name="cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>ドキュメント::オンリッチプレビューテキスト色を変更しました

リッチ プレビューのテキストの色が変更されたときに呼び出されます。

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>解説

## <a name="cdocumentonsavedocument"></a><a name="onsavedocument"></a>ドキュメント::保存ドキュメント

[ファイルの保存] コマンドまたは [名前を付けて保存] コマンドの一部として、フレームワークによって呼び出されます。

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>パラメーター

*パス名*<br/>
ファイルの保存先となる絶対パスへのパスを指定します。

### <a name="return-value"></a>戻り値

ドキュメントが正常に保存された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数の既定の実装では、指定されたファイルを開き[、CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)を呼び出してドキュメントのデータをファイルに書き込み、ドキュメントをクリーンとしてマークします。 フレームワークがドキュメントを保存するときに特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、ドキュメントが別々のファイルではなく、データベース内のレコードを表すアプリケーションを作成できます。

## <a name="cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>Cドキュメント::オンアンロードハンドラー

プレビュー ハンドラがアンロードされたときに、フレームワークによって呼び出されます。

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>解説

## <a name="cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>Cドキュメント::オンアップデートファイル送信メール

メール サポート (MAPI) が存在する場合は、ID_FILE_SEND_MAIL コマンドを有効にします。

```
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
ID_FILE_SEND_MAIL コマンドに関連付けられている[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

それ以外の場合、メニュー項目の上または下の区切り文字を含む、メニューからID_FILE_SEND_MAILコマンドを削除します。 MAPI 32 の場合は、MAPI が有効になります。DLL は、WIN の [メール] セクションのパスに存在します。INI ファイル、MAPI=1。 ほとんどのアプリケーションでは、[ファイル] メニューにこのコマンドを配置します。

`CDocument`は、メールサポート(MAPI)が存在する場合、メールを介して文書を送信することをサポートします。 MFC の[MAPI トピック](../../mfc/mapi.md)と MAPI[サポートの記事を](../../mfc/mapi-support-in-mfc.md)参照してください。

## <a name="cdocumentprecloseframe"></a><a name="precloseframe"></a>ドキュメント::P閉じるフレーム

このメンバー関数は、フレーム ウィンドウが破棄される前に、フレームワークによって呼び出されます。

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>パラメーター

*フレーム*<br/>
関連付けられた`CDocument`オブジェクトを保持する[CFrameWnd](../../mfc/reference/cframewnd-class.md)へのポインター。

### <a name="remarks"></a>解説

カスタム クリーンアップを提供するためにオーバーライドできますが、必ず基本クラスも呼び出してください。

のデフォルトは`PreCloseFrame`、 では`CDocument`何も行いません。 派生クラス[COleDocument](../../mfc/reference/coledocument-class.md)と[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)このメンバー関数を使用します。 `CDocument`

## <a name="cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>ドキュメント::次のチャンク値

次のチャンク値を読み取ります。

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>パラメーター

*再評価*<br/>
[アウト]関数が戻るとき *、ppValue*には読み込まれた値が含まれます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

## <a name="cdocumentreleasefile"></a><a name="releasefile"></a>Cドキュメント::リリースファイル

このメンバー関数は、他のアプリケーションで使用できるように、ファイルを解放するためにフレームワークによって呼び出されます。

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>パラメーター

*ファイル*<br/>
解放する CFile オブジェクトへのポインター。

*中止*<br/>
ファイルを解放`CFile::Close`するかどうかを指定`CFile::Abort`します。 ファイルを[CFile::Close](../../mfc/reference/cfile-class.md#close)を使用して解放する場合は FALSE。ファイルを[CFile::Abort](../../mfc/reference/cfile-class.md#abort)を使用して解放する場合は TRUE。

### <a name="remarks"></a>解説

*bAbort*が TRUE `ReleaseFile` `CFile::Abort`の場合は、 を呼び出し、ファイルが解放されます。 `CFile::Abort`例外はスローされません。

*bAbort*が FALSE `ReleaseFile` `CFile::Close`の場合は、呼び出しを行い、ファイルが解放されます。

ファイルが解放される前にユーザーがアクションを実行するように要求するには、このメンバー関数をオーバーライドします。

## <a name="cdocumentremovechunk"></a><a name="removechunk"></a>Cドキュメント::チャンクの削除

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

### <a name="remarks"></a>解説

## <a name="cdocumentremoveview"></a><a name="removeview"></a>ドキュメント::ビューの削除

ドキュメントからビューを切り離します。

```
void RemoveView(CView* pView);
```

### <a name="parameters"></a>パラメーター

*pビュー*<br/>
削除するビューへのポイント。

### <a name="remarks"></a>解説

この関数は、ドキュメントに関連付けられたビューのリストから指定されたビューを削除します。また、ビューのドキュメント ポインタも NULL に設定されます。 この関数は、フレーム ウィンドウが閉じているか、または分割ウィンドウのウィンドウが閉じられたときに、フレームワークによって呼び出されます。

ビューを手動でデタッチする場合にのみ、この関数を呼び出します。 通常、ドキュメント クラス、ビュー クラス、およびフレーム ウィンドウ クラスを関連付ける[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクトを定義することで、フレームワークでドキュメントとビューをデタッチできます。

実装例については[、AddView](#addview)の例を参照してください。

## <a name="cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>ドキュメント::レポートセーブロード例外

ドキュメントの保存または読み込み中に例外がスローされた場合に呼び出されます ( 通常は[CFileException](../../mfc/reference/cfileexception-class.md)または[CArchiveException](../../mfc/reference/carchiveexception-class.md)) 。

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>パラメーター

*パス名*<br/>
保存または読み込み中のドキュメントの名前へのポイント。

*E*<br/>
スローされた例外へのポイント。 NULL の場合もあります。

*b保存*<br/>
進行中の操作を示すフラグ。ドキュメントが保存されていた場合は 0 以外、読み込まれている場合は 0 以外の値を返します。

*デフォルト*<br/>
関数により具体的なものを指定しない場合に表示されるエラーメッセージの識別子。

### <a name="remarks"></a>解説

既定の実装では、例外オブジェクトを調べ、原因を具体的に説明するエラー メッセージを探します。 特定のメッセージが見つからない場合、または*e*が NULL の場合は *、nIDPDefault*パラメーターで指定された一般メッセージが使用されます。 次に、エラー メッセージを含むメッセージ ボックスを表示します。 カスタマイズされた追加のエラー メッセージを提供する場合は、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。

## <a name="cdocumentsavemodified"></a><a name="savemodified"></a>Cドキュメント::保存変更

変更されたドキュメントを閉じる前に、フレームワークによって呼び出されます。

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>戻り値

ドキュメントを続行して閉じるのが安全な場合は 0 以外の値を返します。ドキュメントを閉じないようにする場合は 0。

### <a name="remarks"></a>解説

この関数の既定の実装では、ドキュメントに変更が加えられた場合に、その変更を保存するかどうかをユーザーに確認するメッセージ ボックスが表示されます。 プログラムで別のプロンプト処理が必要な場合は、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。

## <a name="cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>ドキュメント::セットチャンク値

チャンク値を設定します。

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>パラメーター

*pValue*<br/>
設定するチャンク値を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

## <a name="cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>Cドキュメント::セット修正フラグ

ドキュメントに変更を加えた後、この関数を呼び出します。

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>パラメーター

*bModified*<br/>
ドキュメントが変更されたかどうかを示すフラグです。

### <a name="remarks"></a>解説

この関数を一貫して呼び出すことで、ドキュメントを閉じる前に、フレームワークによってユーザーに変更を保存するように求めるメッセージが表示されます。 通常 *、bModified*パラメータにはデフォルト値の TRUE を使用する必要があります。 ドキュメントをクリーン (変更されていない) としてマークするには、この関数を FALSE の値で呼び出します。

## <a name="cdocumentsetpathname"></a><a name="setpathname"></a>Cドキュメント::セットパス名

ドキュメントのディスク ファイルの絶対パスを指定します。

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>パラメーター

*パス名*<br/>
ドキュメントのパスとして使用する文字列へのポイント。

*ブアドトムル*<br/>
ファイル名を最近使用した (MRU) ファイルリストに追加するかどうかを指定します。 TRUE の場合は、ファイル名が追加されます。FALSE の場合は追加されません。

### <a name="remarks"></a>解説

*bAddToMRU*の値に応じて、アプリケーションによって維持される MRU リストにパスが追加されるか、追加されません。 一部のドキュメントはディスク ファイルに関連付けられていないことに注意してください。 フレームワークで使用するファイルを開いたり保存するために既定の実装をオーバーライドする場合にのみ、この関数を呼び出します。

## <a name="cdocumentsettitle"></a><a name="settitle"></a>Cドキュメント::セットタイトル

ドキュメントのタイトル (フレーム ウィンドウのタイトル バーに表示される文字列) を指定します。

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>パラメーター

*lpszタイトル*<br/>
ドキュメントのタイトルとして使用する文字列へのポイント。

### <a name="remarks"></a>解説

この関数を呼び出すと、ドキュメントを表示するすべてのフレーム ウィンドウのタイトルが更新されます。

## <a name="cdocumentupdateallviews"></a><a name="updateallviews"></a>ドキュメント::すべてのビューを更新します。

ドキュメントが変更された後にこの関数を呼び出します。

```
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ドキュメントを変更したビューへのポイント、またはすべてのビューを更新する場合は NULL を指定します。

*lヒント*<br/>
変更に関する情報が含まれます。

*ヒント*<br/>
変更に関する情報を格納するオブジェクトへのポイント。

### <a name="remarks"></a>解説

この関数は、メンバー関数を呼び出した後[に](#setmodifiedflag)呼び出す必要があります。 この関数は、ドキュメントに添付されている各ビューに *、pSender*で指定されたビューを除き、ドキュメントが変更されたことを通知します。 通常、ユーザーがビューを使用してドキュメントを変更した後、ビュー クラスからこの関数を呼び出します。

この関数は、送信側ビューを除く各ドキュメントのビューに対して[CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)メンバー関数を呼び出し *、pHint*と*lHint*を渡します。 これらのパラメータを使用して、ドキュメントに加えられた変更に関する情報をビューに渡します。 *lHint*を使用して情報をエンコードしたり[、CObject](../../mfc/reference/cobject-class.md)派生クラスを定義して変更に関する情報を格納したり *、pHint*を使用してそのクラスのオブジェクトを渡したりできます。 `CView::OnUpdate` [CView](../../mfc/reference/cview-class.md)派生クラスのメンバー関数をオーバーライドして、渡された情報に基づいてビューの表示の更新を最適化します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>関連項目

[サンプル MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル スナップVW](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル NPP](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[クラス](../../mfc/reference/cdoctemplate-class.md)
