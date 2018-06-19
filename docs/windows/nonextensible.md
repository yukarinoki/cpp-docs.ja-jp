---
title: nonextensible |Microsoft ドキュメント
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
ms.openlocfilehash: 87cdbf66676ed2a3e6054006270b39ad80325857
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881602"
---
# <a name="nonextensible"></a>nonextensible
指定する、`IDispatch`実装にはプロパティのみが含まれます、メソッドのインターフェイスの説明で一覧表示および実行時にメンバーを追加して拡張することはできません。  
  
## <a name="syntax"></a>構文  
  
```  
  
[nonextensible]  
  
```  
  
## <a name="remarks"></a>コメント  
 **Nonextensible** C++ 属性と同じ機能を持つ、 [nonextensible](http://msdn.microsoft.com/library/windows/desktop/aa367120) MIDL 属性。  
  
 使用**nonextensible**も必要です、 [oleautomation](../windows/oleautomation.md)属性。  
  
## <a name="example"></a>例  
 次のコードの用途の 1 つを示しています、 **nonextensible**属性。  
  
```  
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
|**対象**|`interface`|  
|**反復可能**|×|  
|**必要な属性**|**デュアル**と**oleautomation**、または**ディスパッチ インターフェイス**|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
