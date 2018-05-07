---
title: typeof が t::typeid へ移動 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0ae9f772a68735555748e6edbeb6196f1a73d2c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="typeof-goes-to-ttypeid"></a>typeof から T::typeid への移行
`typeof` C++ に置き換わる可能性されてのマネージ拡張で使用する演算子、 `typeid` Visual C でキーワード。  
  
 マネージ拡張で、`__typeof()`演算子は、関連付けられている返します`Type*`オブジェクトのマネージ型の名前が渡されるときにします。 例えば:  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 新しい構文で`__typeof`が別の形式ので置き換えられた`typeid`を返す、`Type^`マネージ型が指定されている場合。  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## <a name="see-also"></a>関連項目  
 [一般的な言語の変更 (C + + CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)