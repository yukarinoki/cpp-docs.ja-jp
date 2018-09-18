---
title: コンパイラ エラー C2909 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2909
dev_langs:
- C++
helpviewer_keywords:
- C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f611a026d0a969f49eaf2dcd93ba081bae052d10
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030886"
---
# <a name="compiler-error-c2909"></a>コンパイラ エラー C2909

'identifier': 関数テンプレートの明示的なインスタンス化には戻り値の型が必要です

関数テンプレートの明示的なインスタンス化では、戻り値の型の明示的な指定が必要です。 暗黙の戻り値型の仕様は機能しません。

次の例では C2909 が生成されます。

```
// C2909.cpp
// compile with: /c
template<class T> int f(T);
template f<int>(int);         // C2909
template int f<int>(int);   // OK
```