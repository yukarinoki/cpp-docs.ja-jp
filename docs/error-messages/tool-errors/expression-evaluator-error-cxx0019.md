---
title: 式エバリュエーター エラー CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 61646462eeba4918a4993b23f7f4b394083296ce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195891"
---
# <a name="expression-evaluator-error-cxx0019"></a>式エバリュエーター エラー CXX0019

不適切な型キャスト

C 式エバリュエーターは、記述された型キャストを実行できません。

このエラーは CAN0019 と同じです。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 指定された型は不明です。

1. ポインター型のレベルが多すぎました。 たとえば、型キャストです。

    ```
    (char **)h_message
    ```

   は、C 式エバリュエーターで評価することはできません。
