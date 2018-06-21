---
title: ディスパッチ マップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 5af6a8644514b18af3397fb22d54d42f649eed09
ms.sourcegitcommit: 05075fce8a0ed7fddb99f50f3931db966a91450d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271319"
---
# <a name="dispatch-maps"></a>ディスパッチ マップ
OLE オートメーションでは、メソッドを呼び出すと、アプリケーション間でプロパティにアクセスする方法を提供します。 これらの要求をディスパッチするためには、Microsoft Foundation Class ライブラリによって提供されるメカニズムは、「ディスパッチ マップ」オブジェクトの関数とプロパティ、およびプロパティ自体のデータ型の内部および外部の名前を指定します。関数の引数。  
  
### <a name="dispatch-maps"></a>ディスパッチ マップ  
  
|||  
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
  
##  <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP  
 場合、 `CCmdTarget`-プログラム内の派生クラスは、クラスがそのメソッドとプロパティを公開するディスパッチ マップを用意する必要がありますの OLE オートメーションをサポートしています。  
  
```   
DECLARE_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Remarks  
 使用して、`DECLARE_DISPATCH_MAP`クラスの宣言の最後にマクロです。 次に、します。クラスのメンバーを定義する CPP ファイルの機能を使用して、`BEGIN_DISPATCH_MAP`マクロです。 クラスの各メソッドとプロパティを公開のマクロのエントリを含める ( `DISP_FUNCTION`、`DISP_PROPERTY`など)。 最後に、使用して、`END_DISPATCH_MAP`マクロです。  
  
> [!NOTE]
>  後のすべてのメンバーを宣言する場合`DECLARE_DISPATCH_MAP`、新しいアクセスの種類を指定する必要があります (**パブリック**、 `private`、または`protected`) にします。  
  
 アプリケーション ウィザードとコードのウィザードでは、オートメーション クラスの作成とディスパッチ マップの管理を支援します。 ディスパッチ マップの詳細については、次を参照してください。[オートメーション サーバー](../../mfc/automation-servers.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  

##  <a name="begin_dispatch_map"></a>  BEGIN_DISPATCH_MAP  
 ディスパッチ マップの定義を宣言します。  
  
```  
BEGIN_DISPATCH_MAP(theClass, baseClass)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このディスパッチ マップを所有するクラスの名前を指定します。  
  
 `baseClass`  
 基本クラスの名前を指定`theClass`です。  
  
### <a name="remarks"></a>Remarks  
 クラスのメンバー関数を定義する実装 (.cpp) ファイルでのディスパッチ マップを開始、`BEGIN_DISPATCH_MAP`マクロ、ディスパッチ関数とプロパティの各マクロ エントリの追加を行いでディスパッチ マップ、 `END_DISPATCH_MAP`マクロです。  

### <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h  

##  <a name="end_dispatch_map"></a>  END_DISPATCH_MAP  
 ディスパッチ マップの定義を終了します。  
  
```   
END_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Remarks  
 組み合わせて使用する必要があります`BEGIN_DISPATCH_MAP`です。  

### <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h  

##  <a name="disp_function"></a>  DISP_FUNCTION  
 ディスパッチ マップで OLE オートメーション関数を定義します。  
  
```   
DISP_FUNCTION(
  theClass, 
  pszName, 
  pfnMember, 
  vtRetVal, 
  vtsParams)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `pszName`  
 関数の外部名。  
  
 `pfnMember`  
 このメンバー関数の名前です。  
  
 `vtRetVal`  
 関数の戻り値の型を指定する値。  
  
 `vtsParams`  
 関数のパラメーター リストを指定する 1 つまたは複数の定数のスペースで区切られた一覧です。  
  
### <a name="remarks"></a>Remarks  
 `vtRetVal`引数の型が**VARTYPE**です。 この引数の次の値がから取得された、`VARENUM`列挙します。  
  
|シンボル|戻り値の型|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**バリアント**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _** 定数。 1 つ以上のスペース (コンマではない) で区切られたこれらの値は、関数のパラメーター リストを指定します。 たとえば、オブジェクトに適用された 
  
 [!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]  
  
 ポインターを続けて短整数を短整数を含むリストを指定します。  
  
 **Vts _** 定数とその意味は次のようには。  
  
|シンボル|パラメーターの型|  
|------------|--------------------|  
|**VTS_I2**|`Short`|  
|**VTS_I4**|`Long`|  
|**VTS_R4**|**Float**|  
|**VTS_R8**|`Double`|  
|**VTS_CY**|**const CY**または**CY\***|  
|**VTS_DATE**|**DATE**|  
|**VTS_BSTR**|`LPCSTR`|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**バリアント型の const\\ \*** または**バリアント (& a)**|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_PI2**|**短い\\\***|  
|**VTS_PI4**|**長い\\\***|  
|**VTS_PR4**|**浮動小数点数\\\***|  
|**VTS_PR8**|**double 型\\\***|  
|**VTS_PCY**|**CY\\\***|  
|**VTS_PDATE**|**日付\\\***|  
|**VTS_PBSTR**|**BSTR\\\***|  
|**VTS_PDISPATCH**|**LPDISPATCH\\\***|  
|**VTS_PSCODE**|**SCODE\\\***|  
|**VTS_PBOOL**|**BOOL\\\***|  
|**VTS_PVARIANT**|**バリアント\\\***|  
|**VTS_PUNKNOWN**|**LPUNKNOWN\\\***|  
|**VTS_NONE**|パラメーターなし|  

### <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h 

##  <a name="disp_property"></a>  DISP_PROPERTY  
 ディスパッチ マップ内の OLE オートメーション プロパティを定義します。  
  
```   
DISP_PROPERTY(
  theClass, 
  pszName, 
  memberName, 
  vtPropType)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `pszName`  
 プロパティの外部名。  
  
 `memberName`  
 プロパティが格納されているメンバー変数の名前です。  
  
 `vtPropType`  
 プロパティの型を指定する値。  
  
### <a name="remarks"></a>Remarks  
 `vtPropType`引数の型が**VARTYPE**です。 この引数に指定できる値はから取得、`VARENUM`列挙します。  
  
|シンボル|**プロパティの型**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**バリアント**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 外部のクライアントで、プロパティで指定されたメンバー変数の値が変更されたとき`memberName`変更; 変更の通知は示されません。  

### <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h 

##  <a name="disp_property_ex"></a>  DISP_PROPERTY_EX  
 OLE オートメーションのプロパティと名前を取得およびディスパッチ マップ内のプロパティの値の設定に使用する関数を定義します。  
  
```   
DISP_PROPERTY_EX(
  theClass, 
  pszName, 
  memberGet, 
  memberSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `pszName`  
 プロパティの外部名。  
  
 `memberGet`  
 プロパティの取得に使用するメンバー関数の名前です。  
  
 `memberSet`  
 このメンバー関数は、プロパティを設定するための名前です。  
  
 `vtPropType`  
 プロパティの型を指定する値。  
  
### <a name="remarks"></a>Remarks  
 `memberGet`と`memberSet`関数によって署名がある、`vtPropType`引数。 `memberGet`関数は引数を使用しないで指定された型の値を返します`vtPropType`です。 `memberSet`関数がで指定された型の引数を受け取る`vtPropType`とは何も返しません。  
  
 `vtPropType`引数の型が**VARTYPE**です。 この引数に指定できる値はから取得、`VARENUM`列挙します。 これらの値の一覧は、「解説」を参照してください、`vtRetVal`パラメーター [DISP_FUNCTION](#disp_function)です。 なお`VT_EMPTY`に一覧されている、 `DISP_FUNCTION` remarks、プロパティのデータ型としては許可されていません。  

### <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h 

##  <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY  
 ディスパッチ マップで通知付きの OLE オートメーション プロパティを定義します。  
  
```   
DISP_PROPERTY_NOTIFY(
  theClass, 
  szExternalName, 
  memberName, 
  pfnAfterSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `szExternalName`  
 プロパティの外部名。  
  
 `memberName`  
 プロパティが格納されているメンバー変数の名前です。  
  
 `pfnAfterSet`  
 通知関数の名前`szExternalName`です。  
  
 `vtPropType`  
 プロパティの型を指定する値。  
  
### <a name="remarks"></a>Remarks  
 定義されたプロパティとは異なり`DISP_PROPERTY`で定義されているプロパティ`DISP_PROPERTY_NOTIFY`で指定された関数が自動的に呼び出さ`pfnAfterSet`プロパティが変更されたとき。  
  
 `vtPropType`引数の型が**VARTYPE**です。 この引数に指定できる値はから取得、`VARENUM`列挙します。  
  
|シンボル|**プロパティの型**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**バリアント**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  

### <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h 

##  <a name="disp_property_param"></a>  DISP_PROPERTY_PARAM  
 個別にアクセスするプロパティを定義**取得**と`Set`メンバー関数。  
  
```   
DISP_PROPERTY_PARAM(
  theClass, 
  pszExternalName, 
  pfnGet, 
  pfnSet, 
  vtPropType,
  vtsParams)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 *pszExternalName*  
 プロパティの外部名。  
  
 `pfnGet`  
 プロパティの取得に使用するメンバー関数の名前です。  
  
 `pfnSet`  
 このメンバー関数は、プロパティを設定するための名前です。  
  
 `vtPropType`  
 プロパティの型を指定する値。  
  
 `vtsParams`  
 スペースで区切られた文字列**vts _** バリアント型パラメーターが型パラメーターごとに 1 つです。  
  
### <a name="remarks"></a>Remarks  
 異なり、`DISP_PROPERTY_EX`マクロ、このマクロを使用するプロパティのパラメーター リストを指定します。 これは、インデックスを作成またはパラメーター化されているプロパティを実装するために役立ちます。  
  
### <a name="example"></a>例  
 Get の次の宣言を検討し、メンバー プロパティにアクセスするときに、特定の行と列を要求するユーザーに許可する機能を設定します。  
  
 [!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]  
  
 これらは、次に対応して`DISP_PROPERTY_PARAM`コントロールのディスパッチ マップ マクロ。  
  
 [!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]  
  
 別の例として、次の取得を考慮し、メンバー関数を設定します。  
  
 [!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]  
  
 これらは、次に対応して`DISP_PROPERTY_PARAM`コントロールのディスパッチ マップ マクロ。  
  
 [!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]  

### <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h 

##  <a name="disp_defvalue"></a>  DISP_DEFVALUE  
 既存のプロパティをオブジェクトの既定値になります。  
  
```   
DISP_DEFVALUE(theClass, pszName)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 クラスの名前です。  
  
 `pszName`  
 オブジェクトの"value"を表すプロパティの外部名。  
  
### <a name="remarks"></a>Remarks  
 既定値を使用して Visual Basic アプリケーションの簡単なオートメーション オブジェクトのプログラミングを行うことができます。  
  
 オブジェクトの「既定値」では、取得またはオブジェクトへの参照が、プロパティまたはメンバー関数を指定しない場合に設定されているプロパティです。  

### <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h 

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
