---
title: コンパイラ エラー C2414
ms.date: 11/04/2016
f1_keywords:
- C2414
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
ms.openlocfilehash: fbe627a57e5defc499a4bc5d463e0bf33494acba
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205661"
---
# <a name="compiler-error-c2414"></a>コンパイラ エラー C2414

オペランドの数が正しくありません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. オペコードに使われているオペランドの数が正しくありません。 アセンブリ言語のリファレンス マニュアルで、正しいオペランド数を調べてください。

1. 最近のプロセッサでは、オペランド数が異なる命令もサポートされます。 新しいプロセッサを使用するように、 [/arch (CPU の最小アーキテクチャ)](../../build/reference/arch-minimum-cpu-architecture.md)オプションを調整します。
