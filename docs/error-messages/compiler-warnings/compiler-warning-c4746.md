---
title: コンパイラの警告 C4746
ms.date: 11/04/2016
f1_keywords:
- C4746
helpviewer_keywords:
- C4746
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
ms.openlocfilehash: 7179e2e6d4ec44355e7338ffc4e9ba36f5de47e4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165107"
---
# <a name="compiler-warning-c4746"></a>コンパイラの警告 C4746

'\<expression > ' の volatile アクセスは/volatile: [iso&#124;ミリ秒] 設定の対象になります。__iso_volatile_load/ストア組み込み関数を使用することを検討してください。

C4746 は、volatile 変数に直接アクセスしたときに出力されます。 これは、現在指定されている特定の volatile モデルの影響を受けるコードの場所を開発者が特定できるようにすることを目的としています ( [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラオプションを使用して制御できます)。 特に、/volatile: ms が使用されているときに、コンパイラによって生成されたハードウェアメモリバリアを特定するときに役立ちます。

__Iso_volatile_load/ストア組み込みを使用して、揮発性モデルの影響を受けずに、揮発性メモリに明示的にアクセスできます。 これらの組み込みを使用しても、C4746 はトリガーされません。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。
