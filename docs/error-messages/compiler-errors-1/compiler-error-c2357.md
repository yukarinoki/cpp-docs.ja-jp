---
title: コンパイラ エラー C2357 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2357
dev_langs:
- C++
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c8739576eced6b831f5c3b72d85417e2daabb06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2357"></a>コンパイラ エラー C2357
'identifier': 'type' 型の関数である必要があります  
  
 コードの宣言のバージョンが、`atexit`コンパイラによって内部的に宣言された関数のバージョンに一致しません。 宣言`atexit`次のようにします。  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 詳細については、次を参照してください。 [init_seg](../../preprocessor/init-seg.md)です。  
  
 次の例では、C2357 が生成されます。  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```