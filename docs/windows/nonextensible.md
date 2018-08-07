---
title: nonextensible |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f670da3ad4858f3c09903f2ed3ec6aa58268180
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608496"
---
# <a name="nonextensible"></a>nonextensible
指定します、`IDispatch`実装にはプロパティのみが含まれていて、メソッドは、インターフェイスの説明に記載して、実行時にメンバーを追加して拡張することはできません。  
  
## <a name="syntax"></a>構文  
  
```  
[nonextensible]  
```  
  
## <a name="remarks"></a>Remarks  
 **Nonextensible** C++ 属性と同じ機能を持つ、 [nonextensible](http://msdn.microsoft.com/library/windows/desktop/aa367120) MIDL 属性。  
  
 使用**nonextensible**も必要です、 [oleautomation](../windows/oleautomation.md)属性。  
  
## <a name="example"></a>例  
 次のコードの用途の 1 つを示しています、 **nonextensible**属性。  
  
```cpp  
// cpp_attr_ref_nonextensible.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export] typedef long HRESULT;  
  
[dual, nonextensible, ms_union, oleautomation,   
uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   HRESULT procedure (int i);   
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**interface**|  
|**反復可能**|いいえ|  
|**必要な属性**|`dual` `oleautomation`、または `dispinterface`|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   