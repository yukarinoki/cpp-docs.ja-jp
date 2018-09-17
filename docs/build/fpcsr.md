---
title: FpCsr |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6ed0500d0382563878d0751ba5386e4cc637fdb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718290"
---
# <a name="fpcsr"></a>FpCsr

レジスタの状態にも、x87 FPU 制御ワード。 呼び出し規約では、このレジスタを不揮発性によって決まります。

X87 FPU 制御ワードのレジスタの先頭に次の標準的な値に設定されているプログラムの実行。

```
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)
FPCSR[7]: Reserved - 0
FPCSR[8:9]: Precision Control - 10B (double precision)
FPCSR[10:11]: Rounding  control - 0 (round to nearest)
FPCSR[12]: Infinity control - 0 (not used)
```

FPCSR 内のフィールドのいずれかを変更する呼び出し先は、呼び出し元に返す前にそれらを復元する必要があります。 さらに、呼び出し元がこれらのフィールドのいずれかが変更する必要がありますの標準値の前に復元アグリーメントによって、呼び出し先が変更後の値を期待しない限り、呼び出し先を呼び出します。

非揮発性に関する規則に制御フラグの 2 つの例外があります。

1. 不揮発性 FpCsr を変更するが、指定された関数のドキュメント化の目的の関数でフラグを設定します。

1. おそらく正しいする動作/手段、これらの規則に違反しない、たとえば、プログラム全体の分析によって、プログラムと同じプログラムで結果をこれらの規則に違反する場合。

## <a name="see-also"></a>関連項目

[呼び出し規則](../build/calling-convention.md)