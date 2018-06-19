---
title: inline_depth |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e40b9382abc8ee0fa0c003964eebe75bc075e473
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849874"
---
# <a name="inlinedepth"></a>inline_depth
(呼び出し先で) `n` を超える深度になる場合に関数がインライン展開されないようにインライン ヒューリスティック検索の深さを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## <a name="remarks"></a>コメント  
 このプラグマを制御、マークされた関数のインライン展開[インライン](../cpp/inline-functions-cpp.md)と[_ _inline](../cpp/inline-functions-cpp.md)または/Ob2 オプションで自動的にインライン展開されます。  
  
 `n` は 0 ～ 255 の値になります。255 は呼び出し先の深さが無制限であることを意味し、0 はインライン展開を禁じます。  `n` が指定されていない場合、既定値 (254) が使用されます。  
  
 **Inline_depth**プラグマは一連の関数呼び出しを展開できる回数を制御します。 たとえば、インライン展開の深さが 4 の場合、A が B を呼び出してから、B が C を呼び出すと、3 回の呼び出しはすべてインライン展開されます。 ただし、最も近いインライン展開が 2 の場合は、A と B のみ展開され、C は関数呼び出しとして残ります。  
  
 このプラグマを使用するには、/Ob コンパイラ オプションを 1 または 2 に設定する必要があります。 このプラグマを使用して設定した深さは、プラグマの後の最初の関数呼び出し時に有効になります。  
  
 インライン展開の深さは展開時に減らすことができますが、増やすことはできません。 インライン展開の深さが 6 で、展開時に、プリプロセッサが発生した場合、 **inline_depth**プラグマ、8、深さの値は 6 のままです。  
  
 **Inline_depth**プラグマでマークされた関数には影響を持たない`__forceinline`です。  
  
> [!NOTE]
>  再帰関数は、最大深度である 16 回の呼び出しまでインラインで置き換えることができます。  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと _ _pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_recursion](../preprocessor/inline-recursion.md)