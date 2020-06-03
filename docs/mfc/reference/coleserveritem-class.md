---
title: COleServerItem クラス
ms.date: 11/04/2016
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
ms.openlocfilehash: bdb91168a7c0ae718ca7d7514448b55965186aa8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753745"
---
# <a name="coleserveritem-class"></a>COleServerItem クラス

OLE アイテムへのサーバー インターフェイスが用意されています。

## <a name="syntax"></a>構文

```
class COleServerItem : public CDocItem
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[アイテムを選択します。](#coleserveritem)|`COleServerItem` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を切り取る::その他のクリップボードの追加データ](#addotherclipboarddata)|プレゼンテーションおよび変換形式をオブジェクトに`COleDataSource`配置します。|
|[クリップボードにコピーします。](#copytoclipboard)|アイテムをクリップボードにコピーします。|
|[オブジェクト::Dをドラッグドロップ](#dodragdrop)|ドラッグ アンド ドロップ操作を実行します。|
|[を取得します。](#getclipboarddata)|データ転送 (ドラッグ アンド ドロップまたはクリップボード) で使用するデータ ソースを取得します。|
|[を取得します。](#getdocument)|アイテムを含むサーバー ドキュメントを返します。|
|[データを埋め込みます。](#getembedsourcedata)|OLE アイテムのCF_EMBEDSOURCEデータを取得します。|
|[アイテムを取得します。](#getitemname)|項目の名前を返します。 リンクされたアイテムにのみ使用されます。|
|[データを取得します。](#getlinksourcedata)|OLE アイテムのCF_LINKSOURCEデータを取得します。|
|[オブジェクト記述子データを取得します。](#getobjectdescriptordata)|OLE アイテムのCF_OBJECTDESCRIPTORデータを取得します。|
|[接続されています。](#isconnected)|アイテムが現在アクティブなコンテナーにアタッチされているかどうかを示します。|
|[をクリックします。](#islinkeditem)|アイテムがリンクされた OLE アイテムを表すかどうかを示します。|
|[を変更しました。](#notifychanged)|リンクの自動更新を使用してすべてのコンテナを更新します。|
|[をクリックします。](#ondoverb)|動詞を実行するために呼び出されます。|
|[を選択します。](#ondraw)|コンテナーが項目の描画を要求したときに呼び出されます。実装が必要です。|
|[をクリックします。](#ondrawex)|特殊な項目の描画用に呼び出されます。|
|[をクリックします。](#ongetclipboarddata)|クリップボードにコピーされるデータを取得するために、フレームワークによって呼び出されます。|
|[を選択します。](#ongetextent)|OLE アイテムのサイズを取得するために、フレームワークによって呼び出されます。|
|[データを受け取る](#oninitfromdata)|指定したデータ転送オブジェクトの内容を使用して OLE アイテムを初期化するために、フレームワークによって呼び出されます。|
|[アイテムを更新します。](#onqueryupdateitems)|リンクされたアイテムが更新を必要とするかどうかを判断するために呼び出されます。|
|[を選択します。](#onrenderdata)|遅延レンダリングの一部としてデータを取得します。|
|[データを表示します。](#onrenderfiledata)|遅延レンダリングの一部`CFile`としてオブジェクトにデータを取得します。|
|[を選択します。](#onrenderglobaldata)|遅延レンダリングの一部として、HGLOBAL にデータを取得します。|
|[を設定します。](#onsetcolorscheme)|アイテムの配色を設定するために呼び出されます。|
|[を使用します。](#onsetdata)|項目のデータを設定するために呼び出されます。|
|[をクリックします。](#onsetextent)|OLE アイテムのサイズを設定するために、フレームワークによって呼び出されます。|
|[サービスアイテム::オンアップデート](#onupdate)|アイテムが属するドキュメントの一部が変更されたときに呼び出されます。|
|[アイテムを更新します。](#onupdateitems)|サーバー ドキュメント内のすべてのアイテムのプレゼンテーション キャッシュを更新するために呼び出されます。|
|[アイテムを選択します。](#setitemname)|項目の名前を設定します。 リンクされたアイテムにのみ使用されます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[を使用します。](#getdatasource)|変換形式の格納に使用するオブジェクトを取得します。|
|[をクリックします。](#onhide)|OLE アイテムを非表示にするために、フレームワークによって呼び出されます。|
|[を開く](#onopen)|OLE アイテムを独自のトップレベル ウィンドウに表示するために、フレームワークによって呼び出されます。|
|[サービスアイテム::オンショー](#onshow)|コンテナーがアイテムの表示を要求したときに呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[サービスアイテム:m_sizeExtent](#m_sizeextent)|OLE アイテムの表示量をサーバーに通知します。|

## <a name="remarks"></a>解説

リンク アイテムは、サーバー ドキュメントの一部またはすべてを表すことができます。 埋め込みアイテムは、常にサーバー ドキュメント全体を表します。

この`COleServerItem`クラスは、通常、コンテナー アプリケーションからの要求に応じて、OLE システム のダイナミック リンク ライブラリ (DLL) によって呼び出される、オーバーライド可能なメンバー関数をいくつか定義します。 これらのメンバー関数を使用すると、コンテナー アプリケーションは、アイテムの表示、動詞の実行、さまざまな形式でのデータの取得など、さまざまな方法で間接的に項目を操作できます。

を使用`COleServerItem`するには、クラスを派生させ[、OnDraw](#ondraw)と[Serialize](../../mfc/reference/cobject-class.md#serialize)メンバー関数を実装します。 この`OnDraw`関数は、アイテムのメタファイル表現を提供し、コンテナアプリケーションが複合ドキュメントを開いたときに表示できるようにします。 の`Serialize`機能は`CObject`、アイテムのネイティブ表現を提供し、埋め込みアイテムをサーバーアプリケーションとコンテナアプリケーション間で転送できるようにします。 [OnGetExtent](#ongetextent)は、コンテナーに対して項目の自然なサイズを提供し、コンテナーが項目のサイズを変更できるようにします。

サーバーおよび関連トピックの詳細については、「[コンテナー : 高度な機能](../../mfc/containers-advanced-features.md)」の「[サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md)」および「コンテナー/サーバー アプリケーションの作成」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

`COleServerItem`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coleserveritemaddotherclipboarddata"></a><a name="addotherclipboarddata"></a>を切り取る::その他のクリップボードの追加データ

指定したオブジェクトに OLE アイテムのプレゼンテーション形式と変換形式を配置します`COleDataSource`。

```cpp
void AddOtherClipboardData(COleDataSource* pDataSource);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
データを`COleDataSource`配置するオブジェクトへのポインター。

### <a name="remarks"></a>解説

OnDraw メンバー関数を[OnDraw](#ondraw)実装して、アイテムのプレゼンテーション形式 (メタファイル画像) を提供する必要があります。 他の変換形式をサポートするには[、GetDataSource](#getdatasource)によって返される[COleDataSource](../../mfc/reference/coledatasource-class.md)オブジェクトを使用してそれらを登録し、サポートする形式でデータを提供する[OnRenderData](#onrenderdata)メンバー関数をオーバーライドします。

## <a name="coleserveritemcoleserveritem"></a><a name="coleserveritem"></a>アイテムを選択します。

オブジェクトを`COleServerItem`構築し、サーバー ドキュメントのドキュメント アイテムのコレクションに追加します。

```
COleServerItem(
    COleServerDoc* pServerDoc,
    BOOL bAutoDelete);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
新しいアイテムを含むドキュメントへのポインター。

*b自動削除*<br/>
オブジェクトへのリンクが解放されたときにオブジェクトを削除できるかどうかを示すフラグです。 オブジェクトが文書の`COleServerItem`データの一部であり、削除する必要がある場合は、FALSE に設定します。 フレームワークによって削除できるドキュメントのデータの範囲を識別するために使用される 2 次構造である場合は、この値を TRUE に設定します。

## <a name="coleserveritemcopytoclipboard"></a><a name="copytoclipboard"></a>クリップボードにコピーします。

OLE アイテムをクリップボードにコピーします。

```cpp
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>パラメーター

*bインクルードリンク*<br/>
リンク データをクリップボードにコピーする場合は、この値を TRUE に設定します。 サーバー アプリケーションがリンクをサポートしていない場合は、これを FALSE に設定します。

### <a name="remarks"></a>解説

この関数は、サポートされている形式で OLE アイテムのデータを含む[COleDataSource](../../mfc/reference/coledatasource-class.md)オブジェクトを作成するのには[、メンバー](#ongetclipboarddata)関数を使用します。 次に、関数は`COleDataSource`[、COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard)関数を使用してクリップボードにオブジェクトを配置します。 オブジェクト`COleDataSource`には、アイテムのネイティブ データと、その表現CF_METAFILEPICT形式での表現、およびサポートする変換形式のデータが含まれます。 このメンバー関数を動作させるには[、Serialize](../../mfc/reference/cobject-class.md#serialize)と[OnDraw](#ondraw)を実装している必要があります。

## <a name="coleserveritemdodragdrop"></a><a name="dodragdrop"></a>オブジェクト::Dをドラッグドロップ

メンバー関数`DoDragDrop`を呼び出してドラッグ アンド ドロップ操作を実行します。

```
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,
    CPoint ptOffset,
    BOOL bIncludeLink = FALSE,
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,
    LPCRECT lpRectStartDrag = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
画面上の項目の四角形 (ピクセル単位) を、クライアント領域に対して相対的に指定します。

*ptオフセット*<br/>
ドラッグ時にマウスの位置が位置していた*lpItemRect*からのオフセット。

*bインクルードリンク*<br/>
リンク データをクリップボードにコピーする場合は、この値を TRUE に設定します。 アプリケーションがリンクをサポートしていない場合は、FALSE に設定します。

*dw エフェクト*<br/>
ドラッグ操作でのドラッグソースの効果 (コピー、移動、およびリンクの組み合わせ) を指定します。

*ドラッグを開始します。*<br/>
ドラッグが実際に開始される位置を定義する四角形へのポインター。 詳細については、「解説」を参照してください。

### <a name="return-value"></a>戻り値

DROPEFFECT 列挙体の値。 DROPEFFECT_MOVE場合は、元のデータを削除する必要があります。

### <a name="remarks"></a>解説

ドラッグ アンド ドロップ操作はすぐには開始されません。 このオブジェクトは *、lpRectStartDrag*で指定された四角形からマウス カーソルが離れるまで、または指定されたミリ秒数が経過するまで待機します。 *lpRectStartDrag*が NULL の場合、既定の四角形が使用され、マウス カーソルが 1 ピクセル移動したときにドラッグが開始されます。

遅延時間は、レジストリ キーの設定で指定します。 遅延時間を変更するには[、CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint)を呼び出します。 遅延時間を指定しない場合は、デフォルト値の 200 ミリ秒が使用されます。 ドラッグ遅延時間は次のように保存されます。

- Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\ソフトウェア\Windows\NT\現在のバージョン\IniFileMapping\win.ini\Windows\ドラッグディレイに保存されます。

- ウィンドウズ 3.x ドラッグ遅延時間は WIN に格納されます。INI ファイル、[ウィンドウ] セクションの下。

- Windows 95/98 ドラッグ遅延時間は、キャッシュされたバージョンの WIN に格納されます。Ini。

レジストリまたは .INI ファイルを[参照してください](/windows/win32/api/winbase/nf-winbase-writeprofilestringw)。

## <a name="coleserveritemgetclipboarddata"></a><a name="getclipboarddata"></a>を取得します。

この関数を呼び出して、クリップボードにコピーされるすべてのデータを指定した[COleDataSource](../../mfc/reference/coledatasource-class.md)オブジェクトに格納[します](#copytoclipboard)。 [DoDragDrop](#dodragdrop)

```cpp
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
サポートされているすべての形式`COleDataSource`で OLE アイテムのデータを受け取るオブジェクトへのポインター。

*bインクルードリンク*<br/>
リンク データをクリップボードにコピーする場合は TRUE。 サーバー アプリケーションがリンクをサポートしていない場合は FALSE。

*を指定します。*<br/>
オブジェクトの原点からのマウス カーソルのオフセット (ピクセル単位)。

*lp サイズ*<br/>
オブジェクトのサイズ (ピクセル単位)。

### <a name="remarks"></a>解説

この関数は、OLE アイテムのネイティブ データを取得する[GetEmbedSourceData](#getembedsourcedata)メンバー関数を呼び出し、プレゼンテーション形式とサポートされている変換形式を取得する[メンバー](#addotherclipboarddata)関数を呼び出します。 *bIncludeLink*が TRUE の場合、関数は[GetLinkSourceData](#getlinksourcedata)を呼び出してアイテムのリンク データを取得します。

によって提供される形式の前後に、オブジェクトに書式`COleDataSource`を配置する場合は、この関数`CopyToClipboard`をオーバーライドします。

## <a name="coleserveritemgetdatasource"></a><a name="getdatasource"></a>を使用します。

サーバー アプリケーションがサポートする変換形式を格納するために使用される[COleDataSource](../../mfc/reference/coledatasource-class.md)オブジェクトを取得します。

```
COleDataSource* GetDataSource();
```

### <a name="return-value"></a>戻り値

変換形式を`COleDataSource`格納するために使用されるオブジェクトへのポインター。

### <a name="remarks"></a>解説

データ転送操作中に、サーバー アプリケーションでさまざまな形式のデータを提供する場合は、この関数によって返`COleDataSource`されるオブジェクトにこれらの形式を登録します。 たとえば、OLE アイテムのCF_TEXT表現をクリップボードまたはドラッグ アンド ドロップ操作に提供する場合は、この関数が返す`COleDataSource`オブジェクトに書式を登録し、`OnRenderXxxData`メンバー関数をオーバーライドしてデータを提供します。

## <a name="coleserveritemgetdocument"></a><a name="getdocument"></a>を取得します。

アイテムを含むドキュメントへのポインターを取得します。

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>戻り値

アイテムを含むドキュメントへのポインター。アイテムがドキュメントの一部でない場合は NULL。

### <a name="remarks"></a>解説

これにより、`COleServerItem`コンストラクタに引数として渡したサーバードキュメントにアクセスできます。

## <a name="coleserveritemgetembedsourcedata"></a><a name="getembedsourcedata"></a>データを埋め込みます。

OLE アイテムのCF_EMBEDSOURCEデータを取得します。

```cpp
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>パラメーター

*中程度*<br/>
OLE アイテムのCF_EMBEDSOURCEデータを受け取る[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体へのポインター。

### <a name="remarks"></a>解説

この形式には、アイテムのネイティブ データが含まれます。 この関数が正しく機能`Serialize`するには、メンバー関数を実装している必要があります。

その後、結果を[COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata)を使用してデータ ソースに追加できます。 この関数は、自動的に呼び出[されます](#ongetclipboarddata)。

詳細については、Windows SDK[の STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)を参照してください。

## <a name="coleserveritemgetitemname"></a><a name="getitemname"></a>アイテムを取得します。

アイテムの名前を取得します。

```
const CString& GetItemName() const;
```

### <a name="return-value"></a>戻り値

アイテムの名前。

### <a name="remarks"></a>解説

通常、この関数はリンクされたアイテムに対してのみ呼び出します。

## <a name="coleserveritemgetlinksourcedata"></a><a name="getlinksourcedata"></a>データを取得します。

OLE アイテムのCF_LINKSOURCEデータを取得します。

```
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>パラメーター

*中程度*<br/>
OLE アイテムのCF_LINKSOURCEデータを受け取る[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この形式には、OLE アイテムの種類を記述する CLSID と、OLE アイテムを含むドキュメントを検索するために必要な情報が含まれます。

その後、結果を[COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata)を使用してデータ ソースに追加できます。 この関数は、[自動的](#ongetclipboarddata)に呼び出されます。

詳細については、Windows SDK[の STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)を参照してください。

## <a name="coleserveritemgetobjectdescriptordata"></a><a name="getobjectdescriptordata"></a>オブジェクト記述子データを取得します。

OLE アイテムのCF_OBJECTDESCRIPTORデータを取得します。

```cpp
void GetObjectDescriptorData(
    LPPOINT lpOffset,
    LPSIZE lpSize,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
OLE アイテムの左上隅からのマウス クリックのオフセット。 NULL にすることができます。

*lp サイズ*<br/>
OLE アイテムのサイズです。 NULL にすることができます。

*中程度*<br/>
OLE アイテムのCF_OBJECTDESCRIPTORデータを受け取る[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体へのポインター。

### <a name="remarks"></a>解説

情報は、 `STGMEDIUM` *lpStgMedium*によって示された構造体にコピーされます。 この形式には、[形式を選択して貼り付け] ダイアログに必要な情報が含まれます。

詳細については、Windows SDK[の STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)を参照してください。

## <a name="coleserveritemisconnected"></a><a name="isconnected"></a>接続されています。

OLE アイテムが接続されているかどうかを確認します。

```
BOOL IsConnected() const;
```

### <a name="return-value"></a>戻り値

項目が接続されている場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

OLE アイテムは、1 つ以上のコンテナーがアイテムへの参照を持っている場合に接続されていると見なされます。 アイテムの参照カウントが 0 より大きい場合、または埋め込みアイテムである場合、アイテムは接続されます。

## <a name="coleserveritemislinkeditem"></a><a name="islinkeditem"></a>をクリックします。

OLE アイテムがリンク アイテムかどうかを確認します。

```
BOOL IsLinkedItem() const;
```

### <a name="return-value"></a>戻り値

アイテムがリンク アイテムの場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

アイテムが有効で、ドキュメントの埋め込みアイテムの一覧に返されない場合、アイテムはリンクされます。 リンクアイテムは、コンテナに接続されている場合と接続されていない場合があります。

リンクアイテムと埋め込みアイテムの両方に同じクラスを使用するのが一般的です。 `IsLinkedItem`では、埋め込みアイテムとは異なる動作を行うことができますが、コードは多くの場合は一般的です。

## <a name="coleserveritemm_sizeextent"></a><a name="m_sizeextent"></a>サービスアイテム:m_sizeExtent

このメンバは、コンテナ ドキュメントに表示されるオブジェクトの量をサーバーに通知します。

```
CSize m_sizeExtent;
```

### <a name="remarks"></a>解説

[OnSetExtent](#onsetextent)の既定の実装では、このメンバーを設定します。

## <a name="coleserveritemnotifychanged"></a><a name="notifychanged"></a>を変更しました。

リンクされたアイテムが変更された後に、この関数を呼び出します。

```cpp
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>パラメーター

*アスペクト*<br/>
OLE アイテムのどの側面が変更されたかを示す DVASPECT 列挙体の値。 このパラメーターには次の値を指定できます。

- アイテムDVASPECT_CONTENT、コンテナ内の埋め込みオブジェクトとして表示できるように表示されます。

- DVASPECT_THUMBNAILアイテムは、閲覧ツールで表示できるように「サムネイル」表現でレンダリングされます。

- DVASPECT_ICON項目はアイコンで表されます。

- DVASPECT_DOCPRINTアイテムは、[ファイル] メニューの [印刷] コマンドを使用して印刷されたかのように表示されます。

### <a name="remarks"></a>解説

コンテナアイテムが自動リンクでドキュメントにリンクされている場合、そのアイテムは変更を反映するように更新されます。 Microsoft ファウンデーション クラス ライブラリを使用して作成されたコンテナー アプリケーションでは、[応答として呼](../../mfc/reference/coleclientitem-class.md#onchange)び出されます。

## <a name="coleserveritemondoverb"></a><a name="ondoverb"></a>をクリックします。

指定された動詞を実行するために、フレームワークによって呼び出されます。

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>パラメーター

*i動詞*<br/>
実行する動詞を指定します。 次のいずれかの方法を使用できます。

|値|意味|Symbol|
|-----------|-------------|------------|
|0|主動詞|OLEIVERB_PRIMARY|
|1|二次動詞|(なし)|
|- 1|編集用のアイテムを表示する|OLEIVERB_SHOW|
|- 2|別のウィンドウでアイテムを編集|OLEIVERB_OPEN|
|- 3|アイテムを非表示にする|OLEIVERB_HIDE|

通常、-1 値は別の動詞の別名です。 オープン編集がサポートされていない場合、-2 の効果は -1 と同じです。 その他の値については、次[を :D参照してください。](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb)

### <a name="remarks"></a>解説

コンテナー アプリケーションが Microsoft Foundation クラス ライブラリで作成された場合、この関数は、対応する`COleClientItem`オブジェクトの[COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate)メンバー関数が呼び出されたときに呼び出されます。 既定の実装では、主動詞またはOLEIVERB_SHOWが指定されている場合は[OnShow](#onshow)メンバー関数を呼び出し、2 番目の動詞またはOLEIVERB_OPENが指定されている場合は[OnOpen、OLEIVERB_HIDE](#onopen)が指定されている場合は[OnHide](#onhide)を呼び出します。 *iVerb*が`OnShow`上記の動詞の 1 つでない場合、既定の実装が呼び出されます。

プライマリ動詞が項目を表示しない場合は、この関数をオーバーライドします。 たとえば、アイテムがサウンド レコーディングで、その主動詞が再生の場合、アイテムを再生するためにサーバー アプリケーションを表示する必要はありません。

詳細については、次を[:D参照してください。](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb)

## <a name="coleserveritemondraw"></a><a name="ondraw"></a>を選択します。

OLE アイテムをメタファイルにレンダリングするために、フレームワークによって呼び出されます。

```
virtual BOOL OnDraw(
    CDC* pDC,
    CSize& rSize) = 0;
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
項目を描画する[CDC](../../mfc/reference/cdc-class.md)オブジェクトへのポインター。 表示コンテキストは属性表示コンテキストに自動的に接続されるため、属性関数を呼び出すことができますが、メタファイルデバイス固有の機能になります。

*rサイズ*<br/>
メタファイルを描画するサイズ (HIMETRIC 単位)。

### <a name="return-value"></a>戻り値

項目が正常に描画された場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

OLE アイテムのメタファイル表現は、コンテナ アプリケーション内のアイテムを表示するために使用されます。 コンテナー アプリケーションが Microsoft Foundation クラス ライブラリで作成された場合、メタファイルは対応する[COleClientItem](../../mfc/reference/coleclientitem-class.md)オブジェクトの[Draw](../../mfc/reference/coleclientitem-class.md#draw)メンバー関数によって使用されます。 既定の実装はありません。 指定したデバイス コンテキストに項目を描画するには、この関数をオーバーライドする必要があります。

## <a name="coleserveritemondrawex"></a><a name="ondrawex"></a>をクリックします。

すべての描画のフレームワークによって呼び出されます。

```
virtual BOOL OnDrawEx(
    CDC* pDC,
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
項目を描画する[CDC](../../mfc/reference/cdc-class.md)オブジェクトへのポインター。 DC は属性 DC に自動的に接続されるため、属性関数を呼び出すことができますが、メタファイル デバイス固有の関数になります。

*アスペクト*<br/>
DVASPECT 列挙体の値。 このパラメーターには次の値を指定できます。

- アイテムDVASPECT_CONTENT、コンテナ内の埋め込みオブジェクトとして表示できるように表示されます。

- DVASPECT_THUMBNAILアイテムは、閲覧ツールで表示できるように「サムネイル」表現でレンダリングされます。

- DVASPECT_ICON項目はアイコンで表されます。

- DVASPECT_DOCPRINTアイテムは、[ファイル] メニューの [印刷] コマンドを使用して印刷されたかのように表示されます。

*rサイズ*<br/>
HIMETRIC 単位のアイテムのサイズです。

### <a name="return-value"></a>戻り値

項目が正常に描画された場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

DVASPECT が`OnDraw`DVASPECT_CONTENTと等しい場合、既定の実装は呼び出します。それ以外の場合は失敗します。

DVASPECT_ICONやDVASPECT_THUMBNAILなど、DVASPECT_CONTENT以外の要素のプレゼンテーション データを提供するには、この関数をオーバーライドします。

## <a name="coleserveritemongetclipboarddata"></a><a name="ongetclipboarddata"></a>をクリックします。

[CopyToClipboard](#copytoclipboard)メンバー関数の`COleDataSource`呼び出しによってクリップボードに格納されるすべてのデータを格納しているオブジェクトを取得するために、フレームワークによって呼び出されます。

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>パラメーター

*bインクルードリンク*<br/>
リンク データをクリップボードにコピーする場合は、この値を TRUE に設定します。 サーバー アプリケーションがリンクをサポートしていない場合は、これを FALSE に設定します。

*を指定します。*<br/>
オブジェクトの原点からのマウス カーソルのオフセット (ピクセル単位)。

*lp サイズ*<br/>
オブジェクトのサイズ (ピクセル単位)。

### <a name="return-value"></a>戻り値

クリップボード データを格納している[COleDataSource](../../mfc/reference/coledatasource-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

この関数の既定の実装は[、GetClipboardData](#getclipboarddata)を呼び出します。

## <a name="coleserveritemongetextent"></a><a name="ongetextent"></a>を選択します。

OLE アイテムのサイズを HIMETRIC 単位で取得するために、フレームワークによって呼び出されます。

```
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>パラメーター

*アスペクト*<br/>
境界を取得する OLE アイテムのアスペクトを指定します。 このパラメーターには次の値を指定できます。

- アイテムDVASPECT_CONTENT、コンテナ内の埋め込みオブジェクトとして表示できるように表示されます。

- DVASPECT_THUMBNAILアイテムは、閲覧ツールで表示できるように「サムネイル」表現でレンダリングされます。

- DVASPECT_ICON項目はアイコンで表されます。

- DVASPECT_DOCPRINTアイテムは、[ファイル] メニューの [印刷] コマンドを使用して印刷されたかのように表示されます。

*rサイズ*<br/>
OLE アイテム`CSize`のサイズを受け取るオブジェクトへの参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

コンテナー アプリケーションが Microsoft Foundation クラス ライブラリで作成された場合、この関数は、対応する`COleClientItem`オブジェクトの[GetExtent](../../mfc/reference/coleclientitem-class.md#getextent)メンバー関数が呼び出されたときに呼び出されます。 既定の実装では、何も行われません。 自分で実装する必要があります。 OLE アイテムのサイズに対する要求を処理するときに特別な処理を実行する場合は、この関数をオーバーライドします。

## <a name="coleserveritemonhide"></a><a name="onhide"></a>をクリックします。

OLE アイテムを非表示にするために、フレームワークによって呼び出されます。

```
virtual void OnHide();
```

### <a name="remarks"></a>解説

既定の呼`COleServerDoc::OnShowDocument( FALSE )`び出しです。 この関数は、OLE アイテムが非表示になったことをコンテナーに通知します。 OLE アイテムを非表示にするときに特別な処理を実行する場合は、この関数をオーバーライドします。

## <a name="coleserveritemoninitfromdata"></a><a name="oninitfromdata"></a>データを受け取る

*pDataObject*の内容を使用して OLE アイテムを初期化するために、フレームワークによって呼び出されます。

```
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,
    BOOL bCreation);
```

### <a name="parameters"></a>パラメーター

*オブジェクト*<br/>
OLE アイテムを初期化するためのさまざまな形式のデータを含む OLE データ オブジェクトへのポインター。

*bクリエーション*<br/>
コンテナー アプリケーションによって新しく作成される OLE アイテムを初期化するために関数が呼び出された場合は TRUE。 既存の OLE アイテムの内容を置き換えるために関数が呼び出された場合は FALSE。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

*bCreation*が TRUE の場合、コンテナが現在の選択内容に基づいて新しいオブジェクトの挿入を実装している場合に、この関数が呼び出されます。 選択したデータは、新しい OLE アイテムを作成するときに使用されます。 たとえば、スプレッドシート プログラムでセル範囲を選択し、[新しいオブジェクトの挿入] を使用して、選択した範囲の値に基づいてグラフを作成します。 既定の実装では、何も行われません。 *pDataObject*が提供する形式から受け入れ可能な形式を選択し、提供されたデータに基づいて OLE アイテムを初期化するには、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。

詳細については、次を[参照](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata)してください。

## <a name="coleserveritemonopen"></a><a name="onopen"></a>を開く

OLE アイテムをサーバー アプリケーションの別のインスタンスに表示するために、フレームワークによって呼び出されます。

```
virtual void OnOpen();
```

### <a name="remarks"></a>解説

既定の実装では、OLE アイテムを含むドキュメントを表示する最初のフレーム ウィンドウがアクティブになります。アプリケーションがミニサーバーの場合、既定の実装はメイン ウィンドウを表示します。 この関数は、OLE アイテムが開かれたことをコンテナーに通知します。

OLE アイテムを開くときに特別な処理を実行する場合は、この関数をオーバーライドします。 これは、リンク先のアイテムを開いたときにリンクを設定する場合に特に一般的です。

詳細については、Windows SDK[の「IOleClient サイト::オンショー ウィンドウ](/windows/win32/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow)」を参照してください。

## <a name="coleserveritemonqueryupdateitems"></a><a name="onqueryupdateitems"></a>アイテムを更新します。

現在のサーバー ドキュメント内のリンク アイテムが最新でないかどうかを調べるには、フレームワークによって呼び出されます。

```
virtual BOOL OnQueryUpdateItems();
```

### <a name="return-value"></a>戻り値

更新が必要な項目がドキュメントに含まれる場合は 0 以外の値を返します。すべての項目が最新の場合は 0。

### <a name="remarks"></a>解説

元のドキュメントが変更されているが、リンクされたアイテムがドキュメントの変更を反映するように更新されていない場合、アイテムは期限切れになります。

## <a name="coleserveritemonrenderdata"></a><a name="onrenderdata"></a>を選択します。

指定した形式でデータを取得するために、フレームワークによって呼び出されます。

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>パラメーター

*フォーマットの問題*<br/>
情報が要求される形式を指定する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。

*中程度*<br/>
データが返される[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体へのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

指定された形式は、遅延レンダリングの`COleDataSource`[遅延レンダリングの遅延レンダリングデータまたは DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderdata)メンバー関数を使用して、オブジェクトに以前に配置された形式です。 [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) この関数の既定の実装は、指定されたストレージ メディアがファイルまたはメモリのいずれかである場合、それぞれ[OnRenderFileData](#onrenderfiledata)または[OnRenderGlobalData](#onrenderglobaldata)を呼び出します。 これらの形式がどちらも指定されていない場合、既定の実装は 0 を返し、何も実行しません。

*lpStgMedium*-> *タイム*がTYMED_NULL場合、STGMEDIUM は*lpFormatEtc->タイム*で指定されたとおりに割り当てられ、埋め込まれます。 TYMED_NULLしない場合は、STGMEDIUM にデータが入力されます。

これは、高度なオーバーライド可能です。 要求された形式とメディアでデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドする必要があります。 データが小さく、サイズが固定されている場合は`OnRenderGlobalData`、 をオーバーライドします。 データがファイル内にある場合、または可変サイズの場合は、`OnRenderFileData`オーバーライドします。

詳細については、Windows SDK の[「IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) [、STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)、[フォーマット、](/windows/win32/api/objidl/ns-objidl-formatetc)および[タイムド](/windows/win32/api/objidl/ne-objidl-tymed)」を参照してください。

## <a name="coleserveritemonrenderfiledata"></a><a name="onrenderfiledata"></a>データを表示します。

ストレージ メディアがファイルの場合に、指定した形式でデータを取得するためにフレームワークによって呼び出されます。

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>パラメーター

*フォーマットの問題*<br/>
情報が要求される形式を指定する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。

*ファイル*<br/>
データが`CFile`レンダリングされるオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

指定された形式は、遅延レンダリングの`COleDataSource` [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata)メンバー関数を使用して、オブジェクトに以前に配置された形式です。 この関数の既定の実装では、単に FALSE が返されます。

これは、高度なオーバーライド可能です。 要求された形式とメディアでデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドする必要があります。 複数のストレージ メディアを処理する場合は[、OnRenderData](#onrenderdata)をオーバーライドします。 データがファイル内にある場合、または可変サイズの場合は、[オーバーライドします](#onrenderfiledata)。

詳細については、Windows SDK[の「IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata)と[FORMATETC」](/windows/win32/api/objidl/ns-objidl-formatetc)を参照してください。

## <a name="coleserveritemonrenderglobaldata"></a><a name="onrenderglobaldata"></a>を選択します。

指定されたストレージ メディアがグローバル メモリである場合に、指定した形式でデータを取得するためにフレームワークによって呼び出されます。

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>パラメーター

*フォーマットの問題*<br/>
情報が要求される形式を指定する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。

*フグローバル*<br/>
データが返されるグローバル メモリへのハンドルへのポイント。 メモリが割り当てられていない場合、このパラメータは NULL にすることができます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

指定された形式は、遅延レンダリングの`COleDataSource` [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata)メンバー関数を使用して、オブジェクトに以前に配置された形式です。 この関数の既定の実装では、単に FALSE が返されます。

*phGlobal*が NULL の場合は、新しい HGLOBAL を割り当て *、phGlobal*に返す必要があります。 それ以外の場合は *、phGlobal*によって指定された HGLOBAL にデータを入力する必要があります。 HGLOBAL に格納されるデータの量は、メモリー・ブロックの現行サイズを超えてはなりません。 また、ブロックを大きなサイズに再割り当てすることはできません。

これは、高度なオーバーライド可能です。 要求された形式とメディアでデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドする必要があります。 複数のストレージ メディアを処理する場合は[、OnRenderData](#onrenderdata)をオーバーライドします。 データがファイル内にある場合、または可変サイズの場合は、[オーバーライドします](#onrenderfiledata)。

詳細については、Windows SDK[の「IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata)と[FORMATETC」](/windows/win32/api/objidl/ns-objidl-formatetc)を参照してください。

## <a name="coleserveritemonsetcolorscheme"></a><a name="onsetcolorscheme"></a>を設定します。

OLE アイテムの編集時に使用するカラー パレットを指定するために、フレームワークによって呼び出されます。

```
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```

### <a name="parameters"></a>パラメーター

*パレット*<br/>
[構造体への](/windows/win32/api/wingdi/ns-wingdi-logpalette)ポインター。

### <a name="return-value"></a>戻り値

カラー パレットを使用する場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

コンテナー アプリケーションが Microsoft ファウンデーション クラス ライブラリを使用して作成された場合、この関数は、対応する`COleClientItem`オブジェクトの[IOleObject::SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme)関数が呼び出されたときに呼び出されます。 既定の実装では FALSE が返されます。 推奨パレットを使用する場合は、この関数をオーバーライドします。 サーバー アプリケーションは、推奨されるパレットを使用する必要はありません。

詳細については、次を[参照](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme)してください。

## <a name="coleserveritemonsetdata"></a><a name="onsetdata"></a>を使用します。

OLE アイテムのデータを指定したデータに置き換えるために、フレームワークによって呼び出されます。

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>パラメーター

*フォーマットの問題*<br/>
データの形式を指定する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポインター。

*中程度*<br/>
データが存在する[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体へのポインター。

*bリリース*<br/>
関数呼び出しの完了後にストレージ メディアの所有権を持つユーザーを示します。 呼び出し元は、ストレージ メディアに代わって割り当てられたリソースを解放する担当者を決定します。 呼び出し元は*bRelease*を設定してこれを行います。 *bRelease*が 0 以外の場合、サーバーアイテムは所有権を取得し、使用が終了するとメディアを解放します。 *bRelease*が 0 の場合、呼び出し元は所有権を保持し、サーバー項目は呼び出しの間のみストレージ メディアを使用できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

サーバーアイテムは、データを正常に取得するまで、そのデータの所有権を取得しません。 つまり、0 を返しても所有権は取得されません。 データ ソースが所有権を取得する場合は[、ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium)関数を呼び出すことによってストレージ メディアを解放します。

既定の実装では、何も行われません。 OLE アイテムのデータを指定したデータに置き換えるには、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。

詳細については、Windows SDK[の「STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)、[フォーマット、](/windows/win32/api/objidl/ns-objidl-formatetc)および[リリース StgMedium」](/windows/win32/api/ole2/nf-ole2-releasestgmedium)を参照してください。

## <a name="coleserveritemonsetextent"></a><a name="onsetextent"></a>をクリックします。

コンテナー ドキュメント内で OLE アイテムに使用できる領域を OLE アイテムに示すために、フレームワークによって呼び出されます。

```
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,
    const CSize& size);
```

### <a name="parameters"></a>パラメーター

*アスペクト*<br/>
境界を指定する OLE アイテムのアスペクトを指定します。 このパラメーターには次の値を指定できます。

- アイテムDVASPECT_CONTENT、コンテナ内の埋め込みオブジェクトとして表示できるように表示されます。

- DVASPECT_THUMBNAILアイテムは、閲覧ツールで表示できるように「サムネイル」表現でレンダリングされます。

- DVASPECT_ICON項目はアイコンで表されます。

- DVASPECT_DOCPRINTアイテムは、[ファイル] メニューの [印刷] コマンドを使用して印刷されたかのように表示されます。

*size*<br/>
OLE アイテムの新しいサイズを指定する[CSize](../../atl-mfc-shared/reference/csize-class.md)構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

コンテナー アプリケーションが Microsoft Foundation クラス ライブラリで作成された場合、この関数は、対応する`COleClientItem`オブジェクトの[SetExtent](../../mfc/reference/coleclientitem-class.md#setextent)メンバー関数が呼び出されたときに呼び出されます。 既定の実装では *、nDrawAspect*がDVASPECT_CONTENT場合[、m_sizeExtent](#m_sizeextent)メンバーを指定されたサイズに設定します。それ以外の場合は 0 を返します。 項目のサイズを変更するときに特別な処理を実行するには、この関数をオーバーライドします。

## <a name="coleserveritemonshow"></a><a name="onshow"></a>サービスアイテム::オンショー

OLE アイテムをその場で表示するようにサーバー アプリケーションに指示するために、フレームワークによって呼び出されます。

```
virtual void OnShow();
```

### <a name="remarks"></a>解説

この関数は通常、コンテナー アプリケーションのユーザーがアイテムを作成するか、またはアイテムを表示する必要がある Edit などの動詞を実行するときに呼び出されます。 既定の実装では、インプレース アクティベーションが試行されます。 このエラーが発生しなかった場合、関数`OnOpen`はメンバー関数を呼び出して、OLE アイテムを別のウィンドウに表示します。

OLE アイテムが表示されたときに特別な処理を実行する場合は、この関数をオーバーライドします。

## <a name="coleserveritemonupdate"></a><a name="onupdate"></a>サービスアイテム::オンアップデート

アイテムが変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnUpdate(
    COleServerItem* pSender,
    LPARAM lHint,
    CObject* pHint,
    DVASPECT nDrawAspect);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ドキュメントを変更したアイテムへのポインター。 NULL にすることができます。

*lヒント*<br/>
変更に関する情報が含まれます。

*ヒント*<br/>
変更に関する情報を格納しているオブジェクトへのポインター。

*アスペクト*<br/>
DVASPECT 列挙体の値。 このパラメーターには、次のいずれかの値を指定できます。

- アイテムDVASPECT_CONTENT、コンテナ内の埋め込みオブジェクトとして表示できるように表示されます。

- DVASPECT_THUMBNAILアイテムは、閲覧ツールで表示できるように「サムネイル」表現でレンダリングされます。

- DVASPECT_ICON項目はアイコンで表されます。

- DVASPECT_DOCPRINTアイテムは、[ファイル] メニューの [印刷] コマンドを使用して印刷されたかのように表示されます。

### <a name="remarks"></a>解説

既定の実装では、ヒントまたは送信者に関係なく[NotifyChanged](#notifychanged)が呼び出されます。

## <a name="coleserveritemonupdateitems"></a><a name="onupdateitems"></a>アイテムを更新します。

サーバー ドキュメント内のすべての項目を更新するために、フレームワークによって呼び出されます。

```
virtual void OnUpdateItems();
```

### <a name="remarks"></a>解説

既定の実装では、ドキュメント内のすべての`COleClientItem`オブジェクトに対して[UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)が呼び出されます。

## <a name="coleserveritemsetitemname"></a><a name="setitemname"></a>アイテムを選択します。

この関数は、リンクアイテムを作成して名前を設定するときに呼び出します。

```cpp
void SetItemName(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
項目の新しい名前へのポインター。

### <a name="remarks"></a>解説

名前は、ドキュメント内で一意である必要があります。 サーバー アプリケーションがリンク アイテムを編集するために呼び出されると、アプリケーションはこの名前を使用してアイテムを検索します。 埋め込みアイテムに対してこの関数を呼び出す必要はありません。

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[CDocItem クラス](../../mfc/reference/cdocitem-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)<br/>
[COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)
