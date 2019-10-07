---
title: COleDataObject クラス
ms.date: 11/04/2016
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
ms.openlocfilehash: e706489a84ad564949e2c2d3d193173fc19b9828
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741627"
---
# <a name="coledataobject-class"></a>COleDataObject クラス

クリップボードや OLE 埋め込みアイテムからさまざまなフォーマットのデータを取得するときのデータ転送に使用します。クリップボードからデータを取得するときは、ドラッグ アンド ドロップを使用します。

## <a name="syntax"></a>構文

```
class COleDataObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleDataObject:: COleDataObject](#coledataobject)|`COleDataObject` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleDataObject:: Attach](#attach)|指定した OLE データオブジェクトをに`COleDataObject`アタッチします。|
|[COleDataObject:: AttachClipboard](#attachclipboard)|クリップボードにあるデータオブジェクトをアタッチします。|
|[COleDataObject:: BeginEnumFormats](#beginenumformats)|1回以上の後続`GetNextFormat`の呼び出しを準備します。|
|[COleDataObject::D etach](#detach)|関連付けられ`IDataObject`たオブジェクトをデタッチします。|
|[COleDataObject:: GetData](#getdata)|アタッチされた OLE データオブジェクトから、指定した形式でデータをコピーします。|
|[COleDataObject::GetFileData](#getfiledata)|アタッチされた OLE データオブジェクトから、指定`CFile`した形式のポインターにデータをコピーします。|
|[COleDataObject:: GetGlobalData](#getglobaldata)|アタッチされた OLE データオブジェクトのデータを`HGLOBAL` 、指定した形式でにコピーします。|
|[COleDataObject:: GetNextFormat](#getnextformat)|使用可能な次のデータ形式を返します。|
|[COleDataObject:: IsDataAvailable](#isdataavailable)|指定された形式でデータを使用できるかどうかを確認します。|
|[COleDataObject::Release](#release)|関連付けられ`IDataObject`たオブジェクトをデタッチして解放します。|

## <a name="remarks"></a>Remarks

`COleDataObject`に基底クラスがありません。

この種類のデータ転送には、変換元と変換先が含まれます。 データソースは、 [COleDataSource](../../mfc/reference/coledatasource-class.md)クラスのオブジェクトとして実装されます。 変換先アプリケーションにデータがドロップされている場合、またはクリップボードから貼り付け操作を実行するよう`COleDataObject`に求められた場合は、クラスのオブジェクトを作成する必要があります。

このクラスを使用すると、指定した形式のデータが存在するかどうかを判断できます。 また、使用可能なデータ形式を列挙したり、特定の形式が使用可能かどうかを確認してから、適切な形式でデータを取得することもできます。 オブジェクトの取得は、 [CFile](../../mfc/reference/cfile-class.md)、HGLOBAL、 `STGMEDIUM`構造体の使用など、いくつかの方法で実現できます。

詳細については、Windows SDK の[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体を参照してください。

アプリケーションでのデータオブジェクトの使用の詳細については、「[データオブジェクトとデータソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`COleDataObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole

##  <a name="attach"></a>  COleDataObject::Attach

この関数を呼び出して、 `COleDataObject`オブジェクトを OLE データオブジェクトに関連付けます。

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpDataObject*<br/>
OLE データオブジェクトをポイントします。

*bAutoRelease*<br/>
`COleDataObject`オブジェクトが破棄されたときに OLE データオブジェクトを解放する場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

詳細については、Windows SDK の「 [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) 」を参照してください。

##  <a name="attachclipboard"></a>COleDataObject:: AttachClipboard

現在クリップボードにあるデータオブジェクトを`COleDataObject`オブジェクトにアタッチするには、この関数を呼び出します。

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

> [!NOTE]
>  この関数を呼び出すと、このデータオブジェクトが解放されるまでクリップボードがロックされます。 データオブジェクトは、 `COleDataObject`のデストラクターで解放されます。 詳細については、「Win32 置かの[Openclipboard](/windows/win32/api/winuser/nf-winuser-openclipboard)と[CloseClipboard](/windows/win32/api/winuser/nf-winuser-closeclipboard) 」を参照してください。

##  <a name="beginenumformats"></a>COleDataObject:: BeginEnumFormats

この関数を呼び出して、項目からデータ`GetNextFormat`形式の一覧を取得するための後続の呼び出しを準備します。

```
void BeginEnumFormats();
```

### <a name="remarks"></a>Remarks

を`BeginEnumFormats`呼び出した後、このデータオブジェクトでサポートされている最初の形式の位置が格納されます。 を`GetNextFormat`連続して呼び出すと、データオブジェクトで使用可能な形式の一覧が列挙されます。

指定された形式でデータが使用可能かどうかを確認するには、 [COleDataObject:: IsDataAvailable](#isdataavailable)を使用します。

詳細については、Windows SDK の「 [IDataObject:: EnumFormatEtc](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc) 」を参照してください。

##  <a name="coledataobject"></a>COleDataObject:: COleDataObject

`COleDataObject` オブジェクトを構築します。

```
COleDataObject();
```

### <a name="remarks"></a>Remarks

他の`COleDataObject`関数を呼び出す前に、 [COleDataObject:: Attach](#attach)または[COleDataObject:: attachclipboard](#attachclipboard)の呼び出しを行う必要があります。

> [!NOTE]
>  ドラッグアンドドロップハンドラーのパラメーターの1つはへの`COleDataObject`ポインターであるため、ドラッグアンドドロップをサポートするためにこのコンストラクターを呼び出す必要はありません。

##  <a name="detach"></a>COleDataObject::D etach

この関数を呼び出して、 `COleDataObject`データオブジェクトを解放せずに、関連付けられている OLE データオブジェクトからオブジェクトをデタッチします。

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>戻り値

デタッチされた OLE データオブジェクトへのポインター。

### <a name="remarks"></a>Remarks

##  <a name="getdata"></a>  COleDataObject::GetData

指定した書式で項目からデータを取得するには、この関数を呼び出します。

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cfFormat*<br/>
データが返される形式。 このパラメーターには、定義済みのクリップボード形式、またはネイティブ Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値のいずれかを指定できます。

*lpStgMedium*<br/>
データを受け取る[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体を指します。

*lpFormatEtc*<br/>
データが返される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を指します。 *CfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメーターの値を指定します。 NULL の場合は、 `FORMATETC`構造体の他のフィールドに既定値が使用されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

詳細については、Windows SDK の「 [IDataObject:: GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata)、 [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)、および[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 」を参照してください。

詳細については、Windows SDK の「 [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 」を参照してください。

##  <a name="getfiledata"></a>  COleDataObject::GetFileData

この関数を呼び出して、 `CFile`また`CFile`はの派生オブジェクトを作成し、指定した形式`CFile`のデータをポインターに取得します。

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cfFormat*<br/>
データが返される形式。 このパラメーターには、定義済みのクリップボード形式、またはネイティブ Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値のいずれかを指定できます。

*lpFormatEtc*<br/>
データが返される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を指します。 *CfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメーターの値を指定します。 NULL の場合は、 `FORMATETC`構造体の他のフィールドに既定値が使用されます。

### <a name="return-value"></a>戻り値

成功した場合`CFile`は`CFile`、データを格納している新しいまたは派生したオブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>Remarks

データが格納されているメディアによっては、戻り値が指す実際の型が`CFile`、 `CSharedFile`、また`COleStreamFile`はになる場合があります。

> [!NOTE]
>  この関数の戻り値によってアクセスされるオブジェクトは、呼び出し元が所有します。`CFile` `CFile`オブジェクトを**削除**するのは呼び出し元の役割であり、その結果、ファイルが閉じられます。

詳細については、Windows SDK の「 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 」を参照してください。

詳細については、Windows SDK の「 [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 」を参照してください。

##  <a name="getglobaldata"></a>  COleDataObject::GetGlobalData

グローバルメモリブロックを割り当て、指定した形式のデータを HGLOBAL に取得するには、この関数を呼び出します。

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cfFormat*<br/>
データが返される形式。 このパラメーターには、定義済みのクリップボード形式、またはネイティブ Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値のいずれかを指定できます。

*lpFormatEtc*<br/>
データが返される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を指します。 *CfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメーターの値を指定します。 NULL の場合は、 `FORMATETC`構造体の他のフィールドに既定値が使用されます。

### <a name="return-value"></a>戻り値

成功した場合は、データを格納しているグローバルメモリブロックのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>Remarks

詳細については、Windows SDK の「 [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 」を参照してください。

詳細については、Windows SDK の「 [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 」を参照してください。

##  <a name="getnextformat"></a>  COleDataObject::GetNextFormat

項目からデータを取得するために使用できるすべての形式を取得するには、この関数を繰り返し呼び出します。

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>パラメーター

*lpFormatEtc*<br/>
関数呼び出しが返されたときに書式情報を受け取る[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を指します。

### <a name="return-value"></a>戻り値

別の形式が使用可能な場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

[COleDataObject:: BeginEnumFormats](#beginenumformats)を呼び出した後、このデータオブジェクトでサポートされている最初の形式の位置が格納されます。 を`GetNextFormat`連続して呼び出すと、データオブジェクトで使用可能な形式の一覧が列挙されます。 使用可能な形式の一覧を表示するには、これらの関数を使用します。

指定された形式が使用可能かどうかを確認するには、 [COleDataObject:: IsDataAvailable](#isdataavailable)を呼び出します。

詳細については、Windows SDK の「 [IEnumXXXX:: Next](/previous-versions//ms695273\(v=vs.85\)) 」を参照してください。

##  <a name="isdataavailable"></a>  COleDataObject::IsDataAvailable

OLE 項目からデータを取得するために特定の形式が使用可能かどうかを判断するには、この関数を呼び出します。

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cfFormat*<br/>
*LpFormatEtc*が指す構造体で使用されるクリップボードのデータ形式。 このパラメーターには、定義済みのクリップボード形式、またはネイティブ Windows [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値のいずれかを指定できます。

*lpFormatEtc*<br/>
目的の形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を指します。 *CfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定してください。 NULL の場合は、 `FORMATETC`構造体の他のフィールドに既定値が使用されます。

### <a name="return-value"></a>戻り値

指定された形式でデータを使用できる場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>Remarks

この関数は、、、 `GetData`また`GetFileData`は`GetGlobalData`を呼び出す前に便利です。

詳細については、Windows SDK の「 [IDataObject:: QueryGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata) and [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) 」を参照してください。

詳細については、Windows SDK の「 [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) 」を参照してください。

### <a name="example"></a>例

  [CRichEditView:: QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata)の例を参照してください。

##  <a name="release"></a>  COleDataObject::Release

この関数を呼び出して、以前に `COleDataObject`オブジェクトに関連付けられていた [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) オブジェクトの所有権を解放します。

```
void Release();
```

### <a name="remarks"></a>Remarks

は、、 `COleDataObject` `Attach`また`IDataObject` はフレームワークによって明示的にまたはを呼び出すことによってに関連付けら`AttachClipboard`れました。 の `Attach` bAutoReleaseパラメーター`IDataObject`が FALSE の場合、オブジェクトは解放されません。 この場合、呼び出し元は、 `IDataObject` [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)を呼び出すことによって、を解放します。

## <a name="see-also"></a>関連項目

[MFC サンプル HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDataSource クラス](../../mfc/reference/coledatasource-class.md)<br/>
[COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)
