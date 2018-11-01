---
title: スタックの使用
ms.date: 11/04/2016
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
ms.openlocfilehash: 5ee9da50a03e1137ed6543cd349481148c9127d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452222"
---
# <a name="stack-usage"></a>スタックの使用

RSP の現在のアドレスを超えるすべてのメモリは揮発性と見なされます。 OS、またはデバッガーの場合は、ユーザーのデバッグ セッションでは、または、割り込みハンドラーの中にこのメモリを上書きできます。 したがって、RSP は常に読み取りまたはスタック フレームに値を書き込みを試行する前に設定する必要があります。

このセクションでは、ローカル変数のスタック領域の割り当てをについて説明しますと、 **alloca**組み込み。

- [スタック割り当て](../build/stack-allocation.md)

- [動的なパラメーター スタック領域の構成](../build/dynamic-parameter-stack-area-construction.md)

- [関数の型](../build/function-types.md)

- [malloc アライメント](../build/malloc-alignment.md)

- [alloca](../build/alloca.md)

## <a name="see-also"></a>関連項目

[x64 ソフトウェア規約](../build/x64-software-conventions.md)