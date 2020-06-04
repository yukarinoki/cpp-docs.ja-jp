---
title: 例外ハンドラーに対する制限
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 54bf4a44d06eacd22dc4b9819d160d3c6a66c684
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179082"
---
# <a name="restrictions-on-exception-handlers"></a>例外ハンドラーに対する制限

コードで例外ハンドラーを使用する場合の主な制限事項は、 **goto**ステートメントを使用して **__try**ステートメントブロックに移動できないことです。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 **__Try**ステートメントブロックから移動し、選択したとおりに例外ハンドラーを入れ子にすることができます。

## <a name="see-also"></a>参照

[例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
