---
title: コンパイラ エラー C2632 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bf03c35c60bebb52c94ed04cca2349f35c06fbc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093651"
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