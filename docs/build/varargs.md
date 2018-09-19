---
title: Varargs |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8305eaddf87a2e67b797bedff1944dbcbbbdbd41
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713649"
---
# <a name="varargs"></a>vararg

Varargs (たとえば、省略記号引数) を使用してパラメーターが指定された場合、基本的には、標準パラメーターの引き渡しでは以降の 5 番目の引数の書き込みなどが適用されます。 もう一度を受け取られるアドレスを持つ引数をダンプする、呼び出し先の責任です。 浮動小数点値の場合にのみ、整数と浮動小数点レジスタの両方が含まれている浮動小数点値場合は、呼び出し先は、整数レジスタに値が必要です。

## <a name="see-also"></a>関連項目

[呼び出し規則](../build/calling-convention.md)