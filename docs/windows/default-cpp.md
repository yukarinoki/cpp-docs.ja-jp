---
title: 既定 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.default
dev_langs:
- C++
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fbd2ab9481d8658bac75b62a4afa18f3ff77f0d5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646258"
---
# <a name="default-c"></a>default (C++)
コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[ default(  
   interface1,  
   interface2  
) ]  
```  
  
### <a name="parameters"></a>パラメーター  
 *interface1*  
 **default** 属性で定義されているクラスに基づいてオブジェクトを作成するスクリプト環境で使用可能になる既定のインターフェイス。  
  
 既定のインターフェイスが指定されていない場合は、最初に見つかったソース以外のインターフェイスが既定値として使用されます。  
  
 *interface2*(省略可能)  
 既定のソース インターフェイス。 このインターフェイスを指定する場合は、 [source](../windows/source-cpp.md) 属性も使用する必要があります。  
  
 既定のソース インターフェイスが指定されていない場合は、最初のソース インターフェイスが既定値として使用されます。  
  
## <a name="remarks"></a>Remarks  
 **default** C++ 属性には、 [default](http://msdn.microsoft.com/library/windows/desktop/aa366787) MIDL 属性と同じ機能があります。 また、 **default** 属性は、 [case](../windows/case-cpp.md) 属性と共に使用されます。  
  
## <a name="example"></a>例  
 次のコードはどのように**既定**をコクラスの定義で指定するため`ICustomDispatch`既定のプログラミング インターフェイスとして。  
  
```cpp  
// cpp_attr_ref_default.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]   
__interface IDual {  
   HRESULT Dual([in] long l, [out, retval] long *pLong);  
};  
  
[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustomDispatch : public IDispatch {  
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);  
};  
  
[   coclass,  
   default(ICustomDispatch),   
   source(IDual),  
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]  
class CClass : public ICustom, public IDual, public ICustomDispatch {  
   HRESULT Custom(long l, long *pLong) { return(S_OK); }  
   HRESULT Dual(long l, long *pLong) { return(S_OK); }  
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }  
};  
  
int main() {  
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch  
   CClass *pClass = new CClass;  
  
   long llong;  
  
   pClass->custom(1, &llong);  
   pClass->dual(1, &llong);  
   pClass->dispinterface(1, &llong);  
   pClass->dispatch(1, &llong);  
  
   delete pClass;  
#endif  
   return(0);  
}  
```  
  
 [default](../windows/source-cpp.md) の使用例については、「 **source**」も参照してくださいにも含まれています。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**、**構造体**、データ メンバー|  
|**反復可能**|いいえ|  
|**必要な属性**|**コクラス**(に適用すると**クラス**または**構造体**)|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [coclass](../windows/coclass.md)   