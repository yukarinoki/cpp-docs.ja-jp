---
title: 同期 |Microsoft Docs
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
ms.openlocfilehash: 583f05e3496ea6308dac8c7fa37c7e350165e74b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020054"
---
# <a name="synchronize"></a>同期
ターゲット メソッドへのアクセスを同期します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[synchronize]  
```  
  
## <a name="remarks"></a>Remarks  
 **同期**C++ 属性には、オブジェクトのターゲット メソッドを同期するためのサポートが実装されています。 同期により、ターゲット メソッドへのアクセスを制御することで、クラスのメソッド) などの一般的なリソースを使用する複数のオブジェクト。  
  
 この属性によって挿入されたコードの呼び出し、適切な`Lock`ターゲット メソッドの先頭には、(スレッド処理モデルによって決定) メソッドです。 メソッドが終了したときに`Unlock`自動的に呼び出されます。 これらの関数の詳細については、次を参照してください[CComAutoThreadModule::Lock。](../atl/reference/ccomautothreadmodule-class.md#lock)  
  
 この属性を使用するには、 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)、または [vi_progid](../windows/vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば場合、`progid`が適用される`vi_progid`と`coclass`も適用されます。  
  
## <a name="example"></a>例  
 次のコードの同期、`UpdateBalance`のメソッド、`CMyClass`オブジェクト。  
  
```cpp  
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
|**反復可能**|いいえ|  
|**必要な属性**|次のいずれかまたは: `coclass`、 `progid`、または`vi_progid`します。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [COM 属性](../windows/com-attributes.md)   