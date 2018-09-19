---
title: コンパイラの警告 (レベル 4) C4710 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4710
dev_langs:
- C++
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f6de17f7005db3834bfcfc93aff03f12f0293ce
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046096"
---
# <a name="compiler-warning-level-4-c4710"></a>コンパイラの警告 (レベル 4) C4710

'function': 関数のインライン化できません

指定された関数がインライン展開の選択されたが、コンパイラが実行されなかった、インライン化します。

インライン展開は、コンパイラの裁量で実行されます。 **インライン**キーワードと同様に、**登録**キーワードがコンパイラにヒントとして使用します。 コンパイラでは、ヒューリスティックを使用して、速度、コンパイルするときに、コードを高速化する特定の関数をインラインにする必要がありますか場合は領域をコンパイルするときに、コードを小さく特定の関数をインラインにする必要がありますかを判断します。 コンパイラでは、領域をコンパイルするときに、だけがインライン展開が非常に小規模関数には。

場合によっては、コンパイラはインラインではなく、特定の関数の機械的な理由からします。 参照してください[C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md)に対して一連の上の理由から、コンパイラがインライン関数ではない可能性があります。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。