---
title: コンパイラの警告 (レベル 4) C4718 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4718
dev_langs:
- C++
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8736902f4c3a1cfac7313806fde65d1b253716b3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054234"
---
# <a name="compiler-warning-level-4-c4718"></a>コンパイラの警告 (レベル 4) C4718

'function call': 再帰呼び出しには副作用がありません、削除しています

関数に再帰呼び出しが含まれていますが、それ以外の副作用はありません。 この関数に対する呼び出しを削除しています。 プログラムの正確性に影響しませんが、動作には影響します。 呼び出しをそのままにした場合、ランタイム スタック オーバーフロー例外が発生する可能性がありますが、呼び出しを削除するとその可能性はなくなります。