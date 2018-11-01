---
title: コンパイラの警告 (レベル 1) C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: c51a4409c2a3028823462539343654b5eac365d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598173"
---
# <a name="compiler-warning-level-1-c4788"></a>コンパイラの警告 (レベル 1) C4788

'識別子' : 識別子は '数値' 文字に切り詰められました

コンパイラによって、関数名に使用できる最大文字数が制限されます。 いくつかのテキストを含む関数の名前を付けます funclet 名を形成、コンパイラは、コードの funclets を生成するとき、"_ _catch"、"\__unwind"、または別の文字列。

作成された funclet 名が長すぎる場合、コンパイラはこれを切り捨てて C4788 を生成します。

この警告を解決するには、元の関数名を短くします。 関数が C++ テンプレート関数またはメソッドの場合は、名前の一部に typedef を使用します。 例えば:

```
C1<x, y, z<T>>::C2<a,b,c>::f
```

これは次のように置換されます。

```
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

この警告は、x64 でのみ発生するコンパイラ。