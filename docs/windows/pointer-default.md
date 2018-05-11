---
title: pointer_default |Microsoft ドキュメント
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
ms.openlocfilehash: ee904f9243cf642d3a942d4bc323f5ec381b0480
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="pointerdefault"></a>pointer_default
パラメーター リストに表示される最上位のポインターを除く、すべてのポインターの既定のポインターの属性を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *値*  
 ポインター型を記述する値: **ptr**、 `ref`、または**一意**です。  
  
## <a name="remarks"></a>コメント  
 **Pointer_default** C++ 属性と同じ機能を持つ、 [pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL 属性。  
  
## <a name="example"></a>例  
 例を参照して[defaultvalue](../windows/defaultvalue.md)の使用例の**pointer_default**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
