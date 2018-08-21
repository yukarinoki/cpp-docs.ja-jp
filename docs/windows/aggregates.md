---
title: 集計 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregates
dev_langs:
- C++
helpviewer_keywords:
- aggregates attribute
- aggregation [C++]
- aggregate objects [C++], aggregates attribute
- aggregates [C++]
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb77d43dabe223308ae3eb0c34ec22d0c1624e2e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646667"
---
# <a name="aggregates"></a>aggregates
オブジェクトが CLSID で指定されたオブジェクトを集約することを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[ aggregates(  
   clsid,  
   variable_name  
) ]  
```  
  
### <a name="parameters"></a>パラメーター  
 *clsid*  
 集約可能オブジェクトの CLSID を指定します。  
  
 *variable_name*  
 挿入する変数の名前。 この変数が含まれています、`IUnknown`の集約対象オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 オブジェクトに適用すると、 **aggregates** C++ 属性は ( `clsid`によって指定された) 集約対象オブジェクトのアウター ラッパーを実装します。  
  
 この属性を使用するには、 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)、または [vi_progid](../windows/vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば場合、`progid`が適用される`vi_progid`と`coclass`も適用されます。  
  
### <a name="atl-projects"></a>ATL プロジェクト  
  
 この属性が ATL を使用するプロジェクト内で使用されている場合、属性の動作は変わります。 まず、次のエントリがターゲット オブジェクトの COM マップに追加されます。  
  
```  
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```  
  
 また、 [DECLARE_GET_CONTROLLING_UNKNOWN](../atl/reference/aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) マクロも追加されます。  
  
## <a name="example"></a>例  
  
```cpp  
// cpp_attr_ref_aggregates.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
// requires 'aggregatable.dll'  
// see aggregatable attribute to create 'aggregatable.dll'  
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;  
  
[module (name="MYObject")];  
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]  
__interface IObject  
{  
};  
  
[ coclass, aggregates(__uuidof(CMyClass)),   
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]  
struct CObject : IObject  
{  
   int i;  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**、**構造体**|  
|**反復可能**|[はい]|  
|**必要な属性**|次のいずれかまたは: `coclass`、 `progid`、または`vi_progid`します。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [COM 属性](../windows/com-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [集計](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [集約可能](http://msdn.microsoft.com/library/windows/desktop/aa366721)   
 [COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](../atl/reference/com-interface-entry-macros.md#com_interface_entry_autoaggregate_blind)   