---
title: inline_recursion |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a51428d32c1e7e5863e777302c3c55b728ce11f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083062"
---
# <a name="inlinerecursion"></a>inline_recursion
直接呼び出しまたは相互再帰関数の呼び出しのインライン展開を制御します。

## <a name="syntax"></a>構文

```
#pragma inline_recursion( [{on | off}] )
```

## <a name="remarks"></a>Remarks

としてマークされたこのプラグマは、制御関数を使用して[インライン](../cpp/inline-functions-cpp.md)と[_ _inline](../cpp/inline-functions-cpp.md)または関数で、コンパイラが自動的に展開を`/Ob2`オプション。 このプラグマの使用が必要です、 [/Ob](../build/reference/ob-inline-function-expansion.md) 1 または 2 のいずれかのコンパイラ オプションの設定。 既定の状態**inline_recursion**はオフです。 このプラグマは、以降の最初の関数呼び出しに対して効果があり、関数の定義には影響を与えません。

**Inline_recursion**プラグマは、再帰関数を展開する方法を制御します。 場合**inline_recursion**はオフであり、インライン関数を呼び出す場合自体 (直接または間接的に)、関数が 1 回しか展開します。 場合**inline_recursion**関数で設定された値に達するまで複数回に展開されますが、上、 [inline_depth](../preprocessor/inline-depth.md)プラグマをで定義されている再帰関数の既定値`inline_depth`プラグマ、または容量を制限します。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_depth](../preprocessor/inline-depth.md)<br/>
[/Ob (関数のインライン展開)](../build/reference/ob-inline-function-expansion.md)