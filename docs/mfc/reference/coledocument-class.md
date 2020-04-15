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
ms.openlocfilehash: 51169de521997890190aab52e4afd02ed383af3b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375032"
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
|[ドキュメント::ドキュメント](#coledocument)|`COleDocument` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ドキュメント::アイテムの追加](#additem)|ドキュメントによって保持されている項目の一覧に項目を追加します。|
|[をクリックします。](#applyprintdevice)|ドキュメント内のすべてのクライアント項目の印刷対象デバイスを設定します。|
|[コンパウンドファイルを有効にする](#enablecompoundfile)|OLE 構造化ストレージ ファイル形式を使用して文書を保存します。|
|[をクリックします。](#getinplaceactiveitem)|現在作業中の OLE アイテムを返します。|
|[次のクライアントアイテムを取得します。](#getnextclientitem)|反復処理の次のクライアント項目を取得します。|
|[次のアイテムを取得します。](#getnextitem)|反復処理の次のドキュメント アイテムを取得します。|
|[次のサーバーアイテムを取得します。](#getnextserveritem)|反復処理の次のサーバー項目を取得します。|
|[を選択しました。](#getprimaryselecteditem)|ドキュメント内で選択されている主な OLE アイテムを返します。|
|[ドキュメント::取得開始位置](#getstartposition)|反復を開始する最初の位置を取得します。|
|[ドキュメント::を空白にします](#hasblankitems)|ドキュメント内の空白の項目をチェックします。|
|[ドキュメント::オンショービュー](#onshowviews)|ドキュメントが表示または非表示になったときに呼び出されます。|
|[アイテムを削除します。](#removeitem)|ドキュメントによって保持されている項目の一覧から項目を削除します。|
|[ドキュメント::更新変更フラグ](#updatemodifiedflag)|含まれている OLE アイテムのいずれかが変更されている場合、ドキュメントを変更済みとしてマークします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ドキュメント::オンエディットチェンジアイコン](#oneditchangeicon)|[アイコンの変更] メニュー コマンドのイベントを処理します。|
|[ドキュメント::オンエディットコンバート](#oneditconvert)|埋め込みオブジェクトまたはリンク オブジェクトの型間の変換を処理します。|
|[ドキュメント::オンエディットリンク](#oneditlinks)|[編集] メニューの [リンク] コマンドでイベントを処理します。|
|[ファイル送信メール](#onfilesendmail)|ドキュメントが添付されたメール メッセージを送信します。|
|[ドキュメント::オンアップデートエディットチェンジアイコン](#onupdateeditchangeicon)|[アイコンの編集/変更] メニュー オプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|
|[次の項目をクリックします。](#onupdateeditlinksmenu)|編集/リンク メニュー オプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|
|[をクリックします。](#onupdateobjectverbmenu)|フレームワークによって呼び出され、編集/*オブジェクト名*メニュー オプションのコマンド UI と、編集/*オブジェクト名*からアクセスされる動詞サブメニューを更新します。|
|[ドキュメント::オンアップデートペーストリンクメニュー](#onupdatepastelinkmenu)|[形式を選択して貼り付け] メニュー オプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|
|[ドキュメント::オンアップデートペーストメニュー](#onupdatepastemenu)|[貼り付け] メニュー オプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

`COleDocument`は`CDocument`から派生し、OLE アプリケーションは、Microsoft Foundation クラス ライブラリが提供するドキュメント/ビュー アーキテクチャを使用できます。

`COleDocument`は、OLE アイテムを処理する[CDocItem](../../mfc/reference/cdocitem-class.md)オブジェクトのコレクションとしてドキュメントを処理します。 コンテナー アプリケーションとサーバー アプリケーションの両方で、OLE アイテムを含めるドキュメントが必要なため、このようなアーキテクチャが必要です。 から派生`CDocItem`した[クラス](../../mfc/reference/coleserveritem-class.md)と[COleClientItem](../../mfc/reference/coleclientitem-class.md)クラスは、アプリケーションと OLE アイテムの間の相互作用を管理します。

単純なコンテナー アプリケーションを作成する場合は、 から`COleDocument`ドキュメント クラスを派生させます。 ドキュメントに含まれる埋め込みアイテムへのリンクをサポートするコンテナ アプリケーションを作成する場合は[、COleリンDoc](../../mfc/reference/colelinkingdoc-class.md)からドキュメント クラスを派生させます。 サーバー アプリケーションまたは組み合わせコンテナー/サーバーを作成する場合は、ドキュメント クラスを[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)から派生させます。 `COleLinkingDoc`および`COleServerDoc`から`COleDocument`派生しているので、これらのクラスは で使用できるすべての`COleDocument`サービス`CDocument`を継承します。

を使用`COleDocument`するには、クラスを派生させ、アプリケーションの OLE 以外のデータ、および埋め込みアイテムやリンクアイテムを管理する機能を追加します。 アプリケーションのネイティブ`CDocItem`データを格納する -derived クラスを定義する場合は、 で`COleDocument`定義されている既定の実装を使用して、OLE データと OLE 以外のデータの両方を格納できます。 OLE アイテムとは別に OLE 以外のデータを格納するための独自のデータ構造を設計することもできます。 詳細については、「[コンテナ: 複合ファイル](../../mfc/containers-compound-files.md)」を参照してください。

`CDocument`は、メールサポート(MAPI)が存在する場合、メールを介して文書を送信することをサポートします。 `COleDocument`複合ドキュメントを正しく処理するように[OnFileSendMail](#onfilesendmail)を更新しました。 詳細については、MFC の[MAPI](../../mfc/mapi.md)と[MAPI サポートの記事を](../../mfc/mapi-support-in-mfc.md)参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coledocumentadditem"></a><a name="additem"></a>ドキュメント::アイテムの追加

ドキュメントにアイテムを追加します。

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
追加するドキュメント アイテムへのポインター。

### <a name="remarks"></a>解説

ドキュメントへのポインターを受け取る`COleClientItem`または`COleServerItem`コンストラクターによって呼び出される場合、この関数を明示的に呼び出す必要はありません。

## <a name="coledocumentapplyprintdevice"></a><a name="applyprintdevice"></a>をクリックします。

アプリケーションのコンテナー ドキュメント内のすべての埋め込み[COleClientItem](../../mfc/reference/coleclientitem-class.md)項目の印刷対象デバイスを変更します。

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>パラメーター

*Ptd*<br/>
新しい印刷`DVTARGETDEVICE`対象デバイスに関する情報を含むデータ構造体へのポインター。 NULL にすることができます。

*Ppd*<br/>
新しい印刷`PRINTDLG`対象デバイスに関する情報を含むデータ構造体へのポインター。 NULL にすることができます。

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、すべての項目の印刷対象デバイスを更新しますが、それらの項目のプレゼンテーション キャッシュは更新されません。 アイテムのプレゼンテーション キャッシュを更新するには[、COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)を呼び出します。

この関数の引数には、OLE がターゲット デバイスを識別するために使用する情報が含まれています。 [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga)構造体には、Windows が共通の印刷ダイアログ ボックスを初期化するために使用する情報が含まれています。 ユーザーがダイアログ ボックスを閉じた後、Windows は、この構造体でユーザーの選択に関する情報を返します。 オブジェクト`m_pd`のメンバーは[CPrintDialog](../../mfc/reference/cprintdialog-class.md)構造体です`PRINTDLG`。

詳細については、Windows SDK の[PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga)構造体を参照してください。

詳細については、Windows SDK の[DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice)構造体を参照してください。

## <a name="coledocumentcoledocument"></a><a name="coledocument"></a>ドキュメント::ドキュメント

`COleDocument` オブジェクトを構築します。

```
COleDocument();
```

## <a name="coledocumentenablecompoundfile"></a><a name="enablecompoundfile"></a>コンパウンドファイルを有効にする

複合ファイル形式を使用して文書を保存する場合は、この関数を呼び出します。

```
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
複合ファイルのサポートを有効にするか無効にするかを指定します。

### <a name="remarks"></a>解説

これは構造化ストレージとも呼ばれます。 通常、この関数は`COleDocument`、派生クラスのコンストラクターから呼び出します。 複合ドキュメントの詳細については、「[コンテナ: 複合ファイル](../../mfc/containers-compound-files.md)」を参照してください。

このメンバー関数を呼び出さない場合、ドキュメントは非構造化 ("フラット" ) ファイル形式で格納されます。

複合ファイルのサポートがドキュメントに対して有効または無効になった後、ドキュメントの有効期間中に設定を変更しないでください。

## <a name="coledocumentgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>をクリックします。

*pWnd*で識別されるビューを含むフレーム ウィンドウ内で現在アクティブになっている OLE アイテムを取得します。

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
コンテナー ドキュメントを表示するウィンドウへのポインター。

### <a name="return-value"></a>戻り値

埋め込み先アクティブな OLE アイテムへのポインター。現在"インプレース アクティブ" 状態の OLE アイテムがない場合は NULL です。

## <a name="coledocumentgetnextclientitem"></a><a name="getnextclientitem"></a>次のクライアントアイテムを取得します。

ドキュメント内の各クライアントアイテムにアクセスするには、この関数を繰り返し呼び出します。

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
前の呼び出しによって設定された POSITION`GetNextClientItem`値への参照。初期値は`GetStartPosition`メンバー関数によって返されます。

### <a name="return-value"></a>戻り値

ドキュメント内の次のクライアント アイテムへのポインター。

### <a name="remarks"></a>解説

各呼び出しの後 *、pos*の値がドキュメント内の次の項目に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

## <a name="coledocumentgetnextitem"></a><a name="getnextitem"></a>次のアイテムを取得します。

ドキュメント内の各アイテムにアクセスするには、この関数を繰り返し呼び出します。

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
前の呼び出しによって設定された POSITION`GetNextItem`値への参照。初期値は`GetStartPosition`メンバー関数によって返されます。

### <a name="return-value"></a>戻り値

指定した位置にあるドキュメント アイテムへのポインター。

### <a name="remarks"></a>解説

各呼び出しの後 *、pos*の値はドキュメント内の次の項目の POSITION 値に設定されます。 取得した要素がドキュメントの最後の要素である場合 *、pos*の新しい値は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

## <a name="coledocumentgetnextserveritem"></a><a name="getnextserveritem"></a>次のサーバーアイテムを取得します。

ドキュメント内の各サーバー項目にアクセスするには、この関数を繰り返し呼び出します。

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
前の呼び出しによって設定された POSITION`GetNextServerItem`値への参照。初期値は`GetStartPosition`メンバー関数によって返されます。

### <a name="return-value"></a>戻り値

ドキュメント内の次のサーバー アイテムへのポインター。

### <a name="remarks"></a>解説

各呼び出しの後 *、pos*の値がドキュメント内の次の項目に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

## <a name="coledocumentgetprimaryselecteditem"></a><a name="getprimaryselecteditem"></a>を選択しました。

フレームワークによって呼び出され、指定されたビューで現在選択されている OLE アイテムを取得します。

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>パラメーター

*pビュー*<br/>
ドキュメントを表示するアクティブなビュー オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

選択された単一の OLE アイテムへのポインター。OLE アイテムが選択されていない場合、または複数のアイテムが選択されている場合は、NULL。

### <a name="remarks"></a>解説

既定の実装では、選択されている 1 つのアイテムについて、含まれている OLE アイテムの一覧を検索し、そのアイテムへのポインターを返します。 選択されている項目がない場合、または複数の項目が選択されている場合、関数は NULL を返します。 この関数を動作`CView::IsSelected`させるには、ビュー クラスのメンバー関数をオーバーライドする必要があります。 含まれている OLE アイテムを格納する独自のメソッドがある場合は、この関数をオーバーライドします。

## <a name="coledocumentgetstartposition"></a><a name="getstartposition"></a>ドキュメント::取得開始位置

ドキュメント内の最初の項目の位置を取得します。

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>戻り値

ドキュメントのアイテムの反復処理を開始するために使用できる POSITION 値。ドキュメントに項目がない場合は NULL。

### <a name="remarks"></a>解説

返される値を`GetNextItem`、 `GetNextClientItem`、`GetNextServerItem`または に渡します。

## <a name="coledocumenthasblankitems"></a><a name="hasblankitems"></a>ドキュメント::を空白にします

ドキュメントに空白の項目が含まれているかどうかを調べます。

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>戻り値

ドキュメントに空白の項目が含まれている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

空白の項目は、四角形が空のアイテムです。

## <a name="coledocumentoneditchangeicon"></a><a name="oneditchangeicon"></a>ドキュメント::オンエディットチェンジアイコン

[OLE のアイコンの変更] ダイアログ ボックスを表示し、現在選択されている OLE アイテムを表すアイコンを、ダイアログ ボックスでユーザーが選択したアイコンに変更します。

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>解説

`OnEditChangeIcon`[アイコンの変更]`COleChangeIconDialog`ダイアログ ボックスが作成され、起動されます。

## <a name="coledocumentoneditconvert"></a><a name="oneditconvert"></a>ドキュメント::オンエディットコンバート

[OLE 変換] ダイアログ ボックスを表示し、ダイアログ ボックスでユーザーが選択した選択に従って、現在選択されている OLE アイテムを変換またはアクティブにします。

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>解説

`OnEditConvert`変換ダイアログボックスを`COleConvertDialog`作成して起動します。

変換の例として、Word 文書をワードパッド ドキュメントに変換する場合があります。

## <a name="coledocumentoneditlinks"></a><a name="oneditlinks"></a>ドキュメント::オンエディットリンク

[OLE 編集/リンク] ダイアログ ボックスを表示します。

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>解説

`OnEditLinks`リンク オブジェクトを`COleLinksDialog`変更するためのリンク ダイアログ ボックスを作成して起動します。

## <a name="coledocumentonfilesendmail"></a><a name="onfilesendmail"></a>ファイル送信メール

ドキュメントを添付ファイルとして、常駐メール ホスト経由でメッセージを送信します( 存在する場合)。

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>解説

`OnFileSendMail`無`OnSaveDocument`題のドキュメントや変更されたドキュメントを一時ファイルにシリアル化 (保存) する呼び出しを、電子メールで送信します。 ドキュメントが変更されていない場合、一時ファイルは必要ありません。オリジナルが送信されます。 `OnFileSendMail`MAPI32 を読み込みます。DLL がまだ読み込まれていない場合。

`OnFileSendMail`の`CDocument`実装とは異なり、この関数は複合ファイルを正しく処理します。

詳細については[、MFC](../../mfc/mapi.md)の MAPI トピックと[MAPI サポートを参照](../../mfc/mapi-support-in-mfc.md)してください。

## <a name="coledocumentonshowviews"></a><a name="onshowviews"></a>ドキュメント::オンショービュー

フレームワークは、ドキュメントの可視性の状態が変更された後に、この関数を呼び出します。

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>パラメーター

*ビジブル*<br/>
ドキュメントが表示または非表示になっているかどうかを示します。

### <a name="remarks"></a>解説

この関数の既定のバージョンでは、何も実行されません。 ドキュメントの表示設定が変更されたときにアプリケーションで特別な処理を実行する必要がある場合は、この値をオーバーライドします。

## <a name="coledocumentonupdateeditchangeicon"></a><a name="onupdateeditchangeicon"></a>ドキュメント::オンアップデートエディットチェンジアイコン

[編集] メニューの [アイコンの変更] コマンドを更新するために、フレームワークによって呼び出されます。

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
update コマンドを`CCmdUI`生成したメニューを表す構造体へのポインター。 更新ハンドラーは、ユーザー`Enable`インターフェイスを更新`CCmdUI`する*pCmdUI*を使用して構造体のメンバー関数を呼び出します。

### <a name="remarks"></a>解説

`OnUpdateEditChangeIcon`は、ドキュメント内に有効なアイコンが存在するかどうかに応じて、コマンドのユーザー インターフェイスを更新します。 動作を変更するには、この関数をオーバーライドします。

## <a name="coledocumentonupdateeditlinksmenu"></a><a name="onupdateeditlinksmenu"></a>次の項目をクリックします。

[編集] メニューの [リンク] コマンドを更新するために、フレームワークによって呼び出されます。

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
update コマンドを`CCmdUI`生成したメニューを表す構造体へのポインター。 更新ハンドラーは、ユーザー`Enable`インターフェイスを更新`CCmdUI`する*pCmdUI*を使用して構造体のメンバー関数を呼び出します。

### <a name="remarks"></a>解説

ドキュメント内の最初の OLE アイテムから`OnUpdateEditLinksMenu`開始し、各アイテムにアクセスし、そのアイテムがリンクであるかどうかをテストし、リンクの場合は [リンク] コマンドを有効にします。 動作を変更するには、この関数をオーバーライドします。

## <a name="coledocumentonupdateobjectverbmenu"></a><a name="onupdateobjectverbmenu"></a>をクリックします。

フレームワークによって呼び出され、編集メニューの*ObjectName*コマンドと *、ObjectName*コマンドからアクセスされる動詞サブメニュー*ObjectName*を更新します。

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
update コマンドを`CCmdUI`生成したメニューを表す構造体へのポインター。 更新ハンドラーは、ユーザー`Enable`インターフェイスを更新`CCmdUI`する*pCmdUI*を使用して構造体のメンバー関数を呼び出します。

### <a name="remarks"></a>解説

`OnUpdateObjectVerbMenu`は、ドキュメント内に有効なオブジェクトが存在するかどうかに応じて*ObjectName*コマンドのユーザー インターフェイスを更新します。 オブジェクトが存在する場合は、[編集] メニューの *[オブジェクト名*] コマンドが有効になります。 このメニュー コマンドを選択すると、動詞サブメニューが表示されます。 動詞サブメニューには、編集、プロパティなど、オブジェクトで使用できるすべての動詞コマンドが含まれています。 動作を変更するには、この関数をオーバーライドします。

## <a name="coledocumentonupdatepastelinkmenu"></a><a name="onupdatepastelinkmenu"></a>ドキュメント::オンアップデートペーストリンクメニュー

リンクされた OLE アイテムをクリップボードから貼り付けることができるかどうかを判断するために、フレームワークによって呼び出されます。

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
update コマンドを`CCmdUI`生成したメニューを表す構造体へのポインター。 更新ハンドラーは、ユーザー`Enable`インターフェイスを更新`CCmdUI`する*pCmdUI*を使用して構造体のメンバー関数を呼び出します。

### <a name="remarks"></a>解説

[形式を選択して貼り付け] メニュー コマンドは、アイテムをドキュメントに貼り付けることができるかどうかによって有効または無効になります。

## <a name="coledocumentonupdatepastemenu"></a><a name="onupdatepastemenu"></a>ドキュメント::オンアップデートペーストメニュー

埋め込み OLE アイテムをクリップボードから貼り付けることができるかどうかを判断するために、フレームワークによって呼び出されます。

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
update コマンドを`CCmdUI`生成したメニューを表す構造体へのポインター。 更新ハンドラーは、ユーザー`Enable`インターフェイスを更新`CCmdUI`する*pCmdUI*を使用して構造体のメンバー関数を呼び出します。

### <a name="remarks"></a>解説

[貼り付け] メニューコマンドとボタンは、アイテムをドキュメントに貼り付けることができるかどうかによって有効または無効になります。

## <a name="coledocumentremoveitem"></a><a name="removeitem"></a>アイテムを削除します。

ドキュメントから項目を削除します。

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
削除するドキュメント アイテムへのポインター。

### <a name="remarks"></a>解説

通常、この関数を明示的に呼び出す必要はありません。と のデストラクタ`COleClientItem`によって呼び出`COleServerItem`されます。

## <a name="coledocumentupdatemodifiedflag"></a><a name="updatemodifiedflag"></a>ドキュメント::更新変更フラグ

含まれている OLE アイテムのいずれかが変更されている場合に、ドキュメントを変更済みとしてマークします。

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>解説

これにより、ドキュメント内のネイティブ データが変更されていない場合でも、閉じる前にドキュメントを保存するようにユーザーに求めるメッセージを表示できます。

## <a name="see-also"></a>関連項目

[MFC サンプル コンテナ](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
