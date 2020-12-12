---
description: 詳細については、「コンパイラエラー C2833」を参照してください。
title: コンパイラ エラー C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: 3c1bd2cc60478dc5868c74d4bfeac1d7d3a4d9a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194489"
---
# <a name="compiler-error-c2833"></a>コンパイラ エラー C2833

> ' operator *operator-name*' は演算子または型として認識されません

この単語の後には、 **`operator`** オーバーライドする *演算子名* または変換する型を指定する必要があります。

マネージ型で定義できる演算子の一覧については、「 [ユーザー定義演算子](../../dotnet/user-defined-operators-cpp-cli.md)」を参照してください。

次の例では、C2833 が生成されます。

```cpp
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```
