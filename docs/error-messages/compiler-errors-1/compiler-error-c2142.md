---
title: コンパイラ エラー C2142 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2142
dev_langs:
- C++
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32301087ac1f06f1958ca8de7d2f66645dafb3d2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032500"
---
# <a name="compiler-error-c2142"></a>コンパイラ エラー C2142

関数の宣言が異なる場合、それらのいずれかのみで指定された変数のパラメーター

関数の 1 つの宣言には、変数パラメーター リストが含まれています。 別の宣言されていません。 ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) のみです。

次の例では、C2142 が生成されます。

```
// C2142.c
// compile with: /Za /c
void func();
void func( int, ... );   // C2142
void func2( int, ... );   // OK
```