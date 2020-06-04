---
title: コンパイラの警告 (レベル 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: 76a33b24446debffb2c00bf1b0497cfc86022ce0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175142"
---
# <a name="compiler-warning-level-1-c4788"></a>コンパイラの警告 (レベル 1) C4788

'識別子' : 識別子は '数値' 文字に切り詰められました

コンパイラによって、関数名に使用できる最大文字数が制限されます。 コンパイラは、EH/SEH コードの funclet を生成するときに、関数名の前に何らかのテキスト (たとえば、"__catch"、"\__unwind"、または別の文字列) を付加することによって、funclet 名を形成します。

作成された funclet 名が長すぎる場合、コンパイラはこれを切り捨てて C4788 を生成します。

この警告を解決するには、元の関数名を短くします。 関数が C++ テンプレート関数またはメソッドの場合は、名前の一部に typedef を使用します。 次に例を示します。

```cpp
C1<x, y, z<T>>::C2<a,b,c>::f
```

これは次のように置換されます。

```cpp
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

この警告は、x64 コンパイラでのみ発生します。
