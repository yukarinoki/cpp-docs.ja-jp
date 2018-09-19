---
title: コンパイラ エラー C2092 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2092
dev_langs:
- C++
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a0b8f65f58ffe65abee0f15eb511f7857657597
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072486"
---
# <a name="compiler-error-c2092"></a>コンパイラ エラー C2092

'名をアレイ' 配列要素の型が関数にすることはできません。

関数の配列を指定することはできません。 関数へのポインターの配列を使用します。

## <a name="example"></a>例

次の例では、C2092 が生成されます。

```
// C2092.cpp
typedef void (F) ();
typedef F AT[10];   // C2092
```

## <a name="example"></a>例

考えられる解決方法:

```
// C2092b.cpp
// compile with: /c
typedef void (F) ();
typedef F * AT[10];
```