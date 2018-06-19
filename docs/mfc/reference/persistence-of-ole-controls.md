---
title: OLE コントロールの永続化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e84e26bae83bd131b53d10e4561ddb60854a8a5e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378335"
---
# <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化
OLE コントロールの機能の 1 つは永続化 (またはプロパティのシリアル化)、これにより、ファイルやストリームとの間、プロパティの値を読み書きする OLE コントロール。 コンテナー アプリケーションでは、シリアル化を使用して、アプリケーションがコントロールを破棄した後も、コントロールのプロパティの値を格納します。 OLE コントロールのプロパティ値をファイルから読み取ることができますし、または、後でストリームとコントロールの新しいインスタンスを作成します。  
  
### <a name="persistence-of-ole-controls"></a>OLE コントロールの永続化  
  
|||  
|-|-|  
|[PX_Blob](#px_blob)|バイナリ ラージ オブジェクト (BLOB) データを格納するコントロールのプロパティを交換します。|  
|[PX_Bool](#px_bool)|型のコントロール プロパティを交換**BOOL**です。|  
|[PX_Color](#px_color)|コントロールの色のプロパティを交換します。|  
|[PX_Currency](#px_currency)|型のコントロール プロパティを交換**CY**です。|  
|[PX_DataPath](#px_datapath)|型のコントロール プロパティを交換`CDataPathProperty`です。|  
|[PX_Double](#px_double)|型のコントロール プロパティを交換**二重**です。|  
|[PX_Font](#px_font)|コントロールのフォント プロパティを交換します。|  
|[PX_Float](#px_float)|型のコントロール プロパティを交換**float**です。|  
|[PX_IUnknown](#px_iunknown)|未定義の型のコントロール プロパティを交換します。|  
|[PX_Long](#px_long)|型のコントロール プロパティを交換**長い**です。|  
|[PX_Picture](#px_picture)|コントロールの picture プロパティを交換します。|  
|[PX_Short](#px_short)|型のコントロール プロパティを交換**短い**です。|  
|[PX_ULong](#px_ulong)|型のコントロール プロパティを交換**ULONG**です。|  
|[PX_UShort](#px_ushort)|型のコントロール プロパティを交換**USHORT**です。|  
|[PXstring](#px_string)|文字の文字列のコントロール プロパティを交換します。|  
|[PX_VBXFontConvert](#px_vbxfontconvert)|OLE コントロールのフォント プロパティに VBX コントロールのフォントに関連するプロパティを交換します。|  
  
 さらに、`AfxOleTypeMatchGuid`間で一致の判定に用意されているグローバル関数、`TYPEDESC`と指定された GUID。  
  
##  <a name="px_blob"></a>  PX_Blob  
 コントロールの内には、この関数を呼び出して`DoPropExchange`メンバー関数をシリアル化またはバイナリ ラージ オブジェクト (BLOB) データを格納するプロパティを初期化します。  
  
```  
 
BOOL  
PX_Blob(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    HGLOBAL& 
hBlob  ,  
    HGLOBAL 
hBlobDefault  
= NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `hBlob`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `hBlobDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値からの読み取りまたはで参照される変数に書き込まれるされる`hBlob` をクリックします。 この変数を初期化する必要があります**NULL**最初に呼び出す前に`PX_Blob`を初めて (通常は、そのため、コントロールのコンス トラクターで)。 場合`hBlobDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールの初期化またはシリアル化プロセスが失敗したときに使用されます。  
  
 ハンドル`hBlob`と`hBlobDefault`を次を含むメモリのブロックを参照してください。  
  
-   A`DWORD`ですぐにその後に続く、バイナリ データの長さ、(バイト単位) が含まれています  
  
-   実際のバイナリ データを格納しているメモリのブロック。  
  
 注意してください`PX_Blob`、Windows を使用しているメモリを割り当てる[GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) API、BLOB 型のプロパティを読み込むときにします。 このメモリの解放を担当しています。 したがって、コントロールのデストラクターを呼び出す必要があります[GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)ハンドルを解放は任意の BLOB 型のプロパティをコントロールに割り当てられたメモリをセットアップします。  
  
##  <a name="px_bool"></a>  PX_Bool  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のプロパティを初期化するメンバー関数**BOOL**です。  
  
```  
 
BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& bValue);

BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& 
bValue  ,  
    BOOL bDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `bValue`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `bDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値からの読み取りまたはで参照される変数に書き込まれるされる`bValue` をクリックします。 場合`bDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_color"></a>  PX_Color  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のプロパティを初期化するメンバー関数**OLE_COLOR**です。  
  
```  
 
BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& 
clrValue  ,  
    OLE_COLOR 
clrDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `clrValue`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `clrDefault`  
 コントロールの開発者によって定義されているように、プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値からの読み取りまたはで参照される変数に書き込まれるされる`clrValue` をクリックします。 場合`clrDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_currency"></a>  PX_Currency  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のプロパティを初期化するメンバー関数**通貨**です。  
  
```  
 
BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& cyValue);

BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& 
cyValue  ,  
    CY cyDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `cyValue`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `cyDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値からの読み取りまたはで参照される変数に書き込まれるされる`cyValue` をクリックします。 場合`cyDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_datapath"></a>  PX_DataPath  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のデータ パス プロパティを初期化するメンバー関数[関数](../../mfc/reference/cdatapathproperty-class.md)です。  
  
```  
 
BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    LPCTSTR 
pszPropName,  
    CDataPathProperty& dataPathProperty);

BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    CDataPathProperty& dataPathProperty);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `dataPathProperty`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 データ パスのプロパティは、非同期のコントロールのプロパティを実装します。 プロパティの値からの読み取りまたはで参照される変数に書き込まれるされる`dataPathProperty` をクリックします。  
  
##  <a name="px_double"></a>  PX_Double  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のプロパティを初期化するメンバー関数**二重**です。  
  
```  
 
BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& doubleValue);

BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& 
doubleValue  ,  
    double doubleDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `doubleValue`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `doubleDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値を読み取りまたはで参照される変数に書き込まれる`doubleValue` をクリックします。 場合`doubleDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_font"></a>  PX_Font  
 コントロールの内には、この関数を呼び出して`DoPropExchange`メンバー関数をシリアル化または種類のフォントのプロパティを初期化します。  
  
```  
 
BOOL  
PX_Font(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CFontHolder& 
font  ,  
    const 
FONTDESC  
FAR* 
pFontDesc  
= 
NULL,  
    LPFONTDISP 
pFontDispAmbient  
= NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `font`  
 参照、`CFontHolder`フォント プロパティを含むオブジェクト。  
  
 `pFontDesc`  
 ポインター、 **FONTDESC**の場合、フォントのプロパティの既定の状態の初期化中に使用する値を含む構造体、`pFontDispAmbient`は**NULL**です。  
  
 `pFontDispAmbient`  
 ポインター、**この**font プロパティの既定の状態の初期化中に使用するフォントのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値がから読み取るまたは書き込む`font`、`CFontHolder`参照、適切な場合です。 場合`pFontDesc`と`pFontDispAmbient`は指定すると、必要なときに、プロパティの既定値を初期化するために使用されます。 これらの値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。 通常、渡す**NULL**の`pFontDesc`アンビエントにによって返される値と`COleControl::AmbientFont`の`pFontDispAmbient`です。 フォント オブジェクトによって返されます注`COleControl::AmbientFont`への呼び出しによって解放される必要があります、 **IFontDisp::Release**メンバー関数。  
  
##  <a name="px_float"></a>  PX_Float  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のプロパティを初期化するメンバー関数**float**です。  
  
```  
 
BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& floatValue);

BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& 
floatValue  ,  
    float floatDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `floatValue`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `floatDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値を読み取りまたはで参照される変数に書き込まれる`floatValue` をクリックします。 場合`floatDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_iunknown"></a>  PX_IUnknown  
 コントロールの内には、この関数を呼び出して`DoPropExchange`、オブジェクトを持つによって表されるプロパティを初期化または逆シリアル化するメンバー関数、 **IUnknown**-派生インターフェイスです。  
  
```  
 
BOOL  
PX_IUnknown(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    LPUNKNOWN& 
pUnk  ,  
    REFIID 
iid  ,  
    LPUNKNOWN 
pUnkDefault  
= NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 *pUnk*  
 プロパティの値を表すオブジェクトのインターフェイスを含む変数への参照。  
  
 `iid`  
 プロパティ オブジェクトのインターフェイスがコントロールによって使用されることを示すインターフェイス ID です。  
  
 `pUnkDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値を読み取りまたはで参照される変数に書き込まれる*pUnk* をクリックします。 場合`pUnkDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_long"></a>  PX_Long  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のプロパティを初期化するメンバー関数**長い**です。  
  
```  
 
BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& lValue);

BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& 
lValue  ,  
    long lDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `lValue`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `lDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値を読み取りまたはで参照される変数に書き込まれる`lValue` をクリックします。 場合`lDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_picture"></a>  PX_Picture  
 コントロールの内には、この関数を呼び出して`DoPropExchange`メンバー関数をシリアル化またはコントロールの picture プロパティを初期化します。  
  
```  
 
BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& pict);

BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& 
pict  ,  
    CPictureHolder& pictDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `pict`  
 参照、 [CPictureHolder](../../mfc/reference/cpictureholder-class.md)プロパティが格納されているオブジェクト (通常、クラスのメンバー変数)。  
  
 `pictDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値を読み取りまたはで参照される変数に書き込まれる`pict` をクリックします。 場合`pictDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_short"></a>  PX_Short  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のプロパティを初期化するメンバー関数**短い**です。  
  
```  
 
BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& sValue);

BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& 
sValue  ,  
    short sDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `sValue`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `sDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値を読み取りまたはで参照される変数に書き込まれる`sValue` をクリックします。 場合`sDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_ulong"></a>  PX_ULong  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のプロパティを初期化するメンバー関数**ULONG**です。  
  
```  
 
BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& ulValue);

BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& 
ulValue  ,  
    long ulDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前です。  
  
 `ulValue`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `ulDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値を読み取りまたはで参照される変数に書き込まれる`ulValue` をクリックします。 場合`ulDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_ushort"></a>  PX_UShort  
 コントロールの内には、この関数を呼び出して`DoPropExchange`シリアル化または型のプロパティを初期化するメンバー関数`unsigned`**短い**です。  
  
```  
 
BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& usValue);

BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& 
usValue  ,  
    USHORT usDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前です。  
  
 *usValue*  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 *usDefault*  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値を読み取りまたはで参照される変数に書き込まれる*usValue* をクリックします。 場合*usDefault*を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_string"></a>  PXstring  
 コントロールの内には、この関数を呼び出して**DoPropExchange**メンバー関数をシリアル化または文字の文字列プロパティを初期化します。  
  
```  
 
BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& strValue);

BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& 
strValue  ,  
    CString strDefault);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `pszPropName`  
 交換されるプロパティの名前。  
  
 `strValue`  
 プロパティが格納されている変数への参照を (通常、クラスのメンバー変数)。  
  
 `strDefault`  
 プロパティの既定値です。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの値を読み取りまたはで参照される変数に書き込まれる`strValue` をクリックします。 場合`strDefault`を指定すると、プロパティの既定値として使用されます。 この値は、何らかの理由で、コントロールのシリアル化プロセスが失敗したときに使用されます。  
  
##  <a name="px_vbxfontconvert"></a>  PX_VBXFontConvert  
 コントロールの内には、この関数を呼び出して`DoPropExchange`VBX コントロールのフォントに関連するプロパティを変換することで、[フォント] プロパティを初期化するためにメンバー関数。  
  
```  
 
BOOL  
PX_VBXFontConvert(
    CPropExchange* 
pPX  ,  
    CFontHolder& font);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクト (通常のパラメーターとして渡される`DoPropExchange`)。  
  
 `font`  
 変換された VBX フォントに関連するプロパティを格納する OLE コントロールのフォント プロパティ。  
  
### <a name="return-value"></a>戻り値  
 交換が成功した場合は 0 以外。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、直接の代わりに、VBX コントロールに設計されている OLE コントロールでのみ使用する必要があります。 Visual Basic 開発環境では、対応する置換 OLE コントロールを使用する VBX コントロールを含むフォームが変換されるときに呼び出すことが、コントロールの**IDataObject::SetData**関数、プロパティに渡すことを設定します。VBX コントロールのプロパティのデータが含まれています。 この操作により、コントロールの`DoPropExchange`呼び出される関数。 `DoPropExchange` 呼び出すことができます`PX_VBXFontConvert`VBX コントロールのフォントに関連するプロパティに変換する (たとえば、"FontName、""FontSize、"など) を OLE コントロールのフォントのプロパティの対応するコンポーネントです。  
  
 `PX_VBXFontConvert` コントロールが VBX フォーム アプリケーションから実際に変換されている場合にのみ呼び出す必要があります。 例えば:  
  
 [!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]  
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
