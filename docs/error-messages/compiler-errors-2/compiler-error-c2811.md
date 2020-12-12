---
description: 詳細については、「コンパイラエラー C2811」を参照してください。
title: コンパイラ エラー C2811
ms.date: 11/04/2016
f1_keywords:
- C2811
helpviewer_keywords:
- C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
ms.openlocfilehash: 02b4770b08bdfc9ee15386874ebba2265716536d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194853"
---
# <a name="compiler-error-c2811"></a>コンパイラ エラー C2811

' type1 ': ' type1 ' から継承することはできません。 ref クラスは ref クラスまたはインターフェイスクラスからのみ継承できます

アンマネージクラスをマネージクラスの基底クラスとして使用しようとしました。

次の例では、C2811 が生成されます。

```cpp
// C2811.cpp
// compile with: /clr /c
struct S{};
ref struct T {};
ref class C : public S {};   // C2811
ref class D : public T {};   // OK
```
