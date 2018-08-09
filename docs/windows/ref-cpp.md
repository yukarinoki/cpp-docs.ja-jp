---
title: ref (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.ref
dev_langs:
- C++
helpviewer_keywords:
- ref attribute
ms.assetid: 67e82d3e-07d9-4ef8-bf2b-0a4491d12557
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04eb49d0b0f5cb78f0dcd893ca97586e9a16e9cb
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010760"
---
# <a name="ref-c"></a>ref (C++)
参照ポインターを識別します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[ref]  
```  
  
## <a name="remarks"></a>Remarks  
 **Ref** C++ 属性と同じ機能を持つ、 [ref](http://msdn.microsoft.com/library/windows/desktop/aa367153) MIDL 属性。  
  
## <a name="example"></a>例  
 次のコードを使用する方法を示しています、 **ref**属性。  
  
```cpp  
// cpp_attr_ref_ref.cpp  
// compile with: /LD  
#include <windows.h>   
[module(name="ATLFIRELib")];  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   [id(1), unique] char * GetFirstName([in, ref] char * pszFullName );   
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**typedef**パラメーターをインターフェイス、インターフェイス メソッド|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   