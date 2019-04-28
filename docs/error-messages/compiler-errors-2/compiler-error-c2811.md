---
title: コンパイラ エラー C2811
ms.date: 11/04/2016
f1_keywords:
- C2811
helpviewer_keywords:
- C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
ms.openlocfilehash: 8dfc462cc0eedfff1661ae38f79bbb79c5c1a8fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281756"
---
# <a name="compiler-error-c2811"></a>コンパイラ エラー C2811

'type1': ref 'type2' から継承できませんクラスは、ref クラスまたはインターフェイス クラスからのみ継承できます。

マネージ クラスの基底クラスとしてアンマネージ クラスを使用しようとしました。

次の例では、C2811 が生成されます。

```
// C2811.cpp
// compile with: /clr /c
struct S{};
ref struct T {};
ref class C : public S {};   // C2811
ref class D : public T {};   // OK
```