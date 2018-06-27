---
title: CDocument クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0d67012afe34cf3fe2c4633f2d838d1f3bfb49
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952532"
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
|[CDocument::CDocument](#cdocument)|`CDocument` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocument::AddView](#addview)|ビューをドキュメントにアタッチします。|  
|[CDocument::BeginReadChunks](#beginreadchunks)|チャンクの読み取りを初期化します。|  
|[CDocument::CanCloseFrame](#cancloseframe)|オーバーライド可能な; 高度なこのドキュメントを表示するフレーム ウィンドウを閉じる前に呼び出されます。|  
|[CDocument::ClearChunkList](#clearchunklist)|チャンクの一覧をクリアします。|  
|[CDocument::ClearPathName](#clearpathname)|ドキュメント オブジェクトのパスを消去します。|  
|[のに](#deletecontents)|ドキュメントのクリーンアップを実行するには、呼び出されます。|  
|[CDocument::FindChunk](#findchunk)|指定した GUID のチャンクを検索します。|  
|[CDocument::GetAdapter](#getadapter)|実装するオブジェクトへのポインターを返します`IDocument`インターフェイスです。|  
|[CDocument::GetDocTemplate](#getdoctemplate)|ドキュメントの種類を説明するドキュメント テンプレートへのポインターを返します。|  
|[CDocument::GetFile](#getfile)|目的にポインターを返します`CFile`オブジェクト。|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|最初の位置を返しますビューの一覧で、。イテレーションを開始するために使用します。|  
|[CDocument::GetNextView](#getnextview)|ドキュメントに関連付けられているビューの一覧を反復処理します。|  
|[CDocument::GetPathName](#getpathname)|ドキュメントのデータ ファイルのパスを返します。|  
|[CDocument::GetThumbnail](#getthumbnail)|サムネイルを表示するサムネイル プロバイダーで使用されるビットマップを作成するには、呼び出されます。|  
|[CDocument::GetTitle](#gettitle)|ドキュメントのタイトルを返します。|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|検索ハンドラーの検索コンテンツを初期化するために呼び出されます。|  
|[CDocument::IsModified](#ismodified)|ドキュメントが最後に保存された後に変更されているかどうかを示します。|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|指示するかどうかのこのインスタンス`CDocument`検索と整理のハンドラーのオブジェクトが作成されました。|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|ストリームからドキュメント データを読み込むと呼ばれます。|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|リッチ プレビューのフォントを変更する前に呼び出されます。|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|ビューが追加またはドキュメントから削除された後に呼び出されます。|  
|[は](#onclosedocument)|文書を閉じると呼ばれます。|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|リッチ プレビュー用プレビューのフレームを作成する必要があるときに、フレームワークによって呼び出されます。|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|ドキュメントのイベントに応答にフレームワークによって呼び出されます。|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|サムネイルのコンテンツを描画する派生クラスでは、このメソッドをオーバーライドします。|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|ドキュメント データをストリームから読み込む必要があるときに、フレームワークによって呼び出されます。|  
|[CDocument::OnNewDocument](#onnewdocument)|新しいドキュメントを作成するには、呼び出されます。|  
|[CDocument::OnOpenDocument](#onopendocument)|開くには、既存のドキュメントと呼ばれます。|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|プレビュー ハンドラー、フォーカス関数の呼び出しから HWND を返すように指示します。|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|プレビュー ハンドラー、プレビュー ハンドラーが実行されているプロセスのメッセージ ポンプから渡されたキー入力を処理するように指示します。|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|リッチ プレビューの背景色が変更されたときに呼び出されます。|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|リッチ プレビュー フォントが変更されたときに呼び出されます。|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|リッチ プレビューのサイトが変更されたときに呼び出されます。|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|リッチ プレビュー テキストの色が変更されたときに呼び出されます。|  
|[単一](#onsavedocument)|ドキュメントをディスクに保存するには、呼び出されます。|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|プレビュー ハンドラーがアンロードされるときに、フレームワークによって呼び出されます。|  
|[CDocument::PreCloseFrame](#precloseframe)|フレーム ウィンドウを閉じる前に呼び出されます。|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|次のチャンク値を読み取ります。|  
|[CDocument::ReleaseFile](#releasefile)|他のアプリケーションで使用できるようにファイルを解放します。|  
|[CDocument::RemoveChunk](#removechunk)|指定した GUID のチャンクを削除します。|  
|[CDocument::RemoveView](#removeview)|ドキュメントからビューをデタッチします。|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|オーバーライド可能な; 高度な開いているときに呼び出されますまたは保存操作は、例外のため完了できません。|  
|[に対して、順番](#savemodified)|オーバーライド可能な; 高度なドキュメントを保存するかどうかをユーザーに確認するには、呼び出されます。|  
|[CDocument::SetChunkValue](#setchunkvalue)|チャンク値を設定します。|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|最後に保存してから、ドキュメントを変更したことを示すフラグを設定します。|  
|[CDocument::SetPathName](#setpathname)|ドキュメントで使用されるデータ ファイルのパスを設定します。|  
|[CDocument::SetTitle](#settitle)|ドキュメントのタイトルを設定します。|  
|[CDocument::UpdateAllViews](#updateallviews)|ドキュメントのすべてのビューが変更されたに通知します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocument::OnFileSendMail](#onfilesendmail)|ドキュメントを添付して、メッセージを送信します。|  
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|メールのサポートが存在する場合は、メール送信コマンドを有効にします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|指定`CDocument`サムネイルの dllhost によってオブジェクトが作成されます。 チェックインする必要があります`CView::OnDraw`です。|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|指定する`CDocument`の prevhost によってオブジェクトが作成された`Rich Preview`です。 チェックインする必要があります`CView::OnDraw`です。|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|指定する`CDocument`インデクサーまたはその他の検索アプリケーションによってオブジェクトが作成されます。|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|リッチ プレビュー ウィンドウの背景色を指定します。 この色は、ホストによって設定されます。|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|リッチ プレビュー ウィンドウの前景色を指定します。 この色は、ホストによって設定されます。|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|リッチ プレビュー ウィンドウのテキストのフォントを指定します。 このフォントの詳細については、ホストによって設定されます。|  
  
## <a name="remarks"></a>Remarks  
 ドキュメントでは、ユーザーは、通常ファイルを開くコマンドを使用して開きし、ファイルの保存のコマンドを使用して保存するデータの単位を表します。  
  
 `CDocument` ドキュメントの作成、保存して、読み込みなどの標準的な操作をサポートしています。 フレームワークによって定義されたインターフェイスを使用して、ドキュメントを操作する`CDocument`です。  
  
 アプリケーションのドキュメントの 1 つ以上の型をサポートできます。たとえば、アプリケーションでは、スプレッドシートやテキスト ドキュメントの両方をサポート可能性があります。 ドキュメントの種類ごとに、関連するドキュメント テンプレートドキュメント テンプレートでは、そのドキュメントの種類に使用がどのようなリソース (たとえば、メニューのアイコン、またはアクセラレータ テーブル) を指定します。 各ドキュメントには、それに関連するへのポインターが含まれています。`CDocTemplate`オブジェクト。  
  
 ユーザーを使用してドキュメントの対話、 [CView](../../mfc/reference/cview-class.md)それに関連付けられているオブジェクト。 ビューはドキュメント フレーム ウィンドウのイメージをレンダリングしでユーザー入力は、ドキュメントに対する操作として解釈します。 ドキュメントには、関連付けられている複数のビューを持つことができます。 ユーザーがウィンドウにドキュメントを開いたときに、フレームワークはビューを作成し、ドキュメントにアタッチします。 ドキュメント テンプレートでは、ドキュメントの種類を表示する使用ビューとフレームのウィンドウの種類を指定します。  
  
 フレームワークの標準の一部であるドキュメント コマンド ルーティングし、その結果 (ファイルの保存のメニュー項目) などの標準のユーザー インターフェイス コンポーネントからコマンドを受信します。 ドキュメントは、アクティブなビューが転送されたコマンドを受信します。 ドキュメントでは、特定のコマンドを処理しない場合は、それを管理するドキュメント テンプレートにコマンドを転送します。  
  
 ドキュメントのデータが変更されると、そのビューの各変更を反映させる必要があります。 `CDocument` 提供、 [UpdateAllViews](#updateallviews)ビューがそれ自体を必要に応じて、repaint ように、ビューにこのような変更を通知するためのメンバー関数。 フレームワークもを閉じる前に変更されたファイルを保存するユーザーに求めます。  
  
 一般的なアプリケーションでドキュメントを実装するには、次の操作を行う必要があります。  
  
-   クラスを派生`CDocument`ドキュメントの種類ごとにします。  
  
-   各ドキュメントのデータを格納するためのメンバー変数を追加します。  
  
-   読み取りと、ドキュメントのデータを変更するためのメンバー関数を実装します。 ドキュメントのビューとは、これらのメンバー関数の最も重要なユーザーです。  
  
-   上書き、 [cobject::serialize](../../mfc/reference/cobject-class.md#serialize)ディスクと、ドキュメントのデータの読み取りし、書き込みをするドキュメント クラスのメンバー関数。  
  
 `CDocument` メール サポート (MAPI) が存在する場合、メールを使用して、ドキュメントの送信をサポートします。 記事を参照して[MAPI](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)です。  
  
 詳細については`CDocument`を参照してください[シリアル化](../../mfc/serialization-in-mfc.md)、[ドキュメント/ビュー アーキテクチャに関するトピック](../../mfc/document-view-architecture.md)、および[ドキュメント/ビューの作成](../../mfc/document-view-creation.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="addview"></a>  CDocument::AddView  
 ビューをドキュメントにアタッチするには、この関数を呼び出します。  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>パラメーター  
 *pView*  
 追加されるビューへのポインター。  
  
### <a name="remarks"></a>Remarks  
 この関数は、ドキュメントに関連付けられているビューの一覧に、指定されたビューを追加します。関数は、このドキュメントにもビューのドキュメント ポインターを設定します。 新しく作成されたビュー オブジェクトをドキュメントにアタッチするときに、フレームワークはこの関数を呼び出しますこれは、応答ファイルを新しいファイルを開く、または新しいウィンドウのコマンドまたは分割ウィンドウを分割すると発生します。  
  
 手動で作成して、ビューをアタッチする場合にのみ、この関数を呼び出します。 Framework のドキュメントとビューを定義することで接続することは通常、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)ドキュメント クラス、ビューのクラスとフレーム ウィンドウ クラスに関連付けるオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="beginreadchunks"></a>  CDocument::BeginReadChunks  
 チャンクの読み取りを初期化します。  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="cancloseframe"></a>  CDocument::CanCloseFrame  
 ドキュメントを表示するフレーム ウィンドウを閉じる前に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFrame*  
 ドキュメントにアタッチされているビューのフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 フレーム ウィンドウを閉じるには安全である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 既定の実装では、他のフレーム ウィンドウのドキュメントを表示するかを確認します。 指定したフレーム ウィンドウがドキュメントを表示する最後の 1 つの場合は、関数が変更された場合は、ドキュメントを保存するように求めるプロンプトを表示します。 フレーム ウィンドウが閉じられたときに、特別な処理を実行する場合は、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。  
  
##  <a name="cdocument"></a>  CDocument::CDocument  
 構築、 **CDocument**オブジェクト。  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、ドキュメントの作成を処理します。 上書き、[でも実質的](#onnewdocument)ドキュメントごと単位での初期化を実行するメンバー関数これは、シングル ドキュメント インターフェイス (SDI) アプリケーションで特に重要です。  
  
##  <a name="clearchunklist"></a>  CDocument::ClearChunkList  
 チャンクの一覧をクリアします。  
  
```  
virtual void ClearChunkList ();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="clearpathname"></a>  CDocument::ClearPathName  
 ドキュメント オブジェクトのパスを消去します。  
  
```  
virtual void ClearPathName();
```  
  
### <a name="remarks"></a>Remarks  
 パスをオフにすると、`CDocument`オブジェクトにより、アプリケーションは、次には、ドキュメントの保存時にユーザーに確認します。 これにより、**保存**コマンドの動作と同様に、**名前を付けて保存**コマンド。  
  
##  <a name="deletecontents"></a>  のに  
 破棄せずに、ドキュメントのデータを削除するためにフレームワークによって呼び出される、 **CDocument**オブジェクト自体です。  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>Remarks  
 ドキュメントが破棄される直前に呼び出されます。 再利用される前に、ドキュメントが空であることを確認するが呼び出されます。 これはドキュメントを 1 つのみを使用して、SDI アプリケーションにとって特に重要です。ユーザーを作成または別のドキュメントを開くたびに、ドキュメントが再利用されます。 編集すべてクリア やドキュメントのデータをすべて削除する同様のコマンドを実装するには、この関数を呼び出します。 この関数の既定の実装は、何も行いません。 ドキュメント内のデータを削除するには、この関数をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="findchunk"></a>  CDocument::FindChunk  
 指定した GUID のチャンクを検索します。  
  
```  
virtual POSITION FindChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>パラメーター  
 *guid*  
 検索するチャンクの GUID を指定します。  
  
 *pid*  
 検索するには、チャンクの PID を指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、内部のチャンク リスト内の位置。 それ以外の場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getadapter"></a>  CDocument::GetAdapter  
 実装するオブジェクトへのポインターを返します、`IDocument`インターフェイスです。  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>戻り値  
 実装するオブジェクトへのポインター、`IDocument`インターフェイスです。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getdoctemplate"></a>  CDocument::GetDocTemplate  
 この関数では、このドキュメントの種類のドキュメント テンプレートへのポインターを取得します。  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このドキュメントの種類のドキュメント テンプレートへのポインターまたは**NULL**ドキュメント テンプレートでは、ドキュメントは管理されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="getfile"></a>  CDocument::GetFile  
 ポインターを取得するには、このメンバー関数を呼び出す、`CFile`オブジェクト。  
  
```  
virtual CFile* GetFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError);
```  
  
### <a name="parameters"></a>パラメーター  
 *場合*  
 目的のファイルのパスを表す文字列。 相対パスまたは絶対パスがあります。  
  
 *pError*  
 操作の完了状態を示す既存のファイルの例外オブジェクトへのポインター。  
  
 *nOpenFlags*  
 共有とアクセス モードです。 ファイルを開くときに実行するアクションを指定します。 CFile コンス トラクターで記載されているオプションを組み合わせることができます[ほか](../../mfc/reference/cfile-class.md#cfile)ビットごとの OR を使用して (&#124;) 演算子。 1 つのアクセス許可と 1 つの共有のオプションが必要です。**modeCreate**と**modeNoInherit**モードは省略可能です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CFile`オブジェクト。  
  
##  <a name="getfirstviewposition"></a>  CDocument::GetFirstViewPosition  
 ドキュメントに関連付けられているビューの一覧内の最初のビューの位置を取得するには、この関数を呼び出します。  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**を反復処理に使用できる値、 [GetNextView](#getnextview)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getnextview"></a>  CDocument::GetNextView  
 すべてのドキュメントのビューを反復処理するには、この関数を呼び出します。  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *rPosition*  
 参照、**位置**を以前の呼び出しによって返される値、`GetNextView`または[GetFirstViewPosition](#getfirstviewposition)メンバー関数。 この値にする必要がありますいない**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 によって識別されるビューへのポインター *rPosition*です。  
  
### <a name="remarks"></a>Remarks  
 によって識別されるビューを返します*rPosition*し、設定*rPosition*を**位置**一覧における次のビューの値。 取得したビューが、一覧内の最後の*rPosition*に設定されている**NULL**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getpathname"></a>  CDocument::GetPathName  
 この関数では、ドキュメントのディスク ファイルの完全修飾パスを取得します。  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの完全修飾パス。 ドキュメントが保存されていないに関連付けられているディスク ファイルがない場合、この文字列が空です。  
  
##  <a name="getthumbnail"></a>  CDocument::GetThumbnail  
 サムネイルを表示するサムネイルのプロバイダーで使用されるビットマップを作成します。  
  
```  
virtual BOOL GetThumbnail(
    UINT cx,  
    HBITMAP* phbmp,  
    DWORD* pdwAlpha);
```  
  
### <a name="parameters"></a>パラメーター  
 *cx*  
 ビットマップの高さと幅を指定します。  
  
 *phbmp*  
 関数が成功した場合、ビットマップへのハンドルが含まれています。  
  
 *pdwAlpha*  
 関数が成功した場合、アルファ チャネル値を指定する DWORD が含まれています。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`正常です。 それ以外の場合、サムネイルのビットマップが作成された場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gettitle"></a>  CDocument::GetTitle  
 通常、ドキュメントのファイル名から派生されるドキュメントのタイトルを取得するには、この関数を呼び出します。  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントのタイトルです。  
  
##  <a name="initializesearchcontent"></a>  CDocument::InitializeSearchContent  
 検索ハンドラーの検索コンテンツを初期化するために呼び出されます。  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>Remarks  
 検索コンテンツを初期化するために派生クラスでこのメソッドをオーバーライドします。 コンテンツで区切られた文字列である必要があります「;」です。 たとえば、"ポイントです。四角形です。ole 項目"です。  
  
##  <a name="ismodified"></a>  CDocument::IsModified  
 ドキュメントが最後に保存された後に変更されているかどうかを判断するには、この関数を呼び出します。  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>戻り値  
 最後の保存からドキュメントが変更された場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="issearchandorganizehandler"></a>  CDocument::IsSearchAndOrganizeHandler  
 指示するかどうかのこのインスタンス`CDocument`検索と整理ハンドラー用に作成されました。  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`場合のこのインスタンス`CDocument`検索と整理ハンドラー用に作成されました。  
  
### <a name="remarks"></a>Remarks  
 この関数が返す現在`TRUE`外のプロセス サーバーに実装されている豊富なプレビュー ハンドラーに対してのみです。 この関数に戻り、アプリケーション レベルで適切なフラグ (m_bPreviewHandlerMode、m_bSearchMode、m_bGetThumbnailMode) を設定することができます`TRUE`です。  
  
##  <a name="loaddocumentfromstream"></a>  CDocument::LoadDocumentFromStream  
 ストリームからドキュメント データを読み込むと呼ばれます。  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStream*  
 ストリームへのポインター。 このストリームは、シェルによって提供されます。  
  
 *dwGrfMode*  
 ストリームへのアクセス モード。  
  
### <a name="return-value"></a>戻り値  
 ロード操作が成功すると、それ以外の場合の HRESULT エラー コードの場合は S_OK です。  
  
### <a name="remarks"></a>Remarks  
 ストリームからデータを読み込む方法をカスタマイズする派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="m_bgetthumbnailmode"></a>  CDocument::m_bGetThumbnailMode  
 指定、`CDocument`サムネイルの dllhost によってオブジェクトが作成されます。 チェックインする必要があります`CView::OnDraw`です。  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>Remarks  
 `TRUE` サムネイルの dllhost でドキュメントが作成されたことを示します。  
  
##  <a name="m_bpreviewhandlermode"></a>  CDocument::m_bPreviewHandlerMode  
 指定する、`CDocument`リッチ プレビュー用 prevhost によってオブジェクトが作成されます。 チェックインする必要があります`CView::OnDraw`です。  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>Remarks  
 `TRUE` リッチ プレビュー用 prevhost によってドキュメントが作成されたことを示します。  
  
##  <a name="m_bsearchmode"></a>  CDocument::m_bSearchMode  
 指定する、`CDocument`インデクサーによって、または別の検索アプリケーションでオブジェクトが作成されました。  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>Remarks  
 `TRUE` インデクサーまたはによって別の検索アプリケーションにドキュメントが作成されたことを示します。  
  
##  <a name="m_clrrichpreviewbackcolor"></a>  CDocument::m_clrRichPreviewBackColor  
 リッチ プレビュー ウィンドウの背景色を指定します。 この色は、ホストによって設定されます。  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_clrrichpreviewtextcolor"></a>  CDocument::m_clrRichPreviewTextColor  
 リッチ プレビュー ウィンドウの前景色を指定します。 この色は、ホストによって設定されます。  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_lfrichpreviewfont"></a>  CDocument::m_lfRichPreviewFont  
 リッチ プレビュー ウィンドウのテキストのフォントを指定します。 このフォントの詳細については、ホストによって設定されます。  
  
```  
CFont m_lfRichPreviewFont;  
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onbeforerichpreviewfontchanged"></a>  CDocument::OnBeforeRichPreviewFontChanged  
 リッチ プレビューのフォントを変更する前に呼び出されます。  
  
```  
virtual void OnBeforeRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onchangedviewlist"></a>  CDocument::OnChangedViewList  
 ビューが追加またはドキュメントから削除した後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>Remarks  
 かどうか最後のビューを削除して、その場合は、ドキュメントを削除します。 この関数の既定の実装を確認します。 フレームワークを追加またはビューを削除する場合は、特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、ビューを関連付けることがない場合でも、開いたままにドキュメントを作成する場合は、この関数をオーバーライドします。  
  
##  <a name="onclosedocument"></a>  は  
 ドキュメントが閉じられたときに、通常、File Close コマンドの一部として、フレームワークによって呼び出されます。  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装のためのドキュメントを表示するフレームのすべてを破棄し、ビューを閉じ、ドキュメントの内容をクリーンアップおよびを呼び出して、 [DeleteContents](#deletecontents)メンバー関数を実行するドキュメントの削除データ。  
  
 フレームワークは、ドキュメントを閉じるときに特別な後処理を実行する場合は、この関数をオーバーライドします。 たとえば、ドキュメントでは、データベース内のレコードを表す、場合、データベースを終了するには、この関数をオーバーライドします。 この関数の基底クラスのバージョンは、オーバーライドから呼び出す必要があります。  
  
##  <a name="oncreatepreviewframe"></a>  CDocument::OnCreatePreviewFrame  
 リッチ プレビュー用プレビューのフレームを作成する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`正常です。 それ以外の場合、フレームが作成された場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondocumentevent"></a>  CDocument::OnDocumentEvent  
 ドキュメントのイベントに応答にフレームワークによって呼び出されます。  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*deEvent*  
 イベントの種類を説明する列挙型。  
  
### <a name="remarks"></a>Remarks  
 ドキュメント イベントを複数のクラスに影響を与える可能性があります。 以外のクラスに影響を与えるドキュメント イベントを処理するため、このメソッドは、 [CDocument クラス](../../mfc/reference/cdocument-class.md)です。 現時点では、ドキュメント イベントに応答する必要がありますを唯一のクラスは、 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)です。 `CDocument`クラスの他の上書き可能なメソッドの効果を対応する必要があります、`CDocument`です。  
  
 次の表に、可能な値*deEvent*しに対応するイベントです。  
  
|[値]|対応するイベント|  
|-----------|-------------------------|  
|`onAfterNewDocument`|新しいドキュメントが作成されました。|  
|`onAfterOpenDocument`|新しいドキュメントが開かれました。|  
|`onAfterSaveDocument`|ドキュメントが保存されました。|  
|`onAfterCloseDocument`|ドキュメントが閉じられました。|  
  
##  <a name="ondrawthumbnail"></a>  CDocument::OnDrawThumbnail  
 縮小表示を描画する派生クラスでは、このメソッドをオーバーライドします。  
  
```  
virtual void OnDrawThumbnail(
    CDC& dc,  
    LPRECT lprcBounds);
```  
  
### <a name="parameters"></a>パラメーター  
 *dc*  
 デバイス コンテキストへの参照。  
  
 *lprcBounds*  
 縮小表示を描画する領域の外接する四角形を指定します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onfilesendmail"></a>  CDocument::OnFileSendMail  
 常駐しているメール ホスト経由でメッセージ (あれば) して送信ドキュメントの添付ファイルとしてします。  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>Remarks  
 `OnFileSendMail` 呼び出し[呼び出す必要はありません](#onsavedocument)(保存) は、電子メールで送信し、一時ファイルに無題と変更されたドキュメントをシリアル化します。 ドキュメントが変更されていない場合、一時ファイルは必要ありません。オリジナルが送信されます。 `OnFileSendMail` MAPI32 を読み込みます。DLL が既に読み込まれていない場合。  
  
 特殊な実装`OnFileSendMail`の[COleDocument](../../mfc/reference/coledocument-class.md)複合ファイルを正しく処理されます。  
  
 **CDocument**メール サポート (MAPI) が存在する場合、メールを使用して、ドキュメントの送信をサポートします。 記事を参照して[MAPI トピック](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)です。  
  
##  <a name="onloaddocumentfromstream"></a>  CDocument::OnLoadDocumentFromStream  
 ドキュメント データをストリームから読み込む必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,  
    DWORD grfMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStream*  
 着信ストリームへのポインター。  
  
 *grfMode*  
 ストリームへのアクセス モード。  
  
### <a name="return-value"></a>戻り値  
 負荷が成功した場合は S_OK、それ以外の場合はエラー コード。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onnewdocument"></a>  CDocument::OnNewDocument  
 ファイルの新規作成 コマンドの一部としてフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnNewDocument();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ドキュメントが正常に初期化します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装、 [DeleteContents](#deletecontents)メンバー関数をドキュメントが空ことを確認し、新しいドキュメントにマークを付けます。 新しいドキュメントのデータ構造を初期化するためには、この関数をオーバーライドします。 この関数の基底クラスのバージョンは、オーバーライドから呼び出す必要があります。  
  
 SDI アプリケーションでファイルの新規作成 を選択すると、フレームワークは新規に作成するのではなく、既存のドキュメントを再初期化するのにこの関数を使用します。 ユーザーは、マルチ ドキュメント インターフェイス (MDI) アプリケーションに新しいファイルを選択、フレームワークはたびに、新しいドキュメントを作成しを初期化するには、この関数を呼び出します。 SDI アプリケーションで有効にするファイルの新しいコマンドのコンス トラクターではなく、この関数には、初期化コードを配置する必要があります。  
  
 注が存在している場合、where`OnNewDocument`が 2 回呼び出されます。 これは、ActiveX ドキュメント サーバーとして、ドキュメントが埋め込まれている場合に発生します。 関数が最初に呼び出された、`CreateInstance`メソッド (によって公開されている、 `COleObjectFactory`-派生クラス) と 2 番目の時間によって、`InitNew`メソッド (によって公開されている、 `COleServerDoc`-派生クラス)。  
  
### <a name="example"></a>例  
 次の例では、ドキュメント オブジェクトの初期化の方法を示します。  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="onopendocument"></a>  CDocument::OnOpenDocument  
 ファイルを開くコマンドの一部としてフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>パラメーター  
 *終了*  
 開かれるドキュメントのパスを指します。  
  
### <a name="return-value"></a>戻り値  
 ドキュメント読み込みが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装は、指定したファイルを開き、 [DeleteContents](#deletecontents)ドキュメントが空であることを確認するメンバー関数が呼び出す[cobject::serialize](../../mfc/reference/cobject-class.md#serialize)ファイルの読み取り内容、およびしてクリーンとしてマークします。 アーカイブ機構やファイル メカニズム以外のものを使用する場合は、この関数をオーバーライドします。 たとえば、ドキュメントが別々 のファイルではなく、データベース内のレコードを表すアプリケーションを作成する場合があります。  
  
 フレームワークでこの関数を使用して、既存の再初期化中の SDI アプリケーション ファイルを開く を選択すると場合、 **CDocument**新規に作成するのではなく、オブジェクトです。 場合は、ユーザーが、MDI アプリケーションでファイルを開く、フレームワークは、新しい**CDocument**オブジェクトごとに初期化するには、この関数を呼び出します。 SDI アプリケーションで有効にするファイルを開くコマンドのコンス トラクターではなく、この関数には、初期化コードを配置する必要があります。  
  
### <a name="example"></a>例  
 次の例では、ドキュメント オブジェクトの初期化の方法を示します。  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="onpreviewhandlerqueryfocus"></a>  CDocument::OnPreviewHandlerQueryFocus  
 プレビュー ハンドラーを呼び出し元から取得した、HWND を返すように指示、`GetFocus`関数。  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *phwnd*  
 [out]このメソッドが戻るときに、呼び出し元から返される HWND へのポインターを含む、`GetFocus`プレビュー ハンドラーのフォア グラウンド スレッドからの関数。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK を返します。または、それ以外の場合、エラー値。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onpreviewhandlertranslateaccelerator"></a>  CDocument::OnPreviewHandlerTranslateAccelerator  
 プレビュー ハンドラー、プレビュー ハンドラーが実行されているプロセスのメッセージ ポンプから渡されたキー入力を処理するように指示します。  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pmsg*  
 [in]ウィンドウ メッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 プレビュー ハンドラーによって、キー入力メッセージを処理できる場合、ハンドラーはプロセスがおよび、S_OK を返します。 ホストには、プレビュー ハンドラーでは、キー入力メッセージを処理できない場合`IPreviewHandlerFrame::TranslateAccelerator`です。 ホストは、メッセージを処理する場合、このメソッドは、S_OK を返します。 ホストにメッセージが処理されない場合、このメソッドは S_FALSE を返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onrichpreviewbackcolorchanged"></a>  CDocument::OnRichPreviewBackColorChanged  
 リッチ プレビューの背景色が変更されたときに呼び出されます。  
  
```  
virtual void OnRichPreviewBackColorChanged();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onrichpreviewfontchanged"></a>  CDocument::OnRichPreviewFontChanged  
 リッチ プレビューのフォントが変更されたときに呼び出されます。  
  
```  
virtual void OnRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onrichpreviewsitechanged"></a>  CDocument::OnRichPreviewSiteChanged  
 リッチ プレビューのサイトが変更されたときに呼び出されます。  
  
```  
virtual void OnRichPreviewSiteChanged();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onrichpreviewtextcolorchanged"></a>  CDocument::OnRichPreviewTextColorChanged  
 リッチ プレビュー テキストの色が変更されたときに呼び出されます。  
  
```  
virtual void OnRichPreviewTextColorChanged();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onsavedocument"></a>  単一  
 ファイルの保存やファイル名を付けてコマンドの一部としてフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>パラメーター  
 *終了*  
 ファイルの保存先の完全修飾パスを指します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ドキュメントが正常に保存されました。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装は、指定したファイルを開き[cobject::serialize](../../mfc/reference/cobject-class.md#serialize)ドキュメントのデータを書き込むファイル、および、マークとしてドキュメントをクリーニングします。 フレームワークは、ドキュメントを保存するときに、特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、ドキュメントが別々 のファイルではなく、データベース内のレコードを表すアプリケーションを作成する場合があります。  
  
##  <a name="onunloadhandler"></a>  CDocument::OnUnloadHandler  
 プレビュー ハンドラーがアンロードされるときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onupdatefilesendmail"></a>  CDocument::OnUpdateFileSendMail  
 により、**判定**コマンド メール サポート (MAPI) が存在するかどうか。  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 *対応付けられました。*  
 ポインター、 [CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトに関連付けられている、**判定**コマンド。  
  
### <a name="remarks"></a>Remarks  
 それ以外の場合、関数を削除、**判定**コマンドをメニューから、上記の区切り記号を含む、または必要に応じて項目のメニューの下。 場合、MAPI が有効になっている MAPI32 です。DLL がパスにし、[メール] のセクション、WIN です。INI ファイル、MAPI = 1 です。 ほとんどのアプリケーションでは、[ファイル] メニューにこのコマンドを配置します。  
  
 **CDocument**メール サポート (MAPI) が存在する場合、メールを使用して、ドキュメントの送信をサポートします。 記事を参照して[MAPI トピック](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)です。  
  
##  <a name="precloseframe"></a>  CDocument::PreCloseFrame  
 このメンバー関数は、フレーム ウィンドウが破棄される前に、フレームワークによって呼び出されます。  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFrame*  
 ポインター、 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 、関連付けられているを保持する`CDocument`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 カスタム クリーンアップが、同様の基本クラスを呼び出してくださいをオーバーライドできます。  
  
 既定値は`PreCloseFrame`何も`CDocument`します。 `CDocument`-派生クラス[COleDocument](../../mfc/reference/coledocument-class.md)と[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)このメンバー関数を使用します。  
  
##  <a name="readnextchunkvalue"></a>  CDocument::ReadNextChunkValue  
 次のチャンク値を読み取ります。  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *ppValue*  
 [out]関数から返されたときに*ppValue*読み取られた値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="releasefile"></a>  CDocument::ReleaseFile  
 このメンバー関数は、他のアプリケーションで使用するために使用できるように、ファイルを解放するためにフレームワークによって呼び出されます。  
  
```  
virtual void ReleaseFile(
    CFile* pFile,  
    BOOL bAbort);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFile*  
 解放される CFile オブジェクトへのポインター。  
  
 *bAbort*  
 ファイルがいずれかを使用して解放されるかどうかを示す`CFile::Close`または`CFile::Abort`です。 **FALSE**を使用して解放する場合は、ファイル[先](../../mfc/reference/cfile-class.md#close)です。**TRUE**を使用して解放する場合は、ファイル[解放](../../mfc/reference/cfile-class.md#abort)です。  
  
### <a name="remarks"></a>Remarks  
 場合*bAbort*は**TRUE**、`ReleaseFile`呼び出し`CFile::Abort`ファイルが離されるとします。 `CFile::Abort` 例外はスローされません。  
  
 場合*bAbort*は**FALSE**、`ReleaseFile`呼び出し`CFile::Close`され、ファイルを解放します。  
  
 ファイルがリリースされる前に、ユーザーが操作を要求するには、このメンバー関数をオーバーライドします。  
  
##  <a name="removechunk"></a>  CDocument::RemoveChunk  
 指定した GUID のチャンクを削除します。  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>パラメーター  
 *Guid*  
 削除するチャンクの GUID を指定します。  
  
 *pid*  
 削除するチャンクの PID を指定します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="removeview"></a>  CDocument::RemoveView  
 ドキュメントからビューをデタッチするには、この関数を呼び出します。  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>パラメーター  
 *pView*  
 削除されるビューへのポインター。  
  
### <a name="remarks"></a>Remarks  
 この関数では、ドキュメントに関連付けられているビューの一覧から、指定されたビューが削除されます。ビューのドキュメントのポインターにセット**NULL**です。 フレーム ウィンドウが閉じているか、分割ウィンドウのウィンドウが閉じられたときに、この関数は、フレームワークによって呼び出されます。  
  
 ビューをデタッチして手動で場合にのみ、この関数を呼び出します。 通常ドキュメントとビューを定義することによってデタッチ フレームワークを使用できますが、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)ドキュメント クラス、ビューのクラスとフレーム ウィンドウ クラスに関連付けるオブジェクト。  
  
 例を参照してください[AddView](#addview)のサンプルを実装します。  
  
##  <a name="reportsaveloadexception"></a>  CDocument::ReportSaveLoadException  
 例外がスローされた場合に呼び出されます (通常、 [CFileException](../../mfc/reference/cfileexception-class.md)または[CArchiveException](../../mfc/reference/carchiveexception-class.md)) を保存またはドキュメントの読み込み中にします。  
  
```  
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,  
    CException* e,  
    BOOL bSaving,  
    UINT nIDPDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 *終了*  
 しようとしたドキュメントの名前を指すの保存または読み込みします。  
  
 *e*  
 スローされた例外を指します。 あります**NULL**です。  
  
 *bSaving*  
 どのような操作が進行中です。 であったことを示すフラグします。ドキュメントが保存されている場合、0、ドキュメントが読み込まれたされている場合は 0 以外の値。  
  
 *nIDPDefault*  
 関数が特定の 1 つを指定しない場合に表示されるエラー メッセージの識別子。  
  
### <a name="remarks"></a>Remarks  
 既定の実装では、例外オブジェクトを検査し、具体的には、原因を説明するエラー メッセージを探します。 特定のメッセージが見つからない場合、または場合*e*は**NULL**で指定された一般的なメッセージ、 *nIDPDefault*パラメーターを使用します。 関数は、エラー メッセージを含むメッセージ ボックスを表示します。 追加のカスタマイズされたエラー メッセージを提供する場合は、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。  
  
##  <a name="savemodified"></a>  に対して、順番  
 変更されたドキュメントが閉じられる前に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>戻り値  
 続行して、ドキュメントを閉じても安全である場合は 0 以外。ドキュメントを閉じてはいけない場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の実装には、ユーザーに確認するには、ドキュメントに変更を保存するかどうか行われている場合、メッセージ ボックスが表示されます。 プログラムには、別のプロンプトを表示する手順が必要な場合は、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。  
  
##  <a name="setchunkvalue"></a>  CDocument::SetChunkValue  
 チャンク値を設定します。  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *pValue*  
 設定するチャンク値を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setmodifiedflag"></a>  CDocument::SetModifiedFlag  
 ドキュメントの変更を行った後は、この関数を呼び出します。  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bModified*  
 ドキュメントが変更されているかどうかを示すフラグします。  
  
### <a name="remarks"></a>Remarks  
 一貫してこの関数を呼び出して、フレームワークがドキュメントを閉じる前に変更を保存するユーザーを要求することを確認します。 通常の既定値を使用する必要があります**TRUE**の*bModified*パラメーター。 この関数の値を呼び出し、(変更なし) のクリーンにドキュメントをマーク、 **FALSE**です。  
  
##  <a name="setpathname"></a>  CDocument::SetPathName  
 この関数では、ドキュメントのディスク ファイルの完全修飾パスを指定します。  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *終了*  
 ドキュメントのパスとして使用する文字列へのポインター。  
  
 *bAddToMRU*  
 ファイル名を追加するかどうか、最近使用した (MRU) ファイルの一覧を決定します。 場合**true の場合、** ファイル名を追加する場合は**FALSE**、追加されていません。  
  
### <a name="remarks"></a>Remarks  
 値に応じて*bAddToMRU*パスを追加、または、アプリケーションによって管理される MRU 一覧に追加されません。 一部のドキュメントがディスク ファイルに関連付けられていないことに注意してください。 開くと、フレームワークによって使用されるファイルの保存の既定の実装をオーバーライドする場合にのみ、この関数を呼び出します。  
  
##  <a name="settitle"></a>  CDocument::SetTitle  
 この関数では、ドキュメントのタイトル (フレーム ウィンドウのタイトル バーに表示される文字列) を指定します。  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszTitle*  
 ドキュメントのタイトルとして使用する文字列へのポインター。  
  
### <a name="remarks"></a>Remarks  
 この関数を呼び出すと、ドキュメントを表示するすべてのフレーム ウィンドウのタイトルが更新されます。  
  
##  <a name="updateallviews"></a>  CDocument::UpdateAllViews  
 ドキュメントが変更された後は、この関数を呼び出します。  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSender*  
 ドキュメントを変更するビューへのポインターまたは**NULL**場合、すべてのビューを更新します。  
  
 *lHint*  
 変更に関する情報が含まれています。  
  
 *pHint*  
 変更に関する情報を格納するオブジェクトへのポインター。  
  
### <a name="remarks"></a>Remarks  
 呼び出した後は、この関数を呼び出す必要があります、 [SetModifiedFlag](#setmodifiedflag)メンバー関数。 この関数で指定されるビューを除く、ドキュメントにアタッチされている各ビューは通知*pSender*ドキュメントが変更されています。 通常この関数を呼び出すビュー クラスからビューを使用してドキュメントをユーザーが変更された後です。  
  
 この関数を呼び出して、 [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)送信以外のドキュメントのビューの各メンバー関数を表示、渡す*pHint*と*lHint*です。 ドキュメントに加えられた変更に関するビューに情報を渡すには、これらのパラメーターを使用します。 使用して情報をエンコードする*lHint*を定義することや、 [CObject](../../mfc/reference/cobject-class.md)-派生したクラスを変更についての情報を格納および使用して、そのクラスのオブジェクトを渡す*pHint*. 上書き、`CView::OnUpdate`でメンバー関数、 [CView](../../mfc/reference/cview-class.md)-渡された情報に基づいて、ビューの表示の更新を最適化するためにクラスを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルは](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [MFC サンプル NPP](../../visual-cpp-samples.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)
