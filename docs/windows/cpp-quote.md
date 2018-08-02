---
title: cpp_quote |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.cpp_quote
dev_langs:
- C++
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3dc81eacdbadb971ab86f4cfde1353e89bbe1342
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463828"
---
# <a name="cppquote"></a>cpp_quote
生成された .idl ファイルに、引用符なしの指定した文字列を出力します。  
  
## <a name="syntax"></a>構文  
  
```  
[ cpp_quote(  
   "statement"  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 *statement*  
 C 命令。  
  
## <a name="remarks"></a>Remarks  
 **Cpp_quote** C++ 属性は、.idl ファイル内のプリプロセッサ ディレクティブを配置する場合に便利です。  
  
 使用することも**cpp_quote** MIDL コンパイルの一部として、.h ファイルを生成します。 たとえば、C の IDL 属性を使用していて、このファイルをいくつかのタスクを使用することはできません、C++ ヘッダー ファイルがある場合は、しをコンパイルできますを使用できる MIDL で生成された .h ファイルを作成すること。  
  
 **Cpp_quote**属性と同じ機能を持つ、 [cpp_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) MIDL 属性。  
  
## <a name="example"></a>例  
 例をご覧ください[デュアル](../windows/dual.md)例については、使用する方法を使用して、 **cpp_quote**します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意の場所|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [スタンドアロン属性](../windows/stand-alone-attributes.md)   