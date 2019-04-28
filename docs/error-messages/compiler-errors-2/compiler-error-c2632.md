---
title: コンパイラ エラー C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: b92d44bcfd04d4de7b39c5bdab5ee146d9b6693b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257635"
---
# <a name="compiler-error-c2632"></a>コンパイラ エラー C2632

'type1' の 'type2' の後に無効です。

このエラーは、2 つの型指定子の間でコードがない場合に発生することができます。

次の例では、C2632 が生成されます。

```
// C2632.cpp
int float i;   // C2632
```

このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成こともできます。 `bool` 適切な型になります。 以前のバージョンで`bool`typedef、その名前の識別子を作成できます。

次の例では、C2632 が生成されます。

```
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

このエラーを解決するには、コードが Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C では有効であるように、識別子の名前を変更します。