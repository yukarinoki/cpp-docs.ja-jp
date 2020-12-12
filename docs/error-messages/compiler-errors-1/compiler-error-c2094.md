---
description: 詳細については、「コンパイラエラー C2094」を参照してください。
title: コンパイラ エラー C2094
ms.date: 11/04/2016
f1_keywords:
- C2094
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
ms.openlocfilehash: 35f67da3259b93eb4ef280d45c8e364df07e9889
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251831"
---
# <a name="compiler-error-c2094"></a>コンパイラ エラー C2094

ラベル 'identifier' が定義されていません

[goto](../../cpp/goto-statement-cpp.md) ステートメントで使用されるラベルが関数に存在しません。

## <a name="example"></a>例

次の例では C2094 が生成されます。

```cpp
// C2094.c
int main() {
   goto test;
}   // C2094
```

考えられる解決策:

```cpp
// C2094b.c
int main() {
   goto test;
   test:
   {
   }
}
```
