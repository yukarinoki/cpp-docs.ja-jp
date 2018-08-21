---
title: pointer_default |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 98e3b9e78f46b14dfeca18a8e69538111d3ba219
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010316"
---
# <a name="pointerdefault"></a>pointer_default
パラメーター リストに表示される最上位レベルのポインターを除く、すべてのポインターの既定のポインターの属性を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[ pointer_default(  
   value  
) ]  
```  
  
### <a name="parameters"></a>パラメーター  
 *値*  
 ポインター型を記述する値: **ptr**、 **ref**、または**一意**します。  
  
## <a name="remarks"></a>Remarks  
 **Pointer_default** C++ 属性と同じ機能を持つ、 [pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL 属性。  
  
## <a name="example"></a>例  
 例をご覧ください[defaultvalue](../windows/defaultvalue.md)の使用サンプル**pointer_default**します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**interface**|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   