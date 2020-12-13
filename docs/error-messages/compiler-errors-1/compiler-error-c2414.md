---
description: 詳細については、「コンパイラエラー C2414」を参照してください。
title: コンパイラ エラー C2414
ms.date: 11/04/2016
f1_keywords:
- C2414
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
ms.openlocfilehash: 5bf2d017ac0018fe092b5a003dee021dd13370b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340334"
---
# <a name="compiler-error-c2414"></a>コンパイラ エラー C2414

オペランドの数が正しくありません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. オペコードに使われているオペランドの数が正しくありません。 アセンブリ言語のリファレンス マニュアルで、正しいオペランド数を調べてください。

1. 最近のプロセッサでは、オペランド数が異なる命令もサポートされます。 新しいプロセッサを使用するように、 [/arch (CPU の最小アーキテクチャ)](../../build/reference/arch-minimum-cpu-architecture.md) オプションを調整します。
