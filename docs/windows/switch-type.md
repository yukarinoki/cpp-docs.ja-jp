---
title: switch_type |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.switch_type
dev_langs:
- C++
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1870e1ee623d8495e9f19dd8f32ea9382070bc14
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="switchtype"></a>switch_type
共用体の判別変数として使用される変数の型を識別します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[switch_type(  
type  
}]  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `type`  
 スイッチの種類は、整数、文字、ブール値、または列挙型を指定できます。  
  
## <a name="remarks"></a>コメント  
 **Switch_type** C++ 属性と同じ機能を持つ、 [switch_type](http://msdn.microsoft.com/library/windows/desktop/aa367276) MIDL 属性。  
  
 C++ 属性をサポートしていない[共用体をカプセル化された](http://msdn.microsoft.com/library/windows/desktop/aa366811)です。 [カプセル化されていない共用体](http://msdn.microsoft.com/library/windows/desktop/aa367119)次の形式でのみサポートされます。  
  
```  
// cpp_attr_ref_switch_type.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
[ export ]  
struct SizedValue2 {  
   [switch_type("char"), switch_is(kind)] union {  
      [case(1), string]  
         wchar_t* wval;  
      [default, string]  
         char* val;  
   };  
   char kind;  
};  
```  
  
## <a name="example"></a>例  
 参照してください、[ケース](../windows/case-cpp.md)のサンプルの使用例**switch_type**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`typedef`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
