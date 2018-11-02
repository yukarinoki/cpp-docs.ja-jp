---
title: 例外ハンドラーに関する制約
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 7d5bf20da61f4b9f5012b7f2aab932dfc904c302
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573993"
---
# <a name="restrictions-on-exception-handlers"></a>例外ハンドラーに関する制約

例外ハンドラーのコードで使用する主な制限が使用できないことを**goto**ステートメントにジャンプ、 **_ _try**ステートメント ブロックです。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 外部にジャンプすることができます、 **_ _try**ステートメントをブロックしを選択すると、例外ハンドラーを入れ子にします。

## <a name="see-also"></a>関連項目

[例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)