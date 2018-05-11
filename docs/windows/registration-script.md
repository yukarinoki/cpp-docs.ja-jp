---
title: registration_script |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.registration_script
dev_langs:
- C++
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4385dd12fccafb154a637dd5260764667d3887a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="registrationscript"></a>registration_script
指定したカスタム登録スクリプトを実行します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ registration_script(   
   script   
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *スクリプト*  
 カスタム登録スクリプト (.rgs) ファイルの完全パスです。 値**none**など`script = "none"`コクラスに登録要件がないことを示します。  
  
## <a name="remarks"></a>コメント  
 **Registration_script** C++ 属性で指定されたカスタム登録スクリプトを実行する**スクリプト**です。 この属性が指定されていない場合は、標準的な .rgs ファイル (コンポーネントを登録するための情報を含む) が使用されます。 .Rgs ファイルの詳細については、次を参照してください。 [ATL レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)です。  
  
 この属性を使用するには、 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)、または [vi_progid](../windows/vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。  
  
## <a name="example"></a>例  
 次のコードでは、コンポーネントが cpp_attr_ref_registration_script.rgs と呼ばれるレジストリ スクリプトを持つことを指定します。  
  
```  
// cpp_attr_ref_registration_script.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="REG")];  
  
[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]  
__interface IFace {};  
  
// requires "cpp_attr_ref_registration_script.rgs"  
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist  
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),  
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]  
class CMyClass:public IFace {};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|**coclass**、 **progid**、 **vi_progid**のうち 1 つ以上。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [COM 属性](../windows/com-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [rdx](../windows/rdx.md)   
