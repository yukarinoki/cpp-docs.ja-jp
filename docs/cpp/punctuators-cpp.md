---
description: '詳細情報: 区切り記号 (C++)'
title: 区切り記号 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- punctuators [C++]
ms.assetid: 1521564c-a977-488a-9490-068079897592
ms.openlocfilehash: 7485ea82725c2221d32d0647123cfce473719ca3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319431"
---
# <a name="punctuators-c"></a>区切り記号 (C++)

C++ の区切り記号はコンパイラに対する構文上およびセマンティック上の意味を持ちますが、それ自体は値を生成する演算を指定しません。 一部の区切り記号 (単独または組み合わせ) は、C++ の演算子としても使用できたり、プリプロセッサで意味を持つことがあります。

次の文字が区切り記号と見なされます。

```
! % ^ & * ( ) - + = { } | ~
[ ] \ ; ' : " < > ? , . / #
```

区切り記号 **[]**、 **()**、および **{}** は、 [変換フェーズ](../preprocessor/phases-of-translation.md) 4 の後にペアで記述する必要があります。

## <a name="see-also"></a>関連項目

[字句表記規則](../cpp/lexical-conventions.md)
