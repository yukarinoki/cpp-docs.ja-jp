---
title: コンパイラ エラー C3418
ms.date: 11/04/2016
f1_keywords:
- C3418
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
ms.openlocfilehash: 21023bfb551a1894e25cc4940892dde0f0440a0e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200885"
---
# <a name="compiler-error-c3418"></a>コンパイラ エラー C3418

アクセス指定子 'specifier' はサポートされていません

CLR アクセス指定子が正しく指定されていません。  詳細については、「[方法: クラスと構造体を定義および使用する (C++/cli)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)」の「型の可視性とメンバーの可視性」を参照してください。

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
