---
title: コンパイラ エラー C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: dad6a64f145c3d49d3b43044ea76a11d35827943
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408369"
---
# <a name="compiler-error-c2833"></a>コンパイラ エラー C2833

'operator 演算子' は認識されている演算子または型ではありません。

単語`operator`続くをオーバーライドする演算子または型に変換する必要があります。

マネージ型で定義できる演算子の一覧は、次を参照してください。[ユーザー定義演算子](../../dotnet/user-defined-operators-cpp-cli.md)します。

次の例では、C2833 が生成されます。

```
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```