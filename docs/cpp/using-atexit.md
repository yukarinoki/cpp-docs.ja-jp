---
title: atexit の使用
ms.date: 11/04/2016
f1_keywords:
- atexit
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
ms.openlocfilehash: 06baba59b5765f853f081b34d73be28a187730ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637451"
---
# <a name="using-atexit"></a>atexit の使用

[Atexit](../c-runtime-library/reference/atexit.md)関数の場合、プログラムの終了前に実行される終了処理関数を指定することができます。 呼び出す前に初期化されてグローバルな静的オブジェクト**atexit**終了処理関数の実行前に破棄されません。

## <a name="see-also"></a>関連項目

[終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)