---
title: OLE コントロールの永続化
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.ole
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: e510cdb2ae64b5b3ed5f8b69bc8ad9c22800a167
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609420"
---
# <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化

OLE コントロールの機能の 1 つは、プロパティの永続化 (またはシリアル化)、OLE コントロール プロパティの値を記述して、ファイルまたはストリームから読み取ったりすることができます。 コンテナー アプリケーションは、シリアル化を使用して、アプリケーションがコントロールを破棄した後でも、コントロールのプロパティの値を格納できます。 OLE コントロールのプロパティ値をファイルから読み取るまたは後でストリームの場合、コントロールの新しいインスタンスを作成します。

### <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化

|||
|-|-|
|[PX_Blob](#px_blob)|バイナリ ラージ オブジェクト (BLOB) データを格納するコントロール プロパティを交換します。|
|[PX_Bool](#px_bool)|型のコントロール プロパティを交換**BOOL**します。|
|[PX_Color](#px_color)|コントロールの色のプロパティを交換します。|
|[PX_Currency](#px_currency)|型のコントロール プロパティを交換**CY**します。|
|[PX_DataPath](#px_datapath)|型のコントロール プロパティを交換`CDataPathProperty`します。|
|[PX_Double](#px_double)|型のコントロール プロパティを交換**二重**します。|
|[PX_Font](#px_font)|コントロールのフォント プロパティを交換します。|
|[PX_Float](#px_float)|型のコントロール プロパティを交換**float**します。|
|[PX_IUnknown](#px_iunknown)|未定義の型のコントロールのプロパティを交換します。|
|[PX_Long](#px_long)|型のコントロール プロパティを交換**長い**します。|
|[PX_Picture](#px_picture)|コントロールの picture プロパティを交換します。|
|[PX_Short](#px_short)|型のコントロール プロパティを交換**短い**します。|
|[PX_ULong](#px_ulong)|型のコントロール プロパティを交換**ULONG**します。|
|[PX_UShort](#px_ushort)|型のコントロール プロパティを交換**USHORT**します。|
|[PXstring](#px_string)|文字の文字列のコントロールのプロパティを交換します。|
|[PX_VBXFontConvert](#px_vbxfontconvert)|OLE コントロールのフォント プロパティに VBX コントロールのフォント関連プロパティを交換します。|

さらに、`AfxOleTypeMatchGuid`グローバル関数が TYPEDESC と指定された GUID の一致の判定に使用されます。

##  <a name="px_blob"></a>  PX_Blob

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化またはバイナリ ラージ オブジェクト (BLOB) データを格納するプロパティを初期化します。

```
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*hBlob*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*hBlobDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値の読み取りまたはで参照される変数に書き込まれたは*hBlob*必要に応じて、します。 この変数は、最初に呼び出す前に NULL に初期化する必要があります`PX_Blob`最初に (通常、これ行うコントロールのコンス トラクターで)。 場合*hBlobDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールの初期化またはシリアル化プロセスが失敗したときに使用されます。

ハンドル*hBlob*と*hBlobDefault*を次を含むメモリのブロックを参照してください。

- すぐに、次のバイナリ データの長さ、(バイト単位) を含む DWORD の後に

- 実際のバイナリ データを格納しているメモリのブロック。

なお`PX_Blob`、Windows を使用して、メモリの割り当ては[GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) API、BLOB 型のプロパティの読み込み時にします。 このメモリの解放を担当します。 そのため、コントロールのデストラクターを呼び出す必要があります[GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree)ハンドルを解放する任意の BLOB の種類プロパティをコントロールに割り当てられたメモリがアップします。

##  <a name="px_bool"></a>  PX_Bool

コントロールの中でこの関数を呼び出す`DoPropExchange`をシリアル化、または BOOL 型のプロパティを初期化します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*bValue*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*bDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値の読み取りまたはで参照される変数に書き込まれたは*bValue*必要に応じて、します。 場合*bDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_color"></a>  PX_Color

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または OLE_COLOR 型のプロパティを初期化します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*clrValue*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*clrDefault*<br/>
コントロールの開発者によって定義されている、プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値の読み取りまたはで参照される変数に書き込まれたは*clrValue*必要に応じて、します。 場合*clrDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_currency"></a>  PX_Currency

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または型のプロパティを初期化する**通貨**します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*cyValue*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*cyDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値の読み取りまたはで参照される変数に書き込まれたは*cyValue*必要に応じて、します。 場合*cyDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_datapath"></a>  PX_DataPath

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または型のデータ パスのプロパティを初期化する[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*dataPathProperty*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

データ パスのプロパティは、非同期のコントロールのプロパティを実装します。 プロパティの値の読み取りまたはで参照される変数に書き込まれたは*dataPathProperty*必要に応じて、します。

##  <a name="px_double"></a>  PX_Double

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または型のプロパティを初期化する**二重**します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*doubleValue*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*doubleDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みで参照される変数を*doubleValue*必要に応じて、します。 場合*doubleDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_font"></a>  PX_Font

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または型のフォントのプロパティを初期化します。

```
BOOL PX_Font(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC FAR* pFontDesc = NULL,
    LPFONTDISP pFontDispAmbient = NULL);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*フォント*<br/>
参照を`CFontHolder`フォント プロパティを含むオブジェクト。

*pFontDesc*<br/>
ポインターを`FONTDESC`の場合は、フォント プロパティの既定の状態の初期化中に使用する値を含む構造体、 *pFontDispAmbient*は NULL です。

*pFontDispAmbient*<br/>
ポインター、`IFontDisp`フォント プロパティの既定の状態の初期化中に使用するフォントのインターフェイス。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みを`font`、`CFontHolder`適切な場合は、参照します。 場合*pFontDesc*と*pFontDispAmbient*は指定すると、必要なときに、プロパティの既定の値を初期化するために使用されます。 これらの値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。 通常は、NULL を渡す*pFontDesc*およびアンビエント値によって返される`COleControl::AmbientFont`の*pFontDispAmbient*します。 によって返されるフォント オブジェクト注`COleControl::AmbientFont`を呼び出して解放する必要があります、`IFontDisp::Release`メンバー関数。

##  <a name="px_float"></a>  PX_Float

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または型のプロパティを初期化する**float**します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*floatValue*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*floatDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みで参照される変数を*floatValue*必要に応じて、します。 場合*floatDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_iunknown"></a>  PX_IUnknown

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、オブジェクトで表されるプロパティを初期化またはシリアル化する、 `IUnknown`-派生インターフェイス。

```
BOOL PX_IUnknown(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    LPUNKNOWN& pUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault = NULL);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*pUnk*<br/>
プロパティの値を表すオブジェクトのインターフェイスを含む変数への参照。

*iid*<br/>
プロパティ オブジェクトのインターフェイスを示すインターフェイス ID は、コントロールによって使用されます。

*pUnkDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みで参照される変数を*pUnk*必要に応じて、します。 場合*pUnkDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_long"></a>  PX_Long

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または型のプロパティを初期化する**長い**します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*左辺値*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*lDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みで参照される変数を*左辺値*必要に応じて、します。 場合*lDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_picture"></a>  PX_Picture

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化またはコントロールの picture プロパティを初期化します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*pict*<br/>
参照を[CPictureHolder](../../mfc/reference/cpictureholder-class.md)プロパティが格納されているオブジェクト (通常、クラスのメンバー変数)。

*pictDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みで参照される変数を*pict*必要に応じて、します。 場合*pictDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_short"></a>  PX_Short

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または型のプロパティを初期化する**短い**します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*sValue*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*sDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みで参照される変数を*sValue*必要に応じて、します。 場合*sDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_ulong"></a>  PX_ULong

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または型のプロパティを初期化する**ULONG**します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前です。

*ulValue*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*ulDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みで参照される変数を*ulValue*必要に応じて、します。 場合*ulDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_ushort"></a>  PX_UShort

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または型のプロパティを初期化する**unsigned short**します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前です。

*usValue*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*usDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みで参照される変数を*usValue*必要に応じて、します。 場合*usDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_string"></a>  PXstring

コントロールの中でこの関数を呼び出す`DoPropExchange`メンバー関数は、シリアル化または文字の文字列プロパティを初期化します。

```
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
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*pszPropName*<br/>
交換されるプロパティの名前。

*strValue*<br/>
プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。

*strDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値がから読み取りまたは書き込みで参照される変数を*strValue*必要に応じて、します。 場合*strDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。

##  <a name="px_vbxfontconvert"></a>  PX_VBXFontConvert

コントロールの中でこの関数を呼び出す`DoPropExchange`VBX コントロールのフォント関連プロパティを変換することで、[フォント] プロパティを初期化するために、メンバー関数。

```
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>パラメーター

*pPX*<br/>
ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。

*フォント*<br/>
変換された VBX フォント関連プロパティを格納する OLE コントロールのフォント プロパティ。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

この関数は、VBX コントロールの直接の置き換えとして設計されている OLE コントロールのみで使用する必要があります。 コントロールを呼び出すが、Visual Basic 開発環境では、対応する置換 OLE コントロールを使用する VBX コントロールを含む形式に変換、 `IDataObject::SetData` VBX コントロールのプロパティのデータを含むプロパティ セットを渡す関数。 この操作により、コントロールの`DoPropExchange`呼び出される関数。 `DoPropExchange` 呼び出すことができます`PX_VBXFontConvert`VBX コントロールのフォント関連プロパティに変換する (たとえば、"FontName、""FontSize、"など) OLE コントロールのフォントのプロパティの対応するコンポーネントにします。

`PX_VBXFontConvert` コントロールが VBX フォーム アプリケーションから実際に変換されている場合にのみ呼び出す必要があります。 例えば:

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
