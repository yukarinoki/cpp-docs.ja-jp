---
title: コンパイラ エラー C3393
ms.date: 11/04/2016
f1_keywords:
- C3393
helpviewer_keywords:
- C3393
ms.assetid: d57f7c69-0a02-4fe3-9e45-bc62644fd77c
ms.openlocfilehash: d2822d5a36b2091881d354131b2a28d386f787c0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520468"
---
# <a name="compiler-error-c3393"></a>コンパイラ エラー C3393

制約句の構文エラー: 'identifier' は型ではありません

制約に渡された識別子は、型である必要があるのに型ではありません。  詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)します。

## <a name="example"></a>例

次の例では C3393 が生成されます。

```
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