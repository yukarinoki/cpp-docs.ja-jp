---
title: ディスパッチ マップ
ms.date: 06/20/2018
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: 59dd8c7a7b0b930ffdb68fd96410fd73aeb02e81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365752"
---
# <a name="dispatch-maps"></a>ディスパッチ マップ

OLE オートメーションは、メソッドを呼び出し、アプリケーション間でプロパティにアクセスする方法を提供します。 これらの要求をディスパッチするための Microsoft Foundation クラス ライブラリによって提供されるメカニズムは、オブジェクトの関数とプロパティの内部名と外部名、およびプロパティ自体のデータ型と関数引数を指定する"ディスパッチ マップ"です。

|ディスパッチ マップ マクロ|説明|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|ディスパッチ マップを使用してクラスのメソッドとプロパティを公開することを宣言します (クラス宣言で使用する必要があります)。|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|ディスパッチ マップの定義を開始します。|
|[END_DISPATCH_MAP](#end_dispatch_map)|ディスパッチ マップの定義を終了します。|
|[DISP_FUNCTION](#disp_function)|OLE オートメーション関数を定義するためにディスパッチ マップで使用されます。|
|[DISP_PROPERTY](#disp_property)|OLE オートメーション プロパティを定義します。|
|[DISP_PROPERTY_EX](#disp_property_ex)|OLE オートメーション プロパティを定義し、Get 関数と Set 関数の名前を指定します。|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|通知を使用して OLE オートメーション プロパティを定義します。|
|[DISP_PROPERTY_PARAM](#disp_property_param)|パラメータを受け取り、Get 関数と Set 関数に名前を付ける OLE オートメーション プロパティを定義します。|
|[DISP_DEFVALUE](#disp_defvalue)|既存のプロパティをオブジェクトの既定値にします。|

## <a name="declare_dispatch_map"></a><a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP

プログラムの`CCmdTarget`派生クラスが OLE オートメーションをサポートしている場合、そのクラスは、そのメソッドとプロパティを公開するディスパッチ マップを提供する必要があります。

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>解説

クラス宣言の最後にDECLARE_DISPATCH_MAPマクロを使用します。 次に、 で.CPP ファイルクラスのメンバー関数を定義する、BEGIN_DISPATCH_MAP マクロを使用します。 次に、クラスの公開メソッドとプロパティ (DISP_FUNCTION、DISP_PROPERTYなど) のマクロ エントリを含めます。 最後に、END_DISPATCH_MAPマクロを使用します。

> [!NOTE]
> DECLARE_DISPATCH_MAP後にメンバーを宣言する場合は、新しいアクセスタイプ ( **public**、 private 、**または****プロテクト**) を指定する必要があります。

アプリケーション ウィザードとコード ウィザードは、オートメーション クラスの作成やディスパッチ マップの保守を支援します。 ディスパッチ マップの詳細については、「[オートメーション サーバー](../../mfc/automation-servers.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="begin_dispatch_map"></a><a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP

ディスパッチ マップの定義を宣言します。

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このディスパッチ マップを所有するクラスの名前を指定します。

*Baseclass*<br/>
クラスの基本クラス名*を*指定します。

### <a name="remarks"></a>解説

クラスのメンバー関数を定義する実装 (.cpp) ファイルで、ディスパッチ マップを BEGIN_DISPATCH_MAP マクロで開始し、ディスパッチ関数とプロパティごとにマクロ エントリを追加し、END_DISPATCH_MAP マクロを使用してディスパッチ マップを完成させます。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="end_dispatch_map"></a><a name="end_dispatch_map"></a>END_DISPATCH_MAP

ディスパッチ マップの定義を終了します。

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>解説

BEGIN_DISPATCH_MAPと組み合わせて使用する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_function"></a><a name="disp_function"></a>DISP_FUNCTION

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

*クラス*<br/>
クラスの名前

*名前*<br/>
関数の外部名。

*メンバー*<br/>
メンバー関数の名前。

*vtRetVal*<br/>
関数の戻り値の型を指定する値。

*vtsパラム*<br/>
関数のパラメーター リストを指定する 1 つ以上の定数のスペース区切りのリスト。

### <a name="remarks"></a>解説

*vtRetVal*引数は、VARTYPE 型です。 この引数に指定できる値は、列挙体から`VARENUM`取得されます。

|Symbol|の戻り値の型 : |
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**長い**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPディスパッチ|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

*vtsParams*引数は、`VTS_*`定数の値をスペースで区切ったリストです。 これらの値のうち 1 つ以上がスペースで区切られ (コンマではなく) 関数のパラメーター・リストが指定されます。 たとえば、次のように入力します。

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

は、短整数の後に短い整数へのポインタが続くリストを指定します。

定数`VTS_`とその意味は次のとおりです。

|Symbol|パラメーターのタイプ|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**長い**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_CY|`const CY` または `CY*`|
|VTS_DATE|DATE|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|LPディスパッチ|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` または `VARIANT&`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_PI2|__short\*__|
|VTS_PI4|__長い\*__|
|VTS_PR4|__float\*__|
|VTS_PR8|__ダブル\*__|
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

## <a name="disp_property"></a><a name="disp_property"></a>DISP_PROPERTY

ディスパッチ マップ内の OLE オートメーション プロパティを定義します。

```cpp
DISP_PROPERTY(
    theClass,
    pszName,
    memberName,
    vtPropType)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
クラスの名前

*名前*<br/>
プロパティの外部名。

*Membername*<br/>
プロパティが格納されているメンバー変数の名前。

*型*<br/>
プロパティの型を指定する値。

### <a name="remarks"></a>解説

*vtPropType*引数の型は**VARTYPE です**。 この引数に指定できる値は、VARENUM 列挙体から取得されます。

|Symbol|プロパティの種類|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**長い**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPディスパッチ|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

外部クライアントがプロパティを変更すると *、memberName*で指定されたメンバー変数の値が変更されます。変更の通知はありません。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_property_ex"></a><a name="disp_property_ex"></a>DISP_PROPERTY_EX

OLE オートメーション プロパティを定義し、ディスパッチ マップでプロパティの値を取得および設定するために使用する関数に名前を付けます。

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
クラスの名前

*名前*<br/>
プロパティの外部名。

*メンバーの取得*<br/>
プロパティを取得するために使用するメンバー関数の名前。

*メンバーセット*<br/>
プロパティの設定に使用するメンバー関数の名前。

*型*<br/>
プロパティの型を指定する値。

### <a name="remarks"></a>解説

*メンバーGet*関数と*メンバー セット*関数には *、vtPropType*引数によってシグネチャが決定されます。 *memberGet*関数は引数を受け取らず *、vtPropType*で指定された型の値を返します。 *メンバー セット*関数は*vtPropType*で指定された型の引数を受け取り、何も返しません。

*vtPropType 引数*は、VARTYPE 型です。 この引数に指定できる値は、VARENUM 列挙体から取得されます。 これらの値の一覧については、「 DISP_FUNCTION の*vtRetVal*パラメーターの解説[」を参照](#disp_function)してください。 DISP_FUNCTIONの注釈にリストされているVT_EMPTYは、プロパティ データ型として使用できません。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_property_notify"></a><a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY

ディスパッチ マップに通知を含む OLE オートメーション プロパティを定義します。

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
クラスの名前

*外部名*<br/>
プロパティの外部名。

*Membername*<br/>
プロパティが格納されているメンバー変数の名前。

*を設定します。*<br/>
*sz 外部名*の通知関数の名前。

*型*<br/>
プロパティの型を指定する値。

### <a name="remarks"></a>解説

DISP_PROPERTYで定義されたプロパティとは異なり、DISP_PROPERTY_NOTIFYで定義されたプロパティは、プロパティが変更されたときに *、pfnAfterSet*で指定された関数を自動的に呼び出します。

*vtPropType 引数*は、VARTYPE 型です。 この引数に指定できる値は、VARENUM 列挙体から取得されます。

|Symbol|プロパティの種類|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**長い**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPディスパッチ|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_property_param"></a><a name="disp_property_param"></a>DISP_PROPERTY_PARAM

独立`Get`したメンバー関数でアクセスされる`Set`プロパティを定義します。

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
クラスの名前

*名前を変更します。*<br/>
プロパティの外部名。

*を取得する*<br/>
プロパティを取得するために使用するメンバー関数の名前。

*を設定します。*<br/>
プロパティの設定に使用するメンバー関数の名前。

*型*<br/>
プロパティの型を指定する値。

*vtsパラム*<br/>
各パラメーターに対して`VTS_*`1 つずつ、スペースで区切られたバリアント 型の文字列。

### <a name="remarks"></a>解説

DISP_PROPERTY_EX マクロとは異なり、このマクロでは、プロパティのパラメーター リストを指定できます。 これは、インデックス付けまたはパラメータ化されたプロパティを実装する場合に便利です。

### <a name="example"></a>例

次の get および set メンバー関数の宣言を検討して、ユーザーがプロパティにアクセスするときに特定の行と列を要求できるようにします。

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

これらは、コントロールディスパッチ マップ内の次のDISP_PROPERTY_PARAMマクロに対応します。

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

別の例として、次の get および set メンバー関数を検討してください。

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

これらは、コントロールディスパッチ マップ内の次のDISP_PROPERTY_PARAMマクロに対応します。

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="disp_defvalue"></a><a name="disp_defvalue"></a>DISP_DEFVALUE

既存のプロパティをオブジェクトの既定値にします。

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
クラスの名前

*名前*<br/>
オブジェクトの "値" を表すプロパティの外部名です。

### <a name="remarks"></a>解説

既定値を使用すると、Visual Basic アプリケーションのオートメーション オブジェクトのプログラミングが簡単になります。

オブジェクトの "既定値" は、オブジェクトへの参照でプロパティまたはメンバー関数が指定されていない場合に取得または設定されるプロパティです。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
