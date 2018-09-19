---
title: 区切り記号 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- punctuators [C++]
ms.assetid: 1521564c-a977-488a-9490-068079897592
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 438b3f0469d1e8426b1e0ec2a19a63d1ae63c041
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039271"
---
# <a name="punctuators-c"></a>区切り記号 (C++)

C++ の区切り記号はコンパイラに対する構文上およびセマンティック上の意味を持ちますが、それ自体は値を生成する演算を指定しません。 一部の区切り記号 (単独または組み合わせ) は、C++ の演算子としても使用できたり、プリプロセッサで意味を持つことがあります。

次の文字が区切り記号と見なされます。

```
! % ^ & * ( ) - + = { } | ~
[ ] \ ; ' : " < > ? , . / #
```

区切り記号 **[]**、**に関するページ ()**、および **{}** 後に、ペアで使用する必要があります[変換フェーズ](../preprocessor/phases-of-translation.md)4 です。

## <a name="see-also"></a>関連項目

[構文規則](../cpp/lexical-conventions.md)