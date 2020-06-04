---
title: 終了ハンドラーに関する制約
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: befe181a41ed418a4a824b131e741a9f02f90e38
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179069"
---
# <a name="restrictions-on-termination-handlers"></a>終了ハンドラーに関する制約

**Goto**ステートメントを使用して、 **__try**ステートメントブロックまたは **__finally**ステートメントブロックに移動することはできません。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 (ただし、 **__try**のステートメントブロックからジャンプできます)。また、例外ハンドラーまたは終了ハンドラーを **__finally**ブロック内に入れ子にすることはできません。

また、終端ハンドラーに割り当てられた一部の種類のコードが生成する結果に問題がある場合があります。したがって、これらは慎重に使用する必要があります。 1つは、 **__finally**ステートメントブロックからジャンプする**goto**ステートメントです。 ブロックが正常終了の一部として実行される場合、特に異常は発生しません。 ただし、システムがスタックをアンワインドしている場合は、そのアンワインドが停止し、異常な終了がなかったかのように現在の関数が制御を得ます。

**__Finally**ステートメントブロック内の**return**ステートメントは、ほぼ同じ状況を示します。 終了ハンドラーを含む関数の直前の呼び出し元に制御が戻ります。 システムがスタックをアンワインドしていた場合、このプロセスは停止し、例外が発生しなかったかのようにプログラムが処理されます。

## <a name="see-also"></a>参照

[終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
