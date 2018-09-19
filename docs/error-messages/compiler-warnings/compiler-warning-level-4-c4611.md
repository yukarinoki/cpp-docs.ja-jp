---
title: コンパイラの警告 (レベル 4) C4611 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4611
dev_langs:
- C++
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 723976dc8b7085ede9b3157445ff3026de6fc4b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091050"
---
# <a name="compiler-warning-level-4-c4611"></a>コンパイラの警告 (レベル 4) C4611

'function' と C++ オブジェクト デストラクション間の相互作用はポータブルでないです。

関数が含まれる一部のプラットフォームで**キャッチ**スコープ外の時の破棄の C++ オブジェクト セマンティクスをサポートしていません。

予期しない動作を回避するには、使用しないように**キャッチ**をコンス トラクターとデストラクターを持つ関数でします。

この警告は 1 回だけです。参照してください[pragma 警告](../../preprocessor/warning.md)します。