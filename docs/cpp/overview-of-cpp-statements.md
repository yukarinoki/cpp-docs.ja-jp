---
title: C++ ステートメントの概要 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c8836f3c82ea21d2ef22ccd3439dff3644380678
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030444"
---
# <a name="overview-of-c-statements"></a>C++ ステートメントの概要

C++ ステートメントは、式ステートメント、選択ステートメント、繰り返しステートメント、またはジャンプ ステートメントによって特にその順序を変更した場合を除き、順次実行されます。

ステートメントは、次の型で構成できます。

```
labeled-statement
expression-statement
compound-statement
selection-statement
iteration-statement
jump-statement
declaration-statement
try-throw-catch
```

ほとんどの場合、C++ ステートメントの構文は ANSI C の場合と同じ2 つの主な違い C では、宣言は許可されて; ブロックの開始時のみC++ の追加、*宣言ステートメント*、効果的にこの制限を削除します。 これによって、プログラム内で、事前計算される初期値を計算できる時点で変数を導入できます。

また、ブロック内部で変数を宣言しても、これらの変数のスコープと有効期間を正確に制御できます。

ステートメントのトピックでは、次の C++ キーワードについて説明します。

|||||
|-|-|-|-|
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[_ _if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[_ _if_not_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||

## <a name="see-also"></a>関連項目

[ステートメント](../cpp/statements-cpp.md)