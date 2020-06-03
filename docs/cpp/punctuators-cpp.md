---
title: 区切り記号 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- punctuators [C++]
ms.assetid: 1521564c-a977-488a-9490-068079897592
ms.openlocfilehash: cc4e56cd0dce3ae91183a8675eba96f174c3c31f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160972"
---
# <a name="punctuators-c"></a>区切り記号 (C++)

C++ の区切り記号はコンパイラに対する構文上およびセマンティック上の意味を持ちますが、それ自体は値を生成する演算を指定しません。 一部の区切り記号 (単独または組み合わせ) は、C++ の演算子としても使用できたり、プリプロセッサで意味を持つことがあります。

次の文字が区切り記号と見なされます。

```
! % ^ & * ( ) - + = { } | ~
[ ] \ ; ' : " < > ? , . / #
```

区切り記号 **[]** 、 **()** 、および **{}** は、[変換フェーズ](../preprocessor/phases-of-translation.md)4 の後にペアで記述する必要があります。

## <a name="see-also"></a>参照

[構文規則](../cpp/lexical-conventions.md)
