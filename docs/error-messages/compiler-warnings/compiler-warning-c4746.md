---
title: コンパイラの警告 C4746 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6abce7ebbcdc41effed05ccf54337e3976c34e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054871"
---
# <a name="compiler-warning-c4746"></a>コンパイラの警告 C4746

揮発性アクセス '\<式 >' は/volatile: [iso&#124;ms] 設定には、_iso_volatile_load/store 組み込み関数を使用して検討してください。

揮発性変数が直接アクセスされるたびに、C4746 が生成されます。 現在指定されている特定の揮発性モデルの影響を受けるコードの場所を特定する開発者を支援するものでは (でこれを制御することができます、 [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプション)。 具体的には、/volatile:ms を使用する場合は、コンパイラによって生成されたハードウェア メモリ バリアを検出するのに便利ですができます。

_Iso_volatile_load/store 組み込み関数は、揮発性モデルの影響を受けることがなく明示的に揮発性メモリへのアクセスに使用できます。 これらの組み込みを使用しても、C4746 はトリガーされません。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。