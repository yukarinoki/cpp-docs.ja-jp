---
title: COleServerDoc クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
dev_langs:
- C++
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a636b07b73da6ded6fb1646b7efa30b4685e55ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377669"
---
# <a name="coleserverdoc-class"></a>COleServerDoc クラス
OLE サーバー ドキュメントの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](#coleserverdoc)|`COleServerDoc` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](#activatedocobject)|関連付けられている DocObject ドキュメントをアクティブにします。|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|インプレース編集用にドキュメントをアクティブにします。|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|サーバーのユーザー インターフェイスを無効になります。|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|元に戻す状態情報を破棄します。|  
|[COleServerDoc::GetClientSite](#getclientsite)|基になるポインターを取得します`IOleClientSite`インターフェイスです。|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|ドキュメント全体を表す項目へのポインターを返します。|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|埋め込み先編集のための現在のクリッピング四角形を返します。|  
|[COleServerDoc::GetItemPosition](#getitemposition)|現在の位置の四角形、一括編集するためのコンテナー アプリケーションのクライアント領域と相対的を返します。|  
|[先](#getzoomfactor)|ズームの倍率をピクセル単位で返します。|  
|[COleServerDoc::IsDocObject](#isdocobject)|ドキュメントが DocObject であるかどうかを判断します。|  
|[COleServerDoc::IsEmbedded](#isembedded)|このドキュメントはコンテナーのドキュメントに埋め込まれているか、実行されているスタンドアロンかどうかを示します。|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|返します`TRUE`場合は、項目が現在の場所でアクティブ化します。|  
|[COleServerDoc::NotifyChanged](#notifychanged)|ユーザーがドキュメントを変更したコンテナーに通知します。|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|ユーザーがドキュメントを閉じたことをコンテナーに通知します。|  
|[COleServerDoc::NotifyRename](#notifyrename)|ユーザーがドキュメントの名前を変更が、コンテナーに通知します。|  
|[COleServerDoc::NotifySaved](#notifysaved)|ユーザーがドキュメントを保存したことをコンテナーに通知します。|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|ユーザーには、インプレース アクティブになったアイテムが非アクティブ化するときに、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|コントロールと、インプレース アクティブ化用に作成されたその他のユーザー インターフェイス要素を破棄するためにフレームワークによって呼び出されます。|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|コンテナーのドキュメント フレーム ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|コンテナー アプリケーションのフレーム ウィンドウまたはドキュメント ウィンドウのサイズ変更時に、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|または、インプレース編集用のコントロール バーを非表示にフレームワークによって呼び出されます。|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|埋め込みアイテムであるサーバー ドキュメントを保存すると、アイテムのコンテナーのコピーを更新するときに、フレームワークによって呼び出されます。|  
|[から](#requestpositionchange)|埋め込み先編集フレームの位置を変更します。|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|ドキュメントを保存するコンテナー アプリケーションに通知します。|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|コンテナーのドキュメントをスクロールします。|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|ユーザーがドキュメントを変更したコンテナーに通知します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|インプレース編集用のフレーム ウィンドウを作成するためにフレームワークによって呼び出されます。|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|埋め込み先編集のためのフレーム ウィンドウを破棄するためにフレームワークによって呼び出されます。|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|新規作成するには、この関数をオーバーライド`CDocObjectServer`オブジェクトし、このドキュメントが DocObject コンテナーであることを示します。|  
|[COleServerDoc::OnClose](#onclose)|コンテナーの要求の文書を閉じるときに、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|指定されたコマンドを実行またはコマンドのヘルプを表示します。|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|コンテナーのフレーム ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|取得すると呼ばれる、`COleServerItem`ドキュメント全体を表す; 埋め込みアイテムを取得するために使用します。 必要な実装です。|  
|[されて](#onreactivateandundo)|一括編集するときに行われた変更を元に戻すために、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|コンテナーの埋め込みオブジェクトのウィンドウのタイトルを設定するときに、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|コンテナー アプリケーションのウィンドウ内で埋め込み先編集フレーム ウィンドウを配置するためにフレームワークによって呼び出されます。|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|または、ドキュメントを非表示にフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 サーバー ドキュメントを含めることができます[COleServerItem](../../mfc/reference/coleserveritem-class.md) 、埋め込みまたはリンクされた項目へのサーバー インターフェイスを表すオブジェクト。 埋め込まれたアイテムを編集するためのコンテナーが、サーバー アプリケーションを起動すると、項目が独自サーバー ドキュメントとして読み込まれます。`COleServerDoc`オブジェクトでは、1 つだけ含まれています`COleServerItem`文書全体で構成されるオブジェクト。 リンクされた項目を編集するためのコンテナーが、サーバー アプリケーションを起動すると、既存のドキュメントがディスクから読み込まれますリンクされた項目を示すために、ドキュメントの内容の一部が強調表示されます。  
  
 `COleServerDoc` オブジェクトの項目を含めることも、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)クラスです。 これにより、コンテナーとサーバー アプリケーションを作成することができます。 フレームワークが正しく格納する機能を提供、`COleClientItem`項目の処理中に、`COleServerItem`オブジェクト。  
  
 サーバー アプリケーションがリンクをサポートしていない場合、サーバーのドキュメントはドキュメントとして全体の埋め込みオブジェクトを表す 1 つだけのサーバー項目を常が含まれます。 場合は、サーバー アプリケーションでは、リンクをサポート、選択範囲をクリップボードにコピーするたびにサーバー項目を作成する必要があります。  
  
 使用する`COleServerDoc`、クラスの派生、および実装、 [OnGetEmbeddedItem](#ongetembeddeditem)メンバー関数は、埋め込まれたアイテムをサポートするようにサーバーを使用します。 クラスを派生`COleServerItem`、ドキュメントに項目を実装し、そのクラスからのオブジェクトを返す`OnGetEmbeddedItem`です。  
  
 リンクされた項目をサポートするために`COleServerDoc`提供、 [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem)メンバー関数。 既定の実装を使用したり、ドキュメント アイテムを管理するための独自の方法がある場合は、メソッドをオーバーライドすることができます。  
  
 1 つ必要`COleServerDoc`-サーバーの各種類のドキュメント、アプリケーションがサポートするクラスを派生します。 などの場合は、サーバー アプリケーションは、ワークシートとグラフをサポートする必要があります 2 `COleServerDoc`-クラスを派生します。  
  
 サーバーの詳細については、記事を参照してください。[サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [直接](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="activatedocobject"></a>  COleServerDoc::ActivateDocObject  
 関連付けられている DocObject ドキュメントをアクティブにします。  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>コメント  
 既定では、 `COleServerDoc` (DocObjects とも呼ばれる) アクティブなドキュメントをサポートしていません。 このサポートを有効にするを参照してください。 [GetDocObjectServer](#getdocobjectserver)とクラス[関数](../../mfc/reference/cdocobjectserver-class.md)です。  
  
##  <a name="activateinplace"></a>  COleServerDoc::ActivateInPlace  
 埋め込み先編集のため、項目をアクティブにします。  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合 0 を返します、項目が完全にオープンであること。  
  
### <a name="remarks"></a>コメント  
 この関数では、インプレース アクティブ化に必要なすべての操作を実行します。 埋め込み先フレーム ウィンドウを作成、アクティブ化してと項目にサイズを設定共有メニューとその他のコントロール、項目をビューにスクロールし、埋め込み先フレーム ウィンドウにフォーカスを設定します。  
  
 この関数は、既定の実装によって呼び出す[COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)です。 アプリケーションが、インプレース アクティブ化 (再生など) の他の動詞をサポートしている場合は、この関数を呼び出します。  
  
##  <a name="coleserverdoc"></a>  COleServerDoc::COleServerDoc  
 構築、 `COleServerDoc` OLE システム Dll に接続しなくてもオブジェクトです。  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) OLE に通信を開始します。 使用している場合[COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) 、アプリケーションで`COleLinkingDoc::Register`によって呼び出されます`COleLinkingDoc`の実装の`OnNewDocument`、 `OnOpenDocument`、および`OnSaveDocument`です。  
  
##  <a name="createinplaceframe"></a>  COleServerDoc::CreateInPlaceFrame  
 フレームワークは、インプレース編集用のフレーム ウィンドウを作成するには、この関数を呼び出します。  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 コンテナー アプリケーションの親ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 埋め込み先フレーム ウィンドウへのポインターまたは**NULL**失敗した場合。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、ドキュメント テンプレートで指定した情報を使用して、フレームを作成します。 使用されているビューは、ドキュメント用に作成された最初のビューです。 このビューは一時的に元のフレームからデタッチされ、新しく作成されたフレームにアタッチされます。  
  
 これは、高度なオーバーライド可能です。  
  
##  <a name="deactivateandundo"></a>  COleServerDoc::DeactivateAndUndo  
 アプリケーションがサポートする元に戻すし、ユーザーが項目をアクティブにした後、編集する前に元に戻す場合は、この関数を呼び出します。  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションが書き込まれる場合、Microsoft Foundation Class ライブラリを使用して、この関数を呼び出すと[COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo)呼び出される非アクティブ化するサーバーのユーザー インターフェイス。  
  
##  <a name="destroyinplaceframe"></a>  COleServerDoc::DestroyInPlaceFrame  
 フレームワークは、埋め込み先フレーム ウィンドウを破棄し、インプレース アクティブ化する前に状態サーバー アプリケーションのドキュメント ウィンドウに戻すには、この関数を呼び出します。  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrameWnd`  
 破棄する埋め込み先フレーム ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 これは、高度なオーバーライド可能です。  
  
##  <a name="discardundostate"></a>  COleServerDoc::DiscardUndoState  
 ユーザーは、編集を元に戻す操作を実行する場合は、その元に戻す状態情報を破棄するコンテナー アプリケーションを強制するには、この関数を呼び出します。  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 この関数は、取り消しをサポートしているサーバーは、それ以外の場合は使用できませんを元に戻す状態情報で利用できるリソースの解放できるように提供されます。  
  
##  <a name="getclientsite"></a>  COleServerDoc::GetClientSite  
 基になるポインターを取得します`IOleClientSite`インターフェイスです。  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>戻り値  
 基になるポインターを取得します[していること](http://msdn.microsoft.com/library/windows/desktop/ms693706)インターフェイスです。  
  
##  <a name="getdocobjectserver"></a>  COleServerDoc::GetDocObjectServer  
 新規作成するには、この関数をオーバーライド`CDocObjectServer`項目し、へのポインターを返します。  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDocSite`  
 ポインター、`IOleDocumentSite`インターフェイスは、このドキュメントをサーバーに接続します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CDocObjectServer`です。**NULL**場合は、操作に失敗しました。  
  
### <a name="remarks"></a>コメント  
 DocObject サーバーが有効な場合、以外の戻り値**NULL**ポインターは、クライアントが DocObjects をサポートできることを示しています。 既定の実装を返します**NULL**です。  
  
 DocObjects をサポートするドキュメントの一般的な実装は、新しい単に割り当てる`CDocObjectServer`オブジェクトし、呼び出し元に戻ります。 例えば:  
  
 [!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="getembeddeditem"></a>  COleServerDoc::GetEmbeddedItem  
 ドキュメント全体を表す項目へのポインターを取得するには、この関数を呼び出します。  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメント全体を表す項目へのポインター**NULL**場合は、操作に失敗しました。  
  
### <a name="remarks"></a>コメント  
 呼び出す[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)実装のない既定の仮想関数。  
  
##  <a name="getitemcliprect"></a>  COleServerDoc::GetItemClipRect  
 呼び出す、`GetItemClipRect`インプレース編集されているアイテムのクリッピング四角形の座標を取得します。  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpClipRect`  
 ポインター、`RECT`構造体、または`CRect`をアイテムのクリッピング四角形の座標を取得するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 座標はコンテナー アプリケーション ウィンドウのクライアント領域と相対的ピクセルで表します。  
  
 クリッピング四角形の外部描画は発生しません。 通常、描画は、自動的に制限されています。 この関数を使用して、ドキュメントの表示部分の外部ユーザーがスクロールするかどうかを決定するには場合は、スクロール、コンテナーのドキュメントへの呼び出しを使用して、必要に応じて[ScrollContainerBy](#scrollcontainerby)です。  
  
##  <a name="getitemposition"></a>  COleServerDoc::GetItemPosition  
 呼び出す、`GetItemPosition`の場で編集されている項目の座標を取得します。  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPosRect`  
 ポインター、`RECT`構造体、または`CRect`項目の座標を受け取るオブジェクト。  
  
### <a name="remarks"></a>コメント  
 座標はコンテナー アプリケーション ウィンドウのクライアント領域と相対的ピクセルで表します。  
  
 アイテムの位置は、項目を (または非表示) の範囲を確認の現在のクリッピング四角形と比較する画面にします。  
  
##  <a name="getzoomfactor"></a>  先  
 `GetZoomFactor`メンバー関数は、インプレース編集をアクティブ化された項目の「倍率」を決定します。  
  
```  
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,  
    LPSIZE lpSizeDenom = NULL,  
    LPCRECT lpPosRect = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpSizeNum*  
 クラスのオブジェクトへのポインター`CSize`倍率の分子を保持します。 指定できます**NULL**です。  
  
 *lpSizeDenom*  
 クラスのオブジェクトへのポインター`CSize`倍率の分母を保持します。 指定できます**NULL**です。  
  
 `lpPosRect`  
 クラスのオブジェクトへのポインター`CRect`アイテムの新しい位置を記述します。 この引数は場合**NULL**関数は、項目の現在の位置を使用します。  
  
### <a name="return-value"></a>戻り値  
 インプレースでのアイテムがアクティブになった場合は 0 以外を編集し、その倍率は以外です。 100% (1:1) です。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ズームの倍率をピクセル単位では、現在の大きさをアイテムのサイズの比率です。 コンテナー アプリケーションが、項目の範囲内で自然なエクステントを設定していない場合 (によって決定される[COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) を使用します。  
  
 関数は、分子と分母、項目の「ズームの倍率」に、最初の 2 つの引数を設定します。 アイテムがインプレース編集されていない場合、関数は、既定値は 100% (または 1:1) にこれらの引数を設定し、0 を返します。 詳細については、テクニカル ノート 40: を参照してください。 [MFC/OLE 埋め込み先サイズ変更とズーム](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)です。  
  
##  <a name="isdocobject"></a>  COleServerDoc::IsDocObject  
 ドキュメントが DocObject であるかどうかを判断します。  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、ドキュメントが DocObject; それ以外の場合**FALSE**です。  
  
##  <a name="isembedded"></a>  COleServerDoc::IsEmbedded  
 呼び出す、`IsEmbedded`ドキュメントがコンテナーに埋め込まれているオブジェクトを表すかどうかを調べます。  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`COleServerDoc`オブジェクトがオブジェクトを表すドキュメント コンテナーに埋め込まれている。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 リンクとしてコンテナー アプリケーションで操作することがありますが、ファイルから読み込まれたドキュメントが埋め込まれていません。 コンテナーのドキュメントに埋め込まれているドキュメントが埋め込まれると見なされます。  
  
##  <a name="isinplaceactive"></a>  COleServerDoc::IsInPlaceActive  
 呼び出す、`IsInPlaceActive`アイテムは現在、インプレース アクティブな状態かどうかを調べます。  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`COleServerDoc`オブジェクトは、インプレース アクティブである場合は 0 です。  
  
##  <a name="notifychanged"></a>  COleServerDoc::NotifyChanged  
 ドキュメントが変更されたドキュメントに接続されているすべてのリンクされた項目に通知するには、この関数を呼び出します。  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>コメント  
 通常、ユーザーがサーバー ドキュメントのサイズなどのグローバルな属性を変更した後、この関数を呼び出します。 OLE 項目が自動のリンクを使用してドキュメントにリンクされている場合、項目は、変更を反映するように更新されます。 Microsoft Foundation Class ライブラリで書かれたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`と呼びます。  
  
> [!NOTE]
>  この関数は、OLE 1 との互換性のために含まれます。 新しいアプリケーションを使用する必要があります[UpdateAllItems](#updateallitems)です。  
  
##  <a name="notifyclosed"></a>  COleServerDoc::NotifyClosed  
 この関数では、ドキュメントが閉じられたことをコンテナーに通知します。  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>コメント  
 [ファイル] メニューから [閉じる] コマンドを選択すると`NotifyClosed`によって呼び出される`COleServerDoc`の実装、[通常](../../mfc/reference/cdocument-class.md#onclosedocument)メンバー関数。 Microsoft Foundation Class ライブラリで書かれたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`と呼びます。  
  
##  <a name="notifyrename"></a>  COleServerDoc::NotifyRename  
 ユーザーには、サーバーのドキュメントが名前を変更した後は、この関数を呼び出します。  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszNewName`  
 サーバー ドキュメントの新しい名前を指定する文字列へのポインターこれは、通常、完全修飾パスです。  
  
### <a name="remarks"></a>コメント  
 [ファイル] メニューから、名前を付けて保存コマンドを選択すると`NotifyRename`によって呼び出される`COleServerDoc`の実装、[呼び出す必要はありません](../../mfc/reference/cdocument-class.md#onsavedocument)メンバー関数。 この関数は、OLE システム Dll で、さらに、コンテナーに通知を通知します。 Microsoft Foundation Class ライブラリで書かれたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`と呼びます。  
  
##  <a name="notifysaved"></a>  COleServerDoc::NotifySaved  
 ユーザーがサーバー ドキュメントを保存した後は、この関数を呼び出します。  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>コメント  
 [ファイル] メニューから [保存] コマンドを選択すると`NotifySaved`によって呼び出されます`COleServerDoc`の実装の[呼び出す必要はありません](../../mfc/reference/cdocument-class.md#onsavedocument)です。 この関数は、OLE システム Dll で、さらに、コンテナーに通知を通知します。 Microsoft Foundation Class ライブラリで書かれたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`と呼びます。  
  
##  <a name="onclose"></a>  COleServerDoc::OnClose  
 コンテナーは、サーバーのドキュメントを閉じることを要求するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCloseOption`  
 列挙から値`OLECLOSE`です。 このパラメーターには、次のいずれかの値を指定できます。  
  
- `OLECLOSE_SAVEIFDIRTY` 変更された場合は、ファイルが保存されます。  
  
- `OLECLOSE_NOSAVE` ファイルは保存されずに閉じられます。  
  
- `OLECLOSE_PROMPTSAVE` ファイルが変更された場合は、保存に求められます。  
  
### <a name="remarks"></a>コメント  
 既定の実装`CDocument::OnCloseDocument`です。  
  
 詳細とその他の値は、次を参照してください。[子](http://msdn.microsoft.com/library/windows/desktop/ms680623)Windows SDK に含まれています。  
  
##  <a name="ondeactivate"></a>  COleServerDoc::OnDeactivate  
 ユーザーには、現在インプレースで有効になっている埋め込みまたはリンクされた項目が非アクティブ化時に、フレームワークによって呼び出されます。  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、コンテナー アプリケーションのユーザー インターフェイスを元の状態に復元し、メニューや、インプレース アクティブ化用に作成されたその他のコントロールを破棄します。  
  
 元に戻す状態情報は無条件にこの時点でします。  
  
 詳細については、記事を参照してください[アクティベーション](../../mfc/activation-cpp.md)..  
  
##  <a name="ondeactivateui"></a>  COleServerDoc::OnDeactivateUI  
 ユーザーには、インプレース アクティブになったアイテムが非アクティブ化時に呼び出されます。  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>パラメーター  
 `bUndoable`  
 編集が完了できるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、コンテナー アプリケーションのユーザー インターフェイスをメニューや、インプレース アクティブ化用に作成されたその他のコントロールを非表示にする、元の状態に復元します。  
  
 常に、フレームワークを設定`bUndoable`に**FALSE**です。 サーバーが元に戻すをサポートし、元に戻すことができる操作を使用して基底クラス実装を呼び出す`bUndoable`'éý' **TRUE**です。  
  
##  <a name="ondocwindowactivate"></a>  COleServerDoc::OnDocWindowActivate  
 フレームワークは、一括編集するためのドキュメント ウィンドウをアクティブ化またはこの関数を呼び出します。  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActivate`  
 ドキュメント ウィンドウがアクティブ化または非アクティブ化するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 既定の実装で、削除するかに応じて、フレーム レベルのユーザー インターフェイス要素を追加します。 アイテムを持つドキュメントがアクティブ化または非アクティブ化されたときに、追加のアクションを実行する場合は、この関数をオーバーライドします。  
  
 詳細については、記事を参照してください[アクティベーション](../../mfc/activation-cpp.md)..  
  
##  <a name="onexecolecmd"></a>  COleServerDoc::OnExecOleCmd  
 フレームワークは、コマンドのヘルプを表示または指定されたコマンドを実行するには、この関数を呼び出します。  
  
```  
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,  
    DWORD nCmdID,  
    DWORD nCmdExecOpt,  
    VARIANTARG* pvarargIn,  
    VARIANTARG* pvarargOut);
```  
  
### <a name="parameters"></a>パラメーター  
 `pguidCmdGroup`  
 コマンドのセットを識別する GUID を指すポインター。 指定できます**NULL**を既定のコマンドのグループを示します。  
  
 `nCmdID`  
 実行するコマンド。 識別されるグループである必要があります`pguidCmdGroup`です。  
  
 *nCmdExecOut*  
 方法は、コマンド、1 つ以上の次の値をオブジェクトを実行する必要があります、**する**列挙します。  
  
 **OLECMDEXECOPT_DODEFAULT**  
  
 **OLECMDEXECOPT_PROMPTUSER**  
  
 **OLECMDEXECOPT_DONTPROMPTUSER**  
  
 **OLECMDEXECOPT_SHOWHELP**  
  
 `pvarargIn`  
 ポインター、 **VARIANTARG**コマンドの入力引数を格納します。 指定できます**NULL**です。  
  
 `pvarargOut`  
 ポインター、 **VARIANTARG**コマンドから出力される戻り値を受信します。 指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合は、次のエラー コードのいずれか。  
  
|[値]|説明|  
|-----------|-----------------|  
|**E_UNEXPECTED**|予期しないエラーが発生しました|  
|**E_FAIL**|エラーが発生しました|  
|**E_NOTIMPL**|MFC を示すを変換し、コマンドをディスパッチする自体を試みる必要があります|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup` 非**NULL**認識されているコマンド グループが指定されていません|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID` グループ内の有効なコマンドとして認識されません。 `pguidCmdGroup`|  
|**OLECMDERR_DISABLED**|によって識別されるコマンド`nCmdID`は無効になり、実行することはできません|  
|**OLECMDERR_NOHELP**|呼び出し元によって識別されるコマンドのヘルプの要望`nCmdID`ヘルプはありませんが、|  
|**OLECMDERR_CANCELED**|ユーザーは、実行をキャンセルしました。|  
  
### <a name="remarks"></a>コメント  
 `COleCmdUI` 有効にする、更新、および DocObject ユーザー インターフェイスのコマンドの他のプロパティを設定するために使用します。 コマンドが初期化された後に実行すると`OnExecOleCmd`です。  
  
 フレームワークは、変換および OLE ドキュメント コマンドをディスパッチする前に、関数を呼び出します。 標準の OLE ドキュメント コマンドを処理するには、この関数をオーバーライドする必要はありませんが、独自のコマンドを処理またはパラメーターを受け入れるか、結果を返すコマンドを処理する場合は、この関数をオーバーライドを指定する必要があります。  
  
 ほとんどのコマンドの引数を受け取るまたはいません値を返します。 コマンドの大半について、呼び出し元を渡すことができます**NULL**の`pvarargIn`と`pvarargOut`です。 入力値を期待するコマンドを呼び出し元は、宣言し、初期化を**VARIANTARG**変数内の変数へのポインターを渡すと`pvarargIn`です。 1 つの値を必要とするコマンド、引数格納できるで直接、 **VARIANTARG**関数に渡されるとします。 内で複数の引数をパッケージ化する必要があります、 **VARIANTARG**でサポートされる型のいずれかを使用して (など`IDispatch`と**SAFEARRAY** )。  
  
 同様に、コマンドで返される引数、呼び出し元が予想される場合を宣言する、 **VARIANTARG**で初期化`VT_EMPTY`でそのアドレスを渡すと`pvarargOut`です。 コマンドが単一の値を返す場合、オブジェクトで直接その値を格納できます`pvarargOut`です。 に対して適切な方法はいくつかに複数の出力値をパッケージ化する必要があります、 **VARIANTARG**です。  
  
 この関数の基本クラスの実装を取り上げます、**対応**コマンド ターゲットしようとして、コマンドに適切なハンドラーのディスパッチに関連付けられている構造体。 基本クラスの実装は、戻り値または引数を受け入れるしないコマンドでのみ動作します。 引数を受け入れるか、値を返すコマンドを処理する必要がある場合は、この関数をオーバーライドしを使用する必要があります、`pvarargIn`と`pvarargOut`パラメーター自分でします。  
  
##  <a name="onframewindowactivate"></a>  COleServerDoc::OnFrameWindowActivate  
 フレームワークは、コンテナー アプリケーションのフレーム ウィンドウがアクティブまたは非アクティブ化されたときに、この関数を呼び出します。  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActivate`  
 フレーム ウィンドウがアクティブ化または非アクティブ化するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、フレーム ウィンドウのヘルプ モードをキャンセルします。 フレーム ウィンドウがアクティブ化または非アクティブ化されたときに、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
 詳細については、記事を参照してください[アクティベーション](../../mfc/activation-cpp.md)..  
  
##  <a name="ongetembeddeditem"></a>  COleServerDoc::OnGetEmbeddedItem  
 コンテナー アプリケーションが作成または埋め込みアイテムを編集するサーバー アプリケーションを呼び出すときに、フレームワークによって呼び出されます。  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメント全体を表す項目へのポインター**NULL**場合は、操作に失敗しました。  
  
### <a name="remarks"></a>コメント  
 既定の実装はありません。 ドキュメント全体を表す項目を返すには、この関数をオーバーライドする必要があります。 この戻り値のオブジェクトをする必要があります、 `COleServerItem`-クラスを派生します。  
  
##  <a name="onreactivateandundo"></a>  されて  
 フレームワークは、インプレース アクティブ化、変更、および、後で非アクティブ化されている項目に加えられた変更を元に戻すを選択すると、この関数を呼び出します。  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装は何も返す以外**FALSE**失敗を示すにします。  
  
 アプリケーションは、元に戻すをサポートしている場合は、この関数をオーバーライドします。 呼び出して、項目をアクティブ化し、元に戻す操作を実行すると通常`ActivateInPlace`です。 コンテナー アプリケーションが書き込まれる場合、Microsoft Foundation Class ライブラリで、呼び出す`COleClientItem::ReactivateAndUndo`と、この関数を呼び出します。  
  
##  <a name="onresizeborder"></a>  COleServerDoc::OnResizeBorder  
 フレームワークは、コンテナー アプリケーションのフレーム ウィンドウのサイズを変更するときに、この関数を呼び出します。  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRectBorder`  
 ポインター、`RECT`構造体、または`CRect`罫線の座標を指定するオブジェクト。  
  
 `lpUIWindow`  
 クラスのオブジェクトへのポインター**埋め込み**現在インプレース編集セッションを所有しています。  
  
 *bFrame*  
 **TRUE**場合`lpUIWindow`コンテナー アプリケーションの最上位のフレーム ウィンドウ、指すまたは**FALSE**場合`lpUIWindow`コンテナー アプリケーションのドキュメント レベルのフレーム ウィンドウを指します。  
  
### <a name="remarks"></a>コメント  
 この関数は、サイズを変更し、ツールバーと新しいウィンドウのサイズに従ってその他のユーザー インターフェイス要素を調整します。  
  
 詳細については、次を参照してください。[埋め込み](http://msdn.microsoft.com/library/windows/desktop/ms680716)Windows SDK に含まれています。  
  
 これは、高度なオーバーライド可能です。  
  
##  <a name="onsethostnames"></a>  COleServerDoc::OnSetHostNames  
 コンテナーを設定またはこの文書のホスト名を変更するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszHost`  
 コンテナー アプリケーションの名前を指定する文字列へのポインター。  
  
 `lpszHostObj`  
 ドキュメントのコンテナーの名前を指定する文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、このドキュメントを参照するすべてのビューのドキュメントのタイトルを変更します。  
  
 アプリケーションが、別のメカニズムを通じて、タイトルを設定する場合は、この関数をオーバーライドします。  
  
##  <a name="onsetitemrects"></a>  COleServerDoc::OnSetItemRects  
 フレームワークは、コンテナー アプリケーションのフレーム ウィンドウ内で埋め込み先編集フレーム ウィンドウを配置するには、この関数を呼び出します。  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPosRect`  
 ポインター、`RECT`構造体、または`CRect`コンテナー アプリケーションのクライアント領域と相対的に埋め込み先フレーム ウィンドウの位置を指定するオブジェクト。  
  
 `lpClipRect`  
 ポインター、`RECT`構造体、または`CRect`コンテナー アプリケーションのクライアント領域と相対的に埋め込み先フレーム ウィンドウのクリッピング四角形を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 必要な場合は、ビューのズームの倍率を更新するには、この関数をオーバーライドします。  
  
 この関数は通常への応答と呼ばれる、`RequestPositionChange`呼び出すには、埋め込み先アイテムの位置の変更を要求するコンテナーによっていつでも呼び出すことができるがします。  
  
##  <a name="onshowcontrolbars"></a>  COleServerDoc::OnShowControlBars  
 フレームワークで識別されるフレーム ウィンドウに関連付けられているサーバー アプリケーションのコントロール バーを非表示には、この関数を呼び出します`pFrameWnd`です。  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrameWnd`  
 コントロール バーを持つを非表示または表示する必要があります、フレーム ウィンドウへのポインター。  
  
 `bShow`  
 コントロール バーを表示または非表示かどうかを判断します。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、そのフレーム ウィンドウが所有するすべてのコントロール バーを列挙または非表示にしを表示します。  
  
##  <a name="onshowdocument"></a>  COleServerDoc::OnShowDocument  
 フレームワークによって、`OnShowDocument`関数の場合、サーバー ドキュメントの非表示または表示する必要があります。  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `bShow`  
 ドキュメントへのユーザー インターフェイスを表示するか非表示にするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 場合`bShow`は**TRUE**既定の実装は、必要に応じて、サーバー アプリケーションをアクティブにし、コンテナー アプリケーションが、項目が表示されるように、そのウィンドウをスクロールします。 場合`bShow`は**FALSE**、既定の実装を呼び出すことによって、アイテムを非アクティブ化`OnDeactivate`、破棄または最初の 1 つを除く、ドキュメント用に作成されたすべてのフレーム ウィンドウを非表示にします。 表示されているドキュメントが残っていない場合、既定の実装には、サーバー アプリケーションが非表示にします。  
  
##  <a name="onupdatedocument"></a>  COleServerDoc::OnUpdateDocument  
 複合ドキュメントに埋め込まれたアイテムは、ドキュメントを保存するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ドキュメントが正常に更新されました。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装、 [COleServerDoc::NotifySaved](#notifysaved)と[COleServerDoc::SaveEmbedding](#saveembedding)メンバー関数をクリーンしてマークします。 特別な埋め込みアイテムを更新するときの処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="requestpositionchange"></a>  から  
 コンテナー アプリケーションのアイテムの位置を変更するには、このメンバー関数を呼び出します。  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPosRect`  
 ポインター、`RECT`構造体、または`CRect`アイテムの新しい位置を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 通常、この関数は呼び出されます (と共に`UpdateAllItems`)、インプレース アクティブな項目内のデータが変更されたとき。 この呼び出しでは、次のコンテナーが可能性がありますまたは呼び出すことによって、変更も実行しない`OnSetItemRects`です。 結果として得られる位置は、要求された異なる可能性があります。  
  
##  <a name="saveembedding"></a>  COleServerDoc::SaveEmbedding  
 コンテナー アプリケーションで埋め込みオブジェクトを保存するには、この関数を呼び出します。  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>コメント  
 この関数から自動的に呼び出されます`OnUpdateDocument`です。 この関数は、ディスク上で更新されるので、通常、特定のユーザーの操作の結果としてのみと呼ばれる項目を注意してください。  
  
##  <a name="scrollcontainerby"></a>  COleServerDoc::ScrollContainerBy  
 呼び出す、`ScrollContainerBy`によって (ピクセル単位) の量でコンテナーのドキュメントをスクロールするメンバー関数が示される`sizeScroll`です。  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>パラメーター  
 `sizeScroll`  
 コンテナー ドキュメントはスクロールをどの程度を示します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 正の値が右にスクロール ダウンを示します負の値を示すを左にスクロールします。  
  
##  <a name="updateallitems"></a>  COleServerDoc::UpdateAllItems  
 ドキュメントが変更されたドキュメントに接続されているすべてのリンクされた項目に通知するには、この関数を呼び出します。  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSender`  
 ドキュメントを変更する項目へのポインターまたは**NULL**場合、すべての項目を更新します。  
  
 `lHint`  
 変更に関する情報が含まれています。  
  
 `pHint`  
 変更に関する情報を格納するオブジェクトへのポインター。  
  
 `nDrawAspect`  
 項目を描画する方法を決定します。 これは、値から、`DVASPECT`列挙します。 このパラメーターには、次のいずれかの値を指定できます。  
  
- `DVASPECT_CONTENT` 項目は、コンテナー内の埋め込みオブジェクトとして表示されること、このような方法で表されます。  
  
- `DVASPECT_THUMBNAIL` 参照ツールで表示できるように、「サムネイル」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON` 項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT` 項目は、[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように表されます。  
  
### <a name="remarks"></a>コメント  
 通常、ユーザーがサーバー ドキュメントを変更した後は、この関数を呼び出します。 OLE 項目が自動のリンクを使用してドキュメントにリンクされている場合、項目は、変更を反映するように更新されます。 Microsoft Foundation Class ライブラリで書かれたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`と呼びます。  
  
 この関数を呼び出して、`OnUpdate`項目、渡す送信以外のドキュメントのアイテムの各メンバー関数`pHint`、 `lHint`、および`nDrawAspect`です。 項目をドキュメントに加えられた変更に関する情報を渡すには、これらのパラメーターを使用します。 使用して情報をエンコードする`lHint`を定義することができます、 `CObject`-派生したクラスを変更についての情報を格納および使用して、そのクラスのオブジェクトを渡す`pHint`です。 上書き、`OnUpdate`でメンバー関数、 `COleServerItem`-その表現が変更されたかどうかに応じて、各項目の更新を最適化するためにクラスを派生します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [直接クラス](../../mfc/reference/colelinkingdoc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [直接クラス](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)
