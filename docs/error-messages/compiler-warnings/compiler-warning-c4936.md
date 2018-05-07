---
title: コンパイラの警告 C4936 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcf9f32a4a1b1e43cb4bd69c754e3ae3a98bff3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4936"></a>コンパイラの警告 C4936
この __declspec は、/clr または /clr:pure でコンパイルされるときのみサポートされます  
  
 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で推奨されなくなりました。  
  
 `__declspec` 修飾子が使用されましたが、この `__declspec` 修飾子は、いずれかの [/clr](../../build/reference/clr-common-language-runtime-compilation.md) オプションでコンパイルされた場合にのみ有効です。  
  
 詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。  
  
 C4936 は、常にエラーとして表示されます。  [warning](../../preprocessor/warning.md) プラグマを使用して、C4936 を無効にすることができます。  
  
 次の例では C4936 が生成されます。  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```