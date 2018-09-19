---
title: exit 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71bff42495c4b6b7bf4016f0f08e7127c2b278ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075177"
---
# <a name="exit-function"></a>exit 関数

**終了**標準インクルード ファイルで宣言された関数\<stdlib.h >、C++ プログラムを終了します。

引数として指定された値**終了**プログラムのリターン コードまたは終了コードとしてオペレーティング システムに返されます。 慣例により、ゼロのリターン コードは、プログラムが正常に完了したことを意味します。

> [!NOTE]
>  EXIT_FAILURE と EXIT_SUCCESS で定義されている定数を使用することができます\<stdlib.h > プログラムの成功または失敗を示すために、します。

発行、**返す**ステートメントから、`main`関数の呼び出しと同じですが、**終了**関数の引数として戻り値。

詳細については、次を参照してください。[終了](../c-runtime-library/reference/exit-exit-exit.md)で、*ランタイム ライブラリ リファレンス*します。

## <a name="see-also"></a>関連項目

[プログラムの終了](../cpp/program-termination.md)