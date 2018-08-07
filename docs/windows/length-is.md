---
title: length_is |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.length_is
dev_langs:
- C++
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e0294c7cc118c4014e998ad570d7e1e453ea2c6
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606502"
---
# <a name="lengthis"></a>length_is
転送する配列要素の数を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
[ length_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>パラメーター  
 *式*  
 1 つ以上の C 言語の式。 空の引数スロットが許可されます。  
  
## <a name="remarks"></a>Remarks  
 **Length_is** C++ 属性と同じ機能を持つ、 [length_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL 属性。  
  
## <a name="example"></a>例  
 参照してください[first_is](../windows/first-is.md)配列のセクションを指定する方法の例についてはします。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|フィールドに**構造体**または**共用体**パラメーターをインターフェイス、インターフェイス メソッド|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [last_is](../windows/last-is.md)   
 [size_is](../windows/size-is.md)   