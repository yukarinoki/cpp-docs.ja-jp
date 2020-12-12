---
description: 詳細については、「コンパイラエラー C3219」を参照してください。
title: コンパイラ エラー C3219
ms.date: 11/04/2016
f1_keywords:
- C3219
helpviewer_keywords:
- C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
ms.openlocfilehash: 0210d8c65972a6adc7d5c2dbe51088f3c3766106
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267743"
---
# <a name="compiler-error-c3219"></a>コンパイラ エラー C3219

'param': ジェネリック パラメーターを、インターフェイスでない複数の 'class' によって制限することはできません

2 つ以上のマネージド クラスでジェネリック パラメーターを制限することはできません。

次の例では、C3219 が生成されます。

```cpp
// C3219.cpp
// compile with: /clr
ref class A {};
ref class B {};

generic <class T>
where T : A, B
ref class E {};   // C3219
```

次の例では、考えられる解決策を示しています。

```cpp
// C3219b.cpp
// compile with: /clr /c
ref class A {};

interface struct C {};

generic <class T>
where T : A
ref class E {};
```
