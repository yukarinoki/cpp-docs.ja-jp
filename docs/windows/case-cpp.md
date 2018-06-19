---
title: ケース (C++) |Microsoft ドキュメント
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
ms.openlocfilehash: 30d665861688054a4f6b7491f449014afe646c71
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860958"
---
# <a name="case-c"></a>case (C++)
使用される、 [switch_type](../windows/switch-type.md)属性、**共用体**です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *値*  
 入力の処理を提供する値。 型**値**種類は次のいずれかになります。  
  
-   `int`  
  
-   `char`  
  
-   `boolean`  
  
-   `enum`  
  
 または、このような型の識別子。  
  
## <a name="remarks"></a>コメント  
 **ケース**C++ 属性と同じ機能を持つ、**ケース**MIDL 属性。 この属性を使用してのみ、 [switch_type](../windows/switch-type.md)属性。  
  
## <a name="example"></a>例  
 次のコードの使い方を示しています、**ケース**属性。  
  
```  
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
|**対象**|メンバー、**クラス**または `struct`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
