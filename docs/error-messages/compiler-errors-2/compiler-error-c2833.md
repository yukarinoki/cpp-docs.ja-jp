---
title: コンパイラ エラー C2833 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2833
dev_langs:
- C++
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53360c1eaf81ad407589fbdb125d9e6fe017708e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070172"
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