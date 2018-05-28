---
title: size_is |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.size_is
dev_langs:
- C++
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c7f97bb82f3387e82be5bbf120db4fed9aaa092f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="sizeis"></a>size_is
サイズのポインターに割り当てられた、サイズのポインター、および 1 次元または多次元配列へのポインターのサイズのメモリのサイズを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ size_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *式*  
 サイズのポインターに割り当てられたメモリのサイズ。  
  
## <a name="remarks"></a>コメント  
 **Size_is** C++ 属性と同じ機能を持つ、 [size_is](http://msdn.microsoft.com/library/windows/desktop/aa367164) MIDL 属性。  
  
## <a name="example"></a>例  
 例を参照して[first_is](../windows/first-is.md)配列のセクションを指定する方法のサンプルについてはします。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|フィールドに`struct`または**共用体**パラメーターをインターフェイスでは、インターフェイス メソッド|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|**max_is**|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [max_is](../windows/max-is.md)   
 [length_is](../windows/length-is.md)   
