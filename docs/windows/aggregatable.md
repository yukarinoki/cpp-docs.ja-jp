---
title: 集計可能では |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregatable
dev_langs:
- C++
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b5d94a1e66043a83e2ffb2aa8c1d44d9cbd16cc
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467197"
---
# <a name="aggregatable"></a>aggregatable
クラスは、集計をサポートしていることを示します。  
  
## <a name="syntax"></a>構文  
  
```  
[ aggregatable(   
   value  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *値*(省略可能)  
 COM オブジェクトを集計できるかを示すパラメーター:  
  
-   **決して**COM オブジェクトを集約することはできません。  
  
-   **許可されている**COM オブジェクトを直接作成できるまたは集計することができます。 既定値です。  
  
-   **常に**COM オブジェクトが直接作成することはできず、集計のみできます。 呼び出すと`CoCreateInstance`、このオブジェクトの集約オブジェクトを指定する必要があります`IUnknown`インターフェイス (制御`IUnknown`)。  
  
## <a name="remarks"></a>Remarks  
 **集約可能**C++ 属性と同じ機能を持つ、[集約可能](http://msdn.microsoft.com/library/windows/desktop/aa366721)MIDL 属性。 つまり、コンパイラが合格する、**集約可能**経由の属性は、生成された .idl ファイルをします。  
  
 この属性を使用するには、 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)、または [vi_progid](../windows/vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば場合、`progid`が適用される`vi_progid`と`coclass`も適用されます。  
  
 **ATL プロジェクト**  
  
 この属性が ATL を使用するプロジェクト内で使用されている場合、属性の動作は変わります。 前に説明した動作に加え、属性も次のマクロのいずれかのクラスに追加ターゲット。  
  
|パラメーター値|挿入されたマクロ|  
|---------------------|--------------------|  
|*ぜんぜん*|[DECLARE_NOT_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|  
|*許可されています。*|[DECLARE_POLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|  
|*常時*|[集約](../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|  
  
## <a name="example"></a>例  
  
```cpp  
// cpp_attr_ref_aggregatable.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyModule")];  
  
[ coclass, aggregatable(allowed),  
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**、**構造体**|  
|**反復可能**|いいえ|  
|**必要な属性**|次のいずれかまたは: `coclass`、 `progid`、または`vi_progid`します。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [集計](http://msdn.microsoft.com/library/windows/desktop/ms686558)   