---
title: ディスパッチ マップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/20/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 107dba503c11d3810f75dcd4ee6e6f5af47008fc
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122981"
---
# <a name="dispatch-maps"></a>ディスパッチ マップ

OLE オートメーションでは、メソッドを呼び出すと、アプリケーション間でプロパティにアクセスする方法を提供します。 これらの要求をディスパッチするためには、Microsoft Foundation Class ライブラリによって提供されるメカニズムは、「ディスパッチ マップ」オブジェクトの関数とプロパティ、およびプロパティ自体のデータ型の内部および外部の名前を指定します。関数の引数。

|ディスパッチ マップ マクロ|説明|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|クラスのメソッドとプロパティ (クラス宣言で使用する必要があります) を公開するディスパッチ マップを使用することを宣言します。|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|ディスパッチ マップの定義を開始します。|
|[END_DISPATCH_MAP](#end_dispatch_map)|ディスパッチ マップの定義を終了します。|
|[DISP_FUNCTION](#disp_function)|ディスパッチ マップで使用すると、OLE オートメーション関数を定義します。|
|[DISP_PROPERTY](#disp_property)|OLE オートメーションのプロパティを定義します。|
|[DISP_PROPERTY_EX](#disp_property_ex)|OLE オートメーションのプロパティを定義し、Get および Set 関数の名前します。|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|通知付きの OLE オートメーション プロパティを定義します。|
|[DISP_PROPERTY_PARAM](#disp_property_param)|OLE オートメーションのプロパティとを受け取るパラメーターの名前、Get および Set 関数を定義します。|
|[DISP_DEFVALUE](#disp_defvalue)|既存のプロパティをオブジェクトの既定値になります。|

## <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP

場合、 `CCmdTarget`-プログラム内の派生クラスは、クラスがそのメソッドとプロパティを公開するディスパッチ マップを用意する必要がありますの OLE オートメーションをサポートしています。

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Remarks

クラスの宣言の最後に DECLARE_DISPATCH_MAP マクロを使用します。 次に、します。クラスのメンバー関数を定義する CPP ファイルでは、BEGIN_DISPATCH_MAP マクロを使用します。 クラスの公開されたメソッドとプロパティ (DISP_FUNCTION DISP_PROPERTY、やなど) の各マクロ エントリが含まれます。 最後に、END_DISPATCH_MAP マクロを使用します。

> [!NOTE]
> DECLARE_DISPATCH_MAP 後にすべてのメンバーを宣言する場合は、新しいアクセスの種類を指定する必要があります (**パブリック**、**プライベート**、または**保護**) にします。

アプリケーション ウィザードとコードのウィザードでは、オートメーション クラスの作成とディスパッチ マップの管理を支援します。 ディスパッチ マップの詳細については、次を参照してください。[オートメーション サーバー](../../mfc/automation-servers.md)です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="begin_dispatch_map"></a>  BEGIN_DISPATCH_MAP

ディスパッチ マップの定義を宣言します。

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>パラメーター

*クラス*  
このディスパッチ マップを所有するクラスの名前を指定します。

*baseClass*  
基本クラスの名前を指定*クラス*です。

### <a name="remarks"></a>Remarks

実装 (.cpp) ファイルに、クラスのメンバー関数を定義する、ディスパッチ マップを BEGIN_DISPATCH_MAP マクロに先頭の各関数のディスパッチと、プロパティのマクロのエントリを追加し、完了、END_DISPATCH_ でディスパッチ マップマップ マクロです。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="end_dispatch_map"></a>  END_DISPATCH_MAP

ディスパッチ マップの定義を終了します。

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Remarks

BEGIN_DISPATCH_MAP と組み合わせて使用する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_function"></a>  DISP_FUNCTION

ディスパッチ マップで OLE オートメーション関数を定義します。

```cpp
DISP_FUNCTION(
  theClass,
  pszName,
  pfnMember,
  vtRetVal,
  vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*  
クラスの名前です。

*pszName*  
関数の外部名。

*pfnMember*  
このメンバー関数の名前です。

*vtRetVal*  
関数の戻り値の型を指定する値。

*vtsParams*  
関数のパラメーター リストを指定する 1 つまたは複数の定数のスペースで区切られた一覧です。

### <a name="remarks"></a>Remarks

*VtRetVal*引数が型 VARTYPE のです。 この引数の次の値がから取得された、`VARENUM`列挙します。

|シンボル|戻り値の型|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

*VtsParams*引数がスペースで区切られた一連の値から、`VTS_*`定数。 1 つ以上のスペース (コンマではない) で区切られたこれらの値は、関数のパラメーター リストを指定します。 たとえば、オブジェクトに適用された

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

ポインターを続けて短整数を短整数を含むリストを指定します。

`VTS_`定数とその意味は次のようには。

|シンボル|パラメーターの型|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_CY|`const CY` または `CY*`|
|VTS_DATE|DATE|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|LPDISPATCH|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` または `VARIANT&`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_PI2|__short\*__|
|VTS_PI4|__long\*__|
|VTS_PR4|__float\*__|
|VTS_PR8|__double\*__|
|VTS_PCY|`CY*`|
|VTS_PDATE|`DATE*`|
|VTS_PBSTR|`BSTR*`|
|VTS_PDISPATCH|`LPDISPATCH*`|
|VTS_PSCODE|`SCODE*`|
|VTS_PBOOL|`BOOL*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_PUNKNOWN|`LPUNKNOWN*`|
|VTS_NONE|パラメーターなし|

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_property"></a>  DISP_PROPERTY

ディスパッチ マップ内の OLE オートメーション プロパティを定義します。

```cpp
DISP_PROPERTY(
  theClass,
  pszName,
  memberName,
  vtPropType)
```

### <a name="parameters"></a>パラメーター

*クラス*  
クラスの名前です。

*pszName*  
プロパティの外部名。

*メンバー名*  
プロパティが格納されているメンバー変数の名前です。

*vtPropType*  
プロパティの型を指定する値。

### <a name="remarks"></a>Remarks

*VtPropType*引数の型が**VARTYPE**です。 この引数に指定できる値は、VARENUM 列挙から取得されます。

|シンボル|プロパティの型|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

外部のクライアントで、プロパティで指定されたメンバー変数の値が変更されたとき*memberName*変更; 変更の通知は示されません。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_property_ex"></a>  DISP_PROPERTY_EX

OLE オートメーションのプロパティと名前を取得およびディスパッチ マップ内のプロパティの値の設定に使用する関数を定義します。

```cpp
DISP_PROPERTY_EX(
  theClass,
  pszName,
  memberGet,
  memberSet,
  vtPropType)
```

### <a name="parameters"></a>パラメーター

*クラス*  
クラスの名前です。

*pszName*  
プロパティの外部名。

*memberGet*  
プロパティの取得に使用するメンバー関数の名前です。

*メンバー セット*  
このメンバー関数は、プロパティを設定するための名前です。

*vtPropType*  
プロパティの型を指定する値。

### <a name="remarks"></a>Remarks

*MemberGet*と*memberSet*関数によって署名がある、 *vtPropType*引数。 *MemberGet*関数は引数を使用しないで指定された型の値を返します*vtPropType*です。 *MemberSet*関数がで指定された型の引数を受け取る*vtPropType*とは何も返しません。

*VtPropType*引数が型 VARTYPE のです。 この引数に指定できる値はの VARENUM 列挙から取得されます。 これらの値の一覧は、「解説」を参照してください、 *vtRetVal*パラメーター [DISP_FUNCTION](#disp_function)です。 プロパティのデータ型として VT_EMPTY、DISP_FUNCTION 解説に一覧表示することはできませんに注意してください。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY

ディスパッチ マップで通知付きの OLE オートメーション プロパティを定義します。

```cpp
DISP_PROPERTY_NOTIFY(
  theClass,
  szExternalName,
  memberName,
  pfnAfterSet,
  vtPropType)
```

### <a name="parameters"></a>パラメーター

*クラス*  
クラスの名前です。

*szExternalName*  
プロパティの外部名。

*メンバー名*  
プロパティが格納されているメンバー変数の名前です。

*pfnAfterSet*  
通知関数の名前*szExternalName*です。

*vtPropType*  
プロパティの型を指定する値。

### <a name="remarks"></a>Remarks

DISP_PROPERTY で定義されたプロパティとは異なり DISP_PROPERTY_NOTIFY で定義されたプロパティが自動的に呼び出すで指定された関数*pfnAfterSet*プロパティが変更されたとき。

*VtPropType*引数が型 VARTYPE のです。 この引数に指定できる値は、VARENUM 列挙から取得されます。

|シンボル|プロパティの型|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_property_param"></a>  DISP_PROPERTY_PARAM

個別にアクセスするプロパティを定義`Get`と`Set`メンバー関数。

```cpp
DISP_PROPERTY_PARAM(
  theClass,
  pszExternalName,
  pfnGet,
  pfnSet,
  vtPropType,
  vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*  
クラスの名前です。

*pszExternalName*  
プロパティの外部名。

*pfnGet*  
プロパティの取得に使用するメンバー関数の名前です。

*pfnSet*  
このメンバー関数は、プロパティを設定するための名前です。

*vtPropType*  
プロパティの型を指定する値。

*vtsParams*  
スペースで区切られた文字列`VTS_*`バリアント型パラメーターが型パラメーターごとに 1 つです。

### <a name="remarks"></a>Remarks

DISP_PROPERTY_EX マクロとは異なりこのマクロは、プロパティのパラメーター リストを指定することができます。 これは、インデックスを作成またはパラメーター化されているプロパティを実装するために役立ちます。

### <a name="example"></a>例

Get の次の宣言を検討し、メンバー プロパティにアクセスするときに、特定の行と列を要求するユーザーに許可する機能を設定します。

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

これらは、コントロールのディスパッチ マップでは、次の DISP_PROPERTY_PARAM マクロに対応します。

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

別の例として、次の取得を考慮し、メンバー関数を設定します。

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

これらは、コントロールのディスパッチ マップでは、次の DISP_PROPERTY_PARAM マクロに対応します。

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_defvalue"></a>  DISP_DEFVALUE

既存のプロパティをオブジェクトの既定値になります。

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>パラメーター

*クラス*  
クラスの名前です。

*pszName*  
オブジェクトの"value"を表すプロパティの外部名。

### <a name="remarks"></a>Remarks

既定値を使用して Visual Basic アプリケーションの簡単なオートメーション オブジェクトのプログラミングを行うことができます。

オブジェクトの「既定値」では、取得またはオブジェクトへの参照が、プロパティまたはメンバー関数を指定しない場合に設定されているプロパティです。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)  
