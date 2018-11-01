---
title: コンパイラ エラー C3418
ms.date: 11/04/2016
f1_keywords:
- C3418
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
ms.openlocfilehash: 8456e9b17b72cd4ac98349d2f2871a1c59f56911
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482772"
---
# <a name="compiler-error-c3418"></a>コンパイラ エラー C3418

アクセス指定子 'specifier' はサポートされていません

CLR アクセス指定子が正しく指定されていません。  詳細については、型の可視性とメンバーの可視性で参照してください[方法: 定義とクラスの使用、および構造体 (C +/cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)します。

## <a name="example"></a>例

次の例では C3418 が生成されます。

```cpp
// C3418.cpp
// compile with: /clr /c
ref struct m {
internal public:   // C3418
   void test(){}
};

ref struct n {
internal:   // OK
   void test(){}
};
```