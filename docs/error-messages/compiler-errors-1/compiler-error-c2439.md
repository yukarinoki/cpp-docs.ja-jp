---
title: コンパイラ エラー C2439
ms.date: 11/04/2016
f1_keywords:
- C2439
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
ms.openlocfilehash: 99f3644869f6c5395684643f0e7802f3a01baa62
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205362"
---
# <a name="compiler-error-c2439"></a>コンパイラ エラー C2439

' identifier ': メンバーを初期化できませんでした

クラス、構造体、または共用体のメンバーを初期化できません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 間接的な基底クラスまたは構造体を初期化しようとしています。

1. クラスまたは構造体の継承されたメンバーを初期化しようとしています。 継承されたメンバーは、クラスまたは構造体のコンストラクターによって初期化される必要があります。
