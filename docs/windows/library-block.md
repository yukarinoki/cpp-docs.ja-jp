---
title: library_block |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.library_block
dev_langs:
- C++
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dbd97897138edffba12baf47d64465b1f6ca0df4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877892"
---
# <a name="libraryblock"></a>library_block
IDL ライブラリ ブロックの内部構造を配置します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[library_block]  
  
```  
  
## <a name="remarks"></a>コメント  
 ライブラリ ブロックの内部構造を配置すると、参照されているかどうかに関係なく、タイプ ライブラリに渡されることを確認してください。 既定では、唯一の構成要素の変更によって、[コクラス](../windows/coclass.md)、[ディスパッチ インターフェイス](../windows/dispinterface.md)、および[idl_module](../windows/idl-module.md)属性は、ライブラリ ブロックに配置されます。  
  
## <a name="example"></a>例  
 次のコードでは、カスタム インターフェイスはライブラリ ブロック内に配置します。  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
};  
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
 [コンパイラ属性](../windows/compiler-attributes.md)   
 [スタンドアロン属性](../windows/stand-alone-attributes.md)   
