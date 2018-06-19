---
title: 例外ハンドラーに対する制限 |Microsoft ドキュメント
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
ms.openlocfilehash: 1f739152b502a156dc62dfab279e5ad044cfff99
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420205"
---
# <a name="restrictions-on-exception-handlers"></a>例外ハンドラーに関する制約
コードで例外ハンドラーを使用する際の主要な制限は、`goto` ステートメントを使用して `__try` ステートメント ブロック内に移動できないことです。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 必要に応じて、`__try` ステートメント ブロックの外に移動して、例外ハンドラーを入れ子にすることができます。  
  
## <a name="see-also"></a>関連項目  
 [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)