---
title: out (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.out
dev_langs:
- C++
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f9a3d102050da84f7dcbc8714a4c04b46cf3f5a1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606125"
---
# <a name="out-c"></a>out (C++)
呼び出されたプロシージャから呼び出したプロシージャ (サーバーからクライアント) に返されるポインター パラメーターを示します。  
  
## <a name="syntax"></a>構文  
  
```  
[out]  
```  
  
## <a name="remarks"></a>Remarks  
 **out** C++ 属性には、 [propput](http://msdn.microsoft.com/library/windows/desktop/aa367136) MIDL 属性と同じ機能があります。  
  
## <a name="example"></a>例  
 [out](../windows/bindable.md) の使用サンプルについては、「 **bindable**」の例を参照してください。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス パラメーター|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [defaultvalue](../windows/defaultvalue.md)   
 [ID](../windows/id.md)   