---
title: コンパイラの警告 (レベル 1) C4715
ms.date: 11/04/2016
f1_keywords:
- C4715
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
ms.openlocfilehash: f165ea3b54b78e2f8fae995815e309d55101244e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406328"
---
# <a name="compiler-warning-level-1-c4715"></a>コンパイラの警告 (レベル 1) C4715

'function': 値を返さないコントロール パスのすべて

指定された関数は、値を返すない可能性のあることができます。

## <a name="example"></a>例

```
// C4715a.cpp
// compile with: /W1 /LD
int func1( int i )
{
   if( i )
   return 3;  // C4715 warning, nothing returned if i == 0
}
```

この警告を防ぐためには、すべてのパスは、関数に戻り値を割り当てるようにコードを変更します。

```
// C4715b.cpp
// compile with: /LD
int func1( int i )
{
   if( i ) return 3;
   else return 0;     // OK, always returns a value
}
```

コードが、次の例のようにを返すことはありません関数の呼び出しを含めることができますことができます。

```
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

このコードは、コンパイラが知らないのでするも、警告を生成`fatal`返すことはありません。 このコードは、エラー メッセージが生成されないように、宣言`fatal`を使用して[__declspec(noreturn)](../../cpp/noreturn.md)します。