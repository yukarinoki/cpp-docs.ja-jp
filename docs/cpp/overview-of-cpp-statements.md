---
description: '詳細情報: C++ ステートメントの概要'
title: C++ ステートメントの概要
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
ms.openlocfilehash: e30b33bbc1aeb94c5b188ff7796a39b130bec827
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145952"
---
# <a name="overview-of-c-statements"></a>C++ ステートメントの概要

C++ ステートメントは、式ステートメント、選択ステートメント、繰り返しステートメント、またはジャンプ ステートメントによって特にその順序を変更した場合を除き、順次実行されます。

ステートメントは、次の型で構成できます。

> *`labeled-statement`*\
> *`expression-statement`*\
> *`compound-statement`*\
> *`selection-statement`*\
> *`iteration-statement`*\
> *`jump-statement`*\
> *`declaration-statement`*\
> *`try-throw-catch`*

ほとんどの場合、C++ ステートメントの構文は、ANSI C89 の構文と同じです。 2つの間の主な違いは、C89 では宣言はブロックの先頭でのみ許可されます。C++ では、 *`declaration-statement`* この制限を実質的に削除するが追加されます。 これによって、プログラム内で、事前計算される初期値を計算できる時点で変数を導入できます。

また、ブロック内部で変数を宣言しても、これらの変数のスコープと有効期間を正確に制御できます。

ステートメントに関する記事では、次の C++ キーワードについて説明します。

:::row:::
   :::column span="":::
      [`break`](../cpp/break-statement-cpp.md)\
      [`case`](../cpp/switch-statement-cpp.md)\
      [`catch`](../cpp/try-throw-and-catch-statements-cpp.md)\
      [`continue`](../cpp/continue-statement-cpp.md)\
      [`default`](../cpp/switch-statement-cpp.md)\
      [`do`](../cpp/do-while-statement-cpp.md)
   :::column-end:::
   :::column span="":::
      [`else`](../cpp/if-else-statement-cpp.md)\
      [`__except`](../cpp/structured-exception-handling-c-cpp.md)\
      [`__finally`](../cpp/structured-exception-handling-c-cpp.md)\
      [`for`](../cpp/for-statement-cpp.md)\
      [`goto`](../cpp/goto-statement-cpp.md)
   :::column-end:::
   :::column span="":::
      [`if`](../cpp/if-else-statement-cpp.md)\
      [`__if_exists`](../cpp/if-exists-statement.md)\
      [`__if_not_exists`](../cpp/if-not-exists-statement.md)\
      [`__leave`](../c-language/try-finally-statement-c.md)\
      [`return`](../cpp/return-statement-cpp.md)
   :::column-end:::
   :::column span="":::
      [`switch`](../cpp/switch-statement-cpp.md)\
      [`throw`](../cpp/try-throw-and-catch-statements-cpp.md)\
      [`__try`](../cpp/structured-exception-handling-c-cpp.md)\
      [`try`](../cpp/try-throw-and-catch-statements-cpp.md)\
      [`while`](../cpp/while-statement-cpp.md)
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>関連項目

[ステートメント](../cpp/statements-cpp.md)
