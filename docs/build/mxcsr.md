---
title: MxCsr |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d18a4247d36e6894230d74322d52cd5854e42fb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726506"
---
# <a name="mxcsr"></a>MxCsr

レジスタの状態には、MxCsr も含まれています。 呼び出し規約は、揮発性の部分と不揮発性の部分にこのレジスタを分割します。 揮発性の部分から成る 6 つの状態フラグ、MXCSR [0:5]、6:15、MXCSR レジスタの残りの部分には、不揮発性と見なされます。

不揮発性の部分は、プログラムの実行の開始時に、次の標準的な値に設定されます。

```
MXCSR[6]         : Denormals are zeros - 0
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)
```

MXCSR 内不揮発性のフィールドのいずれかを変更する呼び出し先は、呼び出し元に返す前にそれらを復元する必要があります。 さらに、呼び出し元がこれらのフィールドのいずれかが変更する必要がありますの標準値の前に復元アグリーメントによって、呼び出し先が変更後の値を期待しない限り、呼び出し先を呼び出します。

非揮発性に関する規則に制御フラグの 2 つの例外があります。

- 不揮発性の MxCsr を変更するが、指定された関数のドキュメント化の目的の関数でフラグを設定します。

- おそらく正しいする動作/手段、これらの規則に違反しない、たとえば、プログラム全体の分析によって、プログラムと同じプログラムで結果をこれらの規則に違反する場合。

関数の境界を越えて MXCSR の揮発性の部分の状態に関する仮定は行われません関数のドキュメントで説明されている場合を除き、します。

## <a name="see-also"></a>関連項目

[呼び出し規則](../build/calling-convention.md)