---
title: コンパイラ エラー C3747 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3747
dev_langs:
- C++
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1f657e6d3f64a4d8a2244ab2927a9a712c14b1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091674"
---
# <a name="compiler-error-c3747"></a>コンパイラ エラー C3747

既定の型パラメーターがありません: パラメーターのパラメーター

ジェネリックまたはテンプレートのパラメーターに既定値は、既定値がないパラメーターでパラメーター リストの後にことはできません。

次の例では、C3747 が生成されます。

```
// C3747.cpp
template <class T1 = int, class T2>   // C3747
struct MyStruct {};
```

考えられる解決方法:

```
// C3747b.cpp
// compile with: /c
template <class T1, class T2 = int>
struct MyStruct {};
```