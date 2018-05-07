---
title: コンパイラの警告 (レベル 4) C4459 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4459
dev_langs:
- C++
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93bdbfe6cceff664e7b7a5f8cee20e8df51e2fb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4459"></a>コンパイラの警告 (レベル 4) C4459
  
> 宣言 '*識別子*' グローバル宣言を非表示になります
  
宣言*識別子*ローカル スコープで、まったく同じ名前の宣言を非表示に*識別子*グローバル スコープでします。 この警告を参照するを認識できます。*識別子*このスコープで解決するにはローカルに宣言されたバージョンを、グローバル バージョンではなく、またはユーザーの意図ができない可能性があります。 一般に、優れたエンジニア リング手法としてグローバル変数の使用を最小限に抑えるをお勧めします。 グローバル名前空間の汚染を最小化するには、グローバル変数の名前付きの名前空間の使用をお勧めします。  
  
この警告は、Visual C コンパイラのバージョン 18.00 では、Visual Studio 2015 の新機能しました。 または、コードを移行するときに、後で、コンパイラのバージョンからの警告を抑制するのには、使用、 [/Wv:18](../../build/reference/compiler-option-warning-level.md)コンパイラ オプション。 

## <a name="example"></a>例
  
 次の例では、C4459 が生成されます。  
  
```cpp  
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() { 
    int global_or_local; // warning C4459 
    global_or_local = 2;
} 
```  
  
この問題を解決する方法の 1 つが、グローバル変数の名前空間の作成が、使用しない、`using`に取り込むその名前空間スコープ、すべての参照を使用する必要があります、明確なのでディレクティブの修飾名。  
  
```cpp  
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() { 
    int global_or_local; // OK 
    global_or_local = 2;
    globals::global_or_local = 3;
} 
```  
