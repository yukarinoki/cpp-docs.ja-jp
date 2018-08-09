---
title: async_uuid |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.async_uuid
dev_langs:
- C++
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0596b15daff5567e2572bf8c1f2b401cdf300a49
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642413"
---
# <a name="asyncuuid"></a>async_uuid
同期および非同期の両方のバージョンの COM インターフェイスを定義する、MIDL コンパイラに指示する UUID を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[async_uuid (  
   uuid  
)]  
```  
  
### <a name="parameters"></a>パラメーター  
 *uuid*  
 インターフェイスのバージョンを識別するための UUID。  
  
## <a name="remarks"></a>Remarks  
 **Async_uuid** C++ 属性と同じ機能を持つ、 [async_uuid](http://msdn.microsoft.com/library/windows/desktop/aa366735) MIDL 属性。  
  
## <a name="example"></a>例  
  
```cpp  
// cpp_attr_ref_async_uuid.cpp  
// compile with: /LD  
#include <Windows.h>  
[module(name="Test")];  
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb"),   
async_uuid("e8583106-38fd-487e-912e-4fc8645c677e")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|**デュアル**、**ディスパッチ インターフェイス**|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   