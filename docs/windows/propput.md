---
title: propput |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propput
dev_langs:
- C++
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: af96a6825c88fb479709b2b6138f3fe6286b8b17
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016812"
---
# <a name="propput"></a>propput
プロパティ設定関数を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[propput]  
```  
  
## <a name="remarks"></a>Remarks  
 **Propput** C++ 属性と同じ機能を持つ、 [propput](http://msdn.microsoft.com/library/windows/desktop/aa367146) MIDL 属性。  
  
## <a name="example"></a>例  
 例をご覧ください[バインド可能な](../windows/bindable.md)の使用サンプル**propput**します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|メソッド|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|`propget`, `propputref`|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [メソッドの属性](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propputref](../windows/propputref.md)