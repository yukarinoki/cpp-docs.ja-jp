---
title: 同期 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.synchronize
dev_langs:
- C++
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 304ceece506465df0a51c56b247407d351fd23b3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889798"
---
# <a name="synchronize"></a>同期
ターゲット メソッドへのアクセスを同期します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[synchronize]  
  
```  
  
## <a name="remarks"></a>コメント  
 **同期**C++ 属性は、オブジェクトの対象のメソッドを同期するためのサポートを実装します。 同期により、対象のメソッドへのアクセスを制御することで、クラスのメソッド) などの一般的なリソースを使用する複数のオブジェクト。  
  
 この属性によって挿入されたコードに呼び出し、適切な`Lock`対象メソッドの先頭にメソッド (スレッド モデルによって決まります)。 メソッドが終了したときに`Unlock`自動的に呼び出されます。 これらの関数の詳細については、次を参照してください[CComAutoThreadModule::Lock。](../atl/reference/ccomautothreadmodule-class.md#lock)  
  
 この属性を使用するには、 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)、または [vi_progid](../windows/vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば、 **progid** を適用すると、 **vi_progid** と **coclass** も適用されます。  
  
## <a name="example"></a>例  
 次のコードの同期機能を提供、`UpdateBalance`のメソッド、`CMyClass`オブジェクト。  
  
```  
// cpp_attr_ref_synchronize.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="SYNC")];  
  
[coclass,  
 threading(both),  
 vi_progid("MyProject.MyClass"),  
 progid("MyProject.MyClass.1"),  
 uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]  
class CMyClass {  
   float m_nBalance;  
  
   [synchronize]  
   void UpdateBalance(float nAdjust) {  
      m_nBalance += nAdjust;  
   }  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|クラスのメソッド|  
|**反復可能**|×|  
|**必要な属性**|**coclass**、 **progid**、 **vi_progid**のうち 1 つ以上。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [COM 属性](../windows/com-attributes.md)   
