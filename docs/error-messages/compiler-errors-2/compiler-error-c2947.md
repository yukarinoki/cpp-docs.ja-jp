---
description: 詳細については、「コンパイラエラー C2947」を参照してください。
title: コンパイラ エラー C2947
ms.date: 11/04/2016
f1_keywords:
- C2947
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
ms.openlocfilehash: 5b1780d49f97bfab33e70a4dd7b1958b56c8df14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189484"
---
# <a name="compiler-error-c2947"></a>コンパイラ エラー C2947

コンストラクターを終了するために ' > ' が必要ですが、' 構文 ' が見つかりました

ジェネリックまたはテンプレートの引数リストが正しく終了していない可能性があります。

C2947 は、構文エラーによって生成されることもあります。

次の例では、C2947 が生成されます。

```cpp
// C2947.cpp
// compile with: /c
template <typename T>=   // C2947
// try the following line instead
// template <typename T>
struct A {};
```
