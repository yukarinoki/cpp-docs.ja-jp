---
description: '詳細情報: 致命的なエラー C1019'
title: 致命的なエラー C1019
ms.date: 11/04/2016
f1_keywords:
- C1019
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
ms.openlocfilehash: d11a4300b29e497fef2f148d07963997586781ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316389"
---
# <a name="fatal-error-c1019"></a>致命的なエラー C1019

予期しない #else です。

`#else` ディレクティブが、 `#if`、 `#ifdef`、または `#ifndef` コンストラクトの外側に置かれています。 `#else` は、これらのコンストラクトのいずれかの内側だけで使用してください。

次の例では C1019 が生成されます。

```cpp
// C1019.cpp
#else   // C1019
#endif

int main() {}
```

考えられる解決策:

```cpp
// C1019b.cpp
#if 1
#else
#endif

int main() {}
```
