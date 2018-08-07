---
title: defaultvtable |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultvtable
dev_langs:
- C++
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 83949616f204ae37b42b91b03d69d8d803a1582f
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569671"
---
# <a name="defaultvtable"></a>defaultvtable
COM オブジェクトの既定の vtable インターフェイスとしてインターフェイスを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
[ defaultvtable(  
   interface  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *interface*  
 COM オブジェクトの既定の vtable する指定されたインターフェイスです。  
  
## <a name="remarks"></a>Remarks  
 **Defaultvtable** C++ 属性と同じ機能を持つ、 [defaultvtable](http://msdn.microsoft.com/library/windows/desktop/aa366795) MIDL 属性。  
  
## <a name="example"></a>例  
 次のコードが使用されるクラスに属性を示します**defaultvtable**を既定のインターフェイスを指定します。  
  
```cpp  
// cpp_attr_ref_defaultvtable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI1 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMyI2 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000003")]  
__interface IMyI3 {  
   HRESULT x();  
};  
  
[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),  
uuid("00000000-0000-0000-0000-000000000004")]  
class CMyC3 : public IMyI3 {};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**、**構造体**|  
|**反復可能**|いいえ|  
|**必要な属性**|**coclass**|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   