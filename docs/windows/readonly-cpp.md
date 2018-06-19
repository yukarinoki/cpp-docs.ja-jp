---
title: readonly (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.readonly
dev_langs:
- C++
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87933b214dfe91f1c9f7db88127ef83da5b7201c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876567"
---
# <a name="readonly-c"></a>readonly (C++)
データ メンバーへの割り当てを禁止します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[readonly]  
  
```  
  
## <a name="remarks"></a>コメント  
 **readonly** C++ 属性には、 [readonly](http://msdn.microsoft.com/library/windows/desktop/aa367152) MIDL 属性と同じ機能があります。  
  
 メソッド パラメーターの変更を禁止する場合は、 [in](../windows/in-cpp.md) 属性を使用します。  
  
## <a name="example"></a>例  
 **readonly** 属性の使用方法は、次のコードのとおりです。  
  
```  
// cpp_attr_ref_readonly.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
  
[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]  
__interface IFireTabCtrl  
{  
   [readonly, id(1)] int i();  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス メソッド|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [データ メンバー属性](../windows/data-member-attributes.md)   
