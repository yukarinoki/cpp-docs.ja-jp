---
title: コンパイラ エラー C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 72646d7611163748fe7e27ea6c78cd38426eb6ad
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447817"
---
# <a name="compiler-error-c3279"></a>コンパイラ エラー C3279

cli 名前空間で宣言されたクラス テンプレートの明示的なインスタンス生成と同様に、部分的または明示的な特殊化は許可されていません

`cli` 名前空間は、Microsoft によって定義され、擬似テンプレートが含まれています。 MicrosoftC++コンパイラやを許容しないユーザー定義、部分的または明示的な特殊化では、クラス テンプレートの明示的なインスタンス化では、この名前空間。

次の例では C3279 が生成されます。

```
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```