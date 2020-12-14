---
description: 詳細については、「コンパイラエラー C2439」を参照してください。
title: コンパイラ エラー C2439
ms.date: 11/04/2016
f1_keywords:
- C2439
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
ms.openlocfilehash: 6493fb634581646c20a8d856658fe728ae27364c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189809"
---
# <a name="compiler-error-c2439"></a>コンパイラ エラー C2439

' identifier ': メンバーを初期化できませんでした

クラス、構造体、または共用体のメンバーを初期化できません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 間接的な基底クラスまたは構造体を初期化しようとしています。

1. クラスまたは構造体の継承されたメンバーを初期化しようとしています。 継承されたメンバーは、クラスまたは構造体のコンストラクターによって初期化される必要があります。
