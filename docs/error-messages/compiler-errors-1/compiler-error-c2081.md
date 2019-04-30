---
title: コンパイラ エラー C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: 2bccd15b8c2b6d1c5cd6c4b536bbdaf350eb0181
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408655"
---
# <a name="compiler-error-c2081"></a>コンパイラ エラー C2081

'identifier': 仮パラメーター リストが不正です名。

識別子には、構文エラーが発生しました。

このエラーは、仮パラメーター リストの古いスタイルを使用して発生することができます。 仮パラメーター リストでは、仮パラメーターの種類を指定する必要があります。

次の例では、C2081 が生成されます。

```
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

考えられる解決方法:

```
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```