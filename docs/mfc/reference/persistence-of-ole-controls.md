---
title: OLE コントロールの永続化
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: a99757854e23708f86822906c7ef9023701ea06b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214062"
---
# <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化

OLE コントロールの1つの機能として、プロパティの永続化 (シリアル化) があります。これにより、OLE コントロールは、ファイルまたはストリームとの間でプロパティ値の読み取りまたは書き込みを行うことができます。 コンテナーアプリケーションは、アプリケーションがコントロールを破棄した後でも、シリアル化を使用してコントロールのプロパティ値を格納できます。 その後、コントロールの新しいインスタンスが作成されたときに、OLE コントロールのプロパティ値をファイルまたはストリームから読み取ることができます。

### <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化

|||
|-|-|
|[PX_Blob](#px_blob)|バイナリラージオブジェクト (BLOB) データを格納するコントロールプロパティを交換します。|
|[PX_Bool](#px_bool)|**BOOL**型のコントロールプロパティを交換します。|
|[PX_Color](#px_color)|コントロールの color プロパティを交換します。|
|[PX_Currency](#px_currency)|型**CY**のコントロールプロパティを交換します。|
|[PX_DataPath](#px_datapath)|型のコントロールプロパティを交換 `CDataPathProperty` します。|
|[PX_Double](#px_double)|型のコントロールプロパティを交換 **`double`** します。|
|[PX_Font](#px_font)|コントロールのフォントプロパティを交換します。|
|[PX_Float](#px_float)|型のコントロールプロパティを交換 **`float`** します。|
|[PX_IUnknown](#px_iunknown)|未定義の型のコントロールプロパティを交換します。|
|[PX_Long](#px_long)|型のコントロールプロパティを交換 **`long`** します。|
|[PX_Picture](#px_picture)|コントロールの picture プロパティを交換します。|
|[PX_Short](#px_short)|型のコントロールプロパティを交換 **`short`** します。|
|[PX_ULong](#px_ulong)|**ULONG**型のコントロールプロパティを交換します。|
|[PX_UShort](#px_ushort)|**USHORT**型のコントロールプロパティを交換します。|
|[PXstring](#px_string)|文字列コントロールのプロパティを交換します。|
|[PX_VBXFontConvert](#px_vbxfontconvert)|VBX コントロールのフォント関連のプロパティを OLE コントロールフォントプロパティに交換します。|

また、 `AfxOleTypeMatchGuid` TYPEDESC と特定の GUID との一致をテストするために、グローバル関数が用意されています。

## <a name="px_blob"></a><a name="px_blob"></a>PX_Blob

`DoPropExchange`バイナリラージオブジェクト (BLOB) データを格納するプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

```cpp
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*hBlob*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*hBlobDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて、 *Hblob*によって参照される変数に対して読み取りまたは書き込みが行われます。 最初にを最初に呼び出す前に、この変数を NULL に初期化する必要があり `PX_Blob` ます (通常、これはコントロールのコンストラクターで行うことができます)。 *Hblobdefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールの初期化またはシリアル化のプロセスが失敗した場合に使用されます。

では、 *Hblob*および*hblobdefault*ハンドルは、次のものを含むメモリブロックを参照します。

- の後に続くバイナリデータの長さ (バイト単位) を含む DWORD です。

- 実際のバイナリデータを格納しているメモリのブロック。

で `PX_Blob` は、BLOB 型プロパティを読み込むときに、Windows [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) API を使用してメモリが割り当てられることに注意してください。 このメモリを解放する必要があります。 したがって、コントロールのデストラクターは、任意の BLOB 型のプロパティハンドルで[GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)を呼び出して、コントロールに割り当てられたメモリを解放する必要があります。

## <a name="px_bool"></a><a name="px_bool"></a>PX_Bool

`DoPropExchange`ブール型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

```cpp
BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue);

BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue,
    BOOL bDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*bValue*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*bDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

必要に応じて、 *Bvalue*によって参照される変数に対して、プロパティの値の読み取りまたは書き込みが行われます。 *Bdefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_color"></a><a name="px_color"></a>PX_Color

`DoPropExchange`OLE_COLOR 型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

```cpp
BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue,
    OLE_COLOR clrDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*clrValue*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*clrDefault*<br/>
コントロール開発者によって定義された、プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

必要に応じて、プロパティの値が*Clrvalue*によって参照される変数に対して読み取りまたは書き込みが行われます。 *Clrdefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_currency"></a><a name="px_currency"></a>PX_Currency

`DoPropExchange` **Currency**型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

```cpp
BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue);

BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue,
    CY cyDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*cyValue*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*cyDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて、 *Cyvalue*によって参照される変数に対して読み取りまたは書き込みが行われます。 *Cydefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_datapath"></a><a name="px_datapath"></a>PX_DataPath

`DoPropExchange` [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)型のデータパスプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

```cpp
BOOL PX_DataPath(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CDataPathProperty& dataPathProperty);

BOOL PX_DataPath(
    CPropExchange* pPX,
    CDataPathProperty& dataPathProperty);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*dataPathProperty*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

データパスプロパティは、非同期コントロールのプロパティを実装します。 プロパティの値は、必要に応じて、 *dataPathProperty*によって参照される変数との間で読み書きされます。

## <a name="px_double"></a><a name="px_double"></a>PX_Double

`DoPropExchange`型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出し **`double`** ます。

```cpp
BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue);

BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue,
    double doubleDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*doubleValue*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*doubleDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて、 *doubleValue*によって参照される変数に対して読み書きされます。 *DoubleDefault*を指定した場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_font"></a><a name="px_font"></a>PX_Font

`DoPropExchange`フォント型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

```cpp
BOOL PX_Font(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC FAR* pFontDesc = NULL,
    LPFONTDISP pFontDispAmbient = NULL);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*font*<br/>
`CFontHolder`Font プロパティを含むオブジェクトへの参照です。

*pFontDesc*<br/>
`FONTDESC`フォントプロパティの既定の状態を初期化するために使用する値を格納している構造体へのポインター ( *Pfontdispambient*が NULL の場合)。

*pFontDispAmbient*<br/>
`IFontDisp`フォントプロパティの既定の状態の初期化に使用するフォントのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

必要に応じて、プロパティの値が参照の読み取りまたは書き込みを `font` `CFontHolder` 行います。 *Pfontdesc*と*Pfontdispアンビエント*が指定されている場合は、必要に応じて、プロパティの既定値を初期化するために使用されます。 これらの値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。 通常、 *Pfontdesc*の場合は NULL、 `COleControl::AmbientFont` *pfontdispアンビエント*の場合はによって返されるアンビエント値を渡します。 によって返される font オブジェクトは、 `COleControl::AmbientFont` メンバー関数の呼び出しによって解放される必要があることに注意してください `IFontDisp::Release` 。

## <a name="px_float"></a><a name="px_float"></a>PX_Float

`DoPropExchange`型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出し **`float`** ます。

```cpp
BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue);

BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue,
    float floatDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*floatValue*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*floatDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて、 *floatValue*によって参照される変数に対して読み書きされます。 *FloatDefault*を指定した場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_iunknown"></a><a name="px_iunknown"></a>PX_IUnknown

`DoPropExchange`派生インターフェイスを持つオブジェクトによって表されるプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出し `IUnknown` ます。

```cpp
BOOL PX_IUnknown(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    LPUNKNOWN& pUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault = NULL);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*パンク*<br/>
プロパティの値を表すオブジェクトのインターフェイスを格納している変数への参照。

*iid*<br/>
コントロールによって使用されるプロパティオブジェクトのインターフェイスを示すインターフェイス ID。

*pUnkDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて、 *pUnk*によって参照される変数に対して読み取りまたは書き込みを行います。 *PUnkDefault*を指定した場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_long"></a><a name="px_long"></a>PX_Long

`DoPropExchange`型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出し **`long`** ます。

```cpp
BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue);

BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue,
    long lDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*起きる*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*lDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて、*左辺*値によって参照される変数に対して読み取りまたは書き込みを行います。 *Ldefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_picture"></a><a name="px_picture"></a>PX_Picture

コントロールのメンバー関数内でこの関数 `DoPropExchange` を呼び出して、コントロールの picture プロパティをシリアル化または初期化します。

```cpp
BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict);

BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict,
    CPictureHolder& pictDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*pict*<br/>
プロパティが格納されている[CPictureHolder](../../mfc/reference/cpictureholder-class.md)オブジェクトへの参照 (通常はクラスのメンバー変数)。

*ピクチャの既定値*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

必要に応じて、 *pict*によって参照される変数に対して、プロパティの値の読み取りまたは書き込みを行います。 この場合、[*既定*] を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_short"></a><a name="px_short"></a>PX_Short

`DoPropExchange`型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出し **`short`** ます。

```cpp
BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue);

BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue,
    short sDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*sValue*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*sDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて、 *sValue*によって参照される変数に対して読み取りまたは書き込みを行います。 *Sdefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_ulong"></a><a name="px_ulong"></a>PX_ULong

`DoPropExchange` **ULONG**型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

```cpp
BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue);

BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue,
    long ulDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*ulValue*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*ulDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

必要に応じて、 *Ulvalue*によって参照される変数に対して、プロパティの値の読み取りまたは書き込みを行います。 *Uldefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_ushort"></a><a name="px_ushort"></a>PX_UShort

`DoPropExchange`型のプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出し **`unsigned short`** ます。

```cpp
BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue);

BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue,
    USHORT usDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*usValue*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*usDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

必要に応じて、 *Usvalue*によって参照される変数に対して、プロパティの値の読み取りまたは書き込みを行います。 *Usdefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="pxstring"></a><a name="px_string"></a>PXstring

`DoPropExchange`文字列プロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

```cpp
BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue);

BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue,
    CString strDefault);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*pszPropName*<br/>
交換されるプロパティの名前。

*strValue*<br/>
プロパティが格納されている変数 (通常はクラスのメンバー変数) への参照。

*strDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

必要に応じて、 *strValue*によって参照される変数に対して、プロパティの値の読み取りまたは書き込みを行います。 *Strdefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_vbxfontconvert"></a><a name="px_vbxfontconvert"></a>PX_VBXFontConvert

コントロールのメンバー関数内でこの関数 `DoPropExchange` を呼び出して、VBX コントロールのフォント関連のプロパティを変換することにより、フォントプロパティを初期化します。

```cpp
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常は、にパラメーターとして渡さ `DoPropExchange` れます)。

*font*<br/>
変換された VBX フォント関連のプロパティを格納する OLE コントロールのフォントプロパティ。

### <a name="return-value"></a>戻り値

交換が成功した場合は0以外の。失敗した場合は0。

### <a name="remarks"></a>解説

この関数は、VBX コントロールの直接置換としてデザインされた OLE コントロールによってのみ使用されます。 Visual Basic 開発環境で、VBX コントロールを含むフォームが、対応する置換 OLE コントロールを使用するように変換されると、コントロールの関数が呼び出され `IDataObject::SetData` 、vbx コントロールのプロパティデータを含むプロパティセットが渡されます。 この操作により、コントロールの `DoPropExchange` 関数が呼び出されます。 `DoPropExchange`を呼び出し `PX_VBXFontConvert` て、VBX コントロールのフォント関連のプロパティ (例: "FontName"、"FontSize" など) を OLE コントロールのフォントプロパティの対応するコンポーネントに変換できます。

`PX_VBXFontConvert`コントロールが実際に VBX フォームアプリケーションから変換されている場合にのみ呼び出す必要があります。 次に例を示します。

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
