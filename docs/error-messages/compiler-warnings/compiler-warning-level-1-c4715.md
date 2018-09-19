---
title: コンパイラの警告 (レベル 1) C4715 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4715
dev_langs:
- C++
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b3de829992bfa650280768a2fcd761feaeaece0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061371"
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