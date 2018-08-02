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
ms.openlocfilehash: 8775f752a541d2a250e9c1c5a0c325b684335988
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464601"
---
# <a name="restrictions-on-exception-handlers"></a>例外ハンドラーに関する制約
例外ハンドラーのコードで使用する主な制限が使用できないことを**goto**ステートメントにジャンプ、 **_ _try**ステートメント ブロックです。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 外部にジャンプすることができます、 **_ _try**ステートメントをブロックしを選択すると、例外ハンドラーを入れ子にします。  
  
## <a name="see-also"></a>関連項目  
 [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)