---
description: 詳細については、「式エバリュエーターエラー CXX0019」を参照してください。
title: 式エバリュエーター エラー CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 1caf4714c1fc719883ee889c14225e4f69e961a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228236"
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
