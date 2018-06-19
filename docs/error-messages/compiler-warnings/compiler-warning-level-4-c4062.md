---
title: コンパイラの警告 (レベル 4) C4062 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4062
dev_langs:
- C++
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b889fb83fa3ea3de844e4ce8c74f0a7c5d150d54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293599"
---
# <a name="compiler-warning-level-4-c4062"></a>コンパイラの警告 (レベル 4) C4062
列挙型 'enumeration' を切り替えた列挙子 'identifier' はハンドルされません  
  
 列挙子には、 `switch` ステートメントに関連付けられたハンドラーがなく、 **既定** のラベルがありません。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 次の例では C4062 が生成されます。  
  
```  
// C4062.cpp  
// compile with: /W4  
#pragma warning(default : 4062)  
enum E { a, b, c };  
void func ( E e ) {  
   switch(e) {  
      case a:  
      case b:  
      break;   // no default label  
   }   // C4062, enumerate 'c' not handled  
}  
  
int main() {  
}  
```