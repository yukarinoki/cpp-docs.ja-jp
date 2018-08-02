---
title: ケース (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.case
dev_langs:
- C++
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6567650d719b56bb320f1b40eae285322bcab364
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464312"
---
# <a name="case-c"></a>case (C++)
使用される、 [switch_type](../windows/switch-type.md)属性、**共用体**します。  
  
## <a name="syntax"></a>構文  
  
```  
[ case(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *値*  
 入力の処理を提供する値。 型**値**次の種類のいずれかを指定できます。  
  
-   `int`  
  
-   `char`  
  
-   `boolean`  
  
-   `enum`  
  
 または、このような種類の識別子。  
  
## <a name="remarks"></a>Remarks  
 **ケース**C++ 属性と同じ機能を持つ、**ケース**MIDL 属性。 この属性でのみ使用、 [switch_type](../windows/switch-type.md)属性。  
  
## <a name="example"></a>例  
 次のコードの使い方を示しています、**ケース**属性。  
  
```cpp  
// cpp_attr_ref_case.cpp  
// compile with: /LD  
#include <unknwn.h>  
[export]  
struct SizedValue2 {  
   [switch_type(char), switch_is(kind)] union {  
      [case(1), string]  
          wchar_t* wval;  
      [default, string]  
          char* val;  
   };  
    char kind;  
};  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|メンバー、**クラス**または**構造体**|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   