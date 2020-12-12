---
description: 詳細については、「コンパイラエラー C2534」を参照してください。
title: コンパイラ エラー C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: fbdc4c292a8eb59ee9ab51de0100455139473f7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302076"
---
# <a name="compiler-error-c2534"></a>コンパイラ エラー C2534

' identifier ': コンストラクターは値を返せません。

コンストラクターは値を返さないか、戻り値の型を持つことができません (戻り値の型も含まれません **`void`** )。

このエラーは、コンストラクター定義からステートメントを削除することによって修正でき **`return`** ます。

次の例では、C2534 が生成されます。

```cpp
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```
