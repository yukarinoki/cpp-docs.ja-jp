---
title: コンパイラ エラー C3063 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3063
dev_langs:
- C++
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9adea484416b85f027693b59acb343d4ca19cf6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021643"
---
# <a name="compiler-error-c3063"></a>コンパイラ エラー C3063

演算子 'operator': すべてのオペランドは同じ列挙型である必要があります

演算子で列挙子を使用する場合は、両方のオペランドが列挙型でなければなりません。 詳細については、次を参照してください。[方法: 定義および c++ の列挙型を使用する/cli CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)します。

## <a name="example"></a>例

次の例では、C3063 を生成し、その修正方法を示しています。

```
// C3063.cpp
// compile with: /clr
enum class E { a, b } e, mask;
int main() {
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)

   if ( ( e & mask ) != E() )   // OK
      ;
}
```