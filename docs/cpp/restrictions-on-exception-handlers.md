---
title: 例外ハンドラーに関する制約
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 1f80cb1574cbfef0783c7e55dcd198dfb822f566
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225905"
---
# <a name="restrictions-on-exception-handlers"></a>例外ハンドラーに関する制約

コードで例外ハンドラーを使用する場合の主な制限事項は、ステートメントを使用して **`goto`** **__try**ステートメントブロックにジャンプすることができないことです。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 **__Try**ステートメントブロックから移動し、選択したとおりに例外ハンドラーを入れ子にすることができます。

## <a name="see-also"></a>関連項目

[例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
