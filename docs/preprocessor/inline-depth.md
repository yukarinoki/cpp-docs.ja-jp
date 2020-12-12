---
description: '詳細については、次を参照してください: inline_depth プラグマ'
title: inline_depth プラグマ
ms.date: 08/29/2019
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
ms.openlocfilehash: 10ac7f5543108018eb7b51e8916dfed149363899
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236400"
---
# <a name="inline_depth-pragma"></a>inline_depth プラグマ

インラインヒューリスティック検索の深さを指定します。 指定された値を超える呼び出しグラフの深度にある関数はインライン展開されません。

## <a name="syntax"></a>構文

> **#pragma inline_depth (** [ *n* ] **)**

## <a name="remarks"></a>解説

このプラグマは、 [inline](../cpp/inline-functions-cpp.md) および [__inline](../cpp/inline-functions-cpp.md)とマークされた関数のインライン展開、またはオプションの下に自動的にインライン展開される関数を制御し `/Ob` ます。

*n* には、0 ~ 255 の値を指定できます。255は、呼び出しグラフの深さを無制限に意味します。 値0は、インライン展開を禁止します。 *N* を指定しない場合、既定値の254が使用されます。

**Inline_depth** プラグマは、一連の関数呼び出しを展開できる回数を制御します。 たとえば、インラインの深さが4であるとします。 A が B を呼び出し、B が C を呼び出した場合、3つの呼び出しはすべてインラインで展開されます。 ただし、最も近いインラインの深さ拡張が2の場合、A と B のみが展開され、C は関数呼び出しとして残ります。

このプラグマを使用するには、 `/Ob` コンパイラオプションを1以上に設定する必要があります。 このプラグマを使用して設定した深さは、プラグマの後の最初の関数呼び出し時に有効になります。

インラインの深さは展開中に減らすことができますが、増加することはできません。 インラインの深さが6で、拡張中にプリプロセッサによって、値が8の **inline_depth** プラグマが検出された場合、その深さは6のままになります。

**Inline_depth** プラグマは、でマークされた関数には影響しません **`__forceinline`** 。

> [!NOTE]
> 再帰関数は、最大深度である 16 回の呼び出しまでインラインで置き換えることができます。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[inline_recursion](../preprocessor/inline-recursion.md)
