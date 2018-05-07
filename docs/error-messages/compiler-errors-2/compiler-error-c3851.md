---
title: コンパイラ エラー C3851 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82104776b2d1153310d0552bd873238333e746f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3851"></a>コンパイラ エラー C3851
'char': ユニバーサル文字名は基本文字セットの文字を指定できません  
  
 C++ としてコンパイルされるコードでは、基本ソース文字セットの文字を表すユニバーサル文字名を使用できません (文字列リテラルまたは文字リテラルの場合を除く)。 詳細については、次を参照してください。[文字セット](../../cpp/character-sets.md)です。 C としてコンパイルされるコードでは、0x20 から 0x7f の範囲内 (両端を含む) の文字に対応するユニバーサル文字名を使用できません。ただし、0x24 ('$')、0x40 ('@')、または 0x60 ('`') は使用できます。  
  
 次の例では、C3851 が生成され、その修正方法が表示されます。  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```