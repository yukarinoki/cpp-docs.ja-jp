---
title: 制限付き |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: af30716208b4caf949630ba5f6965fcc6a1a54c2
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017059"
---
# <a name="restricted"></a>restricted
モジュール、インターフェイス、またはディスパッチ インターフェイスのメンバーを任意に呼び出すことはできませんを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[ restricted(  
   interfaces  
) ]  
```  
  
### <a name="parameters"></a>パラメーター  
 *interfaces*  
 COM オブジェクトに任意に呼ぶことが 1 つまたは複数のインターフェイス。 このパラメーターはクラスに適用される場合に有効です。  
  
## <a name="remarks"></a>Remarks  
 **制限**C++ 属性と同じ機能を持つ、[制限](http://msdn.microsoft.com/library/windows/desktop/aa367157)MIDL 属性。  
  
## <a name="example"></a>例  
 次のコードを使用する方法を示しています、**制限**属性。  
  
```cpp  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイスのメソッド、**インターフェイス**、**クラス**、**構造体**|  
|**反復可能**|いいえ|  
|**必要な属性**|**コクラス**(に適用すると**クラス**または**構造体**)|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [メソッド属性](../windows/method-attributes.md)   