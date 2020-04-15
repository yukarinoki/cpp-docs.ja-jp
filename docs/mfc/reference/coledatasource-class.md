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
ms.openlocfilehash: fcf9505a7792aea6807e37f05cd1cb1aaad55830
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366117"
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
|[をソース:::コレデータソース](#coledatasource)|`COleDataSource` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をソース::キャッシュデータ](#cachedata)|構造体を使用して、指定した形式`STGMEDIUM`でデータを提供します。|
|[をソース::キャッシュグローバルデータ](#cacheglobaldata)|HGLOBAL を使用して、指定された形式でデータを提供します。|
|[:Dデータを提供します。](#delayrenderdata)|遅延レンダリングを使用して、指定した形式でデータを提供します。|
|[データを:D](#delayrenderfiledata)|ポインター内の指定された形式のデータ`CFile`を提供します。|
|[:Dデータデータ](#delaysetdata)|でサポートされているすべての形式に対して呼`OnSetData`び出されます。|
|[:Do ドラッグドロップ](#dodragdrop)|データ ソースでドラッグ アンド ドロップ操作を実行します。|
|[を指定します。](#empty)|データのオブジェクト`COleDataSource`を空にします。|
|[を使用します。](#flushclipboard)|すべてのデータをクリップボードにレンダリングします。|
|[を取得します。](#getclipboardowner)|クリップボードに格納されているデータがまだ存在することを確認します。|
|[データソース::オンレンダリングデータ](#onrenderdata)|遅延レンダリングの一部としてデータを取得します。|
|[データを表示します。](#onrenderfiledata)|遅延レンダリングの一部`CFile`としてデータを取得します。|
|[データソース::オンレンダリンググローバルデータ](#onrenderglobaldata)|遅延レンダリングの一部として、HGLOBAL にデータを取得します。|
|[を使用します。](#onsetdata)|オブジェクト内のデータを置き`COleDataSource`換えるために呼び出されます。|
|[クリップボードを設定します。](#setclipboard)|オブジェクトを`COleDataSource`クリップボードに配置します。|

## <a name="remarks"></a>解説

OLE データ ソースは直接作成できます。 または、[クラス](../../mfc/reference/coleclientitem-class.md)[は、](../../mfc/reference/coleserveritem-class.md)そのクラスと`CopyToClipboard``DoDragDrop`メンバー関数に応答して OLE データ ソースを作成します。 簡単[な説明については、COleServerItem::クリップボードのコピー](../../mfc/reference/coleserveritem-class.md#copytoclipboard)を参照してください。 または`OnGetClipboardData`メンバー関数用に作成された OLE データ ソースのデータにクリップボード形式を追加するには、クライアント アイテムまたは`CopyToClipboard``DoDragDrop`サーバー アイテム クラスのメンバー関数をオーバーライドします。

転送用のデータを準備する場合は、このクラスのオブジェクトを作成し、データに最適な方法を使用してデータをデータに入力する必要があります。 データ ソースへの挿入方法は、データが即時に提供されるか (即時レンダリング)、オンデマンド(遅延レンダリング)かによって直接影響を受けます。 使用するクリップボード形式 (およびオプションの[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体) を渡してデータを提供するすべてのクリップボード形式に対して[、DelayRenderData](#delayrenderdata)を呼び出します。

データ ソースとデータ転送の詳細については、「[データ オブジェクトとデータ ソース (OLE)」](../../mfc/data-objects-and-data-sources-ole.md)を参照してください。 また、この記事の[「クリップボード トピック」では](../../mfc/clipboard.md)、OLE クリップボードのメカニズムについて説明しています。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDataSource`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coledatasourcecachedata"></a><a name="cachedata"></a>をソース::キャッシュデータ

データ転送操作中にデータが提供される形式を指定します。

```
void CacheData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cf フォーマット*<br/>
データを提供するクリップボード形式。 このパラメーターには、定義済みのクリップボード形式の 1 つ、またはネイティブの Windows[の登録クリップボード形式](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値を指定できます。

*中程度*<br/>
指定された形式のデータを含む[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体へのポイント。

*フォーマットの問題*<br/>
データが提供される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。 *cfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメータの値を指定します。 NULL の場合、デフォルト値は構造体の他のフィールドに`FORMATETC`使用されます。

### <a name="remarks"></a>解説

この関数は即時レンダリングを使用してデータを提供するため、データを指定する必要があります。 データは必要になるまでキャッシュされます。

[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体を使用してデータを提供します。 また、提供する`CacheGlobalData`データの量が HGLOBAL を使用して効率的に転送できるほど小さい場合にも、メンバー関数を使用できます。

の`CacheData``ptd`メンバー`lpFormatEtc`への呼び出し後、および*lpStgMedium*の内容は、呼び出し元ではなく、データ オブジェクトによって所有されます。

遅延レンダリングを使用するには、[メンバー](#delayrenderdata)関数を呼び出[します](#delayrenderfiledata)。 MFC で処理される遅延レンダリングの詳細については、「[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)」を参照してください。

詳細については、Windows SDK の[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)および[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を参照してください。

詳細については、「Windows SDK で[クリップボードの書式を登録](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)する」を参照してください。

## <a name="coledatasourcecacheglobaldata"></a><a name="cacheglobaldata"></a>をソース::キャッシュグローバルデータ

データ転送操作中にデータが提供される形式を指定します。

```
void CacheGlobalData(
    CLIPFORMAT cfFormat,
    HGLOBAL hGlobal,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cf フォーマット*<br/>
データを提供するクリップボード形式。 このパラメーターには、定義済みのクリップボード形式の 1 つ、またはネイティブの Windows[の登録クリップボード形式](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値を指定できます。

*Hglobal*<br/>
指定された形式のデータを含むグローバル メモリ ブロックへのハンドル。

*フォーマットの問題*<br/>
データが提供される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。 *cfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメータの値を指定します。 NULL の場合、デフォルト値は構造体の他のフィールドに`FORMATETC`使用されます。

### <a name="remarks"></a>解説

この関数は、即時レンダリングを使用してデータを提供するため、関数を呼び出すときにデータを指定する必要があります。データは必要になるまでキャッシュされます。 大量の`CacheData`データを提供する場合、または構造化ストレージ・メディアが必要な場合は、メンバー関数を使用します。

遅延レンダリングを使用するには、[メンバー](#delayrenderdata)関数を呼び出[します](#delayrenderfiledata)。 MFC で処理される遅延レンダリングの詳細については、「[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)」を参照してください。

詳細については、Windows SDK の[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を参照してください。

詳細については、「Windows SDK で[クリップボードの書式を登録](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)する」を参照してください。

## <a name="coledatasourcecoledatasource"></a><a name="coledatasource"></a>をソース:::コレデータソース

`COleDataSource` オブジェクトを構築します。

```
COleDataSource();
```

## <a name="coledatasourcedelayrenderdata"></a><a name="delayrenderdata"></a>:Dデータを提供します。

データ転送操作中にデータが提供される形式を指定します。

```
void DelayRenderData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cf フォーマット*<br/>
データを提供するクリップボード形式。 このパラメーターには、定義済みのクリップボード形式の 1 つ、またはネイティブの Windows[の登録クリップボード形式](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値を指定できます。

*フォーマットの問題*<br/>
データが提供される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。 *cfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメータの値を指定します。 NULL の場合、デフォルト値は構造体の他のフィールドに`FORMATETC`使用されます。

### <a name="remarks"></a>解説

この関数は遅延レンダリングを使用してデータを提供するため、データはすぐには提供されません。 メンバー[関数が呼](#onrenderdata)び[OnRenderGlobalData](#onrenderglobaldata)出され、データが要求されます。

オブジェクトを介してデータを提供しない場合は、この関数を`CFile`使用します。 `CFile`オブジェクトを介してデータを指定する場合は、[メンバー](#delayrenderfiledata)関数を呼び出します。 MFC で処理される遅延レンダリングの詳細については、「[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)」を参照してください。

即時レンダリングを使用するには、[メンバー](#cachedata)関数を呼[CacheGlobalData](#cacheglobaldata)び出します。

詳細については、Windows SDK の[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を参照してください。

詳細については、「Windows SDK で[クリップボードの書式を登録](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)する」を参照してください。

## <a name="coledatasourcedelayrenderfiledata"></a><a name="delayrenderfiledata"></a>データを:D

データ転送操作中にデータが提供される形式を指定します。

```
void DelayRenderFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cf フォーマット*<br/>
データを提供するクリップボード形式。 このパラメーターには、定義済みのクリップボード形式の 1 つ、またはネイティブの Windows[の登録クリップボード形式](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値を指定できます。

*フォーマットの問題*<br/>
データが提供される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。 *cfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメータの値を指定します。 NULL の場合、デフォルト値は構造体の他のフィールドに`FORMATETC`使用されます。

### <a name="remarks"></a>解説

この関数は遅延レンダリングを使用してデータを提供するため、データはすぐには提供されません。 メンバー[関数](#onrenderfiledata)が呼び出され、データを要求します。

データを提供するためにオブジェクトを使用する場合は`CFile`、この関数を使用します。 `CFile`オブジェクトを使用しない場合は、[メンバー](#delayrenderdata)関数を呼び出します。 MFC で処理される遅延レンダリングの詳細については、「[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)」を参照してください。

即時レンダリングを使用するには、[メンバー](#cachedata)関数を呼[CacheGlobalData](#cacheglobaldata)び出します。

詳細については、Windows SDK の[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を参照してください。

詳細については、「Windows SDK で[クリップボードの書式を登録](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)する」を参照してください。

## <a name="coledatasourcedelaysetdata"></a><a name="delaysetdata"></a>:Dデータデータ

データ ソースの内容の変更をサポートします。

```
void DelaySetData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cf フォーマット*<br/>
データを配置するクリップボード形式。 このパラメーターには、定義済みのクリップボード形式の 1 つ、またはネイティブの Windows[の登録クリップボード形式](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値を指定できます。

*フォーマットの問題*<br/>
データを置き換える形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。 *cfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメータの値を指定します。 NULL の場合、デフォルト値は構造体の他のフィールドに`FORMATETC`使用されます。

### <a name="remarks"></a>解説

[これが発生すると、OnSetData](#onsetdata)はフレームワークによって呼び出されます。 これは、フレームワークが[COleServerItem から](../../mfc/reference/coleserveritem-class.md#getdatasource)データ ソースを返す場合にのみ使用されます。 呼`DelaySetData`び出されない場合、`OnSetData`関数は呼び出されません。 `DelaySetData`は、サポートするクリップボードまたは`FORMATETC`フォーマットごとに呼び出す必要があります。

詳細については、Windows SDK の[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を参照してください。

詳細については、「Windows SDK で[クリップボードの書式を登録](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)する」を参照してください。

## <a name="coledatasourcedodragdrop"></a><a name="dodragdrop"></a>:Do ドラッグドロップ

このデータ ソースに対してドラッグ アンド ドロップ操作を実行するには、通常[は CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)ハンドラーでメンバー関数を呼び出します。 `DoDragDrop`

```
DROPEFFECT DoDragDrop(
    DWORD dwEffects = DROPEFFECT_COPY|DROPEFFECT_MOVE|DROPEFFECT_LINK,
    LPCRECT lpRectStartDrag = NULL,
    COleDropSource* pDropSource = NULL);
```

### <a name="parameters"></a>パラメーター

*dw エフェクト*<br/>
このデータ ソースで許可されているドラッグ アンド ドロップ操作。 次の 1 つ以上の値を指定できます。

- DROPEFFECT_COPY コピー操作を実行できます。

- DROPEFFECT_MOVE 移動操作を実行できます。

- DROPEFFECT_LINK ドロップされたデータから元のデータへのリンクが確立される可能性があります。

- DROPEFFECT_SCROLL ドラッグ スクロール操作が発生する可能性があることを示します。

*ドラッグを開始します。*<br/>
ドラッグが実際に開始される位置を定義する四角形へのポインター。 詳細については、「解説」を参照してください。

*ソースを指定します。*<br/>
ドロップ ソースへのポイント。 NULL の場合は[、COleDropSource](../../mfc/reference/coledropsource-class.md)の既定の実装が使用されます。

### <a name="return-value"></a>戻り値

ドラッグ アンド ドロップ操作によって生成されるドロップ効果。それ以外の場合は、指定された四角形を離れる前にユーザーがマウス ボタンを離したために操作が開始されない場合はDROPEFFECT_NONE。

### <a name="remarks"></a>解説

ドラッグ アンド ドロップ操作はすぐには開始されません。 このオブジェクトは *、lpRectStartDrag*で指定された四角形からマウス カーソルが離れるまで、または指定されたミリ秒数が経過するまで待機します。 *lpRectStartDrag*が NULL の場合、四角形のサイズは 1 ピクセルです。

遅延時間は、レジストリ キーの設定で指定します。 遅延時間を変更するには[、CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint)を呼び出します。 遅延時間を指定しない場合は、デフォルト値の 200 ミリ秒が使用されます。 ドラッグ遅延時間は次のように保存されます。

- Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\ソフトウェア\Windows\NT\現在のバージョン\IniFileMapping\win.ini\Windows\ドラッグディレイに保存されます。

- ウィンドウズ 3.x ドラッグ遅延時間は WIN に格納されます。INI ファイル、[ウィンドウ] セクションの下。

- Windows 95/98 ドラッグ遅延時間は、キャッシュされたバージョンの WIN に格納されます。Ini。

レジストリまたは .INI ファイルを[参照してください](/windows/win32/api/winbase/nf-winbase-writeprofilestringw)。

詳細については、「 [OLE ドラッグ アンド ドロップ](../../mfc/drag-and-drop-ole.md)」を参照してください。

## <a name="coledatasourceempty"></a><a name="empty"></a>を指定します。

データのオブジェクトを空に`COleDataSource`します。

```
void Empty();
```

### <a name="remarks"></a>解説

キャッシュされたレンダリング形式と遅延レンダリング形式の両方が空になり、再利用できます。

詳細については、Windows SDK[のリリース StgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium)を参照してください。

## <a name="coledatasourceflushclipboard"></a><a name="flushclipboard"></a>を使用します。

クリップボードにあるデータをレンダリングし、アプリケーションのシャットダウン後にクリップボードからデータを貼り付けることができます。

```
static void PASCAL FlushClipboard();
```

### <a name="remarks"></a>解説

クリップボードにデータを格納するには、[クリップボードの設定](#setclipboard)を使用します。

## <a name="coledatasourcegetclipboardowner"></a><a name="getclipboardowner"></a>を取得します。

[SetClipboard](#setclipboard)が最後に呼び出された後でクリップボードのデータが変更されたかどうかを調べ、その場合は現在の所有者を識別します。

```
static COleDataSource* PASCAL GetClipboardOwner();
```

### <a name="return-value"></a>戻り値

クリップボードに現在データ ソースが存在しない場合、またはクリップボードに何も存在しない場合、またはクリップボードが呼び出し元アプリケーションによって所有されていない場合は NULL。

## <a name="coledatasourceonrenderdata"></a><a name="onrenderdata"></a>データソース::オンレンダリングデータ

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

指定された形式は、遅延レンダリングの`COleDataSource`[遅延レンダリングの遅延レンダリングデータまたは DelayRenderFileData](#delayrenderdata)メンバー関数を使用して、オブジェクトに以前に配置された形式です。 [DelayRenderFileData](#delayrenderfiledata) この関数の既定の実装は、指定されたストレージ メディアがそれぞれファイルまたはメモリである場合に[、OnRenderFileData](#onrenderfiledata)または[OnRenderGlobalData](#onrenderglobaldata)を呼び出します。 これらの形式がどちらも指定されていない場合、既定の実装は 0 を返し、何もしません。 MFC で処理される遅延レンダリングの詳細については、「[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)」を参照してください。

*lpStgMedium*-> *のタイム*がTYMED_NULL場合は`STGMEDIUM`、 *lpFormatEtc->のタイム*で指定されたとおりに割り当てられ、埋める必要があります。 TYMED_NULLでない場合は、データを`STGMEDIUM`所定の位置に入力する必要があります。

これは、高度なオーバーライド可能です。 要求された形式とメディアでデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドする必要があります。 データが小さく、サイズが固定されている場合は`OnRenderGlobalData`、 をオーバーライドします。 データがファイル内にある場合、または可変サイズの場合は、`OnRenderFileData`オーバーライドします。

詳細については[、STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体と[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体[、TYMED](/windows/win32/api/objidl/ne-objidl-tymed)列挙型、および Windows SDK の[IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata)を参照してください。

## <a name="coledatasourceonrenderfiledata"></a><a name="onrenderfiledata"></a>データを表示します。

指定されたストレージ メディアがファイルである場合に、指定した形式でデータを取得するためにフレームワークによって呼び出されます。

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>パラメーター

*フォーマットの問題*<br/>
情報が要求される形式を指定する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。

*ファイル*<br/>
データがレンダリングされる[CFile](../../mfc/reference/cfile-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

指定された形式は、遅延レンダリングの`COleDataSource` [DelayRenderData](#delayrenderdata)メンバー関数を使用して、オブジェクトに以前に配置された形式です。 この関数の既定の実装では、単に FALSE が返されます。

これは、高度なオーバーライド可能です。 要求された形式とメディアでデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドする必要があります。 複数のストレージ メディアを処理する場合は[、OnRenderData](#onrenderdata)をオーバーライドします。 データがファイル内にある場合、または可変サイズの場合は、`OnRenderFileData`オーバーライドします。 MFC で処理される遅延レンダリングの詳細については、「[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)」を参照してください。

詳細については、Windows SDK の[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体と[IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata)を参照してください。

## <a name="coledatasourceonrenderglobaldata"></a><a name="onrenderglobaldata"></a>データソース::オンレンダリンググローバルデータ

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
データが返されるグローバル メモリへのハンドルへのポイント。 割り当てられていない場合、このパラメーターは NULL にすることができます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

指定された形式は、遅延レンダリングの`COleDataSource` [DelayRenderData](#delayrenderdata)メンバー関数を使用して、オブジェクトに以前に配置された形式です。 この関数の既定の実装では、単に FALSE が返されます。

*phGlobal*が NULL の場合は、新しい HGLOBAL を割り当て *、phGlobal*に返す必要があります。 それ以外の場合は *、phGlobal*によって指定された HGLOBAL にデータを入力する必要があります。 HGLOBAL に格納されるデータの量は、メモリー・ブロックの現行サイズを超えてはなりません。 また、ブロックを大きなサイズに再割り当てすることはできません。

これは、高度なオーバーライド可能です。 要求された形式とメディアでデータを提供するには、この関数をオーバーライドします。 データによっては、代わりにこの関数の他のバージョンの 1 つをオーバーライドする必要があります。 複数のストレージ メディアを処理する場合は[、OnRenderData](#onrenderdata)をオーバーライドします。 データがファイル内にある場合、または可変サイズの場合は、[オーバーライドします](#onrenderfiledata)。 MFC で処理される遅延レンダリングの詳細については、「[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)」を参照してください。

詳細については、Windows SDK の[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体と[IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata)を参照してください。

## <a name="coledatasourceonsetdata"></a><a name="onsetdata"></a>を使用します。

指定した形式で`COleDataSource`オブジェクトのデータを設定または置換するために、フレームワークによって呼び出されます。

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>パラメーター

*フォーマットの問題*<br/>
データを置換する形式を指定する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。

*中程度*<br/>
オブジェクトの現在の内容を置き換えるデータを含む[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体への`COleDataSource`ポイント。

*bリリース*<br/>
関数呼び出しの完了後にストレージ メディアの所有権を持つユーザーを示します。 呼び出し元は、ストレージ メディアに代わって割り当てられたリソースを解放する担当者を決定します。 呼び出し元は*bRelease*を設定してこれを行います。 *bRelease*が 0 以外の場合、データ ソースは所有権を取得し、使用が終了するとメディアを解放します。 *bRelease*が 0 の場合、呼び出し元は所有権を保持し、データ ソースは呼び出しの間のみストレージ メディアを使用できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

データ ソースは、データを正常に取得するまで、データの所有権を取得しません。 つまり、0 を`OnSetData`返しても所有権は取得されません。 データ ソースが所有権を取得する場合は[、ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium)関数を呼び出すことによってストレージ メディアを解放します。

既定の実装では、何も行われません。 指定した形式のデータを置き換えるには、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。

詳細については、Windows SDK の[「STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)および[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体」および「[リリースStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium)および[IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata)関数」を参照してください。

## <a name="coledatasourcesetclipboard"></a><a name="setclipboard"></a>クリップボードを設定します。

次の関数のいずれかを呼び`COleDataSource`出した[後、オブジェクト](#cachedata)に含まれるデータをクリップボードに格納[DelayRenderData](#delayrenderdata)[します](#delayrenderfiledata)。 [CacheGlobalData](#cacheglobaldata)

```
void SetClipboard();
```

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[サンプル O クライアント](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDataObject クラス](../../mfc/reference/coledataobject-class.md)
