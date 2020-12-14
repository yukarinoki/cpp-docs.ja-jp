---
description: 詳細については、「コンパイラエラー C3393」を参照してください。
title: コンパイラ エラー C3393
ms.date: 11/04/2016
f1_keywords:
- C3393
helpviewer_keywords:
- C3393
ms.assetid: d57f7c69-0a02-4fe3-9e45-bc62644fd77c
ms.openlocfilehash: d870498fe235fa1336ea784b7da1dcdd12f8c7cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316318"
---
# <a name="compiler-error-c3393"></a>コンパイラ エラー C3393

制約句の構文エラー: 'identifier' は型ではありません

制約に渡された識別子は、型である必要があるのに型ではありません。  詳細については、「[Constraints on Generic Type Parameters (C++/CLI) (ジェネリック型パラメーターの (C++/CLI))](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では C3393 が生成されます。

```cpp
// C3393.cpp
// compile with: /clr /c
void MyInterface() {}
interface class MyInterface2 {};

generic<typename T>
where T : MyInterface   // C3393
// try the following line instead
// where T : MyInterface2
ref class R {};
```
