---
title: コンパイラの警告 (レベル 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: 2ce261b36344126d541a9b453c88f7f8289ecba0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214335"
---
# <a name="compiler-warning-level-4-c4611"></a>コンパイラの警告 (レベル 4) C4611

' function ' と C++ オブジェクトの破棄の間の相互作用は、移植不可です

一部のプラットフォームでは、が含まれている関数は、スコープ外の **`catch`** 場合に、デストラクターの C++ オブジェクトセマンティクスをサポートしていない可能性があります。

予期しない動作を避けるため、 **`catch`** コンストラクターとデストラクターを持つ関数ではを使用しないでください。

この警告は1回のみ発行されます。[プラグマの警告](../../preprocessor/warning.md)を参照してください。
