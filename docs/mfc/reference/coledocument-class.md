---
title: COleDocument クラス
ms.date: 11/04/2016
f1_keywords:
- COleDocument
- AFXOLE/COleDocument
- AFXOLE/COleDocument::COleDocument
- AFXOLE/COleDocument::AddItem
- AFXOLE/COleDocument::ApplyPrintDevice
- AFXOLE/COleDocument::EnableCompoundFile
- AFXOLE/COleDocument::GetInPlaceActiveItem
- AFXOLE/COleDocument::GetNextClientItem
- AFXOLE/COleDocument::GetNextItem
- AFXOLE/COleDocument::GetNextServerItem
- AFXOLE/COleDocument::GetPrimarySelectedItem
- AFXOLE/COleDocument::GetStartPosition
- AFXOLE/COleDocument::HasBlankItems
- AFXOLE/COleDocument::OnShowViews
- AFXOLE/COleDocument::RemoveItem
- AFXOLE/COleDocument::UpdateModifiedFlag
- AFXOLE/COleDocument::OnEditChangeIcon
- AFXOLE/COleDocument::OnEditConvert
- AFXOLE/COleDocument::OnEditLinks
- AFXOLE/COleDocument::OnFileSendMail
- AFXOLE/COleDocument::OnUpdateEditChangeIcon
- AFXOLE/COleDocument::OnUpdateEditLinksMenu
- AFXOLE/COleDocument::OnUpdateObjectVerbMenu
- AFXOLE/COleDocument::OnUpdatePasteLinkMenu
- AFXOLE/COleDocument::OnUpdatePasteMenu
helpviewer_keywords:
- COleDocument [MFC], COleDocument
- COleDocument [MFC], AddItem
- COleDocument [MFC], ApplyPrintDevice
- COleDocument [MFC], EnableCompoundFile
- COleDocument [MFC], GetInPlaceActiveItem
- COleDocument [MFC], GetNextClientItem
- COleDocument [MFC], GetNextItem
- COleDocument [MFC], GetNextServerItem
- COleDocument [MFC], GetPrimarySelectedItem
- COleDocument [MFC], GetStartPosition
- COleDocument [MFC], HasBlankItems
- COleDocument [MFC], OnShowViews
- COleDocument [MFC], RemoveItem
- COleDocument [MFC], UpdateModifiedFlag
- COleDocument [MFC], OnEditChangeIcon
- COleDocument [MFC], OnEditConvert
- COleDocument [MFC], OnEditLinks
- COleDocument [MFC], OnFileSendMail
- COleDocument [MFC], OnUpdateEditChangeIcon
- COleDocument [MFC], OnUpdateEditLinksMenu
- COleDocument [MFC], OnUpdateObjectVerbMenu
- COleDocument [MFC], OnUpdatePasteLinkMenu
- COleDocument [MFC], OnUpdatePasteMenu
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
ms.openlocfilehash: 2f28178240f7d17e124970d91ec7eb338ef110e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452153"
---
# <a name="coledocument-class"></a>COleDocument クラス

ビジュアル編集をサポートする OLE ドキュメントの基底クラスです。

## <a name="syntax"></a>構文

```
class COleDocument : public CDocument
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleDocument::COleDocument](#coledocument)|`COleDocument` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleDocument::AddItem](#additem)|ドキュメントによって管理されるアイテムのリストに項目を追加します。|
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|文書のすべてのクライアント アイテムの印刷ターゲット デバイスを設定します。|
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|OLE 構造化ストレージ ファイルの形式を使用して格納されるドキュメントをによりします。|
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|現在の実行中である OLE 項目を返します。|
|[COleDocument::GetNextClientItem](#getnextclientitem)|反復処理するためには、クライアントの次の項目を取得します。|
|[COleDocument::GetNextItem](#getnextitem)|反復処理するためには、ドキュメントの次の項目を取得します。|
|[COleDocument::GetNextServerItem](#getnextserveritem)|反復処理するためには、サーバーの次の項目を取得します。|
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|文書内のプライマリの選択されている OLE 項目を返します。|
|[COleDocument::GetStartPosition](#getstartposition)|初期のイテレーションを開始する位置を取得します。|
|[COleDocument::HasBlankItems](#hasblankitems)|文書内の空の項目を確認します。|
|[COleDocument::OnShowViews](#onshowviews)|表示または非表示のドキュメントになると呼び出されます。|
|[COleDocument::RemoveItem](#removeitem)|ドキュメントによって管理されるアイテムの一覧から項目を削除します。|
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|含まれている OLE 項目のいずれかが変更された場合の変更としては、ドキュメントをマークします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|アイコンの変更 メニュー コマンドのイベントを処理します。|
|[COleDocument::OnEditConvert](#oneditconvert)|1 つの型から別の埋め込みまたはリンクされたオブジェクトの変換を処理します。|
|[COleDocument::OnEditLinks](#oneditlinks)|[編集] メニューのリンクのコマンドのイベントを処理します。|
|[COleDocument::OnFileSendMail](#onfilesendmail)|ドキュメントを添付して、メール メッセージを送信します。|
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|アイコンの編集/変更 メニュー オプションのコマンドの UI を更新するためにフレームワークによって呼び出されます。|
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|コマンド UI/リンクの編集 メニュー オプションを更新するためにフレームワークによって呼び出されます。|
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|編集のためのコマンドは、UI を更新するためにフレームワークによって呼び出される/ *ObjectName*メニュー オプションとからアクセスされる動詞サブメニュー/ *ObjectName*します。|
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|貼り付けメニュー オプションのコマンドの UI を更新するためにフレームワークによって呼び出されます。|
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|貼り付けメニュー オプションのコマンドの UI を更新するためにフレームワークによって呼び出されます。|

## <a name="remarks"></a>Remarks

`COleDocument` 派生`CDocument`、OLE アプリケーション、Microsoft Foundation Class ライブラリによって提供されるドキュメント/ビュー アーキテクチャを使用することができます。

`COleDocument` コレクションとしてドキュメントを扱う[CDocItem](../../mfc/reference/cdocitem-class.md) OLE 項目を処理するオブジェクト。 コンテナーとサーバーの両方のアプリケーションでは、自分のドキュメントは、OLE アイテムを含めることができる必要がありますので、このようなアーキテクチャが必要です。 [COleServerItem](../../mfc/reference/coleserveritem-class.md)と[COleClientItem](../../mfc/reference/coleclientitem-class.md)両方から派生したクラス、`CDocItem`アプリケーションと OLE アイテム間の相互作用を管理します。

単純なコンテナー アプリケーションを作成する場合からドキュメント クラスを派生`COleDocument`します。 ドキュメントが含まれている埋め込みアイテムへのリンクをサポートするコンテナー アプリケーションを作成する場合からドキュメント クラスを派生[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)します。 作成する場合、サーバー アプリケーションまたは組み合わせのコンテナー/サーバーからドキュメント クラスを派生[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)します。 `COleLinkingDoc` `COleServerDoc`から派生`COleDocument`これらのクラスで利用できるすべてのサービスを継承するので、`COleDocument`と`CDocument`します。

使用する`COleDocument`、そこから派生クラスを作成およびアプリケーションの非 OLE データだけでなく埋め込みまたはリンクされた項目を管理する機能を追加します。 定義する場合`CDocItem`-アプリケーションのネイティブ データを格納するクラスの派生によって定義された既定の実装を使用する`COleDocument`OLE と非 OLE データの両方を格納します。 OLE 項目から個別に非 OLE データを格納するための独自のデータ構造を設計することもできます。 詳細については、記事を参照してください[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md)..

`CDocument` サポート メール サポート (MAPI) が存在する場合にメールを使ってドキュメントを送信します。 `COleDocument` 更新が[OnFileSendMail](#onfilesendmail)複合ドキュメントを正しく処理します。 詳細については、記事を参照してください[MAPI](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)..

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

##  <a name="additem"></a>  COleDocument::AddItem

ドキュメントに項目を追加するには、この関数を呼び出します。

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
追加されるドキュメント項目へのポインター。

### <a name="remarks"></a>Remarks

呼び出された場合、この関数を明示的に呼び出す必要はありません、`COleClientItem`または`COleServerItem`ドキュメントへのポインターを受け取るコンス トラクター。

##  <a name="applyprintdevice"></a>  COleDocument::ApplyPrintDevice

埋め込まれたすべての出力先デバイスを変更するには、この関数を呼び出す[COleClientItem](../../mfc/reference/coleclientitem-class.md)アプリケーションのコンテナー ドキュメント内の項目。

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>パラメーター

*ptd*<br/>
ポインターを`DVTARGETDEVICE`データ構造は、新しい印刷対象デバイスに関する情報が含まれます。 NULL にすることができます。

*ppd*<br/>
ポインターを`PRINTDLG`データ構造は、新しい印刷対象デバイスに関する情報が含まれます。 NULL にすることができます。

### <a name="return-value"></a>戻り値

関数が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数は、すべての項目の出力先のデバイスを更新が、それらの項目のプレゼンテーションのキャッシュは更新されません。 アイテムのプレゼンテーションのキャッシュを更新するには、呼び出す[COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)します。

この関数の引数には、OLE をターゲット デバイスを識別するために使用する情報が含まれています。 [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda)構造体には、一般的な印刷 ダイアログ ボックスを初期化するために Windows を使用する情報が含まれます。 ユーザーがダイアログ ボックスを閉じた後、Windows はこの構造体で、ユーザーの選択に関する情報を返します。 `m_pd`のメンバー、 [CPrintDialog](../../mfc/reference/cprintdialog-class.md)オブジェクトが、`PRINTDLG`構造体。

詳細については、次を参照してください。、 [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) Windows SDK の構造体。

詳細については、次を参照してください。、 [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) Windows SDK の構造体。

##  <a name="coledocument"></a>  COleDocument::COleDocument

`COleDocument` オブジェクトを構築します。

```
COleDocument();
```

##  <a name="enablecompoundfile"></a>  COleDocument::EnableCompoundFile

複合ファイル形式を使用してドキュメントを格納する場合は、この関数を呼び出します。

```
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
複合ファイルのサポートを有効または無効になっているかどうかを指定します。

### <a name="remarks"></a>Remarks

これは構造化ストレージとも呼ばれます。 通常のコンス トラクターからこの関数を呼び出す、 `COleDocument`-クラスを派生します。 複合ドキュメントの詳細については、記事を参照してください[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md)..

このメンバー関数を呼び出さない場合は、構造化されていない (「フラット」) ファイル形式でドキュメントに格納されています。

複合ファイルのサポートを有効になっているまたはドキュメントを無効にすると、ドキュメントの有効期間中に、設定を変更できません必要があります。

##  <a name="getinplaceactiveitem"></a>  COleDocument::GetInPlaceActiveItem

項目の OLE を取得するには、この関数の呼び出しは、現在の場所で識別されるビューを含むフレーム ウィンドウ内でアクティブ化されて*我が物*します。

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
コンテナーのドキュメントを表示するウィンドウへのポインター。

### <a name="return-value"></a>戻り値

1 つ、インプレース アクティブ OLE アイテムへのポインター項目がない OLE 現在「インプレース アクティブ」状態の場合は NULL します。

##  <a name="getnextclientitem"></a>  COleDocument::GetNextClientItem

クライアント アイテム、ドキュメント内の各にアクセスするには、繰り返しには、この関数を呼び出します。

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しで値セットの位置への参照を`GetNextClientItem`; によって、初期値が返される、`GetStartPosition`メンバー関数。

### <a name="return-value"></a>戻り値

次のクライアントへのポインターは、ドキュメント内の項目または項目をそれ以上クライアントがある場合は NULL。

### <a name="remarks"></a>Remarks

値は、各呼び出しの後に*pos*可能性がありますまたはクライアント アイテムとは限りませんが、ドキュメントの次の項目に設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

##  <a name="getnextitem"></a>  COleDocument::GetNextItem

各ドキュメント内のアイテムにアクセスするには、繰り返しには、この関数を呼び出します。

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しで値セットの位置への参照を`GetNextItem`; によって、初期値が返される、`GetStartPosition`メンバー関数。

### <a name="return-value"></a>戻り値

指定した位置にあるドキュメント項目へのポインター。

### <a name="remarks"></a>Remarks

値は、各呼び出しの後に*pos*ドキュメントの次の項目の位置の値に設定されます。 取得した要素の新しい値は、ドキュメントの最後の要素が場合*pos*は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

##  <a name="getnextserveritem"></a>  COleDocument::GetNextServerItem

各ドキュメント内のサーバー項目にアクセスするには、繰り返しには、この関数を呼び出します。

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しで値セットの位置への参照を`GetNextServerItem`; によって、初期値が返される、`GetStartPosition`メンバー関数。

### <a name="return-value"></a>戻り値

次のサーバーへのポインターは、ドキュメント内の項目またはこれ以上のサーバー項目がある場合は NULL です。

### <a name="remarks"></a>Remarks

値は、各呼び出しの後に*pos*可能性がありますまたはサーバーのアイテムとは限りませんが、ドキュメントの次の項目に設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

##  <a name="getprimaryselecteditem"></a>  COleDocument::GetPrimarySelectedItem

指定したビューで現在選択されている OLE 項目を取得するためにフレームワークによって呼び出されます。

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>パラメーター

*pView*<br/>
ドキュメントを表示するアクティブなビューのオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

1 つ、選択した OLE アイテムへのポインターOLE 項目が選択されていないかが選択されている数より多い場合は NULL です。

### <a name="remarks"></a>Remarks

既定の実装では、1 つ選択したアイテムのアイテムに含まれている OLE の一覧を検索し、ポインターを返します。 選択した項目が存在しない場合、または選択した 1 つ以上の項目がある場合は、関数は NULL を返します。 オーバーライドする必要があります、`CView::IsSelected`させるには、この関数のビュー クラスでメンバー関数。 含まれている OLE 項目を格納する独自のメソッドがある場合は、この関数をオーバーライドします。

##  <a name="getstartposition"></a>  COleDocument::GetStartPosition

ドキュメント内の最初の項目の位置を取得するには、この関数を呼び出します。

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>戻り値

ドキュメントの項目を反復処理を開始するために使用する位置の値ドキュメントに項目があるない場合は NULL です。

### <a name="remarks"></a>Remarks

返される値を渡す`GetNextItem`、 `GetNextClientItem`、または`GetNextServerItem`します。

##  <a name="hasblankitems"></a>  COleDocument::HasBlankItems

この関数では、空白項目がドキュメントに含まれるかどうかを確認します。

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>戻り値

ドキュメントには、空の項目が含まれている場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

空のアイテムは、1 つの四角形が空です。

##  <a name="oneditchangeicon"></a>  COleDocument::OnEditChangeIcon

OLE の [アイコンの変更] ダイアログ ボックスを表示し、ダイアログ ボックスで、ユーザーが選択アイコンへの現在選択されている OLE 項目を表すアイコンを変更します。

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>Remarks

`OnEditChangeIcon` 作成し、起動、`COleChangeIconDialog`アイコンの変更 ダイアログ ボックス。

##  <a name="oneditconvert"></a>  COleDocument::OnEditConvert

OLE 変換 ダイアログ ボックスが表示されますおよびに変換またはに従ってユーザーの選択 ダイアログ ボックスで現在選択されている OLE 項目をアクティブにします。

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>Remarks

`OnEditConvert` 作成し、起動、`COleConvertDialog`変換 ダイアログ ボックス。

変換の例では、ワードパッドのドキュメントに、Microsoft Word のドキュメントを変換です。

##  <a name="oneditlinks"></a>  COleDocument::OnEditLinks

[リンク] ダイアログ ボックスが表示されます。

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>Remarks

`OnEditLinks` 作成し、起動、`COleLinksDialog`ユーザーがリンクされているオブジェクトを変更できるリンク ダイアログ ボックス。

##  <a name="onfilesendmail"></a>  COleDocument::OnFileSendMail

メッセージを送信常駐メール ホスト経由で (ある場合)、ドキュメント、添付ファイルとして。

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>Remarks

`OnFileSendMail` 呼び出し`OnSaveDocument`(保存) 無題と変更されたドキュメントは、電子メールで送信し、一時ファイルをシリアル化します。 ドキュメントが変更されていない場合、一時ファイルは必要ありません。元に送信されます。 `OnFileSendMail` MAPI32 を読み込みます。既に読み込まれていない場合は、DLL です。

実装とは異なり`OnFileSendMail`の`CDocument`、この関数は、複合ファイルを正しく処理します。

詳細については、次を参照してください、 [MAPI トピック](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)記事..

##  <a name="onshowviews"></a>  COleDocument::OnShowViews

フレームワークは、状態の変更、ドキュメントの表示後にこの関数を呼び出します。

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>パラメーター

*bVisible*<br/>
ドキュメントが表示または非表示になるかどうかを示します。

### <a name="remarks"></a>Remarks

この関数の既定のバージョンでは、何も行われません。 アプリケーションは、ドキュメントの可視性が変更されたときに、特別な処理を実行する必要がありますがある場合は、これをオーバーライドします。

##  <a name="onupdateeditchangeicon"></a>  COleDocument::OnUpdateEditChangeIcon

編集 メニューのアイコンの変更 コマンドを更新するためにフレームワークによって呼び出されます。

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*対応付けられました。*<br/>
ポインター、 `CCmdUI` update コマンドが生成されるメニューを表す構造体です。 更新ハンドラーは、`Enable`のメンバー関数、`CCmdUI`を通じて構造体*対応付けられた*ユーザー インターフェイスを更新します。

### <a name="remarks"></a>Remarks

`OnUpdateEditChangeIcon` 有効なアイコンが、ドキュメントに存在するかどうかに応じて、コマンドのユーザー インターフェイスを更新します。 動作を変更するには、この関数をオーバーライドします。

##  <a name="onupdateeditlinksmenu"></a>  COleDocument::OnUpdateEditLinksMenu

[編集] メニューのリンクのコマンドを更新するためにフレームワークによって呼び出されます。

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*対応付けられました。*<br/>
ポインター、 `CCmdUI` update コマンドが生成されるメニューを表す構造体です。 更新ハンドラーは、`Enable`のメンバー関数、`CCmdUI`を通じて構造体*対応付けられた*ユーザー インターフェイスを更新します。

### <a name="remarks"></a>Remarks

以降で、ドキュメントの最初の OLE 項目`OnUpdateEditLinksMenu`各項目にアクセスする、項目は、リンクし、リンクである場合は、リンクの設定 を有効かどうかをテストします。 動作を変更するには、この関数をオーバーライドします。

##  <a name="onupdateobjectverbmenu"></a>  COleDocument::OnUpdateObjectVerbMenu

更新するためにフレームワークによって呼び出されます、 *ObjectName*コマンドを編集 メニューからアクセスされる動詞 サブメニューで、 *ObjectName*コマンド、場所*ObjectName*の名前を指定しますOLE オブジェクトは、ドキュメントに埋め込まれます。

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*対応付けられました。*<br/>
ポインター、 `CCmdUI` update コマンドが生成されるメニューを表す構造体です。 更新ハンドラーは、`Enable`のメンバー関数、`CCmdUI`を通じて構造体*対応付けられた*ユーザー インターフェイスを更新します。

### <a name="remarks"></a>Remarks

`OnUpdateObjectVerbMenu` 更新プログラム、 *ObjectName*ドキュメントで、有効なオブジェクトが存在するかどうかに応じて、コマンドのユーザー インターフェイス。 オブジェクトが存在する場合、 *ObjectName* [編集] メニューのコマンドを有効にします。 このメニュー コマンドを選択すると、動詞のサブメニューが表示されます。 動詞のサブメニューには、編集やプロパティなど、オブジェクトで使用できるすべての動詞コマンドが含まれています。 動作を変更するには、この関数をオーバーライドします。

##  <a name="onupdatepastelinkmenu"></a>  COleDocument::OnUpdatePasteLinkMenu

リンクされている OLE 項目をクリップボードから貼り付けができるかどうかを判断するためにフレームワークによって呼び出されます。

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*対応付けられました。*<br/>
ポインター、 `CCmdUI` update コマンドが生成されるメニューを表す構造体です。 更新ハンドラーは、`Enable`のメンバー関数、`CCmdUI`を通じて構造体*対応付けられた*ユーザー インターフェイスを更新します。

### <a name="remarks"></a>Remarks

貼り付けメニュー コマンドが有効になっているまたは項目が、ドキュメントに貼り付けられるかどうかによって決まります。

##  <a name="onupdatepastemenu"></a>  COleDocument::OnUpdatePasteMenu

埋め込み OLE アイテムは、クリップボードから貼り付けができるかどうかを判断するためにフレームワークによって呼び出されます。

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*対応付けられました。*<br/>
ポインター、 `CCmdUI` update コマンドが生成されるメニューを表す構造体です。 更新ハンドラーは、`Enable`のメンバー関数、`CCmdUI`を通じて構造体*対応付けられた*ユーザー インターフェイスを更新します。

### <a name="remarks"></a>Remarks

[貼り付け] コマンドとボタンが有効になっているまたは項目が、ドキュメントに貼り付けられるかどうかによって決まります。

##  <a name="removeitem"></a>  COleDocument::RemoveItem

ドキュメントから項目を削除するには、この関数を呼び出します。

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
削除するドキュメント項目へのポインター。

### <a name="remarks"></a>Remarks

通常必要はありません。 明示的にこの関数を呼び出すデストラクターを呼び出して`COleClientItem`と`COleServerItem`します。

##  <a name="updatemodifiedflag"></a>  COleDocument::UpdateModifiedFlag

含まれている OLE 項目のいずれかが変更された場合に変更されたドキュメントをマークするには、この関数を呼び出します。

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>Remarks

これにより、ドキュメント内のネイティブのデータが変更されていない場合でも、閉じる前に、ドキュメントを保存するようにユーザーに、フレームワークができます。

## <a name="see-also"></a>関連項目

[MFC サンプル コンテナー](../../visual-cpp-samples.md)<br/>
[MFC サンプル MFCBIND](../../visual-cpp-samples.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)

