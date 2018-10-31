---
title: 式エバリュエーター エラー CXX0019 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0019
dev_langs:
- C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f1e78bd88f35240e90332ef9a9139558051cab5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070128"
---
# <a name="expression-evaluator-error-cxx0019"></a>式エバリュエーター エラー CXX0019

無効な型キャスト

C の式エバリュエーターでは、型キャストを実行できません。

このエラーは、can0019 と同じものと同じです。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 指定した型が不明です。

1. ポインター型のレベルが多すぎますが発生しました。 たとえば、型キャスト

    ```
    (char **)h_message
    ```

   C の式エバリュエーターによって評価ことはできません。