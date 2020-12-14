---
description: 詳細については、「コンパイラエラー C2728」を参照してください。
title: コンパイラエラー C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 7ef24dd037f8d765c072a61320da64411248dbc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245305"
---
# <a name="compiler-error-c2728"></a>コンパイラエラー C2728

'type': ネイティブ配列はこの型を含むことはできません

配列作成の構文が、マネージドまたは WinRT オブジェクトの配列の作成に使用されました。 ネイティブ配列の構文を使用して、マネージドまたは WinRT オブジェクトの配列を作成することはできません。

詳細については、「 [配列](../../extensions/arrays-cpp-component-extensions.md)」を参照してください。

次の例では、C2728 を生成し、その修正方法を示しています。

```cpp
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
