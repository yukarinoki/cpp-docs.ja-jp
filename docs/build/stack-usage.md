---
title: スタックの使用量 |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 827a129c0b7a444cc5b48ba68a3e360712e1c08e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721540"
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