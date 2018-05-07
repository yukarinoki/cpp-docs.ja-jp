---
title: コンパイラ エラー C2728 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2728
dev_langs:
- C++
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e954ba38efc2e1ef7bc4b203c8b54876f7aae0ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2728"></a>コンパイラ エラー C2728
'type': ネイティブ配列はこの型を含むことはできません  
  
 配列作成の構文が、マネージまたは WinRT オブジェクトの配列の作成に使用されました。 ネイティブ配列の構文を使用して、マネージまたは WinRT オブジェクトの配列を作成することはできません。  
  
 詳細については、「 [配列](../../windows/arrays-cpp-component-extensions.md)」を参照してください。  
  
 次の例では、C2728 を生成し、その修正方法を示しています。  
  
```  
// C2728.cpp  
// compile with: /clr  
  
int main() {  
   int^ arr[5];   // C2728  
  
   // try the following line instead  
   array<int>^arr2;  
}  
```  
