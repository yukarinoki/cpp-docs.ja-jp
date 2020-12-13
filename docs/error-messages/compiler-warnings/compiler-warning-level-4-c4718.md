---
description: '詳細情報: コンパイラの警告 (レベル 4) C4718'
title: コンパイラの警告 (レベル 4) C4718
ms.date: 11/04/2016
f1_keywords:
- C4718
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
ms.openlocfilehash: 9c0a24bbec0ae0cf902d905cc2dcecc492efc44b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330544"
---
# <a name="compiler-warning-level-4-c4718"></a>コンパイラの警告 (レベル 4) C4718

'function call': 再帰呼び出しには副作用がありません、削除しています

関数に再帰呼び出しが含まれていますが、それ以外の副作用はありません。 この関数に対する呼び出しを削除しています。 プログラムの正確性に影響しませんが、動作には影響します。 呼び出しをそのままにした場合、ランタイム スタック オーバーフロー例外が発生する可能性がありますが、呼び出しを削除するとその可能性はなくなります。
