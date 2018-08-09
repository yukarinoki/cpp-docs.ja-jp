---
title: helpstring |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstring
dev_langs:
- C++
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df452614bfd5ee95a810300809678e28abfbf8ef
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643161"
---
# <a name="helpstring"></a>helpstring
適用先となる要素を記述するために使用される文字列を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[ helpstring(  
   "string"  
) ]  
```  
  
### <a name="parameters"></a>パラメーター  
 *string*  
 ヘルプ文字列のテキスト。  
  
## <a name="remarks"></a>Remarks  
 **Helpstring** C++ 属性と同じ機能を持つ、 [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) MIDL 属性。  
  
## <a name="example"></a>例  
 例をご覧ください[defaultvalue](../windows/defaultvalue.md)を使用する方法の例については**helpstring**します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**インターフェイス**、 **typedef**、**クラス**メソッド、プロパティ|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [メソッドの属性](../windows/method-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Helpfile](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   