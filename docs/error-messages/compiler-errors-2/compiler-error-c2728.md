---
title: コンパイラ エラー C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 1fbbc3d63386ebe98a447de8b7166a5263d2168f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778788"
---
# <a name="compiler-error-c2728"></a>コンパイラ エラー C2728

'type': ネイティブ配列はこの型を含むことはできません

配列作成の構文が、マネージドまたは WinRT オブジェクトの配列の作成に使用されました。 ネイティブ配列の構文を使用して、マネージドまたは WinRT オブジェクトの配列を作成することはできません。

詳細については、「 [配列](../../extensions/arrays-cpp-component-extensions.md)」を参照してください。

次の例では、C2728 を生成し、その修正方法を示しています。

```
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
