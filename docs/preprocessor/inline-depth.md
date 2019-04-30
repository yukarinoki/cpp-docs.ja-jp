---
title: inline_depth
ms.date: 11/04/2016
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
ms.openlocfilehash: 18d772c8a9f6218ed3afaa385f214445bd0fe8e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383686"
---
# <a name="inlinedepth"></a>inline_depth
関数がインライン展開されない場合よりも大きい (呼び出し先) の深さではするようにインライン ヒューリスティック検索の深さを指定します*n*します。

## <a name="syntax"></a>構文

```
#pragma inline_depth( [n] )
```

## <a name="remarks"></a>Remarks

このプラグマを制御、マークされた関数のインライン展開[インライン](../cpp/inline-functions-cpp.md)と[_ _inline](../cpp/inline-functions-cpp.md)で自動的にインライン化、`/Ob2`オプション。

*n* 0 から 255、255 は呼び出しグラフの深さが無制限を意味して、0 はインライン展開を禁じます場所までの値を指定できます。  ときに*n*が指定されていない、既定値 (254) が使用されます。

**Inline_depth**プラグマは一連の関数呼び出しを展開できる回数を制御します。 たとえば、インライン展開の深さが 4 の場合、A が B を呼び出してから、B が C を呼び出すと、3 回の呼び出しはすべてインライン展開されます。 ただし、最も近いインライン展開が 2 の場合は、A と B のみ展開され、C は関数呼び出しとして残ります。

このプラグマを使用するに設定する必要があります、`/Ob`コンパイラ オプションを 1 または 2 にします。 このプラグマを使用して設定した深さは、プラグマの後の最初の関数呼び出し時に有効になります。

インライン展開の深さは展開時に減らすことができますが、増やすことはできません。 インライン展開の深さは 6 つの拡張中に、プリプロセッサが発生した場合、 **inline_depth**プラグマ、8、深さの値は 6 です。

**Inline_depth**プラグマがでマークされた関数に影響を与えません`__forceinline`します。

> [!NOTE]
> 再帰関数は、最大深度である 16 回の呼び出しまでインラインで置き換えることができます。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_recursion](../preprocessor/inline-recursion.md)