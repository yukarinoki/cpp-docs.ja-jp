---
description: 詳細については、「コンパイラエラー C2142」を参照してください。
title: コンパイラ エラー C2142
ms.date: 11/04/2016
f1_keywords:
- C2142
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
ms.openlocfilehash: 65bd189fe99bb54549e458b093b72d8e47b840a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235529"
---
# <a name="compiler-error-c2142"></a>コンパイラ エラー C2142

関数の宣言は、そのうちの1つでのみ指定された変数パラメーターと異なります。

関数の1つの宣言に、変数パラメーターリストが含まれています。 別の宣言ではできません。 ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)) のみ。

次の例では、C2142 が生成されます。

```c
// C2142.c
// compile with: /Za /c
void func();
void func( int, ... );   // C2142
void func2( int, ... );   // OK
```
