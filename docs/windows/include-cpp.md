---
title: (C++) を含める |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.include
dev_langs:
- C++
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a2c88dd610c1a0b8a8fee4e23da1b5ad844e989c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878425"
---
# <a name="include-c"></a>include (C++)
生成された .idl ファイルに含まれる 1 つまたは複数のヘッダー ファイルを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ include(  
   header_file  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 *header_file*  
 生成された .idl ファイルに追加するファイルの名前。  
  
## <a name="remarks"></a>コメント  
 **含める**C++ 属性により、`#include`ステートメントを下に配置する、`import "docobj.idl"`生成された .idl ファイル内のステートメント。  
  
 **含める**C++ 属性と同じ機能を持つ、[含める](http://msdn.microsoft.com/library/windows/desktop/aa367052)MIDL 属性。  
  
## <a name="example"></a>例  
 次のコードを使用する方法の例を示します**含める**です。 この例では、ファイル include.h にはのみが含まれます、#include ステートメントの include です。  
  
```  
// cpp_attr_ref_include.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[include(cpp_attr_ref_include.h)];  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意の場所|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [スタンドアロン属性](../windows/stand-alone-attributes.md)   
 [インポート](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [includelib](../windows/includelib-cpp.md)   
 [importlib](../windows/importlib.md)   
