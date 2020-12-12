---
description: 詳細については、「コンパイラエラー C3236」を参照してください。
title: コンパイラ エラー C3236
ms.date: 11/04/2016
f1_keywords:
- C3236
helpviewer_keywords:
- C3236
ms.assetid: 4ef1871f-a348-44ae-922b-1e2081de20d0
ms.openlocfilehash: ed9a8e630a3c385bc3f7586c4f9db1e06259a3c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307510"
---
# <a name="compiler-error-c3236"></a>コンパイラ エラー C3236

generic の明示的なインスタンス生成は使用できません

コンパイラでは、ジェネリック クラスを明示的にインスタンス化できません。

次の例では C3236 が生成されます。

```cpp
// C3236.cpp
// compile with: /clr
generic<class T>
public ref class X {};

generic ref class X<int>;   // C3236
```

次の例では、考えられる解決策を示しています。

```cpp
// C3236b.cpp
// compile with: /clr /c
generic<class T>
public ref class X {};
```
