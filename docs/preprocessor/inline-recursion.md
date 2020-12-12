---
description: '詳細については、次を参照してください: inline_recursion プラグマ'
title: inline_recursion プラグマ
ms.date: 08/29/2019
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
ms.openlocfilehash: 1688eb724a9a76ce3f173c7f9eac7d52032fbe13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236374"
---
# <a name="inline_recursion-pragma"></a>inline_recursion プラグマ

直接呼び出しまたは相互再帰関数の呼び出しのインライン展開を制御します。

## <a name="syntax"></a>構文

> **#pragma inline_recursion (** [{ **on**  |  **off** }] **)**

## <a name="remarks"></a>解説

このプラグマを使用して、 [インライン](../cpp/inline-functions-cpp.md) としてマークされている関数と、コンパイラがオプションの下で自動的に展開する関数 [__inline](../cpp/inline-functions-cpp.md) を制御し `/Ob2` ます。 このプラグマを使用するには、 [/Ob](../build/reference/ob-inline-function-expansion.md) コンパイラオプションを1または2のいずれかに設定する必要があります。 **Inline_recursion** の既定の状態は off です。 このプラグマは、プラグマが表示された後の最初の関数呼び出しで有効になり、関数の定義には影響しません。

**Inline_recursion** プラグマは、再帰関数を展開する方法を制御します。 **Inline_recursion** がオフの場合、インライン関数が直接または間接的にそれ自体を呼び出すと、関数は1回だけ拡張されます。 **Inline_recursion** が on の場合、関数は、 [inline_depth](../preprocessor/inline-depth.md)プラグマ、プラグマで定義されている再帰関数の既定値、または容量制限によって設定された値に達するまで、複数回展開され `inline_depth` ます。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[inline_depth](../preprocessor/inline-depth.md)\
[/Ob (関数のインライン展開)](../build/reference/ob-inline-function-expansion.md)
