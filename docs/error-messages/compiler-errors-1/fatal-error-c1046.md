---
title: 致命的なエラー C1046 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1046
dev_langs:
- C++
helpviewer_keywords:
- C1046
ms.assetid: 822ec5f5-b0b0-4711-99e1-fc237b619af6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 449b181167ef493c149e9e34cb2f1a681148411d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035471"
---
# <a name="fatal-error-c1046"></a>致命的なエラー C1046

コンパイラの制限: 構造体の入れ子レベルが深すぎます

構造体、共用体、またはクラスは、15 レベルの入れ子の制限を超えました。 入れ子のレベルを下げるために、定義を書き直してください。 構造体、共用体、またはクラスに 2 つ以上の部分を使用して分割`typedef`を 1 つまたは複数の入れ子になった構造体を定義します。