---
title: defaultvalue |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultvalue
dev_langs:
- C++
helpviewer_keywords:
- defaultvalue attribute
ms.assetid: efa5d050-b2cc-4d9e-9b8e-79954f218d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c838f057d9c5e59193d0578fe8aa871b1b75ee9d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873418"
---
# <a name="defaultvalue"></a>defaultvalue
型指定されたオプションのパラメーターの既定値を指定をできます。  
  
## <a name="syntax"></a>構文  
  
```  
  
[ defaultvalue= value ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *値*  
 パラメーターの既定値。  
  
## <a name="remarks"></a>コメント  
 **Defaultvalue** C++ 属性と同じ機能を持つ、 [defaultvalue](http://msdn.microsoft.com/library/windows/desktop/aa366793) MIDL 属性。  
  
## <a name="example"></a>例  
 インターフェイス メソッドを使用して、次のコードを示しています、 **defaultvalue**属性。  
  
```  
// cpp_attr_ref_defaultvalue.cpp  
// compile with: /LD  
#include <windows.h>  
  
[export] typedef long HRESULT;  
[export, ptr, string] typedef unsigned char * MY_STRING_TYPE;  
  
[  uuid("479B29EE-9A2C-11D0-B696-00A0C903487A"),  
   dual, oleautomation,  
   helpstring("IFireTabCtrl Interface"),  
   helpcontext(122), pointer_default(unique) ]  
  
__interface IFireTabCtrl : IDispatch {  
   [bindable, propget] HRESULT get_Size([out, retval, defaultvalue("33")] long *nSize);  
   [bindable, propput] HRESULT put_Size([in] int nSize);  
};  
  
[ module(name="ATLFIRELib", uuid="479B29E1-9A2C-11D0-B696-00A0C903487A",  
      version="1.0", helpstring="ATLFire 1.0 Type Library") ];  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス パラメーター|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [out](../windows/out-cpp.md)   
 [戻り値](../windows/retval.md)   
 [in](../windows/in-cpp.md)   
 [pointer_default](../windows/pointer-default.md)   
 [unique](../windows/unique-cpp.md)   
