---
description: pragmaMicrosoft C/c + + での inline_recursion ディレクティブの詳細については、こちらを参照してください。
title: inline_recursion pragma
ms.date: 01/22/2021
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragma, inline_recursion
- inline_recursion pragma
no-loc:
- pragma
ms.openlocfilehash: b4e377d4c97c46a20e44a2c41f872a8762cdea4d
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713559"
---
# <a name="inline_recursion-no-locpragma"></a>`inline_recursion` pragma

直接呼び出しまたは相互再帰関数の呼び出しのインライン展開を制御します。

## <a name="syntax"></a>構文

> **`#pragma inline_recursion(`** [ { **`on`** | **`off`** } ] **`)`**

## <a name="remarks"></a>解説

この pragma オプションを使用すると、およびまたは関数としてマークされた関数を、 [`inline`](../cpp/inline-functions-cpp.md) [`__inline`](../cpp/inline-functions-cpp.md) コンパイラがオプションの下で自動的に展開する機能を制御 **`/Ob2`** できます。 このオプションを使用するに pragma [`/Ob`](../build/reference/ob-inline-function-expansion.md) は、1または2のいずれかのコンパイラオプション設定が必要です。 の既定の状態 **`inline_recursion`** は off です。 この操作は pragma 、が表示された後の最初の関数呼び出しで有効になり、 pragma 関数の定義には影響しません。

は、 **`inline_recursion`** pragma 再帰関数を展開する方法を制御します。 **`inline_recursion`** が off で、インライン関数がそれ自体を直接または間接的に呼び出す場合、関数は1回だけ拡張されます。 が on に設定されている場合、関数は、で設定された値に達するか、で定義されている **`inline_recursion`** [`inline_depth`](../preprocessor/inline-depth.md) pragma 再帰関数の既定値、 `inline_depth` pragma または容量制限に達するまで、複数回展開されます。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)\
[`inline_depth`](../preprocessor/inline-depth.md)\
[`/Ob` (関数のインライン展開)](../build/reference/ob-inline-function-expansion.md)
