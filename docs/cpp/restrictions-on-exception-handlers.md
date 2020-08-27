---
title: 例外ハンドラーに関する制約
description: 構造化例外処理ブロックへのジャンプに関する制限について説明します。
ms.date: 08/24/2020
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: c4182f065789533bf7599621d8d2829b2d52d6ed
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898450"
---
# <a name="restrictions-on-exception-handlers"></a>例外ハンドラーに関する制約

コードで例外ハンドラーを使用する場合の主な制限事項は、ステートメントを使用して **`goto`** ステートメントブロックにジャンプすることができないことです **`__try`** 。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 **`__try`** ステートメントブロックからジャンプして、選択したとおりに例外ハンドラーを入れ子にすることができます。

## <a name="see-also"></a>関連項目

[例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
