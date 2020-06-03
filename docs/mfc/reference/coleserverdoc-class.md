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
ms.openlocfilehash: 8e75ec5c00c614a225a059a2b3cf97a7a307c61c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753778"
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
|[をクリックします。](#coleserverdoc)|`COleServerDoc` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ドキュメントオブジェクトをアクティブにします。](#activatedocobject)|関連付けられている DocObject ドキュメントをアクティブにします。|
|[サービスサーバードック::インプレイスをアクティブにする](#activateinplace)|ドキュメントをインプレイス編集用にアクティブにします。|
|[コレクサーバードック::Dアクティブ化と元に戻す](#deactivateandundo)|サーバーのユーザー インターフェイスを非アクティブ化します。|
|[ドキュメント::Dカード元に戻す状態](#discardundostate)|元に戻す状態の情報を破棄します。|
|[をクリックします。](#getclientsite)|基になる`IOleClientSite`インターフェイスへのポインターを取得します。|
|[を取得します。](#getembeddeditem)|ドキュメント全体を表す項目へのポインターを返します。|
|[をクリックします。](#getitemcliprect)|インプレイス編集用の現在のクリッピング四角形を返します。|
|[を指定します。](#getitemposition)|インプレース編集用に、コンテナー アプリケーションのクライアント領域を基準にして、現在位置の四角形を返します。|
|[をクリックします。](#getzoomfactor)|ズーム倍率をピクセル単位で返します。|
|[をクリックします。](#isdocobject)|ドキュメントが DocObject かどうかを判断します。|
|[を組み込む](#isembedded)|ドキュメントがコンテナー ドキュメントに埋め込まれているか、スタンドアロンで実行されているかを示します。|
|[サービスサーバードック::イインプレイスアクティブ](#isinplaceactive)|アイテムが現在その場でアクティブになっている場合は TRUE を返します。|
|[を変更しました。](#notifychanged)|ユーザーがドキュメントを変更したことをコンテナーに通知します。|
|[を閉じました。](#notifyclosed)|ユーザーがドキュメントを閉じたことをコンテナーに通知します。|
|[名前の変更を通知します。](#notifyrename)|ユーザーがドキュメントの名前を変更したことをコンテナーに通知します。|
|[を保存しました。](#notifysaved)|ユーザーがドキュメントを保存したことをコンテナーに通知します。|
|[を無効にします。](#ondeactivate)|ユーザーがアクティブ化されたアイテムを非アクティブ化したときに、フレームワークによって呼び出されます。|
|[サービスサーバードック::オンオフアクティブUI](#ondeactivateui)|コントロールと、インプレース アクティブ化用に作成された他のユーザー インターフェイス要素を破棄するために、フレームワークによって呼び出されます。|
|[をクリックします。](#ondocwindowactivate)|コンテナーのドキュメント フレーム ウィンドウがアクティブまたは非アクティブになったときに、フレームワークによって呼び出されます。|
|[をクリックします。](#onresizeborder)|コンテナー アプリケーションのフレーム ウィンドウまたはドキュメント ウィンドウのサイズが変更されたときに、フレームワークによって呼び出されます。|
|[コントロールバーを表示します。](#onshowcontrolbars)|インプレース編集用のコントロール バーの表示と非表示を切り替えるために、フレームワークによって呼び出されます。|
|[ドキュメントを更新します。](#onupdatedocument)|埋め込みアイテムであるサーバー ドキュメントが保存されるときに、コンテナーのアイテムのコピーを更新するときに、フレームワークによって呼び出されます。|
|[を変更します。](#requestpositionchange)|インプレイス編集フレームの位置を変更します。|
|[を埋め込む](#saveembedding)|ドキュメントを保存するようにコンテナー アプリケーションに指示します。|
|[をクリックします。](#scrollcontainerby)|コンテナー ドキュメントをスクロールします。|
|[をクリックします。](#updateallitems)|ユーザーがドキュメントを変更したことをコンテナーに通知します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#createinplaceframe)|インプレイス編集用のフレーム ウィンドウを作成するために、フレームワークによって呼び出されます。|
|[:Dエストロイインプレイスフレーム](#destroyinplaceframe)|インプレース編集用のフレーム ウィンドウを破棄するために、フレームワークによって呼び出されます。|
|[サーバーサーバー](#getdocobjectserver)|新しい`CDocObjectServer`オブジェクトを作成し、このドキュメントが DocObject コンテナであることを示すには、この関数をオーバーライドします。|
|[を閉じる](#onclose)|コンテナーがドキュメントを閉じる要求を行ったときに、フレームワークによって呼び出されます。|
|[をクリックします。](#onexecolecmd)|指定したコマンドを実行するか、コマンドのヘルプを表示します。|
|[をクリックします。](#onframewindowactivate)|コンテナーのフレーム ウィンドウがアクティブまたは非アクティブになったときに、フレームワークによって呼び出されます。|
|[をクリックします。](#ongetembeddeditem)|ドキュメント全体を表`COleServerItem`すを取得するために呼び出されます。埋め込みアイテムを取得するために使用されます。 実装が必要です。|
|[コレクサーバードック::オン再アクティブ化と元に戻す](#onreactivateandundo)|インプレース編集中に行われた変更を元に戻すために、フレームワークによって呼び出されます。|
|[ホスト名を設定します。](#onsethostnames)|コンテナーが埋め込みオブジェクトのウィンドウ タイトルを設定するときに、フレームワークによって呼び出されます。|
|[をクリックします。](#onsetitemrects)|コンテナー アプリケーションのウィンドウ内で埋め込み可能な編集フレーム ウィンドウを配置するために、フレームワークによって呼び出されます。|
|[ドキュメントを表示します。](#onshowdocument)|ドキュメントを表示または非表示にするために、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

サーバー ドキュメントには、埋め込みアイテムまたはリンクアイテムへのサーバー インターフェイスを表す[COleServerItem](../../mfc/reference/coleserveritem-class.md)オブジェクトを含めることができます。 埋め込みアイテムを編集するためにコンテナーによってサーバー アプリケーションが起動されると、そのアイテムは独自のサーバー ドキュメントとして読み込まれます。オブジェクト`COleServerDoc`には、ドキュメント全体`COleServerItem`で構成されるオブジェクトが 1 つだけ含まれます。 リンクされたアイテムを編集するためにサーバー アプリケーションがコンテナーによって起動されると、既存のドキュメントがディスクから読み込まれます。ドキュメントの内容の一部がハイライト表示され、リンクされたアイテムが示されます。

`COleServerDoc`オブジェクトには、[クラス](../../mfc/reference/coleclientitem-class.md)の項目を含めることもできます。 これにより、コンテナー サーバー アプリケーションを作成できます。 フレームワークは、オブジェクトのサービスを提供`COleClientItem`しながら、アイテムを`COleServerItem`適切に格納する機能を提供します。

サーバー アプリケーションがリンクをサポートしていない場合、サーバー ドキュメントには常に 1 つのサーバー アイテムのみが含まれます。 サーバー アプリケーションがリンクをサポートしている場合は、選択内容がクリップボードにコピーされるたびにサーバー アイテムを作成する必要があります。

を使用`COleServerDoc`するには、クラスを派生し、サーバーが埋め込みアイテムをサポートできるようにする[OnGetEmbeddedItem](#ongetembeddeditem)メンバー関数を実装します。 からクラス`COleServerItem`を派生してドキュメント内の項目を実装し、そのクラスのオブジェクトを`OnGetEmbeddedItem`から返します。

リンクされたアイテムをサポート`COleServerDoc`するには、[メンバー](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem)関数を提供します。 ドキュメント項目を独自に管理する方法がある場合は、既定の実装を使用するか、オーバーライドできます。

アプリケーションがサポート`COleServerDoc`するサーバー ドキュメントの種類ごとに、1 つの派生クラスが必要です。 たとえば、サーバー アプリケーションがワークシートとグラフをサポートしている場合は、2`COleServerDoc`つの派生クラスが必要です。

サーバーの詳細については、「[サーバー : サーバーの実装](../../mfc/servers-implementing-a-server.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

`COleServerDoc`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coleserverdocactivatedocobject"></a><a name="activatedocobject"></a>ドキュメントオブジェクトをアクティブにします。

関連付けられている DocObject ドキュメントをアクティブにします。

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>解説

既定では、`COleServerDoc`アクティブ ドキュメント (DocObjects とも呼ばれます) はサポートされていません。 このサポートを有効にするには、[次を参照](#getdocobjectserver)[してください。](../../mfc/reference/cdocobjectserver-class.md)

## <a name="coleserverdocactivateinplace"></a><a name="activateinplace"></a>サービスサーバードック::インプレイスをアクティブにする

インプレイス編集用のアイテムをアクティブにします。

```
BOOL ActivateInPlace();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合は 0 で、アイテムが完全に開かっていることを示します。

### <a name="remarks"></a>解説

この関数は、インプレース アクティベーションに必要なすべての操作を実行します。 インプレイス フレーム ウィンドウを作成し、アクティブにしてアイテムのサイズを設定し、共有メニューやその他のコントロールを設定し、アイテムをスクロールしてビューに移動し、フォーカスをインプレイス フレーム ウィンドウに設定します。

この関数は、既定の実装によって呼び出[されます](../../mfc/reference/coleserveritem-class.md#onshow)。 アプリケーションがインプレース アクティブ化用に別の動詞 (Play など) をサポートしている場合は、この関数を呼び出します。

## <a name="coleserverdoccoleserverdoc"></a><a name="coleserverdoc"></a>をクリックします。

OLE システム`COleServerDoc`DLL に接続せずにオブジェクトを構築します。

```
COleServerDoc();
```

### <a name="remarks"></a>解説

OLE との通信を開くには[、COleリンキング Doc::登録](../../mfc/reference/colelinkingdoc-class.md#register)を呼び出す必要があります。 アプリケーションで[COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)を使用している場合`COleLinkingDoc::Register`は、 、`OnOpenDocument`および`COleLinkingDoc`の`OnNewDocument`実装によって呼び`OnSaveDocument`出されます。

## <a name="coleserverdoccreateinplaceframe"></a><a name="createinplaceframe"></a>をクリックします。

フレームワークは、この関数を呼び出して、インプレース編集用のフレーム ウィンドウを作成します。

```
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
コンテナー アプリケーションの親ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

埋め込みフレーム ウィンドウへのポインター。

### <a name="remarks"></a>解説

既定の実装では、ドキュメント テンプレートで指定された情報を使用してフレームを作成します。 使用されるビューは、ドキュメントに対して最初に作成されたビューです。 このビューは、元のフレームから一時的に切り離され、新しく作成されたフレームにアタッチされます。

これは、高度なオーバーライド可能です。

## <a name="coleserverdocdeactivateandundo"></a><a name="deactivateandundo"></a>コレクサーバードック::Dアクティブ化と元に戻す

アプリケーションが Undo をサポートし、ユーザーが項目をアクティブにした後、編集する前に [元に戻す] を選択した場合に、この関数を呼び出します。

```
BOOL DeactivateAndUndo();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>解説

コンテナー アプリケーションが Microsoft Foundation クラス ライブラリを使用して記述されている場合、この関数を呼び出すと[、COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo)が呼び出され、サーバーのユーザー インターフェイスが無効になります。

## <a name="coleserverdocdestroyinplaceframe"></a><a name="destroyinplaceframe"></a>:Dエストロイインプレイスフレーム

フレームワークは、インプレース フレーム ウィンドウを破棄し、インプレース アクティブ化前にサーバー アプリケーションのドキュメント ウィンドウをその状態に戻すために、この関数を呼び出します。

```
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
破棄されるインプレイス フレーム ウィンドウへのポインター。

### <a name="remarks"></a>解説

これは、高度なオーバーライド可能です。

## <a name="coleserverdocdiscardundostate"></a><a name="discardundostate"></a>ドキュメント::Dカード元に戻す状態

元に戻すことができない編集操作をユーザーが実行する場合は、この関数を呼び出して、コンテナー アプリケーションに元に戻す状態の情報を強制的に破棄します。

```
BOOL DiscardUndoState();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>解説

この関数は、Undo をサポートするサーバーが、使用できない元に戻す状態情報によって消費されるリソースを解放できるように提供されています。

## <a name="coleserverdocgetclientsite"></a><a name="getclientsite"></a>をクリックします。

基になる`IOleClientSite`インターフェイスへのポインターを取得します。

```
LPOLECLIENTSITE GetClientSite() const;
```

### <a name="return-value"></a>戻り値

基になるインターフェイスへのポインター[を](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite)取得します。

## <a name="coleserverdocgetdocobjectserver"></a><a name="getdocobjectserver"></a>サーバーサーバー

新しい`CDocObjectServer`項目を作成し、その項目へのポインターを返す場合は、この関数をオーバーライドします。

```
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
このドキュメントを`IOleDocumentSite`サーバーに接続するインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

へのポインター。 `CDocObjectServer`操作が失敗した場合は NULL。

### <a name="remarks"></a>解説

DocObject サーバーがアクティブ化されると、NULL 以外のポインタが返されると、クライアントが DocObjects をサポートできることが示されます。 既定の実装では NULL が返されます。

DocObjects をサポートするドキュメントの一般的な実装では、単`CDocObjectServer`に新しいオブジェクトを割り当てて呼び出し元に返します。 次に例を示します。

[!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]

## <a name="coleserverdocgetembeddeditem"></a><a name="getembeddeditem"></a>を取得します。

ドキュメント全体を表す項目へのポインターを取得します。

```
COleServerItem* GetEmbeddedItem();
```

### <a name="return-value"></a>戻り値

ドキュメント全体を表す項目へのポインター。操作が失敗した場合は NULL。

### <a name="remarks"></a>解説

これは、既定[の](#ongetembeddeditem)実装を持たない仮想関数を呼び出します。

## <a name="coleserverdocgetitemcliprect"></a><a name="getitemcliprect"></a>をクリックします。

メンバー関数`GetItemClipRect`を呼び出して、編集中のアイテムのクリッピング四角形座標を取得します。

```cpp
void GetItemClipRect(LPRECT lpClipRect) const;
```

### <a name="parameters"></a>パラメーター

*lp クリップレック*<br/>
アイテムの`RECT`クリッピング四角形`CRect`座標を受け取る構造体またはオブジェクトへのポインター。

### <a name="remarks"></a>解説

座標は、コンテナー アプリケーション ウィンドウのクライアント領域に対する相対的なピクセル数です。

クリッピング四角形の外側に描画を行う必要があります。 通常、描画は自動的に制限されます。 この関数を使用して、ユーザーが文書の表示部分の外側にスクロールしたかどうかを調べます。その場合は、必要に応じて[、ScrollContainerBy](#scrollcontainerby)を呼び出してコンテナー ドキュメントをスクロールします。

## <a name="coleserverdocgetitemposition"></a><a name="getitemposition"></a>を指定します。

メンバー関数`GetItemPosition`を呼び出して、編集中の項目の座標を取得します。

```cpp
void GetItemPosition(LPRECT lpPosRect) const;
```

### <a name="parameters"></a>パラメーター

*lpPosRect*<br/>
項目の`RECT`座標を`CRect`受け取る構造体またはオブジェクトへのポインター。

### <a name="remarks"></a>解説

座標は、コンテナー アプリケーション ウィンドウのクライアント領域に対する相対的なピクセル数です。

項目の位置を現在のクリッピング四角形と比較して、画面上でアイテムが表示される (または表示されない) 範囲を決定できます。

## <a name="coleserverdocgetzoomfactor"></a><a name="getzoomfactor"></a>をクリックします。

メンバー`GetZoomFactor`関数は、インプレース編集のためにアクティブ化されている項目の「ズーム係数」を決定します。

```
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,
    LPSIZE lpSizeDenom = NULL,
    LPCRECT lpPosRect = NULL) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ズーム倍率の分子を`CSize`保持するクラスのオブジェクトへのポインター。 NULL にすることができます。

*lpサイズデノム*<br/>
ズーム係数の分母を`CSize`保持するクラスのオブジェクトへのポインター。 NULL にすることができます。

*lpPosRect*<br/>
項目の新しい位置を`CRect`記述するクラスのオブジェクトへのポインター。 この引数が NULL の場合、関数は項目の現在位置を使用します。

### <a name="return-value"></a>戻り値

インプレイス編集のために項目がアクティブ化され、そのズーム倍率が 100% (1:1) 以外の場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ズーム倍率 (ピクセル単位) は、現在の範囲に対するアイテムのサイズの比率です。 コンテナー アプリケーションがアイテムの範囲を設定していない場合は、その自然な範囲[(COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)によって決定される) が使用されます。

この関数は、最初の 2 つの引数を、項目の "ズームファクター" の分子と分母に設定します。 アイテムがインプレイス編集されていない場合、関数はこれらの引数をデフォルト値の 100% (または 1:1) に設定し、ゼロを返します。 詳細については、テクニカル ノート 40、 [MFC/OLE のインプレース サイズとズームを参照](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)してください。

## <a name="coleserverdocisdocobject"></a><a name="isdocobject"></a>をクリックします。

ドキュメントが DocObject かどうかを判断します。

```
BOOL IsDocObject() const;
```

### <a name="return-value"></a>戻り値

ドキュメントが DocObject の場合は TRUE。それ以外の場合は FALSE。

## <a name="coleserverdocisembedded"></a><a name="isembedded"></a>を組み込む

ドキュメントが`IsEmbedded`コンテナーに埋め込まれたオブジェクトを表しているかどうかを判断するには、メンバー関数を呼び出します。

```
BOOL IsEmbedded() const;
```

### <a name="return-value"></a>戻り値

オブジェクトがコンテナーに`COleServerDoc`埋め込まれたオブジェクトを表すドキュメントの場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ファイルから読み込まれたドキュメントは埋め込まれませんが、コンテナ アプリケーションによってリンクとして操作される場合があります。 コンテナー ドキュメントに埋め込まれているドキュメントは、埋め込みと見なされます。

## <a name="coleserverdocisinplaceactive"></a><a name="isinplaceactive"></a>サービスサーバードック::イインプレイスアクティブ

メンバー関数`IsInPlaceActive`を呼び出して、アイテムが現在インプレース アクティブ状態かどうかを確認します。

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>戻り値

オブジェクトがインプレー`COleServerDoc`スでアクティブな場合は 0 以外。それ以外の場合は 0。

## <a name="coleserverdocnotifychanged"></a><a name="notifychanged"></a>を変更しました。

ドキュメントにリンクされているすべてのアイテムに、ドキュメントが変更されたことを通知します。

```cpp
void NotifyChanged();
```

### <a name="remarks"></a>解説

通常、ユーザーがサーバー ドキュメントのサイズなどのグローバル属性を変更した後に、この関数を呼び出します。 OLE アイテムが自動リンクを使用してドキュメントにリンクされている場合、そのアイテムは更新されて変更が反映されます。 Microsoft ファウンデーション クラス ライブラリで記述されたコンテナ アプリケーションでは`COleClientItem`[、OnChange](../../mfc/reference/coleclientitem-class.md#onchange)メンバー関数が呼び出されます。

> [!NOTE]
> この関数は OLE 1 との互換性のために用意されています。 新しいアプリケーションでは[、UpdateAllItems を使用する](#updateallitems)必要があります。

## <a name="coleserverdocnotifyclosed"></a><a name="notifyclosed"></a>を閉じました。

ドキュメントが閉じられたことをコンテナーに通知します。

```cpp
void NotifyClosed();
```

### <a name="remarks"></a>解説

ユーザーが [ファイル] メニューの [閉じる`NotifyClosed`] コマンド`COleServerDoc`を選択すると[、OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument)メンバー関数の実装によって呼び出されます。 Microsoft ファウンデーション クラス ライブラリで記述されたコンテナ アプリケーションでは`COleClientItem`[、OnChange](../../mfc/reference/coleclientitem-class.md#onchange)メンバー関数が呼び出されます。

## <a name="coleserverdocnotifyrename"></a><a name="notifyrename"></a>名前の変更を通知します。

ユーザーがサーバー ドキュメントの名前を変更した後に、この関数を呼び出します。

```cpp
void NotifyRename(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>パラメーター

*新しい名前を指定します。*<br/>
サーバー ドキュメントの新しい名前を指定する文字列へのポインター。通常、これは完全修飾パスです。

### <a name="remarks"></a>解説

ユーザーが [ファイル] メニューの [名前を付`NotifyRename`けて保存]`COleServerDoc`をクリックすると[、OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument)メンバー関数の実装によって呼び出されます。 この関数は、OLE システム DLL に通知し、次にコンテナーに通知します。 Microsoft ファウンデーション クラス ライブラリで記述されたコンテナ アプリケーションでは`COleClientItem`[、OnChange](../../mfc/reference/coleclientitem-class.md#onchange)メンバー関数が呼び出されます。

## <a name="coleserverdocnotifysaved"></a><a name="notifysaved"></a>を保存しました。

ユーザーがサーバー ドキュメントを保存した後に、この関数を呼び出します。

```cpp
void NotifySaved();
```

### <a name="remarks"></a>解説

ユーザーが [ファイル] メニューの [上書`NotifySaved`き保存] を`COleServerDoc`クリックすると、 [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument)の実装によって呼び出されます。 この関数は、OLE システム DLL に通知し、次にコンテナーに通知します。 Microsoft ファウンデーション クラス ライブラリで記述されたコンテナ アプリケーションでは`COleClientItem`[、OnChange](../../mfc/reference/coleclientitem-class.md#onchange)メンバー関数が呼び出されます。

## <a name="coleserverdoconclose"></a><a name="onclose"></a>を閉じる

コンテナーがサーバー ドキュメントの閉じを要求したときに、フレームワークによって呼び出されます。

```
virtual void OnClose(OLECLOSE dwCloseOption);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
列挙型の OLECLOSE からの値。 このパラメーターには、次のいずれかの値を指定できます。

- OLECLOSE_SAVEIFDIRTY ファイルが変更されている場合は、ファイルが保存されます。

- OLECLOSE_NOSAVE ファイルは保存されずに閉じられます。

- OLECLOSE_PROMPTSAVE ファイルが変更されている場合、保存を確認するメッセージが表示されます。

### <a name="remarks"></a>解説

既定の実装では`CDocument::OnCloseDocument`、 が呼び出されます。

詳細と追加の値については、Windows SDK[の「OLECLOSE」](/windows/win32/api/oleidl/ne-oleidl-oleclose)を参照してください。

## <a name="coleserverdocondeactivate"></a><a name="ondeactivate"></a>を無効にします。

現在埋め込み先編集が有効な埋め込みアイテムまたはリンク アイテムを非アクティブ化したときに、フレームワークによって呼び出されます。

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>解説

この関数は、コンテナー アプリケーションのユーザー インターフェイスを元の状態に復元し、インプレース アクティブ化用に作成されたメニューやその他のコントロールを破棄します。

この時点で、元に戻す状態情報は無条件に解放する必要があります。

詳細については、記事「[アクティベーション](../../mfc/activation-cpp.md)」を参照してください。

## <a name="coleserverdocondeactivateui"></a><a name="ondeactivateui"></a>サービスサーバードック::オンオフアクティブUI

ユーザーが、その場でアクティブ化された項目を非アクティブ化したときに呼び出されます。

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>パラメーター

*元に戻す*<br/>
編集の変更を元に戻すことができるかどうかを指定します。

### <a name="remarks"></a>解説

この関数は、コンテナー アプリケーションのユーザー インターフェイスを元の状態に戻し、インプレース アクティブ化用に作成されたメニューやその他のコントロールを非表示にします。

フレームワークは常に*bUndoable*を FALSE に設定します。 サーバーが元に戻す操作をサポートしていて、元に戻すことができる操作がある場合は *、bUndoable*を TRUE に設定して基本クラスの実装を呼び出します。

## <a name="coleserverdocondocwindowactivate"></a><a name="ondocwindowactivate"></a>をクリックします。

フレームワークは、この関数を呼び出して、ドキュメント ウィンドウをアクティブまたは非アクティブにしてインプレース編集を行います。

```
virtual void OnDocWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*bアクティブ化*<br/>
ドキュメント ウィンドウをアクティブにするか非アクティブにするかを指定します。

### <a name="remarks"></a>解説

既定の実装では、フレーム レベルのユーザー インターフェイス要素を必要に応じて削除または追加します。 アイテムを含むドキュメントがアクティブまたは非アクティブ化されたときに追加のアクションを実行する場合は、この関数をオーバーライドします。

詳細については、記事「[アクティベーション](../../mfc/activation-cpp.md)」を参照してください。

## <a name="coleserverdoconexecolecmd"></a><a name="onexecolecmd"></a>をクリックします。

フレームワークは、指定したコマンドを実行したり、コマンドのヘルプを表示するために、この関数を呼び出します。

```
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,
    DWORD nCmdID,
    DWORD nCmdExecOpt,
    VARIANTARG* pvarargIn,
    VARIANTARG* pvarargOut);
```

### <a name="parameters"></a>パラメーター

*グループ化*<br/>
コマンドのセットを識別する GUID へのポインター。 既定のコマンド グループを示すには、NULL を指定できます。

*をクリックします。*<br/>
実行するコマンドです。 によって識別されるグループに*含まれる*必要があります。

*を実行します。*<br/>
OLECMDEXECOPT 列挙体から、次の値の 1 つ以上のコマンドをオブジェクトが実行する方法。

OLECMDEXECOPT_DODEFAULT

OLECMDEXECOPT_PROMPTUSER

OLECMDEXECOPT_DONTPROMPTUSER

OLECMDEXECOPT_SHOWHELP

*プヴァルギン*<br/>
コマンドの入力引数を含む VARIANTARG へのポインター。 NULL にすることができます。

*プヴァールアウト*<br/>
コマンドから出力戻り値を受け取る VARIANTARG へのポインター。 NULL にすることができます。

### <a name="return-value"></a>戻り値

成功した場合はS_OKを返します。それ以外の場合は、次のいずれかのエラー コードを示します。

|値|説明|
|-----------|-----------------|
|E_UNEXPECTED|予期しないエラーが発生しました|
|E_FAIL|エラーが発生しました|
|E_NOTIMPL|MFC 自体がコマンドの変換とディスパッチを試みることを示します。|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup*は NULL 以外ですが、認識されたコマンド グループを指定しません|
|OLECMDERR_E_NOTSUPPORTED|*グループ* *pguidCmd グループ*で有効なコマンドとして認識されません。|
|OLECMDERR_DISABLED|*nCmdID*で識別されたコマンドは無効になっており、実行できません|
|OLECMDERR_NOHELP|呼び出し元は*nCmdID*で識別されたコマンドに関するヘルプを求めましたが、ヘルプがありません|
|OLECMDERR_CANCELED|ユーザーが実行をキャンセルしました|

### <a name="remarks"></a>解説

`COleCmdUI`を使用して、DocObject ユーザー インターフェイス コマンドのその他のプロパティを有効、更新、および設定できます。 コマンドが初期化された後、それらを で`OnExecOleCmd`実行できます。

フレームワークは、OLE ドキュメント コマンドを変換してディスパッチする前に、関数を呼び出します。 標準の OLE ドキュメント コマンドを処理するためにこの関数をオーバーライドする必要はありませんが、独自のカスタム コマンドを処理したり、パラメーターを受け取ったり結果を返したりするコマンドを処理する場合は、この関数にオーバーライドを指定する必要があります。

ほとんどのコマンドは引数や戻り値を受け取りません。 コマンドの大半の場合、呼び出し元は*pvarargIn*および*pvarargOut*のヌルを渡すことができます。 入力値を予期するコマンドの場合、呼び出し元は VARIANTARG 変数を宣言して初期化し、 *pvarargIn*内の変数にポインターを渡すことができます。 単一の値を必要とするコマンドの場合、引数は直接 VARIANTARG に格納され、関数に渡されます。 サポートされている型 (および SAFEARRAY など`IDispatch`) のいずれかを使用して、バリアント型の内部に複数の引数をパッケージ化する必要があります。

同様に、コマンドが引数を返す場合、呼び出し元は VARIANTARG を宣言し、VT_EMPTYに初期化し、そのアドレスを*pvarargOut*で渡します。 コマンドが単一の値を返す場合、オブジェクトはその値を*pvarargOut*に直接格納できます。 複数の出力値は、バリアント型 (VARIANT) に適した何らかの方法でパッケージ化する必要があります。

この関数の基本クラスの実装は、コマンド ターゲットに関連付けられているOLE_COMMAND_MAP構造体をウォークし、適切なハンドラーにコマンドをディスパッチしようとします。 基本クラスの実装は、引数または戻り値を受け取らないコマンドでのみ機能します。 引数や戻り値を受け入れるコマンドを処理する必要がある場合は、この関数をオーバーライドして *、pvarargIn*と*pvarargOut*パラメーターを自分で処理する必要があります。

## <a name="coleserverdoconframewindowactivate"></a><a name="onframewindowactivate"></a>をクリックします。

フレームワークは、コンテナー アプリケーションのフレーム ウィンドウがアクティブまたは非アクティブになったときに、この関数を呼び出します。

```
virtual void OnFrameWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*bアクティブ化*<br/>
フレーム ウィンドウをアクティブにするか非アクティブにするかを指定します。

### <a name="remarks"></a>解説

既定の実装では、フレーム ウィンドウが含まれる可能性のあるヘルプ モードがキャンセルされます。 フレーム ウィンドウがアクティブまたは非アクティブになったときに特別な処理を実行する場合は、この関数をオーバーライドします。

詳細については、記事「[アクティベーション](../../mfc/activation-cpp.md)」を参照してください。

## <a name="coleserverdocongetembeddeditem"></a><a name="ongetembeddeditem"></a>をクリックします。

コンテナー アプリケーションがサーバー アプリケーションを呼び出して埋め込みアイテムを作成または編集するときに、フレームワークによって呼び出されます。

```
virtual COleServerItem* OnGetEmbeddedItem() = 0;
```

### <a name="return-value"></a>戻り値

ドキュメント全体を表す項目へのポインター。操作が失敗した場合は NULL。

### <a name="remarks"></a>解説

既定の実装はありません。 ドキュメント全体を表す項目を返す場合は、この関数をオーバーライドする必要があります。 この戻り値は、派生クラスの`COleServerItem`オブジェクトである必要があります。

## <a name="coleserverdoconreactivateandundo"></a><a name="onreactivateandundo"></a>コレクサーバードック::オン再アクティブ化と元に戻す

フレームワークは、ユーザーが、その場所でアクティブ化され、変更され、その後非アクティブ化された項目に対して行われた変更を元に戻すことを選択したときに、この関数を呼び出します。

```
virtual BOOL OnReactivateAndUndo();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

既定の実装では、失敗を示すために FALSE を返す以外は何も行いません。

アプリケーションが元に戻す機能をサポートしている場合は、この関数をオーバーライドします。 通常は、元に戻す操作を実行し、 を`ActivateInPlace`呼び出して項目をアクティブにします。 コンテナー アプリケーションが Microsoft Foundation クラス ライブラリで記述`COleClientItem::ReactivateAndUndo`されている場合、呼び出すとこの関数が呼び出されます。

## <a name="coleserverdoconresizeborder"></a><a name="onresizeborder"></a>をクリックします。

フレームワークは、コンテナー アプリケーションのフレーム ウィンドウのサイズが変更されたときに、この関数を呼び出します。

```
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,
    LPOLEINPLACEUIWINDOW lpUIWindow,
    BOOL bFrame);
```

### <a name="parameters"></a>パラメーター

*国境を越える*<br/>
境界の`RECT`座標を`CRect`指定する構造体またはオブジェクトへのポインター。

*ウィンドウ*<br/>
現在の埋め込み`IOleInPlaceUIWindow`編集セッションを所有するクラスのオブジェクトへのポインター。

*bフレーム*<br/>
true を指定すると *、lpUIWindow が*コンテナー アプリケーションの最上位のフレーム ウィンドウを指し、*コンテナー*アプリケーションのドキュメント レベルのフレーム ウィンドウをポイントする場合は FALSE。

### <a name="remarks"></a>解説

この関数は、新しいウィンドウ サイズに合わせて、ツールバーやその他のユーザー インターフェイス要素のサイズを変更し、調整します。

詳細については、Windows SDK[の「IOleInPlaceUI ウィンドウ](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceuiwindow)」を参照してください。

これは、高度なオーバーライド可能です。

## <a name="coleserverdoconsethostnames"></a><a name="onsethostnames"></a>ホスト名を設定します。

コンテナーがこのドキュメントのホスト名を設定または変更するときに、フレームワークによって呼び出されます。

```
virtual void OnSetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>パラメーター

*ホスト*<br/>
コンテナー アプリケーションの名前を指定する文字列へのポインター。

*をクリックします。*<br/>
ドキュメントのコンテナー名を指定する文字列へのポインター。

### <a name="remarks"></a>解説

既定の実装では、このドキュメントを参照するすべてのビューのドキュメント タイトルが変更されます。

アプリケーションが別のメカニズムを使用してタイトルを設定する場合は、この関数をオーバーライドします。

## <a name="coleserverdoconsetitemrects"></a><a name="onsetitemrects"></a>をクリックします。

フレームワークは、コンテナー アプリケーションのフレーム ウィンドウ内で埋め込み位置編集フレーム ウィンドウを配置するために、この関数を呼び出します。

```
virtual void OnSetItemRects(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>パラメーター

*lpPosRect*<br/>
コンテナー アプリケーション`RECT`の`CRect`クライアント領域に対するインプレース フレーム ウィンドウの相対位置を指定する構造体またはオブジェクトへのポインター。

*lp クリップレック*<br/>
コンテナー アプリケーション`RECT`の`CRect`クライアント領域に対する埋め込みフレーム ウィンドウのクリッピング四角形を指定する構造体またはオブジェクトへのポインター。

### <a name="remarks"></a>解説

必要に応じてビューのズーム倍率を更新するには、この関数をオーバーライドします。

この関数は通常、`RequestPositionChange`呼び出しに応答して呼び出されますが、コンテナーからいつでも呼び出して、インプレース項目の位置変更を要求できます。

## <a name="coleserverdoconshowcontrolbars"></a><a name="onshowcontrolbars"></a>コントロールバーを表示します。

フレームワークはこの関数を呼び出して *、pFrameWnd*で識別されるフレーム ウィンドウに関連付けられているサーバー アプリケーションのコントロール バーを表示または非表示にします。

```
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
コントロール バーを非表示または表示するフレーム ウィンドウへのポインター。

*bショー*<br/>
コントロール バーを表示するか非表示にするかを指定します。

### <a name="remarks"></a>解説

既定の実装では、そのフレーム ウィンドウが所有するすべてのコントロール バーを列挙し、非表示または表示します。

## <a name="coleserverdoconshowdocument"></a><a name="onshowdocument"></a>ドキュメントを表示します。

フレームワークは、サーバー`OnShowDocument`ドキュメントを非表示にしたり表示したりする必要があるときに関数を呼び出します。

```
virtual void OnShowDocument(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
ドキュメントへのユーザー インターフェイスを表示するか非表示にするかを指定します。

### <a name="remarks"></a>解説

*bShow*が TRUE の場合、既定の実装は、必要に応じてサーバー アプリケーションをアクティブにし、コンテナー アプリケーションがスクロールして項目が表示されるようにします。 *bShow*が FALSE の場合、既定の実装では、 への`OnDeactivate`呼び出しによって項目が非アクティブ化され、最初のフレーム ウィンドウを除いて、ドキュメント用に作成されたすべてのフレーム ウィンドウが破棄または非表示になります。 表示可能なドキュメントが残っていない場合、既定の実装ではサーバー アプリケーションが非表示になります。

## <a name="coleserverdoconupdatedocument"></a><a name="onupdatedocument"></a>ドキュメントを更新します。

複合ドキュメント内の埋め込みアイテムであるドキュメントを保存するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnUpdateDocument();
```

### <a name="return-value"></a>戻り値

ドキュメントが正常に更新された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

既定の実装は[、メンバー](#notifysaved)関数を呼び出し、ドキュメント[を](#saveembedding)クリーンとしてマークします。 埋め込みアイテムを更新するときに特別な処理を実行する場合は、この関数をオーバーライドします。

## <a name="coleserverdocrequestpositionchange"></a><a name="requestpositionchange"></a>を変更します。

コンテナー アプリケーションで項目の位置を変更するには、このメンバー関数を呼び出します。

```cpp
void RequestPositionChange(LPCRECT lpPosRect);
```

### <a name="parameters"></a>パラメーター

*lpPosRect*<br/>
アイテムの`RECT`新しい位置を`CRect`含む構造体またはオブジェクトへのポインター。

### <a name="remarks"></a>解説

この関数は、通常、インプレース`UpdateAllItems`アクティブアイテムのデータが変更されたときに 、 と共に ) 呼び出されます。 この呼び出しの後、コンテナーは を呼び出`OnSetItemRects`して変更を実行する場合と実行しない場合があります。 結果の位置は、要求された位置と異なる場合があります。

## <a name="coleserverdocsaveembedding"></a><a name="saveembedding"></a>を埋め込む

埋め込みオブジェクトを保存するようにコンテナー アプリケーションに指示します。

```cpp
void SaveEmbedding();
```

### <a name="remarks"></a>解説

この関数は、 から`OnUpdateDocument`自動的に呼び出されます。 この関数は、ディスク上で項目が更新されるため、通常は特定のユーザー操作の結果としてのみ呼び出されることに注意してください。

## <a name="coleserverdocscrollcontainerby"></a><a name="scrollcontainerby"></a>をクリックします。

メンバー関数`ScrollContainerBy`を呼び出して、コンテナー ドキュメントを、 で`sizeScroll`示されるピクセル単位でスクロールします。

```
BOOL ScrollContainerBy(CSize sizeScroll);
```

### <a name="parameters"></a>パラメーター

*サイズスクロール*<br/>
コンテナー ドキュメントがスクロールする距離を示します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

正の値は、スクロールダウンと右を示します。負の値は、左にスクロールすることを示します。

## <a name="coleserverdocupdateallitems"></a><a name="updateallitems"></a>をクリックします。

ドキュメントにリンクされているすべてのアイテムに、ドキュメントが変更されたことを通知します。

```cpp
void UpdateAllItems(
    COleServerItem* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL,
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ドキュメントを変更したアイテムへのポインター。

*lヒント*<br/>
変更に関する情報が含まれます。

*ヒント*<br/>
変更に関する情報を格納しているオブジェクトへのポインター。

*アスペクト*<br/>
アイテムの描画方法を決定します。 これは DVASPECT 列挙体の値です。 このパラメーターには、次のいずれかの値を指定できます。

- アイテムDVASPECT_CONTENT、コンテナ内の埋め込みオブジェクトとして表示できるように表示されます。

- DVASPECT_THUMBNAILアイテムは、閲覧ツールで表示できるように「サムネイル」表現でレンダリングされます。

- DVASPECT_ICON項目はアイコンで表されます。

- DVASPECT_DOCPRINTアイテムは、[ファイル] メニューの [印刷] コマンドを使用して印刷されたかのように表示されます。

### <a name="remarks"></a>解説

通常、ユーザーがサーバー ドキュメントを変更した後に、この関数を呼び出します。 OLE アイテムが自動リンクを使用してドキュメントにリンクされている場合、そのアイテムは更新されて変更が反映されます。 Microsoft ファウンデーション クラス ライブラリで記述されたコンテナ アプリケーションでは`COleClientItem`[、OnChange](../../mfc/reference/coleclientitem-class.md#onchange)メンバー関数が呼び出されます。

この関数は、`OnUpdate`送信アイテムを除くドキュメントの各アイテムのメンバー関数を呼び出し *、pHint*、 *lHint*、*および nDrawAspect*を渡します。 これらのパラメーターを使用して、ドキュメントに加えられた変更に関する情報を項目に渡します。 *lHint*を使用して情報をエンコードするか、変更`CObject`に関する情報を格納し、そのクラスのオブジェクトを*pHint*を使用して渡す -derived クラスを定義できます。 派生クラス`OnUpdate`のメンバー関数を`COleServerItem`オーバーライドして、各項目の表示が変更されたかどうかに応じて各項目の更新を最適化します。

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[COleLinkingDoc クラス](../../mfc/reference/colelinkingdoc-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDocument クラス](../../mfc/reference/coledocument-class.md)<br/>
[COleLinkingDoc クラス](../../mfc/reference/colelinkingdoc-class.md)<br/>
[COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)
