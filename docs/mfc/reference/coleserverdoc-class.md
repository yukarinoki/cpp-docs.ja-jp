---
title: COleServerDoc クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 3069c5f53b37984cbeae8bee1379bb8b0c36ccc3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285283"
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
|[COleServerDoc::ActivateInPlace](#activateinplace)|一括編集用にドキュメントをアクティブにします。|
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|サーバーのユーザー インターフェイスを無効になります。|
|[COleServerDoc::DiscardUndoState](#discardundostate)|元に戻す状態情報を破棄します。|
|[COleServerDoc::GetClientSite](#getclientsite)|基になるポインターを取得します`IOleClientSite`インターフェイス。|
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|ドキュメント全体を表す項目へのポインターを返します。|
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|一括編集するための現在のクリッピング四角形を返します。|
|[COleServerDoc::GetItemPosition](#getitemposition)|一括編集するためのコンテナー アプリケーションのクライアント領域を基準と、現在の位置四角を返します。|
|[先](#getzoomfactor)|ズームの倍率をピクセル単位で返します。|
|[COleServerDoc::IsDocObject](#isdocobject)|ドキュメントが DocObject であるかどうかを判断します。|
|[COleServerDoc::IsEmbedded](#isembedded)|ドキュメントがコンテナー ドキュメントに埋め込まれた、またはスタンドアロンの実行中かどうかを示します。|
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|項目が現在インプレース アクティブ化される場合は、TRUE を返します。|
|[COleServerDoc::NotifyChanged](#notifychanged)|ユーザーのドキュメントが変更されたことをコンテナーに通知します。|
|[COleServerDoc::NotifyClosed](#notifyclosed)|ユーザーがドキュメントを閉じたことをコンテナーに通知します。|
|[COleServerDoc::NotifyRename](#notifyrename)|ユーザーがドキュメントの名前を変更が、コンテナーに通知します。|
|[COleServerDoc::NotifySaved](#notifysaved)|ユーザーがドキュメントを保存したことをコンテナーに通知します。|
|[COleServerDoc::OnDeactivate](#ondeactivate)|ユーザーには、インプレース アクティブなアイテムが非アクティブ化時に、フレームワークによって呼び出されます。|
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|コントロールとインプレース アクティブ化用に作成されたその他のユーザー インターフェイス要素を破棄するためにフレームワークによって呼び出されます。|
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|コンテナーのドキュメント フレーム ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|
|[COleServerDoc::OnResizeBorder](#onresizeborder)|コンテナー アプリケーションのフレーム ウィンドウまたはドキュメント ウィンドウのサイズ変更時に、フレームワークによって呼び出されます。|
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|またはインプレース編集用のコントロール バーを非表示にフレームワークによって呼び出されます。|
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|埋め込み項目がサーバー ドキュメントを保存すると、アイテムのコンテナーのコピーを更新するときに、フレームワークによって呼び出されます。|
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|埋め込み先編集フレームの位置を変更します。|
|[COleServerDoc::SaveEmbedding](#saveembedding)|ドキュメントを保存するコンテナーのアプリケーションに指示します。|
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|コンテナーのドキュメントをスクロールします。|
|[COleServerDoc::UpdateAllItems](#updateallitems)|ユーザーのドキュメントが変更されたことをコンテナーに通知します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|一括編集するためのフレーム ウィンドウを作成するためにフレームワークによって呼び出されます。|
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|一括編集するためのフレーム ウィンドウを破棄するためにフレームワークによって呼び出されます。|
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|新たに作成するには、この関数をオーバーライド`CDocObjectServer`オブジェクトし、このドキュメントが DocObject コンテナーであることを示します。|
|[COleServerDoc::OnClose](#onclose)|コンテナーは、ドキュメントを閉じる要求したときに、フレームワークによって呼び出されます。|
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|指定したコマンドを実行またはコマンドのヘルプを表示します。|
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|コンテナーのフレーム ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|取得するという、`COleServerItem`ドキュメント全体を表します。 埋め込みアイテムを取得するために使用します。 必要な実装です。|
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|一括編集中に行われた変更を元に戻すために、フレームワークによって呼び出されます。|
|[COleServerDoc::OnSetHostNames](#onsethostnames)|コンテナーは、埋め込みオブジェクトのウィンドウのタイトルを設定すると、フレームワークによって呼び出されます。|
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|コンテナー アプリケーションのウィンドウ内で埋め込み先編集フレーム ウィンドウを配置するためにフレームワークによって呼び出されます。|
|[COleServerDoc::OnShowDocument](#onshowdocument)|または、ドキュメントを非表示にフレームワークによって呼び出されます。|

## <a name="remarks"></a>Remarks

サーバーのドキュメントに含めることができます[COleServerItem](../../mfc/reference/coleserveritem-class.md)埋め込みまたはリンクされた項目をサーバーのインターフェイスを表すオブジェクト。 埋め込みアイテムを編集するためのコンテナーでサーバー アプリケーションが起動され、項目が独自サーバー ドキュメントとして読み込まれます`COleServerDoc`オブジェクトには、1 つだけ含まれる`COleServerItem`ドキュメント全体で構成されるオブジェクト。 リンクされた項目を編集するためのコンテナーでサーバー アプリケーションが起動され、既存のドキュメントがディスクから読み込まれますドキュメントの内容の一部は、リンクされた項目を強調表示されます。

`COleServerDoc` オブジェクトの項目を含めることも、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)クラス。 これにより、コンテナー/サーバー アプリケーションを作成することができます。 フレームワークが正しく保存する機能を提供、`COleClientItem`項目を処理しながら、`COleServerItem`オブジェクト。

サーバー アプリケーションがリンクをサポートしていない場合をサーバー ドキュメントには常にドキュメントとして全体の埋め込みオブジェクトを表す 1 つだけのサーバー項目が含まれます。 サーバー アプリケーションがリンクをサポートしている場合、選択範囲をクリップボードにコピーするたびにサーバー項目を作成する必要があります。

使用する`COleServerDoc`、そこから派生クラスを作成および実装、 [OnGetEmbeddedItem](#ongetembeddeditem)メンバー関数は、埋め込みアイテムをサポートするようにサーバーを使用します。 クラスを派生`COleServerItem`、ドキュメントにアイテムを実装しからそのクラスのオブジェクトを返します`OnGetEmbeddedItem`します。

リンクされた項目をサポートするために`COleServerDoc`提供、 [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem)メンバー関数。 既定の実装を使用したり、ドキュメントの項目を管理する独自の方法がある場合にオーバーライドできます。

必要な`COleServerDoc`-サーバーの各種類のドキュメント、アプリケーションがサポートするクラスを派生します。 などの場合は、サーバー アプリケーションでは、ワークシートとグラフをサポートする必要があります 2 `COleServerDoc`-クラスを派生します。

サーバーの詳細については、記事を参照してください。[サーバー。サーバーを実装する](../../mfc/servers-implementing-a-server.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

`COleServerDoc`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

##  <a name="activatedocobject"></a>  COleServerDoc::ActivateDocObject

関連付けられている DocObject ドキュメントをアクティブにします。

```
void ActivateDocObject();
```

### <a name="remarks"></a>Remarks

既定では、 `COleServerDoc` (DocObjects とも呼ばれる) アクティブなドキュメントをサポートしていません。 このサポートを有効にするのを参照してください。 [GetDocObjectServer](#getdocobjectserver)とクラス[CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)します。

##  <a name="activateinplace"></a>  COleServerDoc::ActivateInPlace

インプレース編集対象の項目をアクティブにします。

```
BOOL ActivateInPlace();
```

### <a name="return-value"></a>戻り値

成功した場合、0 以外の場合それ以外の場合 0 を返します、項目が完全で開かれています。

### <a name="remarks"></a>Remarks

この関数は、インプレース アクティブ化に必要なすべての操作を実行します。 で埋め込み先フレーム ウィンドウを作成します、アクティブ化されますとサイズを項目を共有メニューとその他のコントロールを設定、項目をスクロール表示、および埋め込み先フレーム ウィンドウにフォーカスを設定します。

この関数は、既定の実装の[COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)します。 アプリケーションは、(再生) など、インプレース アクティブ化のもう 1 つの動詞をサポートしている場合は、この関数を呼び出します。

##  <a name="coleserverdoc"></a>  COleServerDoc::COleServerDoc

構築、 `COleServerDoc` OLE システム Dll に接続しなくてもオブジェクトです。

```
COleServerDoc();
```

### <a name="remarks"></a>Remarks

呼び出す必要があります[COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) OLE で通信を開始します。 使用する場合[COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)アプリケーションでは、`COleLinkingDoc::Register`によって呼び出されますが`COleLinkingDoc`の実装の`OnNewDocument`、 `OnOpenDocument`、および`OnSaveDocument`します。

##  <a name="createinplaceframe"></a>  COleServerDoc::CreateInPlaceFrame

フレームワークは、インプレース編集用のフレーム ウィンドウを作成するには、この関数を呼び出します。

```
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
コンテナー アプリケーションの親ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

埋め込み先フレーム ウィンドウ、または失敗した場合は NULL へのポインター。

### <a name="remarks"></a>Remarks

既定の実装では、ドキュメント テンプレートで指定された情報を使用して、フレームを作成します。 使用されるビューは、ドキュメント用に作成された最初のビューです。 このビューは一時的に元のフレームからデタッチされ、新しく作成されたフレームにアタッチされています。

これは、高度なオーバーライド可能な。

##  <a name="deactivateandundo"></a>  COleServerDoc::DeactivateAndUndo

アプリケーションがサポートを元に戻すし、ユーザーが項目をアクティブ化した後、編集する前に元に戻す場合は、この関数を呼び出します。

```
BOOL DeactivateAndUndo();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>Remarks

Microsoft Foundation Class ライブラリを使用して、コンテナー アプリケーションが記述されている場合にこの関数を呼び出すと、 [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo)が呼び出されるユーザー インターフェイスのサーバーの非アクティブ化されます。

##  <a name="destroyinplaceframe"></a>  COleServerDoc::DestroyInPlaceFrame

フレームワークは、埋め込み先フレーム ウィンドウを破棄し、サーバー アプリケーションのドキュメント ウィンドウをインプレース アクティブ化する前に状態に戻すには、この関数を呼び出します。

```
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>パラメーター

*pFrameWnd*<br/>
破棄するフレーム ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

これは、高度なオーバーライド可能な。

##  <a name="discardundostate"></a>  COleServerDoc::DiscardUndoState

ユーザーは、元に戻すことができない編集の操作を実行する場合は、その元に戻す状態情報を破棄するコンテナー アプリケーションを強制するには、この関数を呼び出します。

```
BOOL DiscardUndoState();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>Remarks

この関数は、元に戻すをサポートしているサーバーがそれ以外の場合は使用できませんを元に戻す状態情報によって使用されるリソースを解放するために提供されます。

##  <a name="getclientsite"></a>  COleServerDoc::GetClientSite

基になるポインターを取得します`IOleClientSite`インターフェイス。

```
LPOLECLIENTSITE GetClientSite() const;
```

### <a name="return-value"></a>戻り値

基になるポインターを取得します[していること](/windows/desktop/api/oleidl/nn-oleidl-ioleclientsite)インターフェイス。

##  <a name="getdocobjectserver"></a>  COleServerDoc::GetDocObjectServer

新たに作成するには、この関数をオーバーライド`CDocObjectServer`項目し、ポインターを返します。

```
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```

### <a name="parameters"></a>パラメーター

*pDocSite*<br/>
ポインター、`IOleDocumentSite`このドキュメントをサーバーに接続するインターフェイス。

### <a name="return-value"></a>戻り値

ポインター、 `CDocObjectServer`;操作が失敗した場合は NULL です。

### <a name="remarks"></a>Remarks

DocObject サーバーがアクティブになって、クライアントが DocObjects をサポートできる NULL 以外のポインターの戻り値が表示されます。 既定の実装では、NULL を返します。

DocObjects をサポートするドキュメントの一般的な実装は、新しい単純に割り当てる`CDocObjectServer`オブジェクトし、呼び出し元に戻すこと。 例:

[!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]

##  <a name="getembeddeditem"></a>  COleServerDoc::GetEmbeddedItem

ドキュメント全体を表す項目へのポインターを取得するには、この関数を呼び出します。

```
COleServerItem* GetEmbeddedItem();
```

### <a name="return-value"></a>戻り値

ドキュメント全体を表す項目へのポインター操作が失敗した場合は NULL です。

### <a name="remarks"></a>Remarks

呼び出す[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)、実装のない既定の仮想関数。

##  <a name="getitemcliprect"></a>  COleServerDoc::GetItemClipRect

呼び出す、`GetItemClipRect`インプレース編集されているアイテムのクリッピング四角形の座標を取得します。

```
void GetItemClipRect(LPRECT lpClipRect) const;
```

### <a name="parameters"></a>パラメーター

*lpClipRect*<br/>
ポインターを`RECT`構造または`CRect`アイテムのクリッピング四角形の座標を受け取るオブジェクト。

### <a name="remarks"></a>Remarks

座標は、コンテナー アプリケーション ウィンドウのクライアント領域を基準と (ピクセル単位)。

描画は、クリッピング四角形の外側は発生しません。 通常は、描画は、自動的に制限されています。 この関数を使用して、ドキュメントの表示部分の外部ユーザーがスクロールするかどうかを判断するには場合は、スクロール、コンテナーのドキュメントへの呼び出しを使用して、必要に応じて[ScrollContainerBy](#scrollcontainerby)します。

##  <a name="getitemposition"></a>  COleServerDoc::GetItemPosition

呼び出す、`GetItemPosition`インプレース編集中の項目の座標を取得するメンバー関数。

```
void GetItemPosition(LPRECT lpPosRect) const;
```

### <a name="parameters"></a>パラメーター

*lpPosRect*<br/>
ポインターを`RECT`構造または`CRect`項目の座標を受け取るオブジェクト。

### <a name="remarks"></a>Remarks

座標は、コンテナー アプリケーション ウィンドウのクライアント領域を基準と (ピクセル単位)。

アイテムの位置は、項目を表示する (か非表示) する程度を調べますの現在のクリッピング四角形と比較する画面。

##  <a name="getzoomfactor"></a>  COleServerDoc::GetZoomFactor

`GetZoomFactor`メンバー関数は、インプレース編集をアクティブ化された項目の「倍率」を決定します。

```
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,
    LPSIZE lpSizeDenom = NULL,
    LPCRECT lpPosRect = NULL) const;
```

### <a name="parameters"></a>パラメーター

*lpSizeNum*<br/>
クラスのオブジェクトへのポインター`CSize`倍率の分子を保持します。 NULL にすることができます。

*lpSizeDenom*<br/>
クラスのオブジェクトへのポインター`CSize`倍率の分母を保持します。 NULL にすることができます。

*lpPosRect*<br/>
クラスのオブジェクトへのポインター`CRect`アイテムの新しい位置をについて説明します。 この引数が NULL の場合、関数は、現在の項目の位置を使用します。

### <a name="return-value"></a>戻り値

項目が、インプレース アクティブ化する場合は 0 以外を編集し、そのズームの倍率以外が 100% (1:1)。それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

ズームの倍率、ピクセル単位では、現在の大きさを項目のサイズの比率です。 コンテナー アプリケーションが、項目の範囲において、本来のエクステントを設定していない場合 (によって決定される[COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) が使用されます。

関数は、分子と分母の項目の「ズーム要素」に、最初の 2 つの引数を設定します。 項目がインプレース編集されていない場合、関数はこれらの引数を 100% (または 1:1) の既定値に設定し、0 を返します。 詳細については、テクニカル ノート 40: を参照してください。 [MFC/OLE 埋め込み先サイズ変更とズーム](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)します。

##  <a name="isdocobject"></a>  COleServerDoc::IsDocObject

ドキュメントが DocObject であるかどうかを判断します。

```
BOOL IsDocObject() const;
```

### <a name="return-value"></a>戻り値

ドキュメントが DocObject; である場合は TRUE。それ以外の場合は FALSE です。

##  <a name="isembedded"></a>  COleServerDoc::IsEmbedded

呼び出す、`IsEmbedded`ドキュメントがコンテナー内に埋め込まれたオブジェクトを表すかどうかを調べます。

```
BOOL IsEmbedded() const;
```

### <a name="return-value"></a>戻り値

0 以外の値、`COleServerDoc`オブジェクトがオブジェクトを表すドキュメント コンテナー内の埋め込み。 それ以外の場合 0。

### <a name="remarks"></a>Remarks

これは、リンクとしてのコンテナー アプリケーションによって処理される可能性が、ファイルから読み込まれたドキュメントが埋め込まれていません。 コンテナーのドキュメントに埋め込まれているドキュメントが埋め込まれると見なされます。

##  <a name="isinplaceactive"></a>  COleServerDoc::IsInPlaceActive

呼び出す、`IsInPlaceActive`メンバー関数は、項目が現在、インプレース アクティブな状態かどうかを確認します。

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>戻り値

0 以外の値、`COleServerDoc`オブジェクトが場所でアクティブな場合は 0 それ以外の場合。

##  <a name="notifychanged"></a>  COleServerDoc::NotifyChanged

ドキュメントが変更されたドキュメントに接続されているすべてのリンクされた項目に通知するには、この関数を呼び出します。

```
void NotifyChanged();
```

### <a name="remarks"></a>Remarks

通常、ユーザーがサーバー ドキュメントのサイズなどのグローバルな属性を変更した後、この関数を呼び出します。 OLE 項目が自動のリンクを使用して、ドキュメントにリンクされている場合は、変更を反映するように、項目が更新されます。 Microsoft Foundation Class ライブラリで記述されたアプリケーションをコンテナーで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。

> [!NOTE]
>  この関数は、OLE 1 と互換性のために含まれています。 新しいアプリケーションを使用する必要があります[UpdateAllItems](#updateallitems)します。

##  <a name="notifyclosed"></a>  COleServerDoc::NotifyClosed

この関数では、コンテナーに、ドキュメントが閉じられたことを通知します。

```
void NotifyClosed();
```

### <a name="remarks"></a>Remarks

ユーザーが [ファイル] メニューから [閉じる] コマンド`NotifyClosed`によって呼び出される`COleServerDoc`の実装、[通常](../../mfc/reference/cdocument-class.md#onclosedocument)メンバー関数。 Microsoft Foundation Class ライブラリで記述されたアプリケーションをコンテナーで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。

##  <a name="notifyrename"></a>  COleServerDoc::NotifyRename

ユーザー、サーバー ドキュメントの名前を変更した後は、この関数を呼び出します。

```
void NotifyRename(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>パラメーター

*lpszNewName*<br/>
サーバー ドキュメントの新しい名前を指定する文字列へのポインターこれは、通常、完全修飾パスです。

### <a name="remarks"></a>Remarks

ユーザーが [ファイル] メニューから名前を付けて保存コマンド`NotifyRename`によって呼び出される`COleServerDoc`の実装、[呼び出す必要はありません](../../mfc/reference/cdocument-class.md#onsavedocument)メンバー関数。 この関数は、OLE システム Dll で、さらに、コンテナーへの通知を通知します。 Microsoft Foundation Class ライブラリで記述されたアプリケーションをコンテナーで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。

##  <a name="notifysaved"></a>  COleServerDoc::NotifySaved

ユーザーがサーバー ドキュメントを保存した後は、この関数を呼び出します。

```
void NotifySaved();
```

### <a name="remarks"></a>Remarks

ユーザーが [ファイル] メニューから [保存] コマンド`NotifySaved`によって呼びます`COleServerDoc`の実装の[呼び出す必要はありません](../../mfc/reference/cdocument-class.md#onsavedocument)します。 この関数は、OLE システム Dll で、さらに、コンテナーへの通知を通知します。 Microsoft Foundation Class ライブラリで記述されたアプリケーションをコンテナーで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。

##  <a name="onclose"></a>  COleServerDoc::OnClose

コンテナーは、サーバーのドキュメントを閉じることを要求したときに、フレームワークによって呼び出されます。

```
virtual void OnClose(OLECLOSE dwCloseOption);
```

### <a name="parameters"></a>パラメーター

*dwCloseOption*<br/>
列挙子の値。 このパラメーターには、次のいずれかの値を指定できます。

- OLECLOSE_SAVEIFDIRTY が変更された場合に、ファイルが保存されます。

- 保存されることがなく、ファイルが閉じられた OLECLOSE_NOSAVE します。

- OLECLOSE_PROMPTSAVE 場合、ファイルは変更されて、ユーザーはについて保存するように求められます。

### <a name="remarks"></a>Remarks

既定の実装`CDocument::OnCloseDocument`します。

詳細とその他の値は、次を参照してください。[子](/windows/desktop/api/oleidl/ne-oleidl-tagoleclose)Windows SDK に含まれています。

##  <a name="ondeactivate"></a>  COleServerDoc::OnDeactivate

ユーザーが現在位置で有効になっている埋め込みまたはリンクされた項目を非アクティブ化時に、フレームワークによって呼び出されます。

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>Remarks

この関数は、コンテナー アプリケーションのユーザー インターフェイスを元の状態に復元し、メニューやインプレース アクティブ化用に作成されたその他のコントロールを破棄します。

元に戻す状態情報は無条件にこの時点でします。

詳細については、記事を参照してください[アクティベーション](../../mfc/activation-cpp.md)..

##  <a name="ondeactivateui"></a>  COleServerDoc::OnDeactivateUI

ユーザーは、インプレース アクティブなアイテムを非アクティブ化時に呼び出されます。

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>パラメーター

*bUndoable*<br/>
編集が完了できるかどうかを指定します。

### <a name="remarks"></a>Remarks

この関数は、元の状態にメニューやインプレース アクティブ化用に作成されたその他のコントロールを非表示にコンテナー アプリケーションのユーザー インターフェイスを復元します。

常に、フレームワークを設定*bUndoable*を FALSE にします。 サーバーは元に戻す、サポート、元に戻すことができる操作がある場合は、基底クラス実装を呼び出す*bUndoable*を TRUE に設定します。

##  <a name="ondocwindowactivate"></a>  COleServerDoc::OnDocWindowActivate

フレームワークは、アクティブ化またはインプレース編集するためのドキュメント ウィンドウを非アクティブ化するには、この関数を呼び出します。

```
virtual void OnDocWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*bActivate*<br/>
ドキュメント ウィンドウがアクティブ化または非アクティブ化するかどうかを指定します。

### <a name="remarks"></a>Remarks

既定の実装で、削除するかに応じて、フレーム レベルのユーザー インターフェイス要素を追加します。 アイテムを持つドキュメントをアクティブ化または非アクティブ化されたときに、追加のアクションを実行する場合は、この関数をオーバーライドします。

詳細については、記事を参照してください[アクティベーション](../../mfc/activation-cpp.md)..

##  <a name="onexecolecmd"></a>  COleServerDoc::OnExecOleCmd

フレームワークは、指定したコマンドを実行またはコマンドのヘルプを表示するには、この関数を呼び出します。

```
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,
    DWORD nCmdID,
    DWORD nCmdExecOpt,
    VARIANTARG* pvarargIn,
    VARIANTARG* pvarargOut);
```

### <a name="parameters"></a>パラメーター

*pguidCmdGroup*<br/>
コマンドのセットを識別する GUID へのポインター。 既定のコマンド グループを示す NULL を指定できます。

*nCmdID*<br/>
実行するコマンド。 識別されるグループである必要があります*pguidCmdGroup*します。

*nCmdExecOut*<br/>
オブジェクトでは、する方法から、コマンド、1 つ以上の次の値を実行する必要があります。

OLECMDEXECOPT_DODEFAULT

OLECMDEXECOPT_PROMPTUSER

OLECMDEXECOPT_DONTPROMPTUSER

OLECMDEXECOPT_SHOWHELP

*pvarargIn*<br/>
コマンドの入力引数を含む VARIANTARG へのポインター。 NULL にすることができます。

*pvarargOut*<br/>
出力を受信するパラメータ リストへのポインターは、コマンドからの値を返します。 NULL にすることができます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返します。次のエラー コードの 1 つをそれ以外の場合:

|[値]|説明|
|-----------|-----------------|
|E_UNEXPECTED|予期しないエラーが発生しました|
|E_FAIL|エラーが発生しました|
|E_NOTIMPL|MFC を示す変換し、コマンドをディスパッチする自体を試みる必要があります。|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* NULL 以外ですが、認識されたコマンドのグループを指定できません|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID*はグループ内の有効なコマンドとして認識されません*pguidCmdGroup*|
|OLECMDERR_DISABLED|によって識別されるコマンド*nCmdID*は無効になり、実行することはできません|
|OLECMDERR_NOHELP|呼び出し元によって識別されるコマンドのヘルプについてよく寄せられる*nCmdID*ヘルプはありませんが、|
|OLECMDERR_CANCELED|ユーザーは、実行をキャンセルしました。|

### <a name="remarks"></a>Remarks

`COleCmdUI` 有効にする、更新、および DocObject ユーザー インターフェイスのコマンドの他のプロパティを設定するために使用します。 コマンドは初期化され後でそれらを実行できる`OnExecOleCmd`します。

フレームワークは、変換および OLE ドキュメント コマンドをディスパッチする前に、関数を呼び出します。 標準の OLE ドキュメント コマンドを処理するには、この関数をオーバーライドする必要はありませんが、独自のカスタム コマンドを処理するか、パラメーターを受け入れるか、結果を返すのコマンドを処理する場合は、この関数をオーバーライドを指定する必要があります。

ほとんどのコマンドの引数を受け取るまたは戻り値はできません。 ほとんどのコマンドの呼び出し元は、null 値を渡すことができます*pvarargIn*と*元*します。 入力値を期待するコマンドの呼び出し元宣言し VARIANTARG 変数を初期化およびできますで変数へのポインターを渡す*pvarargIn*します。 1 つの値を必要とするコマンド、引数を VARIANTARG に直接格納されている、関数に渡されることができます。 複数の引数はサポートされている型のいずれかを使用して VARIANTARG 内でパッケージ化する必要があります (など`IDispatch`と SAFEARRAY)。

同様に、コマンドが、呼び出し元の宣言、VARIANTARG が予想される引数を返す場合 VT_EMPTY に初期化し、そのアドレスを渡す*元*します。 コマンドが 1 つの値を返す場合、オブジェクトで直接その値を格納できます*元*します。 複数の出力値は、VARIANTARG に適した何らかの方法でパッケージ化する必要があります。

この関数の基本クラスの実装はコマンド ターゲットに関連付けられている対応の構造について説明し、適切なハンドラーにコマンドをディスパッチしようとしています。 基本クラスの実装は、戻り値または引数を受け入れるしないコマンドでのみ動作します。 コマンド引数を受け入れるか、戻り値を処理する必要がある場合は、この関数をオーバーライドしを使用する必要があります、 *pvarargIn*と*元*パラメーター自分でします。

##  <a name="onframewindowactivate"></a>  COleServerDoc::OnFrameWindowActivate

フレームワークは、コンテナー アプリケーションのフレーム ウィンドウがアクティブ化または非アクティブ化されたときに、この関数を呼び出します。

```
virtual void OnFrameWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*bActivate*<br/>
フレーム ウィンドウがアクティブ化または非アクティブ化するかどうかを指定します。

### <a name="remarks"></a>Remarks

既定の実装では、フレーム ウィンドウのヘルプ モードをキャンセルします。 フレーム ウィンドウをアクティブ化または非アクティブ化されたときに、特別な処理を実行する場合は、この関数をオーバーライドします。

詳細については、記事を参照してください[アクティベーション](../../mfc/activation-cpp.md)..

##  <a name="ongetembeddeditem"></a>  COleServerDoc::OnGetEmbeddedItem

コンテナー アプリケーションを作成または埋め込みアイテムを編集するサーバー アプリケーションを呼び出すときに、フレームワークによって呼び出されます。

```
virtual COleServerItem* OnGetEmbeddedItem() = 0;
```

### <a name="return-value"></a>戻り値

ドキュメント全体を表す項目へのポインター操作が失敗した場合は NULL です。

### <a name="remarks"></a>Remarks

既定の実装はありません。 ドキュメント全体を表す項目を返すには、この関数をオーバーライドする必要があります。 この戻り値のオブジェクトである必要があります、 `COleServerItem`-クラスを派生します。

##  <a name="onreactivateandundo"></a>  COleServerDoc::OnReactivateAndUndo

フレームワークは、インプレース アクティブ化、変更、およびその後に非アクティブ化された項目に加えられた変更を元に戻す、ユーザーが選択したときに、この関数を呼び出します。

```
virtual BOOL OnReactivateAndUndo();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

既定の実装では、失敗する場合は FALSE を返す点を除いて何も行われません。

アプリケーションは、元に戻すをサポートしている場合は、この関数をオーバーライドします。 通常、元に戻す操作を実行し、呼び出すことによって、項目をアクティブ化する`ActivateInPlace`します。 呼び出して、Microsoft Foundation Class ライブラリでコンテナー アプリケーションを記述すると場合、`COleClientItem::ReactivateAndUndo`によりこの関数を呼び出します。

##  <a name="onresizeborder"></a>  COleServerDoc::OnResizeBorder

フレームワークは、コンテナー アプリケーションのフレーム ウィンドウのサイズを変更するときに、この関数を呼び出します。

```
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,
    LPOLEINPLACEUIWINDOW lpUIWindow,
    BOOL bFrame);
```

### <a name="parameters"></a>パラメーター

*lpRectBorder*<br/>
ポインターを`RECT`構造または`CRect`罫線の座標を指定するオブジェクト。

*lpUIWindow*<br/>
クラスのオブジェクトへのポインター`IOleInPlaceUIWindow`現在のインプレース編集セッションを所有しています。

*bFrame*<br/>
TRUE の場合*lpUIWindow*コンテナー アプリケーションの最上位レベルのフレーム ウィンドウ、または場合は FALSE を指す*lpUIWindow*コンテナー アプリケーションのドキュメント レベルのフレーム ウィンドウを指します。

### <a name="remarks"></a>Remarks

この関数は、サイズを変更し、ツールバーと新しいウィンドウのサイズに従ってその他のユーザー インターフェイス要素を調整します。

詳細については、次を参照してください。[埋め込み](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceuiwindow)Windows SDK に含まれています。

これは、高度なオーバーライド可能な。

##  <a name="onsethostnames"></a>  COleServerDoc::OnSetHostNames

コンテナーを設定またはこのドキュメントのホスト名を変更するときに、フレームワークによって呼び出されます。

```
virtual void OnSetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>パラメーター

*lpszHost*<br/>
コンテナー アプリケーションの名前を指定する文字列へのポインター。

*lpszHostObj*<br/>
ドキュメントのコンテナーの名前を指定する文字列へのポインター。

### <a name="remarks"></a>Remarks

既定の実装では、このドキュメントを参照するすべてのビューのドキュメントのタイトルを変更します。

アプリケーションが別のメカニズムでタイトルを設定している場合は、この関数をオーバーライドします。

##  <a name="onsetitemrects"></a>  COleServerDoc::OnSetItemRects

フレームワークは、コンテナー アプリケーションのフレーム ウィンドウ内でのインプレース編集フレーム ウィンドウの配置には、この関数を呼び出します。

```
virtual void OnSetItemRects(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>パラメーター

*lpPosRect*<br/>
ポインターを`RECT`構造または`CRect`コンテナー アプリケーションのクライアント領域に対して相対的で埋め込み先フレーム ウィンドウの位置を指定するオブジェクト。

*lpClipRect*<br/>
ポインターを`RECT`構造または`CRect`コンテナー アプリケーションのクライアント領域に対して相対的で埋め込み先フレーム ウィンドウのクリッピング四角形を指定するオブジェクト。

### <a name="remarks"></a>Remarks

必要な場合は、ビューのズームの倍率を更新するには、この関数をオーバーライドします。

この関数は通常への応答と呼ばれる、`RequestPositionChange`呼び出すには、インプレース項目の位置の変更を要求するコンテナーによっていつでも呼び出すことができますが。

##  <a name="onshowcontrolbars"></a>  COleServerDoc::OnShowControlBars

フレームワークで識別されるフレーム ウィンドウに関連付けられているサーバー アプリケーションのコントロール バーを非表示には、この関数を呼び出します*pFrameWnd*します。

```
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*pFrameWnd*<br/>
コントロール バーを非表示または表示する必要があります、フレーム ウィンドウへのポインター。

*bShow*<br/>
コントロール バーを表示または非表示かどうかを判断します。

### <a name="remarks"></a>Remarks

既定の実装は、そのフレーム ウィンドウが所有するすべてのコントロール バーを列挙します。 または非表示にし、それらを表示します。

##  <a name="onshowdocument"></a>  COleServerDoc::OnShowDocument

フレームワークによって、`OnShowDocument`関数の場合、サーバーのドキュメントを非表示または表示する必要があります。

```
virtual void OnShowDocument(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
ドキュメントにユーザー インターフェイスを表示/非表示かどうかを指定します。

### <a name="remarks"></a>Remarks

場合*bShow*が true の場合、既定の実装は、必要に応じて、サーバー アプリケーションをアクティブにし、コンテナー アプリケーションで、項目が表示されるように、そのウィンドウをスクロールします。 場合*bShow* false で、既定の実装への呼び出しを使用して、アイテムを非アクティブ化`OnDeactivate`、破棄または最初の 1 つを除く、ドキュメント用に作成されたすべてのフレーム ウィンドウを非表示にします。 表示されているドキュメントが残っていない場合、既定の実装には、サーバー アプリケーションが非表示にします。

##  <a name="onupdatedocument"></a>  COleServerDoc::OnUpdateDocument

複合ドキュメントに埋め込まれた項目は、文書を保存するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnUpdateDocument();
```

### <a name="return-value"></a>戻り値

以外の場合は、ドキュメントが正常に更新されました。それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

既定の実装、 [COleServerDoc::NotifySaved](#notifysaved)と[COleServerDoc::SaveEmbedding](#saveembedding)メンバー関数し、クリーンとしてマークします。 特別な埋め込みアイテムを更新するときの処理を実行する場合は、この関数をオーバーライドします。

##  <a name="requestpositionchange"></a>  COleServerDoc::RequestPositionChange

コンテナー アプリケーションを項目の位置を変更するには、このメンバー関数を呼び出します。

```
void RequestPositionChange(LPCRECT lpPosRect);
```

### <a name="parameters"></a>パラメーター

*lpPosRect*<br/>
ポインターを`RECT`構造または`CRect`アイテムの新しい位置を格納しているオブジェクト。

### <a name="remarks"></a>Remarks

この関数は通常呼び出されます (と共に`UpdateAllItems`)、インプレース アクティブなアイテムのデータが変更されたとき。 この呼び出しでは、次のコンテナーがありますまたは呼び出すことで、変更を実行しない可能性があります`OnSetItemRects`します。 結果の位置は、要求されたものとは異なる場合があります。

##  <a name="saveembedding"></a>  COleServerDoc::SaveEmbedding

この関数では、埋め込みオブジェクトを保存するコンテナーのアプリケーションに指示します。

```
void SaveEmbedding();
```

### <a name="remarks"></a>Remarks

この関数から自動的に呼び出される`OnUpdateDocument`します。 この関数により、アイテムは、通常は特定のユーザー アクションの結果としてのみと呼ばれるため、ディスク上で更新であることに注意してください。

##  <a name="scrollcontainerby"></a>  COleServerDoc::ScrollContainerBy

呼び出す、`ScrollContainerBy`で (ピクセル単位) の量で、コンテナーのドキュメントをスクロールするメンバー関数が示される`sizeScroll`します。

```
BOOL ScrollContainerBy(CSize sizeScroll);
```

### <a name="parameters"></a>パラメーター

*sizeScroll*<br/>
コンテナーのドキュメントでスクロールがどれだけ遅れたかを示します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

正の値が右にスクロール ダウンを示します負の値を示すを左へスクロールします。

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

*pSender*<br/>
ドキュメントを変更する項目へのポインターまたはすべての項目を更新するか場合は NULL です。

*lHint*<br/>
変更に関する情報が含まれています。

*pHint*<br/>
変更に関する情報を格納するオブジェクトへのポインター。

*nDrawAspect*<br/>
項目が描画される方法を決定します。 これは、列挙型の値です。 このパラメーターには、次のいずれかの値を指定できます。

- DVASPECT_CONTENT 項目は、そのコンテナー内の埋め込みオブジェクトとして表示されることがこのような方法で表されます。

- DVASPECT_THUMBNAIL アイテムは、参照ツールで表示できるように、「サムネイル」表記で表示されます。

- DVASPECT_ICON 項目がアイコンで表されます。

- [ファイル] メニューから [印刷] コマンドを使用して印刷した場合と、DVASPECT_DOCPRINT 項目が表されます。

### <a name="remarks"></a>Remarks

通常、ユーザーがサーバー ドキュメントを変更した後は、この関数を呼び出します。 OLE 項目が自動のリンクを使用して、ドキュメントにリンクされている場合は、変更を反映するように、項目が更新されます。 Microsoft Foundation Class ライブラリで記述されたアプリケーションをコンテナーで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。

この関数を呼び出して、`OnUpdate`メンバー関数の各項目を渡すことの送信を除く、ドキュメントの項目の*pHint*、 *lHint*、および*nDrawAspect*します。 これらのパラメーターを使用して、ドキュメントに加えられた変更についてのアイテムに情報を渡します。 使用して情報をエンコードする*lHint*を定義することができます、 `CObject`-派生クラスを変更についての情報を格納しを使用してそのクラスのオブジェクトを渡す*pHint*します。 上書き、`OnUpdate`でメンバー関数、 `COleServerItem`-そのプレゼンテーションが変更されたかどうかに応じて、各項目の更新を最適化するためにクラスを派生します。

## <a name="see-also"></a>関連項目

[MFC サンプル HIERSVR](../../visual-cpp-samples.md)<br/>
[COleLinkingDoc クラス](../../mfc/reference/colelinkingdoc-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDocument クラス](../../mfc/reference/coledocument-class.md)<br/>
[COleLinkingDoc クラス](../../mfc/reference/colelinkingdoc-class.md)<br/>
[COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)
