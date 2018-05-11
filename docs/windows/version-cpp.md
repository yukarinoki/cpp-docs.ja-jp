---
title: バージョン (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 43da63d75d3541915eba3e561ee08fe1048fa579
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="version-c"></a>version (C++)
クラスの複数のバージョン間で特定のバージョンを識別します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *version*  
 コクラスのバージョン番号。 指定しない場合、1.0 は .idl ファイルに配置されます。  
  
## <a name="remarks"></a>コメント  
 **バージョン**C++ 属性と同じ機能を持つ、[バージョン](http://msdn.microsoft.com/library/windows/desktop/aa367306)MIDL 属性が生成された .idl ファイルに渡されます。  
  
## <a name="example"></a>例  
 参照してください、[バインド可能な](../windows/bindable.md)のサンプルの使用例**バージョン**します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|**coclass**|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ属性](../windows/compiler-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
