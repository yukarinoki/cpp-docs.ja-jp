---
title: コンパイラの警告 (レベル 1) C4715
ms.date: 11/04/2016
f1_keywords:
- C4715
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
ms.openlocfilehash: 7dba86d591f18fd7c9c562078204916000d47384
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175325"
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

また、このコードでは、`fatal` が返されないことをコンパイラが認識しないため、警告が生成されます。 このコードによってエラーメッセージが生成されないようにするには、 [__declspec (noreturn)](../../cpp/noreturn.md)を使用して `fatal` を宣言します。
