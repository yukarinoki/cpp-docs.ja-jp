---
title: exit 関数
ms.date: 11/04/2016
f1_keywords:
- Exit
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
ms.openlocfilehash: 82c9d00a49c8a080d893a51052739a0265ad0860
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532562"
---
# <a name="exit-function"></a>exit 関数

**終了**標準インクルード ファイルで宣言された関数\<stdlib.h >、C++ プログラムを終了します。

引数として指定された値**終了**プログラムのリターン コードまたは終了コードとしてオペレーティング システムに返されます。 慣例により、ゼロのリターン コードは、プログラムが正常に完了したことを意味します。

> [!NOTE]
>  EXIT_FAILURE と EXIT_SUCCESS で定義されている定数を使用することができます\<stdlib.h > プログラムの成功または失敗を示すために、します。

発行、**返す**ステートメントから、`main`関数の呼び出しと同じですが、**終了**関数の引数として戻り値。

詳細については、[終了](../c-runtime-library/reference/exit-exit-exit.md)で、*ランタイム ライブラリ リファレンス*を参照してください。

## <a name="see-also"></a>関連項目

[プログラムの終了](../cpp/program-termination.md)