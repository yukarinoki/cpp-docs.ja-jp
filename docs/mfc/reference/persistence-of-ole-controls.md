---
title: OLE コントロールの永続化
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: 88707da503b1d1cdc809827dc4d1bac0ccad9b5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373008"
---
# <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化

OLE コントロールの機能の 1 つに、プロパティの永続化 (シリアル化) があり、OLE コントロールはファイルまたはストリームとの間でプロパティ値を読み書きできます。 コンテナー アプリケーションは、シリアル化を使用して、コントロールを破棄した後でも、コントロールのプロパティ値を格納できます。 OLE コントロールのプロパティ値は、後で新しいインスタンスが作成されたときに、ファイルまたはストリームから読み取ることができます。

### <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化

|||
|-|-|
|[PX_Blob](#px_blob)|バイナリ ラージ オブジェクト (BLOB) データを格納するコントロール プロパティを交換します。|
|[PX_Bool](#px_bool)|**BOOL**型のコントロール プロパティを交換します。|
|[PX_Color](#px_color)|コントロールのカラー プロパティを交換します。|
|[PX_Currency](#px_currency)|**CY**型のコントロール プロパティを交換します。|
|[PX_DataPath](#px_datapath)|型のコントロール プロパティを交換`CDataPathProperty`します。|
|[PX_Double](#px_double)|**種類が倍**精度浮動小数点数型のコントロール プロパティを交換します。|
|[PX_Font](#px_font)|コントロールのフォント プロパティを交換します。|
|[PX_Float](#px_float)|**float**型のコントロール プロパティを交換します。|
|[PX_IUnknown](#px_iunknown)|未定義の型のコントロール プロパティを交換します。|
|[PX_Long](#px_long)|**long**型のコントロール プロパティを交換します。|
|[PX_Picture](#px_picture)|コントロールの画像プロパティを交換します。|
|[PX_Short](#px_short)|**short**型のコントロール プロパティを交換します。|
|[PX_ULong](#px_ulong)|**ULONG**型のコントロール プロパティを交換します。|
|[PX_UShort](#px_ushort)|**USHORT**型のコントロール プロパティを交換します。|
|[PX 文字列](#px_string)|文字列制御プロパティを交換します。|
|[PX_VBXFontConvert](#px_vbxfontconvert)|VBX コントロールのフォント関連プロパティを OLE コントロール のフォント プロパティに変換します。|

さらに、TYPEDESC`AfxOleTypeMatchGuid`と指定された GUID の一致をテストするグローバル関数が提供されます。

## <a name="px_blob"></a><a name="px_blob"></a>PX_Blob

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して、バイナリ ラージ オブジェクト (BLOB) データを格納するプロパティをシリアル化または初期化します。

```cpp
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*hBlob*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*デフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて hBlob によって参照される変数から読み取られるか、または*hBlob*によって参照される変数に書き込まれます。 この変数は、最初に最初に呼び`PX_Blob`出す前に NULL に初期化する必要があります (通常、これはコントロールのコンストラクターで行うことができます)。 *hBlobDefault*が指定されている場合、プロパティの既定値として使用されます。 この値は、何らかの理由でコントロールの初期化またはシリアル化プロセスが失敗した場合に使用されます。

ハンドル*hBlob*と*hBlobDefault*は、次の内容を含むメモリのブロックを参照します。

- 続くバイナリ データの長さ (バイト単位) を含む DWORD

- 実際のバイナリ データを含むメモリのブロック。

BLOB`PX_Blob`型のプロパティを読み込むときに、Windows [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) API を使用してメモリを割り当てることに注意してください。 このメモリを解放する責任があります。 したがって、コントロールのデストラクターは、任意の BLOB 型のプロパティ ハンドルで[GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)を呼び出して、コントロールに割り当てられたメモリを解放する必要があります。

## <a name="px_bool"></a><a name="px_bool"></a>PX_Bool

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して、BOOL 型のプロパティをシリアル化または初期化します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*b値*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*bデフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は *、bValue*で参照される変数から読み取られるか、または適切に書き込まれます。 *bDefault*を指定すると、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_color"></a><a name="px_color"></a>PX_Color

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して、OLE_COLOR型のプロパティをシリアル化または初期化します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*値*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*既定*<br/>
コントロールの開発者が定義したプロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて*clrValue*によって参照される変数から読み取られるか、または変数に書き込まれます。 *clrDefault*が指定されている場合は、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_currency"></a><a name="px_currency"></a>PX_Currency

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して **、currency**型のプロパティをシリアル化または初期化します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*サイバリュー*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*デフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は *、cyValue*によって参照される変数から読み取られるか、または書き込まれます。 *cyDefault*を指定すると、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_datapath"></a><a name="px_datapath"></a>PX_DataPath

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して、[型 CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)のデータ パス プロパティをシリアル化または初期化します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*プロパティ*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

データ パス プロパティは、非同期コントロール プロパティを実装します。 プロパティの値は、必要に応じて dataPathProperty によって参照される変数から読み取られるか、または*dataPathProperty*に書き込まれます。

## <a name="px_double"></a><a name="px_double"></a>PX_Double

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して **、型**double のプロパティをシリアル化または初期化します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*ダブルバリュー*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*ダブルデフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて*doubleValue*で参照される変数から読み取られるか、または変数に書き込まれます。 *doubleDefault*を指定すると、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_font"></a><a name="px_font"></a>PX_Font

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して、フォント型のプロパティをシリアル化または初期化します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*フォント*<br/>
フォント プロパティを`CFontHolder`含むオブジェクトへの参照。

*フォントデック*<br/>
*フォント*プロパティの`FONTDESC`既定の状態を初期化する場合に使用する値を含む構造体へのポインターです。

*アンビエント*<br/>
フォント プロパティの`IFontDisp`既定の状態を初期化する場合に使用するフォントのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて、`font`から読`CFontHolder`み取られるか、参照に書き込まれます。 *pFontDesc*と*pFontDisp アンビエント*が指定されている場合、必要に応じて、プロパティの既定値を初期化するために使用されます。 これらの値は、何らかの理由でコントロールのシリアル化プロセスが失敗した場合に使用されます。 通常 *、pFontDesc*には NULL を渡し`COleControl::AmbientFont`*、pFontDisp アンビエント*で返されるアンビエント値を渡します。 返されるフォント オブジェクトは、`COleControl::AmbientFont``IFontDisp::Release`メンバー関数の呼び出しによって解放される必要があります。

## <a name="px_float"></a><a name="px_float"></a>PX_Float

float**型の**`DoPropExchange`プロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*フロートバリュー*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*フロートデフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて floatValue によって参照される変数から読み取られるか、または*floatValue*によって参照される変数に書き込まれます。 *floatDefault*が指定されている場合、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_iunknown"></a><a name="px_iunknown"></a>PX_IUnknown

派生インターフェイスを持つオブジェクトによって表`DoPropExchange`されるプロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの`IUnknown`関数を呼び出します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*パンク*<br/>
プロパティの値を表すオブジェクトのインターフェイスを含む変数への参照。

*Iid*<br/>
コントロールで使用されるプロパティ オブジェクトのインターフェイスを示すインターフェイス ID。

*既定の値*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて*pUnk*によって参照される変数から読み取られるか、または書き込まれます。 *pUnkDefault*を指定すると、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_long"></a><a name="px_long"></a>PX_Long

long**型の**`DoPropExchange`プロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*l値*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*lデフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は *、lValue*によって参照される変数から読み取られるか、または適切に書き込まれます。 *lDefault*を指定すると、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_picture"></a><a name="px_picture"></a>PX_Picture

コントロールの`DoPropExchange`ピクチャ プロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*Pict*<br/>
プロパティが格納されている[CPictureHolder](../../mfc/reference/cpictureholder-class.md)オブジェクトへの参照 (通常はクラスのメンバー変数)。

*ピクトデフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は *、pict*によって参照される変数から読み取られるか、または書き込まれます。 *pictDefault*を指定すると、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_short"></a><a name="px_short"></a>PX_Short

short**型の**`DoPropExchange`プロパティをシリアル化または初期化するには、コントロールのメンバー関数内でこの関数を呼び出します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*Svalue*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*デフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は *、sValue*によって参照される変数から読み取られるか、または書き込まれます。 *sDefault*が指定されている場合、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_ulong"></a><a name="px_ulong"></a>PX_ULong

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して、**型 ULONG**のプロパティをシリアル化または初期化します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*ul値*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*ul デフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は、必要に応じて*ulValue*によって参照される変数から読み取られるか、または書き込まれます。 *ulDefault*を指定すると、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_ushort"></a><a name="px_ushort"></a>PX_UShort

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して、**符号なし short**型のプロパティをシリアル化または初期化します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*私たち評価*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*私たちデフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は、 *usValue*によって参照される変数から読み取られるか、または書き込まれます。 *usDefault*が指定されている場合、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="pxstring"></a><a name="px_string"></a>PX 文字列

コントロールの`DoPropExchange`メンバー関数内でこの関数を呼び出して、文字列プロパティをシリアル化または初期化します。

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
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*名前を変更します。*<br/>
交換されるプロパティの名前。

*strValue*<br/>
プロパティが格納されている変数への参照 (通常はクラスのメンバー変数)。

*既定*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は *、strValue*によって参照される変数から読み取られるか、または書き込まれます。 *strDefault*を指定すると、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化プロセスが失敗した場合に使用されます。

## <a name="px_vbxfontconvert"></a><a name="px_vbxfontconvert"></a>PX_VBXFontConvert

コントロールのメンバー関数内でこの関数を`DoPropExchange`呼び出して、VBX コントロールのフォント関連プロパティを変換してフォント プロパティを初期化します。

```cpp
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
[CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトへのポインター (通常はパラメーターとして渡`DoPropExchange`されます)。

*フォント*<br/>
変換された VBX フォント関連のプロパティを含む OLE コントロールのフォント プロパティ。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

この関数は、VBX コントロールの直接置換として設計された OLE コントロールでのみ使用してください。 Visual Basic 開発環境は、VBX コントロールを含むフォームを変換して、対応する置換 OLE コントロールを使用すると、`IDataObject::SetData`コントロールの関数を呼び出して、VBX コントロールのプロパティ データを含むプロパティ セットを渡します。 この操作によって、コントロールの`DoPropExchange`関数が呼び出されます。 `DoPropExchange`は、VBX コントロールのフォント関連プロパティ ("FontName"、"FontSize"など) を OLE コントロールのフォント プロパティの対応するコンポーネントに変換するために呼び出`PX_VBXFontConvert`すことができます。

`PX_VBXFontConvert`コントロールが実際に VBX フォーム アプリケーションから変換されている場合にのみ呼び出されます。 次に例を示します。

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
