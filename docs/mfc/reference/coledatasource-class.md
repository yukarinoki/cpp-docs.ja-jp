---
title: COleDataSource クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4df2584bd9b74640266d8ddf87087e2820deaac8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376708"
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
|[取得](#cachedata)|使用して、指定された形式でデータを提供する**STGMEDIUM**構造体。|  
|[COleDataSource::CacheGlobalData](#cacheglobaldata)|使用して、指定された形式でデータを提供する`HGLOBAL`です。|  
|[COleDataSource::DelayRenderData](#delayrenderdata)|遅延レンダリングを使用して、指定された形式でデータを提供します。|  
|[COleDataSource::DelayRenderFileData](#delayrenderfiledata)|指定された形式でデータを提供する`CFile`ポインター。|  
|[COleDataSource::DelaySetData](#delaysetdata)|サポートされているすべての形式と呼ばれる`OnSetData`です。|  
|[された](#dodragdrop)|データ ソースをドラッグ アンド ドロップ操作を実行します。|  
|[COleDataSource::Empty](#empty)|空にして、`COleDataSource`データのオブジェクト。|  
|[COleDataSource::FlushClipboard](#flushclipboard)|クリップボードにすべてのデータを表示します。|  
|[COleDataSource::GetClipboardOwner](#getclipboardowner)|データがクリップボードに配置がまだ存在を確認します。|  
|[と](#onrenderdata)|遅延レンダリングの一部としてデータを取得します。|  
|[と](#onrenderfiledata)|データを取得、`CFile`遅延レンダリングの一部として。|  
|[COleDataSource::OnRenderGlobalData](#onrenderglobaldata)|データを取得、`HGLOBAL`遅延レンダリングの一部として。|  
|[COleDataSource::OnSetData](#onsetdata)|データを置換すると呼ばれる、`COleDataSource`オブジェクト。|  
|[COleDataSource::SetClipboard](#setclipboard)|場所、`COleDataSource`クリップボード上のオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 OLE のデータ ソースを直接作成することができます。 または、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)と[COleServerItem](../../mfc/reference/coleserveritem-class.md)クラスへの応答の OLE データ ソースの作成、`CopyToClipboard`と`DoDragDrop`メンバー関数。 参照してください[COleServerItem::CopyToClipboard](../../mfc/reference/coleserveritem-class.md#copytoclipboard)簡単な説明。 上書き、`OnGetClipboardData`の OLE データ ソース内のデータに追加のクリップボード形式を追加するクライアント アイテムまたはサーバー項目クラスのメンバー関数が作成された、`CopyToClipboard`または`DoDragDrop`メンバー関数。  
  
 転送するデータを準備するときにこのクラスのオブジェクトを作成、データの最適な方法を使ってデータを入力してください。 データ ソースに挿入される方法は直接影響を受けたデータがすぐに提供されるかどうか (即時レンダリング)、またはオンデマンドで (遅延レンダリング)。 クリップボードの形式が使用されるクリップボードの形式を渡すことによってデータを提供するすべての (省略可能[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体)、呼び出す[に](#delayrenderdata)です。  
  
 データ ソースおよびデータ転送する方法の詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)です。 さらに、アーティクル[クリップボード トピック](../../mfc/clipboard.md)OLE クリップボード機構について説明します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="cachedata"></a>  取得  
 この関数では、データが提供するデータの中に転送操作の形式を指定します。  
  
```  
void CacheData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが提供されるがクリップボードの形式です。 このパラメーターには、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)指定された形式のデータを含む構造体。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)提示されるデータの形式を記述する構造体。 指定されたクリップボードの形式の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`です。 ある場合**NULL**、既定値は、他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 この関数が即時の表示を使用して、提供されるため、データを指定してください。 データが必要になるまでにキャッシュされます。  
  
 データを使用して、提供、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)構造体。 使用することも、`CacheGlobalData`データの量を指定している場合、メンバー関数がそれを使用して効率的に転送するほど、`HGLOBAL`です。  
  
 呼び出し後`CacheData`、 **ptd**のメンバー`lpFormatEtc`とその内容の`lpStgMedium`呼び出し元ではなく、データ オブジェクトが所有します。  
  
 遅延レンダリングを使用するのには、呼び出し、[に](#delayrenderdata)または[DelayRenderFileData](#delayrenderfiledata)メンバー関数。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)です。  
  
 詳細については、次を参照してください。、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK 内の構造体。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="cacheglobaldata"></a>  COleDataSource::CacheGlobalData  
 この関数では、データが提供するデータの中に転送操作の形式を指定します。  
  
```  
void CacheGlobalData(
    CLIPFORMAT cfFormat,  
    HGLOBAL hGlobal,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが提供されるがクリップボードの形式です。 このパラメーターには、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 *hGlobal*  
 指定された形式のデータを含むグローバル メモリ ブロックへのハンドルします。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)提示されるデータの形式を記述する構造体。 指定されたクリップボードの形式の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`です。 ある場合**NULL**、既定値は、他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 この関数は、;、関数を呼び出すときにデータを指定する必要がありますので、即時の表示を使用してデータを提供します。データが必要になるまでにキャッシュされます。 使用して、`CacheData`大量のデータまたは構造化された記憶域メディアが必要なかどうかを指定している場合、メンバー関数。  
  
 遅延レンダリングを使用するのには、呼び出し、[に](#delayrenderdata)または[DelayRenderFileData](#delayrenderfiledata)メンバー関数。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)です。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK 内の構造。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="coledatasource"></a>  COleDataSource::COleDataSource  
 `COleDataSource` オブジェクトを構築します。  
  
```  
COleDataSource();
```  
  
##  <a name="delayrenderdata"></a>  COleDataSource::DelayRenderData  
 この関数では、データが提供するデータの中に転送操作の形式を指定します。  
  
```  
void DelayRenderData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが提供されるがクリップボードの形式です。 このパラメーターには、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)提示されるデータの形式を記述する構造体。 指定されたクリップボードの形式の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`です。 ある場合**NULL**、既定値は、他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 この関数は、データがすぐに指定されていないので、遅延レンダリングを使用してデータを提供します。 [は](#onrenderdata)または[によって](#onrenderglobaldata)データを要求するメンバー関数が呼び出されます。  
  
 使ってデータを指定しない場合は、この関数を使用して、`CFile`オブジェクト。 データを提供しようとする場合、`CFile`オブジェクトを呼び出す、 [DelayRenderFileData](#delayrenderfiledata)メンバー関数。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)です。  
  
 即時の表示を使用するのには、呼び出し、 [CacheData](#cachedata)または[使う](#cacheglobaldata)メンバー関数。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK 内の構造。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="delayrenderfiledata"></a>  COleDataSource::DelayRenderFileData  
 この関数では、データが提供するデータの中に転送操作の形式を指定します。  
  
```  
void DelayRenderFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが提供されるがクリップボードの形式です。 このパラメーターには、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)提示されるデータの形式を記述する構造体。 指定されたクリップボードの形式の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`です。 ある場合**NULL**、既定値は、他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 この関数は、データがすぐに指定されていないので、遅延レンダリングを使用してデータを提供します。 [可変](#onrenderfiledata)データを要求するメンバー関数が呼び出されます。  
  
 使用する場合は、この関数を使用して、`CFile`データを提供するオブジェクト。 使用しない場合、`CFile`オブジェクトを呼び出し、[に](#delayrenderdata)メンバー関数。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)です。  
  
 即時の表示を使用するのには、呼び出し、 [CacheData](#cachedata)または[使う](#cacheglobaldata)メンバー関数。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK 内の構造。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="delaysetdata"></a>  COleDataSource::DelaySetData  
 データ ソースの内容の変更をサポートするためには、この関数を呼び出します。  
  
```  
void DelaySetData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 クリップボードの形式をデータを配置します。 このパラメーターには、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)置き換えられるデータの形式を記述する構造体。 指定されたクリップボードの形式の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`です。 ある場合**NULL**、既定値は、他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="remarks"></a>コメント  
 [データ変更](#onsetdata)このような場合に、フレームワークによって呼び出されますが。 フレームワークからのデータ ソースが返されるときにだけ使用[は](../../mfc/reference/coleserveritem-class.md#getdatasource)します。 場合`DelaySetData`は呼び出されません、`OnSetData`関数は呼び出されません。 `DelaySetData` クリップボードの内容がそれぞれ呼び出す必要がありますまたは**FORMATETC**をサポートする形式。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK 内の構造。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="dodragdrop"></a>  された  
 呼び出す、`DoDragDrop`で通常、このデータ ソースのドラッグ アンド ドロップ操作を実行するメンバー関数、 [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)ハンドラー。  
  
```  
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,  
    LPCRECT lpRectStartDrag = NULL,  
    COleDropSource* pDropSource = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwEffects`  
 ドラッグ アンド ドロップ操作ができるこのデータ ソース。 次の 1 つ以上を指定できます。  
  
- `DROPEFFECT_COPY` コピー操作を実行する可能性があります。  
  
- `DROPEFFECT_MOVE` 移動操作を実行できませんでした。  
  
- `DROPEFFECT_LINK` ドロップされたデータから、元のデータへのリンクを確立できませんでした。  
  
- `DROPEFFECT_SCROLL` ドラッグ スクロール操作が行われる可能性を示します。  
  
 `lpRectStartDrag`  
 実際には、ドラッグの開始位置を定義する四角形を指すポインター。 詳細については、「解説」を参照してください。  
  
 *pDropSource*  
 ドロップ ソースへのポインター。 場合**NULL**の既定の実装、 [COleDropSource](../../mfc/reference/coledropsource-class.md)使用されます。  
  
### <a name="return-value"></a>戻り値  
 ドロップ操作のドラッグ アンド ドロップ操作によって生成される結果それ以外の場合`DROPEFFECT_NONE`場合は、操作は、ユーザーが指定された四角形を終了する前に、マウス ボタンを解放するために決してが開始します。  
  
### <a name="remarks"></a>コメント  
 ドラッグ アンド ドロップ操作がすぐに開始しません。 によって指定される四角形をマウス カーソルが離れるまで待機して`lpRectStartDrag`または指定したミリ秒数が経過するまでです。 場合`lpRectStartDrag`は**NULL**、四角形のサイズは 1 ピクセルです。  
  
 遅延時間は、レジストリ キー設定によって指定されます。 遅延時間を変更するには呼び出すことによって[CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[cwinapp::writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)です。 遅延時間を指定しない場合は、200 ミリ秒の既定値が使用されます。 ドラッグの遅延時間は、次のように格納されます。  
  
-   Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay に格納されます。  
  
-   Windows 3.x ドラッグ遅延時間は、WIN に格納されます。INI ファイルの [Windows} セクションです。  
  
-   Windows 95/98 ドラッグ遅延時間は、WIN のキャッシュされたバージョンに格納されます。INI です。  
  
 遅延の情報は、レジストリに格納されている方法の詳細についてドラッグのまたはします。INI ファイルを参照してください[WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504) Windows SDK に含まれています。  
  
 詳細については、記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ソースの実装](../../mfc/drag-and-drop-implementing-a-drop-source.md)です。  
  
##  <a name="empty"></a>  COleDataSource::Empty  
 空には、この関数を呼び出して、`COleDataSource`データのオブジェクト。  
  
```  
void Empty();
```  
  
### <a name="remarks"></a>コメント  
 両方をキャッシュし、再利用できるように、遅延レンダリングされた形式が空にします。  
  
 詳細については、次を参照してください。 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491) Windows SDK に含まれています。  
  
##  <a name="flushclipboard"></a>  COleDataSource::FlushClipboard  
 データをクリップボードにし、アプリケーションのシャット ダウン後に、クリップボードからデータを貼り付けすることができますをレンダリングします。  
  
```  
static void PASCAL FlushClipboard();
```  
  
### <a name="remarks"></a>コメント  
 使用して[SetClipboard](#setclipboard)をクリップボードにデータを格納します。  
  
##  <a name="getclipboardowner"></a>  COleDataSource::GetClipboardOwner  
 以降、クリップボードのデータが変更されたかどうかを判断[SetClipboard](#setclipboard)と、最後に呼び出された場合は、現在の所有者を識別します。  
  
```  
static COleDataSource* PASCAL GetClipboardOwner();
```  
  
### <a name="return-value"></a>戻り値  
 現在、クリップボードにデータ ソースまたは**NULL**クリップボードにコピーがない場合、またはクリップボードが呼び出し元アプリケーションによって所有されていません。  
  
##  <a name="onrenderdata"></a>  と  
 指定された形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データが返される構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 以前に指定の形式は、`COleDataSource`オブジェクトを使用して、[に](#delayrenderdata)または[DelayRenderFileData](#delayrenderfiledata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を呼び出す[可変](#onrenderfiledata)または[によって](#onrenderglobaldata)場合は、指定されたストレージ メディア ファイルまたはメモリ、それぞれします。 これらの形式のどちらも、指定した場合、既定の実装は 0 を返し、何もしません。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)です。  
  
 場合`lpStgMedium` ->  *tymed*は**TYMED_NULL**、 **STGMEDIUM**割り当てられで指定された入力*lpFormatEtc ->tymed*です。 ない場合は**TYMED_NULL**、 **STGMEDIUM**のデータが配置を入力する必要があります。  
  
 これは、高度なオーバーライド可能です。 要求された形式および中規模でデータを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンの 1 つを上書きする可能性があります。 データが小規模で固定サイズの場合は、オーバーライド`OnRenderGlobalData`です。 データをファイル内や可変サイズのオーバーライド`OnRenderFileData`です。  
  
 詳細については、次を参照してください、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体、 [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227)列挙型、および[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) 。windows SDK。  
  
##  <a name="onrenderfiledata"></a>  と  
 指定されたストレージ メディア ファイルは、ときに、指定された形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `pFile`  
 指す、 [CFile](../../mfc/reference/cfile-class.md)データが表示されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 以前に指定の形式は、`COleDataSource`オブジェクトを使用して、[に](#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を単純に返します**FALSE**です。  
  
 これは、高度なオーバーライド可能です。 要求された形式および中規模でデータを提供するには、この関数をオーバーライドします。 によっては、データは、代わりにこの関数の他のバージョンの 1 つをオーバーライドすることができます。 複数の記憶域メディアを処理する場合は、オーバーライド[は](#onrenderdata)します。 データをファイル内や可変サイズのオーバーライド`OnRenderFileData`です。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)です。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造と[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK に含まれています。  
  
##  <a name="onrenderglobaldata"></a>  COleDataSource::OnRenderGlobalData  
 指定されたストレージ メディアが使用するグローバル メモリに指定された形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `phGlobal`  
 データが返されるグローバル メモリへのハンドルへのポインター。 このパラメーターを指定できますいずれかがまだ割り当てられていない場合、 **NULL**です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 以前に指定の形式は、`COleDataSource`オブジェクトを使用して、[に](#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を単純に返します**FALSE**です。  
  
 場合`phGlobal`は**NULL**、し、新しい`HGLOBAL`割り当てられで返される必要があります`phGlobal`です。 それ以外の場合、`HGLOBAL`によって指定された`phGlobal`データを格納する必要があります。 内に配置するデータ量、`HGLOBAL`メモリ ブロックの現在のサイズを超えない必要があります。 また、ブロックは、大きいサイズに再割り当てできません。  
  
 これは、高度なオーバーライド可能です。 要求された形式および中規模でデータを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンの 1 つを上書きする可能性があります。 複数の記憶域メディアを処理する場合は、オーバーライド[は](#onrenderdata)します。 データをファイル内や可変サイズのオーバーライド[可変](#onrenderfiledata)です。 詳細については遅延レンダリングの MFC で処理されるは、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)です。  
  
 詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造と[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK に含まれています。  
  
##  <a name="onsetdata"></a>  COleDataSource::OnSetData  
 設定または内のデータを置換するためにフレームワークによって呼び出される、`COleDataSource`指定された形式でのオブジェクト。  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データを交換する形式を指定します。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)の現在の内容で置換されるデータを含む構造体、`COleDataSource`オブジェクト。  
  
 `bRelease`  
 関数呼び出しを完了した後、記憶域メディアの所有権を持っているユーザーを示します。 呼び出し元は、ストレージ メディア代理で割り当てられたリソースを解放する担当者を決定します。 呼び出し元は設定することで`bRelease`です。 場合`bRelease`は 0 以外の場合、データ ソース所有権を終了時に使用するメディアを解放します。 ときに`bRelease`0 は、呼び出し元が所有権を保持およびデータ ソースは、呼び出しの間でのみストレージ メディアを使用できます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 正常に取得するまで、データ ソースは、データの所有権になりません。 つまり、その所有権を持ちません場合`OnSetData`0 を返します。 データ ソースの所有権を呼び出すことによってストレージ メディアを解放、 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491)関数。  
  
 既定の実装では、何も行われません。 指定された形式でデータを置換するには、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。  
  
 詳細については、次を参照してください、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体および[ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491)と[IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) 。Windows SDK で機能します。  
  
##  <a name="setclipboard"></a>  COleDataSource::SetClipboard  
 含まれるデータを格納、 `COleDataSource` 、次の関数の 1 つを呼び出した後に、クリップボード上のオブジェクト: [CacheData](#cachedata)、[使う](#cacheglobaldata)、[に](#delayrenderdata)、または[DelayRenderFileData](#delayrenderfiledata)です。  
  
```  
void SetClipboard();
```  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [MFC サンプル OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDataObject クラス](../../mfc/reference/coledataobject-class.md)
