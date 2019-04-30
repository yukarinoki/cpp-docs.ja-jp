---
title: 致命的なエラー C1019
ms.date: 11/04/2016
f1_keywords:
- C1019
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
ms.openlocfilehash: 2d8e63510b762b0de0cda50ab7a03b773dfb949a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383127"
---
# <a name="fatal-error-c1019"></a>致命的なエラー C1019

予期しない #else です。

`#else` ディレクティブが、 `#if`、 `#ifdef`、または `#ifndef` 構成体の外側に置かれています。 `#else` は、これらの構成体のいずれかの内側だけで使用してください。

次の例では C1019 が生成されます。

```
// C1019.cpp
#else   // C1019
#endif

int main() {}
```

考えられる解決方法:

```
// C1019b.cpp
#if 1
#else
#endif

int main() {}
```