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
ms.openlocfilehash: 5e1545a033ab482e838fbc944b0ca9b3e543d651
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366129"
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
|[オブジェクト:::オブジェクト](#coledataobject)|`COleDataObject` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オブジェクト::アタッチ](#attach)|指定した OLE データ オブジェクトを`COleDataObject`にアタッチします。|
|[クリップボードをアタッチします。](#attachclipboard)|クリップボードにあるデータ オブジェクトをアタッチします。|
|[オブジェクト::ビギン列挙形式](#beginenumformats)|1 つ以上の後続の`GetNextFormat`呼び出しの準備をします。|
|[コレデータオブジェクト::Dエタッハ](#detach)|関連付けられた`IDataObject`オブジェクトをデタッチします。|
|[オブジェクトを取得します。](#getdata)|アタッチされた OLE データ オブジェクトのデータを指定した形式でコピーします。|
|[オブジェクト::ファイルデータを取得します。](#getfiledata)|アタッチされた OLE データ オブジェクトのデータ`CFile`を、指定した形式のポインターにコピーします。|
|[オブジェクト::取得グローバルデータ](#getglobaldata)|アタッチされた OLE データ オブジェクトのデータ`HGLOBAL`を、指定した形式で にコピーします。|
|[次の書式を取得します。](#getnextformat)|次に使用可能なデータ形式を返します。|
|[オブジェクト::IsDataAvailable](#isdataavailable)|データが指定された形式で使用可能かどうかをチェックします。|
|[オブジェクト::リリース](#release)|関連付けられた`IDataObject`オブジェクトをデタッチして解放します。|

## <a name="remarks"></a>解説

`COleDataObject`は基本クラスを持っていません。

この種のデータ転送には、転送元と転送先が含まれます。 データ ソースは、[クラス](../../mfc/reference/coledatasource-class.md)のオブジェクトとして実装されます。 コピー先のアプリケーションでデータがドロップされたり、クリップボードから貼り付け操作を行うよう求められたりするたびに、`COleDataObject`クラスのオブジェクトを作成する必要があります。

このクラスを使用すると、データが指定された形式で存在するかどうかを確認できます。 また、使用可能なデータ形式を列挙したり、特定の形式が使用可能かどうかを確認して、優先形式でデータを取得することもできます。 オブジェクトの取得は[、CFile](../../mfc/reference/cfile-class.md)、HGLOBAL、または構造体の使用を含む、いくつかの異なる方法`STGMEDIUM`で行うことができます。

詳細については、Windows SDK の[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造を参照してください。

アプリケーションでデータ オブジェクトを使用する方法の詳細については、「[データ オブジェクトとデータ ソース (OLE)」](../../mfc/data-objects-and-data-sources-ole.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`COleDataObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coledataobjectattach"></a><a name="attach"></a>オブジェクト::アタッチ

オブジェクトを OLE データ`COleDataObject`オブジェクトに関連付けます。

```
void Attach(
    LPDATAOBJECT lpDataObject,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>パラメーター

*オブジェクト*<br/>
OLE データ オブジェクトへのポイント。

*b自動リリース*<br/>
オブジェクトが破棄されたときに OLE データ オブジェクトを`COleDataObject`解放する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

詳細については、Windows SDK[の「IDataObject」](/windows/win32/api/objidl/nn-objidl-idataobject)を参照してください。

## <a name="coledataobjectattachclipboard"></a><a name="attachclipboard"></a>クリップボードをアタッチします。

クリップボードに現在置かれているデータ オブジェクトを`COleDataObject`オブジェクトにアタッチします。

```
BOOL AttachClipboard();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

> [!NOTE]
> この関数を呼び出すと、このデータ オブジェクトが解放されるまでクリップボードがロックされます。 データ オブジェクトは、 のデストラクターで解放`COleDataObject`されます。 詳細については、Win32 ドキュメントの[「クリップボードを開く](/windows/win32/api/winuser/nf-winuser-openclipboard)」および「[クリップボードを閉じる](/windows/win32/api/winuser/nf-winuser-closeclipboard)」を参照してください。

## <a name="coledataobjectbeginenumformats"></a><a name="beginenumformats"></a>オブジェクト::ビギン列挙形式

アイテムからデータ形式の一覧を取得`GetNextFormat`するための後続の呼び出しを準備します。

```
void BeginEnumFormats();
```

### <a name="remarks"></a>解説

を`BeginEnumFormats`呼び出した後、このデータ オブジェクトでサポートされる最初の形式の位置が格納されます。 の`GetNextFormat`連続呼び出しは、データ オブジェクトで使用可能な形式の一覧を列挙します。

指定された形式でデータが使用できるかどうか確認するには[、COleDataObject::IsDataAvailable](#isdataavailable)を使用します。

詳細については、Windows SDK[の「IDataObject::列挙形式の問題](/windows/win32/api/objidl/nf-objidl-idataobject-enumformatetc)」を参照してください。

## <a name="coledataobjectcoledataobject"></a><a name="coledataobject"></a>オブジェクト:::オブジェクト

`COleDataObject` オブジェクトを構築します。

```
COleDataObject();
```

### <a name="remarks"></a>解説

他`COleDataObject`の関数を呼び出す前に[、COleDataObject::アタッチ](#attach)または[COleDataObject::アタッチクリップボード](#attachclipboard)の呼び出しを行う必要があります。

> [!NOTE]
> ドラッグ アンド ドロップ ハンドラへのパラメータの 1 つは`COleDataObject`へのポインタであるため、ドラッグ アンド ドロップをサポートするためにこのコンストラクタを呼び出す必要はありません。

## <a name="coledataobjectdetach"></a><a name="detach"></a>コレデータオブジェクト::Dエタッハ

データ`COleDataObject`オブジェクトを解放せずに、関連付けられた OLE データ オブジェクトからオブジェクトをデタッチします。

```
LPDATAOBJECT Detach();
```

### <a name="return-value"></a>戻り値

デタッチされた OLE データ オブジェクトへのポインター。

### <a name="remarks"></a>解説

## <a name="coledataobjectgetdata"></a><a name="getdata"></a>オブジェクトを取得します。

指定した形式のアイテムからデータを取得します。

```
BOOL GetData(
    CLIPFORMAT cfFormat,
    LPSTGMEDIUM lpStgMedium,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cf フォーマット*<br/>
データが返される形式。 このパラメーターには、定義済みのクリップボード形式の 1 つ、またはネイティブの Windows[の登録クリップボード形式](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値を指定できます。

*中程度*<br/>
データを受信する[STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)構造体へのポイント。

*フォーマットの問題*<br/>
データが返される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。 *cfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメータの値を指定します。 NULL の場合、デフォルト値は構造体の他のフィールドに`FORMATETC`使用されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

詳細については、Windows SDK[の「IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) [、STGMEDIUM、](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)および[フォーマット」](/windows/win32/api/objidl/ns-objidl-formatetc)を参照してください。

詳細については、「Windows SDK で[クリップボードの書式を登録](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)する」を参照してください。

## <a name="coledataobjectgetfiledata"></a><a name="getfiledata"></a>オブジェクト::ファイルデータを取得します。

この関数を呼び出`CFile`して`CFile`、派生オブジェクトまたは派生オブジェクトを作成し、指定した形式`CFile`のデータをポインターに取得します。

```
CFile* GetFileData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cf フォーマット*<br/>
データが返される形式。 このパラメーターには、定義済みのクリップボード形式の 1 つ、またはネイティブの Windows[の登録クリップボード形式](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値を指定できます。

*フォーマットの問題*<br/>
データが返される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。 *cfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメータの値を指定します。 NULL の場合、デフォルト値は構造体の他のフィールドに`FORMATETC`使用されます。

### <a name="return-value"></a>戻り値

成功した場合は`CFile`、`CFile`データを含む新規または派生オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

データが格納されるメディアに応じて、戻り値によって示される実際の型は`CFile`、 `CSharedFile`、または`COleStreamFile`である場合があります。

> [!NOTE]
> この`CFile`関数の戻り値によってアクセスされるオブジェクトは、呼び出し元によって所有されます。 オブジェクトを**削除**し、それによってファイルを`CFile`閉じるのは、呼び出し元の責任です。

詳細については、Windows SDK[の「FORMATETC」](/windows/win32/api/objidl/ns-objidl-formatetc)を参照してください。

詳細については、「Windows SDK で[クリップボードの書式を登録](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)する」を参照してください。

## <a name="coledataobjectgetglobaldata"></a><a name="getglobaldata"></a>オブジェクト::取得グローバルデータ

グローバル メモリ ブロックを割り当て、指定した形式のデータを取得して HGLOBAL に変換します。

```
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cf フォーマット*<br/>
データが返される形式。 このパラメーターには、定義済みのクリップボード形式の 1 つ、またはネイティブの Windows[の登録クリップボード形式](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値を指定できます。

*フォーマットの問題*<br/>
データが返される形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。 *cfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合は、このパラメータの値を指定します。 NULL の場合、デフォルト値は構造体の他のフィールドに`FORMATETC`使用されます。

### <a name="return-value"></a>戻り値

成功した場合は、データを含むグローバル メモリ ブロックのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

詳細については、Windows SDK[の「FORMATETC」](/windows/win32/api/objidl/ns-objidl-formatetc)を参照してください。

詳細については、「Windows SDK で[クリップボードの書式を登録](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)する」を参照してください。

## <a name="coledataobjectgetnextformat"></a><a name="getnextformat"></a>次の書式を取得します。

この関数を繰り返し呼び出して、アイテムからデータを取得するために使用できるすべての形式を取得します。

```
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```

### <a name="parameters"></a>パラメーター

*フォーマットの問題*<br/>
関数呼び出しが戻るときにフォーマット情報を受け取る[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体を指します。

### <a name="return-value"></a>戻り値

別の形式が使用可能な場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

[呼](#beginenumformats)び出しの後、このデータ オブジェクトでサポートされる最初の形式の位置が格納されます。 の`GetNextFormat`連続呼び出しは、データ オブジェクトで使用可能な形式の一覧を列挙します。 これらの関数を使用して、使用可能な形式をリストします。

特定の形式が使用できるかどうか確認するには[、COleDataObject::IsDataAvailable](#isdataavailable)を呼び出します。

詳細については、Windows SDK の[IEnumXXXX::次](/previous-versions//ms695273\(v=vs.85\))を参照してください。

## <a name="coledataobjectisdataavailable"></a><a name="isdataavailable"></a>オブジェクト::IsDataAvailable

OLE アイテムからデータを取得するために特定の形式が使用できるかどうかを調べます。

```
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>パラメーター

*cf フォーマット*<br/>
*lpFormatEtc*が指す構造体で使用されるクリップボード データ形式。 このパラメーターには、定義済みのクリップボード形式の 1 つ、またはネイティブの Windows[の登録クリップボード形式](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数によって返される値を指定できます。

*フォーマットの問題*<br/>
目的の形式を記述する[FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc)構造体へのポイント。 *cfFormat*で指定されたクリップボード形式以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定します。 NULL の場合、デフォルト値は構造体の他のフィールドに`FORMATETC`使用されます。

### <a name="return-value"></a>戻り値

データが指定された形式で使用可能な場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、 、 `GetData` `GetFileData`、または`GetGlobalData`を呼び出す前に便利です。

詳細については、Windows SDK[の「IDataObject::クエリGetData](/windows/win32/api/objidl/nf-objidl-idataobject-querygetdata)と[フォーマット」](/windows/win32/api/objidl/ns-objidl-formatetc)を参照してください。

詳細については、「Windows SDK で[クリップボードの書式を登録](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)する」を参照してください。

### <a name="example"></a>例

  の[例を参照](../../mfc/reference/cricheditview-class.md#queryacceptdata)してください。

## <a name="coledataobjectrelease"></a><a name="release"></a>オブジェクト::リリース

この関数を呼び出して、オブジェクトに以前に関連付けられていた[IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)オブジェクトの所有権を`COleDataObject`解放します。

```
void Release();
```

### <a name="remarks"></a>解説

呼`IDataObject`び出し`COleDataObject``Attach`によって、または明示的`AttachClipboard`に、またはフレームワークによってに関連付けられていた。 *bAutoRelease*パラメータ`Attach`が FALSE の場合`IDataObject`、オブジェクトは解放されません。 この場合、呼び出し元は、呼び`IDataObject`出すことによってを解放する必要[があります: リリース](/windows/win32/api/unknwn/nf-unknwn-iunknown-release).

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[サンプル O クライアント](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDataSource クラス](../../mfc/reference/coledatasource-class.md)<br/>
[クラス](../../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)
