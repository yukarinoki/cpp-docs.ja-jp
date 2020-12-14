---
description: '詳細情報: コンパイラの警告 (レベル 1) C4715'
title: コンパイラの警告 (レベル 1) C4715
ms.date: 11/04/2016
f1_keywords:
- C4715
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
ms.openlocfilehash: 41682beae6e32ba397f3c9dae43d57a182b09b65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249101"
---
# <a name="compiler-warning-level-1-c4715"></a>コンパイラの警告 (レベル 1) C4715

' function ': すべてのコントロールパスが値を返すわけではありません

指定された関数は、値を返さない可能性があります。

## <a name="example"></a>例

```cpp
// C4715a.cpp
// compile with: /W1 /LD
int func1( int i )
{
   if( i )
   return 3;  // C4715 warning, nothing returned if i == 0
}
```

この警告を回避するには、すべてのパスが関数に戻り値を割り当てるようにコードを変更します。

```cpp
// C4715b.cpp
// compile with: /LD
int func1( int i )
{
   if( i ) return 3;
   else return 0;     // OK, always returns a value
}
```

次の例のように、コードにが返されることがない関数の呼び出しが含まれている可能性があります。

```cpp
// C4715c.cpp
// compile with: /W1 /LD
void fatal()
{
}
int glue()
{
   if(0)
      return 1;
   else if(0)
      return 0;
   else
      fatal();   // C4715
}
```

このコードでも警告が生成されます。これは、が返されることがないことをコンパイラが認識しないため `fatal` です。 このコードによってエラーメッセージが生成されないようにするには、 `fatal` [__declspec (noreturn)](../../cpp/noreturn.md)を使用してを宣言します。
