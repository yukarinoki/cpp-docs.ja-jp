---
description: pragmaMicrosoft C/c + + での inline_depth ディレクティブの詳細については、こちらを参照してください。
title: inline_depth pragma
ms.date: 01/22/2021
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
helpviewer_keywords:
- pragma, inline_depth
- inline_depth pragma
no-loc:
- pragma
ms.openlocfilehash: 6daffdbcb598304925675c15c955941eb8369d23
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713572"
---
# <a name="inline_depth-no-locpragma"></a>`inline_depth` pragma

インラインヒューリスティック検索の深さを指定します。 指定された値を超える呼び出しグラフの深度にある関数はインライン展開されません。

## <a name="syntax"></a>構文

> **`#pragma inline_depth(`** [ *n* ] **`)`**

## <a name="remarks"></a>解説

これにより、、 pragma [`inline`](../cpp/inline-functions-cpp.md) [`__inline`](../cpp/inline-functions-cpp.md) 、またはコンパイラオプションの下で自動的にインライン化された関数のインライン展開を制御し **`/Ob`** ます。 詳細については、「 [ `/Ob` (関数のインライン展開)](../build/reference/ob-inline-function-expansion.md)」を参照してください。

*n* には、0 ~ 255 の値を指定できます。255は、呼び出しグラフの深さを無制限に意味します。 値0は、インライン展開を禁止します。 *N* を指定しない場合、既定値の254が使用されます。

は、 **`inline_depth`** pragma 一連の関数呼び出しを展開できる回数を制御します。 たとえば、インラインの深さが4であるとします。 A が B を呼び出し、B が C を呼び出した場合、3つの呼び出しはすべてインラインで展開されます。 ただし、最も近いインラインの深さ拡張が2の場合、A と B のみが展開され、C は関数呼び出しとして残ります。

これを使用するには、 pragma コンパイラオプションを1以上に設定する必要があり **`/Ob`** ます。 このを使用して設定した深度は pragma 、の後の最初の関数呼び出しで有効になり pragma ます。

インラインの深さは展開中に減らすことができますが、増加することはできません。 インラインの深さが6で、拡張中にプリプロセッサが値8を持つを検出した場合、 **`inline_depth`** pragma その深さは6のままです。

は、 **`inline_depth`** pragma でマークされた関数には影響しません **`__forceinline`** 。

> [!NOTE]
> 再帰関数は、最大深度である 16 回の呼び出しまでインラインで置き換えることができます。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)\
[`inline_recursion`](../preprocessor/inline-recursion.md)
