---
title: 関数の型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dfb36dc9e177fdb9ad196c0e2a8ad0f352d5f2d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709567"
---
# <a name="function-types"></a>関数の型

基本的には、関数の 2 つの種類があります。 スタック フレームを必要とする関数には、フレームの関数は呼び出されます。 スタック フレームを必要としない関数には、リーフ関数は呼び出されます。

フレームの関数は、スタック領域の割り当て、その他の関数を呼び出し、不揮発性レジスタを保存または例外処理を使用する関数です。 関数のテーブルのエントリも必要です。 フレームの関数は、プロローグとエピローグが必要です。 フレームの関数では、スタック領域を動的に割り当てることができます、フレーム ポインターを使用できます。 フレーム関数には、標準的な破棄された時点の呼び出しのすべての機能がいます。

フレームの関数が別の関数を呼び出さないかどうかは、スタックを配置する必要はありません (セクションで参照されている[スタック割り当て](../build/stack-allocation.md))。

リーフ関数とは、関数のテーブルのエントリは不要です。 など、任意の関数を呼び出すまたはスタック領域の割り当てできないということを意味 RSP、不揮発性レジスタに加えることはできません。 実行中にスタックの整列されていないままにすることができます。

## <a name="see-also"></a>関連項目

[スタックの使用](../build/stack-usage.md)
