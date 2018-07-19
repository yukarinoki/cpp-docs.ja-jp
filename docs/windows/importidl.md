---
title: importidl |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5284c631813271f5682343c74cff693d1ea785e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877476"
---
# <a name="importidl"></a>importidl
指定された .idl ファイルを生成された .idl ファイルに挿入します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 `idl_file`  
 アプリケーションに対して生成される .idl ファイルにマージする .idl ファイルの名前を識別します。  
  
## <a name="remarks"></a>コメント  
 **Importidl** C++ 属性ライブラリ ブロックの外側でセクションの配置 (で`idl_file`) に、プログラムの生成された .idl ファイルとライブラリのセクション (で`idl_file`) ライブラリのセクションに、プログラムの生成された .idl ファイルです。  
  
 使用することがあります**importidl**など、生成された .idl ファイルを手動でコーディングした .idl ファイルを使用する場合。  
  
## <a name="example"></a>例  
  
```  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
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
 [インポート](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [含まれます](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
