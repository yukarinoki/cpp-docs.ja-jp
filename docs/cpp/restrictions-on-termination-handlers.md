---
title: 終了ハンドラーに関する制約
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: d53792afbc3d25fb21edafa7817919b63b79ab65
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225892"
---
# <a name="restrictions-on-termination-handlers"></a>終了ハンドラーに関する制約

ステートメントを使用して **`goto`** 、 **__try**ステートメントブロックまたはステートメントブロックに移動することはできません **`__finally`** 。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 (ただし、 **__try**のステートメントブロックからジャンプできます)。また、ブロック内の例外ハンドラーまたは終了ハンドラーを入れ子にすることはできません **`__finally`** 。

また、終端ハンドラーに割り当てられた一部の種類のコードが生成する結果に問題がある場合があります。したがって、これらは慎重に使用する必要があります。 1つは、 **`goto`** ステートメントブロックからジャンプするステートメントです **`__finally`** 。 ブロックが正常終了の一部として実行される場合、特に異常は発生しません。 ただし、システムがスタックをアンワインドしている場合は、そのアンワインドが停止し、異常な終了がなかったかのように現在の関数が制御を得ます。

ステートメント **`return`** ブロック内のステートメントは **`__finally`** 、ほぼ同じ状況を示します。 終了ハンドラーを含む関数の直前の呼び出し元に制御が戻ります。 システムがスタックをアンワインドしていた場合、このプロセスは停止し、例外が発生しなかったかのようにプログラムが処理されます。

## <a name="see-also"></a>関連項目

[終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
