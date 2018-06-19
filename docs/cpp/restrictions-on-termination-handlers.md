---
title: 終了ハンドラーに関する制約 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f35560c6f29e341b05f6b8bdf22873847644d7c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420583"
---
# <a name="restrictions-on-termination-handlers"></a>終了ハンドラーに関する制約
`goto` ステートメントを使用して、`__try` ステートメント ブロックまたは `__finally` ステートメント ブロックにジャンプすることはできません。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 (ただし、`__try` ステートメント ブロックの外部にジャンプすることもできます)。また、`__finally` ブロック内の例外ハンドラーまたは終了ハンドラーは入れ子にできません。  
  
 また、終端ハンドラーに割り当てられた一部の種類のコードが生成する結果に問題がある場合があります。したがって、これらは慎重に使用する必要があります。 1 つは、`goto` ステートメント ブロックの外部にジャンプする `__finally` ステートメントです。 ブロックが正常終了の一部として実行される場合、特に異常は発生しません。 ただし、システムがスタックをアンワインドしている場合は、そのアンワインドが停止し、異常な終了がなかったかのように現在の関数が制御を得ます。  
  
 `return` ステートメント ブロック内の `__finally` ステートメントが、同じ状況を大まかに示します。 終了ハンドラーを含む関数の直前の呼び出し元に制御が戻ります。 システムがスタックをアンワインドしていた場合、このプロセスは停止し、例外が発生しなかったかのようにプログラムが処理されます。  
  
## <a name="see-also"></a>関連項目  
 [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)