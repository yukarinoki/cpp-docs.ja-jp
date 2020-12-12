---
description: 詳細については、「コンパイラエラー C3398」を参照してください。
title: コンパイラ エラー C3398
ms.date: 11/04/2016
f1_keywords:
- C3398
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
ms.openlocfilehash: 024390ec03ad145f418f79d2db3228bd790a6de7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321942"
---
# <a name="compiler-error-c3398"></a>コンパイラ エラー C3398

'operator': 'function_signature' から 'function_pointer' に変換できません。 ソース式は関数シンボルでなければなりません

[/clr](../../cpp/clrcall.md) を使用してコンパイルするときに、 **__clrcall** 呼び出し規則が指定されていないと、コンパイラは各関数に対して、ネイティブ エントリ ポイントとマネージド エントリ ポイントという 2 つのエントリ ポイント (アドレス) を生成します。

既定では、コンパイラはネイティブ エントリ ポイントを返しますが、場合によっては、マネージド エントリ ポイントが必要な場合があります (たとえば、 `__clrcall` 関数ポインターにアドレスを 割り当てる場合など)。 割り当てでコンパイラが確実にマネージド エントリ ポイントを選択するためには、右辺を関数シンボルにする必要があります。
