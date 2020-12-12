---
description: ': COleDocument クラスに関する詳細情報'
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
ms.openlocfilehash: 804721c4055ecfdb64aab86b8ecc964d3bbbc42b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227183"
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
|[COleDocument:: COleDocument](#coledocument)|`COleDocument` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleDocument:: AddItem](#additem)|ドキュメントによって管理されている項目のリストに項目を追加します。|
|[COleDocument:: ApplyPrintDevice](#applyprintdevice)|ドキュメント内のすべてのクライアントアイテムの印刷ターゲットデバイスを設定します。|
|[COleDocument:: EnableCompoundFile](#enablecompoundfile)|OLE 構造化ストレージファイル形式を使用してドキュメントを保存します。|
|[COleDocument:: Getinplace Activeitem](#getinplaceactiveitem)|現在アクティブな OLE アイテムを返します。|
|[COleDocument:: GetNextClientItem](#getnextclientitem)|反復処理の対象となる次のクライアント項目を取得します。|
|[COleDocument:: GetNextItem](#getnextitem)|反復処理の対象となる次のドキュメント項目を取得します。|
|[COleDocument:: GetNextServerItem](#getnextserveritem)|反復処理の対象となる次のサーバー項目を取得します。|
|[COleDocument:: GetPrimarySelectedItem](#getprimaryselecteditem)|ドキュメントで選択されているプライマリ OLE 項目を返します。|
|[COleDocument:: GetStartPosition](#getstartposition)|反復処理を開始する最初の位置を取得します。|
|[COleDocument:: Hasitems Items](#hasblankitems)|ドキュメント内の空白の項目を確認します。|
|[COleDocument:: OnShowViews](#onshowviews)|ドキュメントが表示または非表示になったときに呼び出されます。|
|[COleDocument:: RemoveItem](#removeitem)|ドキュメントによって管理されている項目の一覧から項目を削除します。|
|[COleDocument:: UpdateModifiedFlag](#updatemodifiedflag)|含まれている OLE 項目のいずれかが変更された場合に、ドキュメントを変更済みとしてマークします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[COleDocument:: OnEditChangeIcon](#oneditchangeicon)|[アイコンの変更] メニューコマンドのイベントを処理します。|
|[COleDocument:: OnEditConvert](#oneditconvert)|埋め込みオブジェクトまたはリンクされたオブジェクトをある型から別の型に変換する処理を行います。|
|[COleDocument:: OnEditLinks](#oneditlinks)|[編集] メニューの [リンク] コマンドでイベントを処理します。|
|[COleDocument:: OnFileSendMail](#onfilesendmail)|添付されたドキュメントを使用してメールメッセージを送信します。|
|[COleDocument:: OnUpdateEditChangeIcon](#onupdateeditchangeicon)|[編集]/[アイコンの変更] メニューオプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|
|[COleDocument:: OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|[編集/リンク] メニューオプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|
|[COleDocument:: OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Edit/ *objectname* メニューオプションのコマンド UI と、Edit/ *objectname* からアクセスされる動詞サブメニューを更新するために、フレームワークによって呼び出されます。|
|[COleDocument:: OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|[特殊な貼り付け] メニューオプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|
|[COleDocument:: OnUpdatePasteMenu](#onupdatepastemenu)|[貼り付け] メニューオプションのコマンド UI を更新するために、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

`COleDocument` は、から派生したもの `CDocument` であり、Microsoft Foundation Class ライブラリによって提供されるドキュメント/ビューアーキテクチャを OLE アプリケーションで使用できるようにします。

`COleDocument` ドキュメントを [CDocItem](../../mfc/reference/cdocitem-class.md) オブジェクトのコレクションとして扱い、OLE 項目を処理します。 コンテナーとサーバーの両方のアプリケーションでは、これらのドキュメントに OLE 項目を含めることができる必要があるため、このようなアーキテクチャが必要です。 から派生した [COleServerItem](../../mfc/reference/coleserveritem-class.md) クラスと [COleClientItem](../../mfc/reference/coleclientitem-class.md) クラスは、 `CDocItem` アプリケーションと OLE アイテム間の相互作用を管理します。

単純なコンテナーアプリケーションを作成する場合は、からドキュメントクラスを派生させ `COleDocument` ます。 ドキュメントに含まれる埋め込みアイテムへのリンクをサポートするコンテナーアプリケーションを作成する場合は、 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)からドキュメントクラスを派生させます。 サーバーアプリケーションまたはコンテナー/サーバーを作成する場合は、 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)からドキュメントクラスを派生させます。 `COleLinkingDoc` と `COleServerDoc` はから派生している `COleDocument` ため、これらのクラスは、およびで使用できるすべてのサービスを継承し `COleDocument` `CDocument` ます。

を使用するには `COleDocument` 、そこからクラスを派生させ、アプリケーションの OLE 以外のデータだけでなく、埋め込みまたはリンクされた項目を管理する機能を追加します。 `CDocItem`アプリケーションのネイティブデータを格納するための派生クラスを定義する場合は、で定義されている既定の実装を使用して、 `COleDocument` ole データと非 ole データの両方を格納できます。 Ole 項目とは別に、OLE 以外のデータを格納するための独自のデータ構造を設計することもできます。 詳細については、「 [コンテナー: 複合ファイル](../../mfc/containers-compound-files.md).」を参照してください。

`CDocument` メールサポート (MAPI) が存在する場合は、メールを使用したドキュメントの送信をサポートします。 `COleDocument` は、複合ドキュメントを正しく処理するように [Onfilesendmail](#onfilesendmail) を更新しました。 詳細については、「 [MFC で](../../mfc/mapi-support-in-mfc.md)の[mapi](../../mfc/mapi.md)および mapi のサポート」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>要件

**ヘッダー:** afxole

## <a name="coledocumentadditem"></a><a name="additem"></a> COleDocument:: AddItem

ドキュメントに項目を追加するには、この関数を呼び出します。

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
追加されるドキュメント項目へのポインター。

### <a name="remarks"></a>解説

`COleClientItem`ドキュメントへのポインターを受け入れるコンストラクターまたはコンストラクターによって呼び出された場合、この関数を明示的に呼び出す必要はありません `COleServerItem` 。

## <a name="coledocumentapplyprintdevice"></a><a name="applyprintdevice"></a> COleDocument:: ApplyPrintDevice

アプリケーションのコンテナードキュメントに埋め込まれているすべての [COleClientItem](../../mfc/reference/coleclientitem-class.md) 項目の印刷ターゲットデバイスを変更するには、この関数を呼び出します。

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>パラメーター

*ptd*<br/>
`DVTARGETDEVICE`新しい印刷ターゲットデバイスに関する情報を格納するデータ構造体へのポインター。 NULL にすることができます。

*ppd*<br/>
`PRINTDLG`新しい印刷ターゲットデバイスに関する情報を格納するデータ構造体へのポインター。 NULL にすることができます。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、すべての項目の印刷ターゲットデバイスを更新しますが、それらの項目のプレゼンテーションキャッシュを更新しません。 項目のプレゼンテーションキャッシュを更新するには、 [COleClientItem:: UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)を呼び出します。

この関数の引数には、OLE がターゲットデバイスを識別するために使用する情報が含まれています。 [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga)構造体には、コモン印刷ダイアログボックスを初期化するために Windows が使用する情報が含まれています。 ユーザーがダイアログボックスを閉じた後、Windows は、この構造体のユーザーの選択に関する情報を返します。 `m_pd` [CPrintDialog](../../mfc/reference/cprintdialog-class.md)オブジェクトのメンバーは `PRINTDLG` 構造体です。

詳細については、Windows SDK の [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) 構造体を参照してください。

詳細については、Windows SDK の [DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) 構造体を参照してください。

## <a name="coledocumentcoledocument"></a><a name="coledocument"></a> COleDocument:: COleDocument

`COleDocument` オブジェクトを構築します。

```
COleDocument();
```

## <a name="coledocumentenablecompoundfile"></a><a name="enablecompoundfile"></a> COleDocument:: EnableCompoundFile

複合ファイル形式を使用してドキュメントを保存する場合は、この関数を呼び出します。

```cpp
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
複合ファイルのサポートを有効にするか無効にするかを指定します。

### <a name="remarks"></a>解説

これは、構造化ストレージとも呼ばれます。 通常、この関数は、派生クラスのコンストラクターから呼び出すことができ `COleDocument` ます。 複合ドキュメントの詳細については、「 [コンテナー: 複合ファイル](../../mfc/containers-compound-files.md).」を参照してください。

このメンバー関数を呼び出さない場合、ドキュメントは nonstructured ("フラット") ファイル形式で格納されます。

ドキュメントに対して複合ファイルのサポートを有効または無効にした後は、ドキュメントの有効期間中は設定を変更しないでください。

## <a name="coledocumentgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a> COleDocument:: Getinplace Activeitem

この関数を呼び出して、現在アクティブになっている OLE 項目を、ウィンドウ内で現在アクティブになっている、 *pWnd* によって識別されるビューを格納します。

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
コンテナードキュメントを表示するウィンドウへのポインター。

### <a name="return-value"></a>戻り値

埋め込み先の単一のアクティブな OLE 項目へのポインター。現在 "インプレースアクティブ" 状態に OLE 項目がない場合は NULL です。

## <a name="coledocumentgetnextclientitem"></a><a name="getnextclientitem"></a> COleDocument:: GetNextClientItem

ドキュメント内の各クライアント項目にアクセスするには、この関数を繰り返し呼び出します。

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
の前の呼び出しで設定された位置の値への参照 `GetNextClientItem` 。初期値は、メンバー関数によって返され `GetStartPosition` ます。

### <a name="return-value"></a>戻り値

ドキュメント内の次のクライアント項目へのポインター。それ以上クライアント項目がない場合は NULL。

### <a name="remarks"></a>解説

各呼び出しの後、ドキュメントの次の項目に対して *pos* の値が設定されます。これは、クライアント項目である場合もあれば、それ以外の場合もあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

## <a name="coledocumentgetnextitem"></a><a name="getnextitem"></a> COleDocument:: GetNextItem

ドキュメント内の各項目にアクセスするには、この関数を繰り返し呼び出します。

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
の前の呼び出しで設定された位置の値への参照 `GetNextItem` 。初期値は、メンバー関数によって返され `GetStartPosition` ます。

### <a name="return-value"></a>戻り値

指定した位置にあるドキュメント項目へのポインター。

### <a name="remarks"></a>解説

各呼び出しの後に、 *pos* の値は、ドキュメント内の次の項目の位置の値に設定されます。 取得した要素がドキュメントの最後の要素である場合、 *pos* の新しい値は NULL になります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

## <a name="coledocumentgetnextserveritem"></a><a name="getnextserveritem"></a> COleDocument:: GetNextServerItem

ドキュメント内の各サーバー項目にアクセスするには、この関数を繰り返し呼び出します。

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
の前の呼び出しで設定された位置の値への参照 `GetNextServerItem` 。初期値は、メンバー関数によって返され `GetStartPosition` ます。

### <a name="return-value"></a>戻り値

ドキュメント内の次のサーバー項目へのポインター。他のサーバー項目がない場合は NULL。

### <a name="remarks"></a>解説

各呼び出しの後に、ドキュメント内の次の項目に対して *pos* の値が設定されます。これは、サーバー項目である場合とない場合があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

## <a name="coledocumentgetprimaryselecteditem"></a><a name="getprimaryselecteditem"></a> COleDocument:: GetPrimarySelectedItem

指定されたビューで現在選択されている OLE 項目を取得するために、フレームワークによって呼び出されます。

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>パラメーター

*pView*<br/>
ドキュメントを表示しているアクティブなビューオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

選択された単一の OLE 項目へのポインター。OLE 項目が選択されていない場合、または複数選択されている場合は NULL です。

### <a name="remarks"></a>解説

既定の実装では、1つの選択した項目について、含まれている OLE 項目の一覧が検索され、その項目へのポインターが返されます。 項目が選択されていない場合、または複数の項目が選択されている場合、関数は NULL を返します。 `CView::IsSelected`この関数を機能させるには、ビュークラスのメンバー関数をオーバーライドする必要があります。 含まれている OLE 項目を格納する独自のメソッドがある場合は、この関数をオーバーライドします。

## <a name="coledocumentgetstartposition"></a><a name="getstartposition"></a> COleDocument:: GetStartPosition

ドキュメント内の最初の項目の位置を取得するには、この関数を呼び出します。

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>戻り値

ドキュメントの項目の反復処理を開始するために使用できる位置の値。ドキュメントに項目がない場合は NULL です。

### <a name="remarks"></a>解説

返された値を `GetNextItem` 、、 `GetNextClientItem` またはに渡し `GetNextServerItem` ます。

## <a name="coledocumenthasblankitems"></a><a name="hasblankitems"></a> COleDocument:: Hasitems Items

ドキュメントに空白の項目が含まれているかどうかを判断するには、この関数を呼び出します。

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>戻り値

ドキュメントに空白の項目が含まれている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

空の項目とは、四角形が空である項目のことです。

## <a name="coledocumentoneditchangeicon"></a><a name="oneditchangeicon"></a> COleDocument:: OnEditChangeIcon

OLE の [アイコンの変更] ダイアログボックスを表示し、現在選択されている OLE 項目を表すアイコンを、ユーザーがダイアログボックスで選択したアイコンに変更します。

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>解説

`OnEditChangeIcon` [ `COleChangeIconDialog` アイコンの変更] ダイアログボックスを作成して起動します。

## <a name="coledocumentoneditconvert"></a><a name="oneditconvert"></a> COleDocument:: OnEditConvert

[OLE 変換] ダイアログボックスを表示し、ダイアログボックスでのユーザーの選択に応じて、現在選択されている OLE アイテムを変換またはアクティブ化します。

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>解説

`OnEditConvert` [変換] ダイアログボックスを作成して起動し `COleConvertDialog` ます。

変換の例として、Microsoft Word 文書をワードパッドドキュメントに変換することが挙げられます。

## <a name="coledocumentoneditlinks"></a><a name="oneditlinks"></a> COleDocument:: OnEditLinks

OLE の [編集/リンク] ダイアログボックスを表示します。

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>解説

`OnEditLinks` リンクのダイアログボックスを作成して起動し `COleLinksDialog` 、ユーザーがリンクオブジェクトを変更できるようにします。

## <a name="coledocumentonfilesendmail"></a><a name="onfilesendmail"></a> COleDocument:: OnFileSendMail

常駐メールホスト (存在する場合) を介してメッセージを添付ファイルとして送信します。

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>解説

`OnFileSendMail` を呼び出して、 `OnSaveDocument` 無題および変更されたドキュメントを一時ファイルにシリアル化 (保存) し、電子メールで送信します。 ドキュメントが変更されていない場合、一時ファイルは必要ありません。元のが送信されます。 `OnFileSendMail` まだ読み込まれていない場合は MAPI32.DLL を読み込みます。

のの実装とは異なり `OnFileSendMail` `CDocument` 、この関数は複合ファイルを正しく処理します。

詳細については、「MFC の記事」の [mapi のトピック](../../mfc/mapi.md) と [mapi サポート](../../mfc/mapi-support-in-mfc.md) を参照してください。

## <a name="coledocumentonshowviews"></a><a name="onshowviews"></a> COleDocument:: OnShowViews

フレームワークは、ドキュメントの表示状態が変更された後に、この関数を呼び出します。

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>パラメーター

*bVisible*<br/>
ドキュメントが表示または非表示になっているかどうかを示します。

### <a name="remarks"></a>解説

この関数の既定のバージョンでは、何も実行されません。 アプリケーションでドキュメントの可視性が変更されたときに特別な処理を実行する必要がある場合は、オーバーライドします。

## <a name="coledocumentonupdateeditchangeicon"></a><a name="onupdateeditchangeicon"></a> COleDocument:: OnUpdateEditChangeIcon

[編集] メニューの [アイコンの変更] コマンドを更新するために、フレームワークによって呼び出されます。

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*pCmdUI*<br/>
`CCmdUI`Update コマンドを生成したメニューを表す構造体へのポインター。 更新ハンドラーは、 `Enable` `CCmdUI` *pCmdUI* を介して構造体のメンバー関数を呼び出し、ユーザーインターフェイスを更新します。

### <a name="remarks"></a>解説

`OnUpdateEditChangeIcon` ドキュメント内に有効なアイコンがあるかどうかに応じて、コマンドのユーザーインターフェイスを更新します。 動作を変更するには、この関数をオーバーライドします。

## <a name="coledocumentonupdateeditlinksmenu"></a><a name="onupdateeditlinksmenu"></a> COleDocument:: OnUpdateEditLinksMenu

[編集] メニューの [リンク] コマンドを更新するために、フレームワークによって呼び出されます。

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*pCmdUI*<br/>
`CCmdUI`Update コマンドを生成したメニューを表す構造体へのポインター。 更新ハンドラーは、 `Enable` `CCmdUI` *pCmdUI* を介して構造体のメンバー関数を呼び出し、ユーザーインターフェイスを更新します。

### <a name="remarks"></a>解説

ドキュメント内の最初の OLE 項目から開始し、各項目にアクセスして、 `OnUpdateEditLinksMenu` 項目がリンクであるかどうかをテストします。また、リンクの場合は、Links コマンドを有効にします。 動作を変更するには、この関数をオーバーライドします。

## <a name="coledocumentonupdateobjectverbmenu"></a><a name="onupdateobjectverbmenu"></a> COleDocument:: OnUpdateObjectVerbMenu

Objectname *コマンドを* 更新するためにフレームワークによって呼び出されます。ここで、 *objectname* は 、ドキュメントに埋め込まれている OLE オブジェクトの名前です。

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*pCmdUI*<br/>
`CCmdUI`Update コマンドを生成したメニューを表す構造体へのポインター。 更新ハンドラーは、 `Enable` `CCmdUI` *pCmdUI* を介して構造体のメンバー関数を呼び出し、ユーザーインターフェイスを更新します。

### <a name="remarks"></a>解説

`OnUpdateObjectVerbMenu` ドキュメント内に有効なオブジェクトが存在するかどうかに応じて、 *ObjectName* コマンドのユーザーインターフェイスを更新します。 オブジェクトが存在する場合は、[編集] メニューの *ObjectName* コマンドが有効になります。 このメニューコマンドを選択すると、動詞サブメニューが表示されます。 動詞サブメニューには、オブジェクトで使用できるすべての動詞コマンド (Edit、Properties など) が含まれています。 動作を変更するには、この関数をオーバーライドします。

## <a name="coledocumentonupdatepastelinkmenu"></a><a name="onupdatepastelinkmenu"></a> COleDocument:: OnUpdatePasteLinkMenu

リンクされた OLE 項目をクリップボードから貼り付けることができるかどうかを判断するために、フレームワークによって呼び出されます。

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*pCmdUI*<br/>
`CCmdUI`Update コマンドを生成したメニューを表す構造体へのポインター。 更新ハンドラーは、 `Enable` `CCmdUI` *pCmdUI* を介して構造体のメンバー関数を呼び出し、ユーザーインターフェイスを更新します。

### <a name="remarks"></a>解説

項目をドキュメントに貼り付けることができるかどうかによって、[特殊な貼り付け] メニューコマンドが有効または無効になります。

## <a name="coledocumentonupdatepastemenu"></a><a name="onupdatepastemenu"></a> COleDocument:: OnUpdatePasteMenu

埋め込み OLE 項目をクリップボードから貼り付けることができるかどうかを判断するために、フレームワークによって呼び出されます。

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*pCmdUI*<br/>
`CCmdUI`Update コマンドを生成したメニューを表す構造体へのポインター。 更新ハンドラーは、 `Enable` `CCmdUI` *pCmdUI* を介して構造体のメンバー関数を呼び出し、ユーザーインターフェイスを更新します。

### <a name="remarks"></a>解説

貼り付けメニューコマンドとボタンは、項目をドキュメントに貼り付けることができるかどうかによって、有効または無効になります。

## <a name="coledocumentremoveitem"></a><a name="removeitem"></a> COleDocument:: RemoveItem

ドキュメントから項目を削除するには、この関数を呼び出します。

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>パラメーター

*pItem*<br/>
削除するドキュメント項目へのポインター。

### <a name="remarks"></a>解説

通常、この関数を明示的に呼び出す必要はありません。このメソッドは、およびのデストラクターによって呼び出され `COleClientItem` `COleServerItem` ます。

## <a name="coledocumentupdatemodifiedflag"></a><a name="updatemodifiedflag"></a> COleDocument:: UpdateModifiedFlag

含まれている OLE 項目のいずれかが変更された場合に、ドキュメントを変更済みとしてマークするには、この関数を呼び出します。

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>解説

これにより、フレームワークは、ドキュメント内のネイティブデータが変更されていない場合でも、ドキュメントを閉じる前に保存するようにユーザーに求めることができます。

## <a name="see-also"></a>関連項目

[MFC サンプルコンテナー](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[CDocument クラス](../../mfc/reference/cdocument-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
