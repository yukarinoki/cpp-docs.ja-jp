---
description: 詳細については、「コンパイラエラー C2081」を参照してください。
title: コンパイラエラー C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: e6f75d6d478d9523d36a9671457cf2a5618e4f21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151178"
---
# <a name="compiler-error-c2081"></a>コンパイラエラー C2081

' identifier ': 仮パラメーターリスト内の名前が正しくありません

識別子によって構文エラーが発生しました。

このエラーは、仮パラメーターリストの古いスタイルを使用することによって発生することがあります。 仮パラメーターリストでは、仮パラメーターの型を指定する必要があります。

次の例では、C2081 が生成されます。

```c
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

考えられる解決策:

```c
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```
