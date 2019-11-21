---
title: 終了ハンドラーに関する制約
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 6c39407270037756c55dc42aed80e1d04616c9ee
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246376"
---
# <a name="restrictions-on-termination-handlers"></a>終了ハンドラーに関する制約

You cannot use a **goto** statement to jump into a **__try** statement block or a **__finally** statement block. 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 (You can, however, jump out of a **__try** statement block.) Also, you cannot nest an exception handler or termination handler inside a **__finally** block.

また、終端ハンドラーに割り当てられた一部の種類のコードが生成する結果に問題がある場合があります。したがって、これらは慎重に使用する必要があります。 One is a **goto** statement that jumps out of a **__finally** statement block. ブロックが正常終了の一部として実行される場合、特に異常は発生しません。 ただし、システムがスタックをアンワインドしている場合は、そのアンワインドが停止し、異常な終了がなかったかのように現在の関数が制御を得ます。

A **return** statement inside a **__finally** statement block presents roughly the same situation. 終了ハンドラーを含む関数の直前の呼び出し元に制御が戻ります。 システムがスタックをアンワインドしていた場合、このプロセスは停止し、例外が発生しなかったかのようにプログラムが処理されます。

## <a name="see-also"></a>関連項目

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)