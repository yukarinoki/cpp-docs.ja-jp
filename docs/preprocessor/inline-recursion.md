---
title: inline_recursion |Microsoft ドキュメント
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
ms.openlocfilehash: f81347c8286dfa1f0651af43bd3134565a22aade
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849497"
---
# <a name="inlinerecursion"></a>inline_recursion
直接呼び出しまたは相互再帰関数の呼び出しのインライン展開を制御します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## <a name="remarks"></a>コメント  
 としてマークされている制御関数には、このプラグマを使用して[インライン](../cpp/inline-functions-cpp.md)と[_ _inline](../cpp/inline-functions-cpp.md)またはコンパイラが/Ob2 オプションで自動的に展開する関数。 このプラグマの使用を必要とする[/Ob](../build/reference/ob-inline-function-expansion.md) 1 または 2 のいずれかのコンパイラ オプションの設定。 `inline_recursion` の既定の状態はオフです。 このプラグマは、以降の最初の関数呼び出しに対して効果があり、関数の定義には影響を与えません。  
  
 `inline_recursion` プラグマは再帰関数の展開方法を制御します。 `inline_recursion` が off の場合、インライン関数が自身を (直接または間接的に) 呼び出すと、関数は 1 回しか展開されません。 場合`inline_recursion`関数で設定された値に達するまで複数回に展開されますが、上、 [inline_depth](../preprocessor/inline-depth.md)プラグマで定義されている再帰関数の既定値、`inline_depth`プラグマ、または容量制限.  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと _ _pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_depth](../preprocessor/inline-depth.md)   
 [/Ob (関数のインライン展開)](../build/reference/ob-inline-function-expansion.md)