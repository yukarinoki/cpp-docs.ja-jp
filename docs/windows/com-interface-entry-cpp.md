---
title: com_interface_entry (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.com_interface_entry
dev_langs:
- C++
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b0fb7de1987d77f19e04f867aac68cbcc67c1f1e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="cominterfaceentry-c"></a>com_interface_entry (C++)
ターゲット クラスの COM マップにインターフェイス エントリを追加します。  
  
## <a name="syntax"></a>構文  
  
```  
  
     [ com_interface_entry(   
  com_interface_entry  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *com_interface_entry*  
 エントリの実際のテキストを含む文字列。 使用可能な値の一覧は、次を参照してください。 [COM_INTERFACE_ENTRY マクロ](../atl/reference/com-interface-entry-macros.md)です。  
  
## <a name="remarks"></a>コメント  
 `com_interface_entry` C++ 属性は、文字列の unabridged 内容を対象オブジェクトの COM インターフェイス マップに挿入します。 属性はターゲット オブジェクトに 1 回適用する場合、エントリは、既存のインターフェイス マップの先頭に挿入されます。 属性は、同じターゲット オブジェクトに繰り返し適用した場合、エントリは、受信した順序で、インターフェイス マップの先頭に挿入されます。  
  
 この属性を使用するには、 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)、または [vi_progid](../windows/vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば、 **progid** を適用すると、 **vi_progid** と **coclass** も適用されます。  
  
 の最初の使用`com_interface_entry`インターフェイス マップの先頭に挿入する新しいインターフェイスにより COM_INTERFACE_ENTRY 種類は次のいずれかにする必要があります。  
  
-   COM_INTERFACE_ENTRY  
  
-   COM_INTERFACE_ENTRY_IID  
  
-   COM_INTERFACE_ENTRY2  
  
-   COM_INTERFACE_ENTRY2_IID  
  
 追加の使用法、`com_interface_entry`属性はサポートされているすべての COM_INTERFACE_ENTRY 型を使用できます。  
  
 この制限は、ATL は、インターフェイス マップに最初のエントリを id として使用するために必要な**IUnknown**。 したがって、エントリは有効なインターフェイスである必要があります。 たとえば、次のコード サンプルはインターフェイス マップの最初のエントリで、実際の COM インターフェイスが指定されていないため無効です。  
  
```  
[ coclass, com_interface_entry =  
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"  
]  
   class CMyClass  
   {  
   };  
```  
  
## <a name="example"></a>例  
 次のコードでは、2 つのエントリを追加するは、既存の COM インターフェイス マップ**CMyBaseClass**です。 1 つは、標準インターフェイスであり、2 番目、 **IDebugTest**インターフェイスです。  
  
```  
// cpp_attr_ref_com_interface_entry.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name ="ldld")];  
  
[ object,  
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]  
__interface IDebugTest{};  
  
[ object,  
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]  
__interface IMyClass{};  
  
[ coclass,  
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),  
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),  
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")  
]  
  
class CMyClass: public IMyClass, public IDebugTest  
{  
};  
```  
  
 結果の COM オブジェクトのマップ**CMyBaseClass**のとおりです。  
  
```  
BEGIN_COM_MAP(CMyClass)  
    COM_INTERFACE_ENTRY (IMyClass)  
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)  
    COM_INTERFACE_ENTRY(IMyClass)  
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)  
    COM_INTERFACE_ENTRY(IDebugTest)  
    COM_INTERFACE_ENTRY(IProvideClassInfo)  
END_COM_MAP()  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|[はい]|  
|**必要な属性**|**coclass**、 **progid**、 **vi_progid**のうち 1 つ以上。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [COM 属性](../windows/com-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
