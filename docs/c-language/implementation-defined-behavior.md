---
title: 実装定義の動作 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Visual C, portability of Microsoft C
- portability [C++], Microsoft C to ANSI C
- ANSI [C++], C standard
- implementation-defined behavior
ms.assetid: c9f50670-23cb-401f-8ad7-136972012eb9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 496403f21ddd7e55aa5a504dd12e2c1e5e423a88
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095535"
---
# <a name="implementation-defined-behavior"></a>実装定義の動作

ANSI X3.159-1989 (*American National Standard for Information Systems* - *Programming Language* - *C*) には、移植性の問題に関するセクションがあります。 この ANSI セクションには、ANSI が特定の実装に対して開放している C 言語の領域が記載されています。 ここでは、C 言語のこれらの実装定義領域が Microsoft C でどのように処理されるかについて説明します。

このセクションは ANSI のセクションと同じ順序に従っています。 対象となる各項目には、実装定義の動作を説明する ANSI への参照が含まれています。

> [!NOTE]
>  このセクションでは、米国英語版の C コンパイラについてのみ説明します。 他の言語の Microsoft C の実装は多少異なる場合があります。

## <a name="see-also"></a>参照

[C 言語リファレンス](../c-language/c-language-reference.md)