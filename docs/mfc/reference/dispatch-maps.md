---
title: ディスパッチ マップ
ms.date: 06/20/2018
f1_keywords:
- vc.mfc.macros.maps
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: 5ebedaa02a03bcc7802110977b96659dae45f174
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322515"
---
# <a name="dispatch-maps"></a>ディスパッチ マップ

OLE オートメーションでは、メソッドを呼び出すと、アプリケーション間でプロパティにアクセスする方法を提供します。 これらの要求をディスパッチするためには、Microsoft Foundation Class ライブラリによって提供されるメカニズムは、「ディスパッチ マップ」オブジェクトの関数とプロパティ、およびプロパティ自体のデータ型の内部および外部の名前を指定します。関数の引数。

|ディスパッチ マップ マクロ|説明|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|クラスのメソッドとプロパティ (クラス宣言で使用する必要があります) を公開するディスパッチ マップが使用されることを宣言します。|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|ディスパッチ マップの定義を開始します。|
|[END_DISPATCH_MAP](#end_dispatch_map)|ディスパッチ マップの定義を終了します。|
|[DISP_FUNCTION](#disp_function)|ディスパッチ マップで使用すると、OLE オートメーション関数を定義します。|
|[DISP_PROPERTY](#disp_property)|OLE オートメーションのプロパティを定義します。|
|[DISP_PROPERTY_EX](#disp_property_ex)|OLE オートメーションのプロパティを定義し、Get および Set 関数の名前します。|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|通知の OLE オートメーション プロパティを定義します。|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Get および Set 関数のパラメーターと名前を受け取る OLE オートメーションのプロパティを定義します。|
|[DISP_DEFVALUE](#disp_defvalue)|既存のプロパティをオブジェクトの既定値になります。|

## <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP

場合、 `CCmdTarget`-プログラムでクラスを派生クラスがそのメソッドとプロパティを公開するディスパッチ マップを提供する必要がありますの OLE オートメーションをサポートします。

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Remarks

クラスの宣言の最後に DECLARE_DISPATCH_MAP マクロを使用します。 次に、します。クラスのメンバー関数を定義する CPP ファイルでは、BEGIN_DISPATCH_MAP マクロを使用します。 クラスの公開されたメソッドとプロパティ (DISP_FUNCTION や DISP_PROPERTY、) の各マクロのエントリが含まれます。 最後に、END_DISPATCH_MAP マクロを使用します。

> [!NOTE]
> DECLARE_DISPATCH_MAP 後にすべてのメンバーを宣言する場合は、新しいアクセスの種類を指定する必要があります (**パブリック**、**プライベート**、または**保護**) にします。

アプリケーション ウィザードとコード ウィザードでは、オートメーション クラスの作成とディスパッチ マップの管理を支援します。 ディスパッチ マップの詳細については、次を参照してください。[オートメーション サーバー](../../mfc/automation-servers.md)します。

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

*クラス*<br/>
このディスパッチ マップを所有しているクラスの名前を指定します。

*baseClass*<br/>
基本クラスの名前を示す*クラス*します。

### <a name="remarks"></a>Remarks

クラスのメンバー関数を定義する、実装 (.cpp) ファイルで BEGIN_DISPATCH_MAP マクロでディスパッチ マップを開始、ごと、ディスパッチ関数とプロパティのマクロのエントリを追加し、END_DISPATCH_ でディスパッチ マップを完了マップ マクロです。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="end_dispatch_map"></a>  END_DISPATCH_MAP

ディスパッチ マップの定義を終了します。

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Remarks

これは、BEGIN_DISPATCH_MAP と組み合わせて使用する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_function"></a>  DISP_FUNCTION

ディスパッチ マップでは、OLE オートメーション関数を定義します。

```cpp
DISP_FUNCTION(
  theClass,
  pszName,
  pfnMember,
  vtRetVal,
  vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
クラスの名前。

*pszName*<br/>
関数の外部名。

*pfnMember*<br/>
メンバー関数の名前。

*vtRetVal*<br/>
関数の戻り値の型を指定する値。

*vtsParams*<br/>
関数のパラメーター リストを指定する 1 つまたは複数の定数のスペースで区切られたリスト。

### <a name="remarks"></a>Remarks

*VtRetVal* VARTYPE 型の引数は、します。 この引数の次の値がから取得されます、`VARENUM`列挙体。

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

*VtsParams*引数は、スペースで区切られたリストから値の`VTS_*`定数。 1 つ以上のスペース (コンマではない) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例えば以下のようにします。

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

短整数へのポインターの後に、短整数を含むリストを指定します。

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

ディスパッチ マップでの OLE オートメーション プロパティを定義します。

```cpp
DISP_PROPERTY(
  theClass,
  pszName,
  memberName,
  vtPropType)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
クラスの名前。

*pszName*<br/>
プロパティの外部名。

*memberName*<br/>
プロパティが格納されているメンバー変数の名前。

*vtPropType*<br/>
プロパティの型を指定する値。

### <a name="remarks"></a>Remarks

*VtPropType*引数が型の**VARTYPE**します。 この引数に指定できる値は、VARENUM 列挙から取得されます。

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

外部クライアントで、プロパティで指定されたメンバー変数の値が変更されたとき*memberName* ; の変更、変更の通知はありません。

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

*クラス*<br/>
クラスの名前。

*pszName*<br/>
プロパティの外部名。

*memberGet*<br/>
プロパティを取得するために使用するメンバー関数の名前。

*memberSet*<br/>
プロパティを設定するために使用するメンバー関数の名前。

*vtPropType*<br/>
プロパティの型を指定する値。

### <a name="remarks"></a>Remarks

*MemberGet*と*memberSet*関数は、によって決まりますシグネチャを持つ、 *vtPropType*引数。 *MemberGet*関数の引数をとらないし、で指定された型の値を返します*vtPropType*します。 *MemberSet*関数がで指定された型の引数を受け取る*vtPropType*とは何も返しません。

*VtPropType* VARTYPE 型の引数は、します。 この引数に指定できる値は、VARENUM 列挙から取得されます。 これらの値の一覧は、「解説」を参照してください、 *vtRetVal*パラメーター [DISP_FUNCTION](#disp_function)します。 プロパティのデータ型として VT_EMPTY、DISP_FUNCTION の注釈内に表示することはできませんに注意してください。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY

ディスパッチ マップ内通知で OLE オートメーションのプロパティを定義します。

```cpp
DISP_PROPERTY_NOTIFY(
  theClass,
  szExternalName,
  memberName,
  pfnAfterSet,
  vtPropType)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
クラスの名前。

*szExternalName*<br/>
プロパティの外部名。

*memberName*<br/>
プロパティが格納されているメンバー変数の名前。

*pfnAfterSet*<br/>
通知関数の名前*szExternalName*します。

*vtPropType*<br/>
プロパティの型を指定する値。

### <a name="remarks"></a>Remarks

DISP_PROPERTY で定義されたプロパティとは異なり DISP_PROPERTY_NOTIFY で定義されているプロパティは自動的に関数を呼び出すで指定された*pfnAfterSet*プロパティが変更されたとき。

*VtPropType* VARTYPE 型の引数は、します。 この引数に指定できる値は、VARENUM 列挙から取得されます。

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

個別にアクセスされるプロパティを定義します。`Get`と`Set`メンバー関数。

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

*クラス*<br/>
クラスの名前。

*pszExternalName*<br/>
プロパティの外部名。

*pfnGet*<br/>
プロパティを取得するために使用するメンバー関数の名前。

*pfnSet*<br/>
プロパティを設定するために使用するメンバー関数の名前。

*vtPropType*<br/>
プロパティの型を指定する値。

*vtsParams*<br/>
スペースで区切られた文字列`VTS_*`バリアント型パラメーターが型パラメーターごとに 1 つ。

### <a name="remarks"></a>Remarks

このマクロでは、DISP_PROPERTY_EX マクロとは異なり、プロパティのパラメーター リストを指定できます。 これは、インデックス付きまたはパラメーター化されるプロパティを実装するために便利です。

### <a name="example"></a>例

Get の次の宣言を検討してください。 し、メンバーのプロパティにアクセスするときに、特定の行と列を要求するユーザーを許可する関数を設定します。

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

これらは、コントロールのディスパッチ マップでは、次の DISP_PROPERTY_PARAM マクロに対応します。

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

別の例としては、次の取得を検討してくださいし、セットのメンバー関数。

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

*クラス*<br/>
クラスの名前。

*pszName*<br/>
オブジェクトの"value"を表すプロパティの外部名。

### <a name="remarks"></a>Remarks

既定値を使用すると、Visual Basic アプリケーションの簡単なオートメーション オブジェクトをプログラミングすることができます。

オブジェクトの「既定値」では、取得またはオブジェクトへの参照は、プロパティ、またはメンバー関数を指定しない場合に設定されているプロパティです。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
