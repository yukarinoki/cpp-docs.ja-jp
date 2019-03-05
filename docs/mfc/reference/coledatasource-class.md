---
title: COleDataSource クラス
ms.date: 11/04/2016
f1_keywords:
- COleDataSource
- AFXOLE/COleDataSource
- AFXOLE/COleDataSource::COleDataSource
- AFXOLE/COleDataSource::CacheData
- AFXOLE/COleDataSource::CacheGlobalData
- AFXOLE/COleDataSource::DelayRenderData
- AFXOLE/COleDataSource::DelayRenderFileData
- AFXOLE/COleDataSource::DelaySetData
- AFXOLE/COleDataSource::DoDragDrop
- AFXOLE/COleDataSource::Empty
- AFXOLE/COleDataSource::FlushClipboard
- AFXOLE/COleDataSource::GetClipboardOwner
- AFXOLE/COleDataSource::OnRenderData
- AFXOLE/COleDataSource::OnRenderFileData
- AFXOLE/COleDataSource::OnRenderGlobalData
- AFXOLE/COleDataSource::OnSetData
- AFXOLE/COleDataSource::SetClipboard
helpviewer_keywords:
- COleDataSource [MFC], COleDataSource
- COleDataSource [MFC], CacheData
- COleDataSource [MFC], CacheGlobalData
- COleDataSource [MFC], DelayRenderData
- COleDataSource [MFC], DelayRenderFileData
- COleDataSource [MFC], DelaySetData
- COleDataSource [MFC], DoDragDrop
- COleDataSource [MFC], Empty
- COleDataSource [MFC], FlushClipboard
- COleDataSource [MFC], GetClipboardOwner
- COleDataSource [MFC], OnRenderData
- COleDataSource [MFC], OnRenderFileData
- COleDataSource [MFC], OnRenderGlobalData
- COleDataSource [MFC], OnSetData
- COleDataSource [MFC], SetClipboard
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
ms.openlocfilehash: bc3d9f089dc6289331c79c6a1e18eccbc9ff4993
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296976"
---
# <a name="coledatasource-class"></a>COleDataSource クラス

OLE アプリケーションが、クリップボード操作やドラッグ アンド ドロップ操作のようなデータ転送操作中に用意するデータを置くキャッシュの役目をします。

## <a name="syntax"></a>構文

```
class COleDataSource : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleDataSource::COleDataSource](#coledatasource)|`COleDataSource` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleDataSource::CacheData](#cachedata)|使用して、指定された形式でデータを提供する`STGMEDIUM`構造体。|
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|渡すを使用して、指定された形式でデータを提供します。|
|[COleDataSource::DelayRenderData](#delayrenderdata)|遅延レンダリングを使用して、指定された形式でデータを提供します。|
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|指定された形式でデータを提供する`CFile`ポインター。|
|[COleDataSource::DelaySetData](#delaysetdata)|サポートされているすべての形式と呼ばれる`OnSetData`します。|
|[COleDataSource::DoDragDrop](#dodragdrop)|データ ソースとドラッグ アンド ドロップ操作を実行します。|
|[COleDataSource::Empty](#empty)|空に、`COleDataSource`データのオブジェクト。|
|[COleDataSource::FlushClipboard](#flushclipboard)|すべてのデータをクリップボードにレンダリングします。|
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|クリップボードにデータがまだあることを確認します。|
|[COleDataSource::OnRenderData](#onrenderdata)|遅延レンダリングの一部としてデータを取得します。|
|[COleDataSource::OnRenderFileData](#onrenderfiledata)|データを取得、`CFile`遅延レンダリングの一部として。|
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|遅延レンダリングの一部として hglobal データを取得します。|
|[COleDataSource::OnSetData](#onsetdata)|内のデータを交換できるという、`COleDataSource`オブジェクト。|
|[COleDataSource::SetClipboard](#setclipboard)|場所、`COleDataSource`クリップボード上のオブジェクト。|

## <a name="remarks"></a>Remarks

OLE のデータ ソースを直接作成することができます。 または、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)と[COleServerItem](../../mfc/reference/coleserveritem-class.md)クラスへの応答での OLE データ ソースの作成、`CopyToClipboard`と`DoDragDrop`メンバー関数。 参照してください[COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard)簡単な説明。 上書き、 `OnGetClipboardData` OLE のデータ ソース内のデータに追加のクリップボード形式を追加するクライアント項目またはサーバー項目クラスのメンバー関数用に作成、`CopyToClipboard`または`DoDragDrop`メンバー関数。

データの転送を準備するときに、このクラスのオブジェクトを作成し、データの最適な方法を使用してデータを格納する必要があります。 データ ソースに挿入する方法にデータがすぐに提供されるかどうかは直接影響 (即時レンダリング)、またはオンデマンド (遅延レンダリング)。 使用するクリップボード形式を渡すことによって、データの提供をすべてのクリップボード形式の (と省略可能な[FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)構造)、呼び出す[に](#delayrenderdata)。

データ ソースとデータ転送する方法の詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)します。 さらに、この記事で[クリップボード トピック](../../mfc/clipboard.md)OLE クリップボード機構について説明します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDataSource`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

##  <a name="cachedata"></a>  COleDataSource::CacheData

提供されるデータのデータ転送操作の形式を指定するには、この関数を呼び出します。

```
void CacheData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cfFormat*<br/>
データが提供されるクリップボード形式。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)関数。

*lpStgMedium*<br/>
指す、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)指定された形式でデータを含む構造体。

*lpFormatEtc*<br/>
指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)提供されるデータの形式を記述する構造体。 指定されたクリップボード形式の書式の追加情報を指定する場合、このパラメーターの値を指定*cfFormat*します。 他のフィールドの既定値が使用されますが、NULL の場合、`FORMATETC`構造体。

### <a name="remarks"></a>Remarks

この関数は即時レンダリングを使用して提供するために、データを指定してください。 データは、必要になるまでにキャッシュされます。

使用してデータを提供する[STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)構造体。 使用することも、`CacheGlobalData`データの量を指定している場合、メンバー関数がそれほど効率的に渡すを使用して転送します。

呼び出し後`CacheData`、`ptd`のメンバー`lpFormatEtc`の内容と*lpStgMedium*呼び出し元ではなく、データ オブジェクトによって所有されています。

遅延レンダリングを使用する呼び出し、[に](#delayrenderdata)または[DelayRenderFileData](#delayrenderfiledata)メンバー関数。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース。操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。

詳細については、次を参照してください。、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)と[FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK 内の構造体。

詳細については、次を参照してください。[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)Windows SDK に含まれています。

##  <a name="cacheglobaldata"></a>  COleDataSource::CacheGlobalData

提供されるデータのデータ転送操作の形式を指定するには、この関数を呼び出します。

```
void CacheGlobalData(
    CLIPFORMAT cfFormat,
    HGLOBAL hGlobal,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cfFormat*<br/>
データが提供されるクリップボード形式。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)関数。

*hGlobal*<br/>
指定された形式のデータを含むグローバル メモリ ブロックへのハンドルします。

*lpFormatEtc*<br/>
指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)提供されるデータの形式を記述する構造体。 指定されたクリップボード形式の書式の追加情報を指定する場合、このパラメーターの値を指定*cfFormat*します。 他のフィールドの既定値が使用されますが、NULL の場合、`FORMATETC`構造体。

### <a name="remarks"></a>Remarks

この関数はこの関数を呼び出すときに、データを指定する必要がありますので、即時レンダリングを使用してデータを提供します。データは、必要になるまでにキャッシュされます。 使用して、`CacheData`大量のデータや構造化された記憶域メディアが必要なかどうかを指定している場合、メンバー関数。

遅延レンダリングを使用する呼び出し、[に](#delayrenderdata)または[DelayRenderFileData](#delayrenderfiledata)メンバー関数。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース。操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。

詳細については、次を参照してください。、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK の構造体。

詳細については、次を参照してください。[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)Windows SDK に含まれています。

##  <a name="coledatasource"></a>  COleDataSource::COleDataSource

`COleDataSource` オブジェクトを構築します。

```
COleDataSource();
```

##  <a name="delayrenderdata"></a>  COleDataSource::DelayRenderData

提供されるデータのデータ転送操作の形式を指定するには、この関数を呼び出します。

```
void DelayRenderData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cfFormat*<br/>
データが提供されるクリップボード形式。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)関数。

*lpFormatEtc*<br/>
指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)提供されるデータの形式を記述する構造体。 指定されたクリップボード形式の書式の追加情報を指定する場合、このパラメーターの値を指定*cfFormat*します。 他のフィールドの既定値が使用されますが、NULL の場合、`FORMATETC`構造体。

### <a name="remarks"></a>Remarks

この関数は、データがすぐに指定されていないため、遅延レンダリングを使用してデータを提供します。 [は](#onrenderdata)または[によって](#onrenderglobaldata)メンバー関数は、データを要求します。

使用してデータを指定しない場合は、この関数を使用して、`CFile`オブジェクト。 使用してデータを指定する場合、`CFile`オブジェクトを呼び出し、 [DelayRenderFileData](#delayrenderfiledata)メンバー関数。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース。操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。

即時のレンダリングを使用する呼び出し、 [CacheData](#cachedata)または[使う](#cacheglobaldata)メンバー関数。

詳細については、次を参照してください。、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK の構造体。

詳細については、次を参照してください。[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)Windows SDK に含まれています。

##  <a name="delayrenderfiledata"></a>  COleDataSource::DelayRenderFileData

提供されるデータのデータ転送操作の形式を指定するには、この関数を呼び出します。

```
void DelayRenderFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cfFormat*<br/>
データが提供されるクリップボード形式。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)関数。

*lpFormatEtc*<br/>
指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)提供されるデータの形式を記述する構造体。 指定されたクリップボード形式の書式の追加情報を指定する場合、このパラメーターの値を指定*cfFormat*します。 他のフィールドの既定値が使用されますが、NULL の場合、`FORMATETC`構造体。

### <a name="remarks"></a>Remarks

この関数は、データがすぐに指定されていないため、遅延レンダリングを使用してデータを提供します。 [可変](#onrenderfiledata)メンバー関数は、データを要求します。

使用する場合は、この関数を使用して、`CFile`データを提供するオブジェクト。 使用しようとしていない場合、`CFile`オブジェクトを呼び出し、[に](#delayrenderdata)メンバー関数。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース。操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。

即時のレンダリングを使用する呼び出し、 [CacheData](#cachedata)または[使う](#cacheglobaldata)メンバー関数。

詳細については、次を参照してください。、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK の構造体。

詳細については、次を参照してください。[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)Windows SDK に含まれています。

##  <a name="delaysetdata"></a>  COleDataSource::DelaySetData

データ ソースの内容の変更をサポートするためには、この関数を呼び出します。

```
void DelaySetData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cfFormat*<br/>
データの配置先のクリップボード形式。 このパラメーターは、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)関数。

*lpFormatEtc*<br/>
指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)データの交換形式を記述する構造体。 指定されたクリップボード形式の書式の追加情報を指定する場合、このパラメーターの値を指定*cfFormat*します。 他のフィールドの既定値が使用されますが、NULL の場合、`FORMATETC`構造体。

### <a name="remarks"></a>Remarks

[データ変更](#onsetdata)このような場合に、フレームワークが呼び出します。 フレームワークからのデータ ソースが返されるときにだけ使用[は](../../mfc/reference/coleserveritem-class.md#getdatasource)します。 場合`DelaySetData`は呼び出されません、`OnSetData`関数は呼び出されません。 `DelaySetData` クリップボードの内容が各呼び出す必要がありますまたは`FORMATETC`をサポートする形式。

詳細については、次を参照してください。、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK の構造体。

詳細については、次を参照してください。[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)Windows SDK に含まれています。

##  <a name="dodragdrop"></a>  COleDataSource::DoDragDrop

呼び出す、`DoDragDrop`メンバー関数は通常、このデータ ソースのドラッグ アンド ドロップ操作を実行する、 [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)ハンドラー。

```
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,
    LPCRECT lpRectStartDrag = NULL,
    COleDropSource* pDropSource = NULL);
```

### <a name="parameters"></a>パラメーター

*dwEffects*<br/>
ドラッグ アンド ドロップ操作ができるこのデータ ソース。 次の 1 つ以上を指定できます。

- DROPEFFECT_COPY コピー操作を実行できます。

- 行った移動操作を実行できます。

- 元のデータをドロップしたデータから DROPEFFECT_LINK A リンクを確立でした。

- DROPEFFECT_SCROLL では、ドラッグのスクロール操作が発生することを示します。

*lpRectStartDrag*<br/>
実際には、ドラッグの開始位置を定義する四角形を指すポインター。 詳細については、「解説」を参照してください。

*pDropSource*<br/>
ドロップ ソースへのポインター。 場合の既定の実装は、NULL [COleDropSource](../../mfc/reference/coledropsource-class.md)使用されます。

### <a name="return-value"></a>戻り値

ドラッグ アンド ドロップ操作によって生成される効果をドロップします。それ以外の場合せず、操作を開始しないため、指定された四角形を終了する前に、マウス ボタンを離した場合。

### <a name="remarks"></a>Remarks

ドラッグ アンド ドロップ操作はすぐに開始されません。 指定された四角形をマウス カーソルが離れる待機*lpRectStartDrag*または指定したミリ秒数が経過するまでです。 場合*lpRectStartDrag*が null の場合、四角形のサイズが 1 ピクセルです。

時刻の遅延は、レジストリ キーの設定によって指定されます。 遅延時間を変更するには呼び出すことによって[CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[cwinapp::writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)します。 遅延時間を指定しない場合は、200 ミリ秒の既定値が使用されます。 ドラッグの遅延時間は、次のように格納されます。

- Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay に格納されます。

- Windows 3.x ドラッグの遅延時間は、WIN に格納されます。INI ファイルの [Windows} セクション。

- Windows 95/98 ドラッグ遅延時間は、WIN のキャッシュされたバージョンに格納されます。INI します。

レジストリのいずれかの遅延情報が格納されている方法の詳細についてはドラッグのまたはします。INI ファイルを参照してください[WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) Windows SDK に含まれています。

詳細については、この記事を参照してください。[ドラッグ アンド ドロップします。ドロップ ソースの実装](../../mfc/drag-and-drop-implementing-a-drop-source.md)します。

##  <a name="empty"></a>  COleDataSource::Empty

この関数は、空を呼び出して、`COleDataSource`データのオブジェクト。

```
void Empty();
```

### <a name="remarks"></a>Remarks

両方のキャッシュし、再利用できるように、遅延レンダリング フォーマットが空にします。

詳細については、次を参照してください。 [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) Windows SDK に含まれています。

##  <a name="flushclipboard"></a>  COleDataSource::FlushClipboard

クリップボードにおよび、アプリケーションのシャット ダウンした後、クリップボードからデータをペーストできますし、データを表示します。

```
static void PASCAL FlushClipboard();
```

### <a name="remarks"></a>Remarks

使用[SetClipboard](#setclipboard)をクリップボードにデータを格納します。

##  <a name="getclipboardowner"></a>  COleDataSource::GetClipboardOwner

クリップボードにデータが変更されたかどうかを判断します[SetClipboard](#setclipboard)と、最後に呼び出された場合は、現在の所有者を識別します。

```
static COleDataSource* PASCAL GetClipboardOwner();
```

### <a name="return-value"></a>戻り値

データは、クリップボードに現在ソースか、クリップボードがない場合、またはクリップボードが呼び出し元アプリケーションによって所有されていない場合は NULL。

##  <a name="onrenderdata"></a>  COleDataSource::OnRenderData

指定された形式でデータを取得するためにフレームワークによって呼び出されます。

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>パラメーター

*lpFormatEtc*<br/>
指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)情報が要求された形式を指定します。

*lpStgMedium*<br/>
指す、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)データが返される構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](#delayrenderdata)または[DelayRenderFileData](#delayrenderfiledata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を呼び出す[可変](#onrenderfiledata)または[によって](#onrenderglobaldata)場合は、指定したストレージ メディアは、ファイルまたはメモリ、それぞれします。 これらの形式のどちらを指定した場合、既定の実装は 0 が返され、何もしません。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース。操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。

場合*lpStgMedium*-> *tymed* TYMED_NULL には、`STGMEDIUM`割り当てられで指定したとおりに入力する必要があります*lpFormatEtc tymed]-> [* します。 TYMED_NULL、ない場合、`STGMEDIUM`のデータが配置を入力する必要があります。

これは、高度なオーバーライド可能な。 要求された形式および中規模のデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドすることがあります。 データが小さく、固定サイズの場合は、オーバーライド`OnRenderGlobalData`します。 データは、ファイルでは、または可変サイズは、オーバーライド`OnRenderFileData`します。

詳細については、次を参照してください、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)と[FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)構造体、 [TYMED](/windows/desktop/api/objidl/ne-objidl-tagtymed)列挙型、および[IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) 。で、Windows SDK。

##  <a name="onrenderfiledata"></a>  COleDataSource::OnRenderFileData

ファイルの指定したストレージ メディアは、指定された形式でデータを取得するためにフレームワークによって呼び出されます。

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>パラメーター

*lpFormatEtc*<br/>
指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)情報が要求された形式を指定します。

*pFile*<br/>
指す、 [CFile](../../mfc/reference/cfile-class.md)データがレンダリングされるオブジェクト。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装は、単に FALSE を返します。

これは、高度なオーバーライド可能な。 要求された形式および中規模のデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドする可能性があります。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)します。 データは、ファイルでは、または可変サイズは、オーバーライド`OnRenderFileData`します。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース。操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。

詳細については、次を参照してください。、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)構造と[IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK に含まれています。

##  <a name="onrenderglobaldata"></a>  COleDataSource::OnRenderGlobalData

指定したストレージ メディアがグローバル メモリに指定された形式でデータを取得するためにフレームワークによって呼び出されます。

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>パラメーター

*lpFormatEtc*<br/>
指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)情報が要求された形式を指定します。

*phGlobal*<br/>
データが返されるグローバル メモリ ハンドルへのポインター。 いずれかがまだ割り当てられていない場合、このパラメーターは NULL を指定できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装は、単に FALSE を返します。

場合*phGlobal*新しい HGLOBAL を割り当てられで返される必要がありますし、NULL の場合は、 *phGlobal*します。 指定された、HGLOBAL のそれ以外の場合、 *phGlobal*データが格納される必要があります。 HGLOBAL で配置されるデータ量は、メモリ ブロックの現在のサイズを超えない必要があります。 また、ブロックより大きなサイズに再割り当てできることはできません。

これは、高度なオーバーライド可能な。 要求された形式および中規模のデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドすることがあります。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)します。 データは、ファイルでは、または可変サイズは、オーバーライド[可変](#onrenderfiledata)します。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース。操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。

詳細については、次を参照してください。、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)構造と[IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) Windows SDK に含まれています。

##  <a name="onsetdata"></a>  COleDataSource::OnSetData

設定または内のデータを置換するためにフレームワークによって呼び出される、`COleDataSource`指定した形式のオブジェクト。

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>パラメーター

*lpFormatEtc*<br/>
指す、 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)データを交換する形式を指定します。

*lpStgMedium*<br/>
指す、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)を現在の内容を置き換えるデータを含む構造体、`COleDataSource`オブジェクト。

*bRelease*<br/>
関数呼び出しの完了後、ストレージ メディアの所有権を持っているユーザーを示します。 呼び出し元は、ストレージ メディアの代わりに割り当てられたリソースを解放するため担当するユーザーを決定します。 呼び出し元は設定することによって*bRelease*します。 場合*bRelease*が 0 以外の場合、データ ソースが所有権、使用が完了したら、メディアを解放します。 ときに*bRelease* 0 は、呼び出し元が所有権を保持およびデータ ソースは、ストレージ メディアを使用して、呼び出しの期間に対してのみです。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

正常に取得するまで、データ ソースによるデータの所有権はなりません。 つまり、その所有権を持ちません場合`OnSetData`0 を返します。 呼び出すことによってストレージ メディアを解放、データ ソースに所有権がある場合は、パラメーター、 [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium)関数。

既定の実装では、何も行われません。 指定された形式でデータを置換するには、この関数をオーバーライドします。 これは、高度なオーバーライド可能な。

詳細については、次を参照してください、 [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium)と[FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc)構造体と[ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium)と[IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) 。Windows SDK で機能します。

##  <a name="setclipboard"></a>  COleDataSource::SetClipboard

含まれるデータの格納、`COleDataSource`後、次の関数のいずれかを呼び出してクリップボード上のオブジェクト。[CacheData](#cachedata)、[使う](#cacheglobaldata)、[に](#delayrenderdata)、または[DelayRenderFileData](#delayrenderfiledata)します。

```
void SetClipboard();
```

## <a name="see-also"></a>関連項目

[MFC サンプル HIERSVR](../../visual-cpp-samples.md)<br/>
[MFC サンプルの OCLIENT](../../visual-cpp-samples.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDataObject クラス](../../mfc/reference/coledataobject-class.md)
