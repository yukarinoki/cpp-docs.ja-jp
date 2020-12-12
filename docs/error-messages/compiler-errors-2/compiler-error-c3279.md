---
description: 詳細については、「コンパイラエラー C3279」を参照してください。
title: コンパイラ エラー C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: c257a97cad1603703e7dbf2ed0d9f5cb3e6134a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258019"
---
# <a name="compiler-error-c3279"></a>コンパイラ エラー C3279

cli 名前空間で宣言されたクラス テンプレートの明示的なインスタンス生成と同様に、部分的または明示的な特殊化は許可されていません

`cli` 名前空間は、Microsoft によって定義され、擬似テンプレートが含まれています。 Microsoft C++ コンパイラでは、ユーザー定義、部分的および明示的な特殊化、およびこの名前空間のクラステンプレートの明示的なインスタンス化は許可されていません。

次の例では C3279 が生成されます。

```cpp
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```
