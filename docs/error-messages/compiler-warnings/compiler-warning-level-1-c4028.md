---
title: コンパイラの警告 (レベル 1) C4028 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4028
dev_langs:
- C++
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c96abd732a00e5b37b48be8c3053cbfbb8c37c37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274360"
---
# <a name="compiler-warning-level-1-c4028"></a>コンパイラの警告 (レベル 1) C4028
仮パラメーター 'number' が宣言と一致しません  
  
 仮パラメーターの型は、宣言に対応するパラメーターと一致しません。 元の宣言で型が使用されます。  
  
 この警告は C ソース コードについてのみです。  
  
## <a name="example"></a>例  
 次の例では、C4028 を生成します。  
  
```  
// C4028.c  
// compile with: /W1 /Za  
void f(int , ...);  
void f(int i, int j) {}   // C4028  
  
void g(int , int);  
void g(int i, int j) {}   // OK  
  
int main() {}  
```