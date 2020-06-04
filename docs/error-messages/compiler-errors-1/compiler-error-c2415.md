---
title: コンパイラ エラー C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: a0cdd528eca8ea267c62e6d44752d29ae16830c4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205622"
---
# <a name="compiler-error-c2415"></a>コンパイラ エラー C2415

オペランドの型が無効です。

このオペコードは、この型のオペランドを使いません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. オペコードに使われているオペランドの数が正しくありません。 アセンブリ言語のリファレンス マニュアルで、正しいオペランド数を調べてください。

1. 最近のプロセッサでは、別の型を使用する命令もサポートされます。 新しいプロセッサを使用するように、 [/arch (CPU の最小アーキテクチャ)](../../build/reference/arch-minimum-cpu-architecture.md)オプションを調整します。
