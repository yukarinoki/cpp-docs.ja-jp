---
title: コンパイラの警告 (レベル 1) C4420 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1ba4ef4c4fc006e1a5950d0d16dc530ccc06a1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049749"
---
# <a name="compiler-warning-level-1-c4420"></a>コンパイラの警告 (レベル 1) C4420

'operator': 演算子は使用できません代わりに 'operator' を使用する。実行時チェックを侵害する可能性があります。

使用する場合、この警告が生成された、 [/rtcv させる](../../build/reference/rtc-run-time-error-checks.md)(新規/削除の確認をベクトル) とベクトル形式が見つかりませんでした。 この場合、非ベクター形式が使用されます。

/Rtcv を正しく動作させるためには、コンパイラが常に呼び出しベクトル形式の[新しい](../../cpp/new-operator-cpp.md)/[削除](../../cpp/delete-operator-cpp.md)ベクター構文を使用した場合。