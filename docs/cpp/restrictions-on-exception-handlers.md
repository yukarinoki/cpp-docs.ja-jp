---
title: 例外ハンドラーに関する制約 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29a462f83bff3bab158e9bcf9fa7947efb56a79b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074475"
---
# <a name="restrictions-on-exception-handlers"></a>例外ハンドラーに関する制約

例外ハンドラーのコードで使用する主な制限が使用できないことを**goto**ステートメントにジャンプ、 **_ _try**ステートメント ブロックです。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 外部にジャンプすることができます、 **_ _try**ステートメントをブロックしを選択すると、例外ハンドラーを入れ子にします。

## <a name="see-also"></a>関連項目

[例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)<br/>
[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)