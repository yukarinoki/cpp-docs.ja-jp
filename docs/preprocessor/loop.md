---
description: pragmaMicrosoft C/c + + での loop ディレクティブの詳細について説明します。
title: ループ pragma
ms.date: 01/22/2021
f1_keywords:
- loop_CPP
- vc-pragma.loop
helpviewer_keywords:
- loop pragma
- pragma, loop
no-loc:
- pragma
ms.openlocfilehash: 4aac76cb5220e57dd378ac00ff576521c9001218
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713533"
---
# <a name="loop-no-locpragma"></a>`loop` pragma

ループコードが自動並行化によってどのように見なされるかを制御します。または、自動ベクター化によって考慮されないループを除外します。

## <a name="syntax"></a>構文

> **`#pragma loop( hint_parallel(`***n***`) )`**\
> **`#pragma loop( no_vector )`**\
> **`#pragma loop( ivdep )`**

### <a name="parameters"></a>パラメーター

**`hint_parallel(`***n***`)`**\
*N* スレッド間でこのループを並列化する必要があることをコンパイラにヒントします。 *n* は、正の整数リテラルまたは0です。 *N* が0の場合、スレッドの最大数が実行時に使用されます。 これは、コマンドではなく、コンパイラに対するヒントです。 ループが並列化される保証はありません。 ループにデータの依存関係または構造上の問題がある場合は、並列化されません。 たとえば、ループ本体の外で使用されるスカラーに格納する場合は、並列化されません。

コンパイラは、 [`/Qpar`](../build/reference/qpar-auto-parallelizer.md) コンパイラスイッチが指定されていない限り、このオプションを無視します。

**`no_vector`**\
既定では、自動ベクター化は、評価されたすべてのループのベクター化を試行することができます。 次の pragma ループの自動ベクター化を無効にするには、これを指定します。

**`ivdep`**\
このループのベクター依存関係を無視するためのヒント。

## <a name="remarks"></a>解説

を使用するには、ループ定義ではなく、の直前に **`loop`** pragma 配置します。 は、その pragma 後に続くループのスコープに対して有効になります。 ループには複数の pragma ディレクティブを任意の順序で適用できますが、それぞれを個別のステートメントで指定する必要があり pragma ます。

## <a name="see-also"></a>関連項目

[自動並列化と自動ベクター化](../parallel/auto-parallelization-and-auto-vectorization.md)\
[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
