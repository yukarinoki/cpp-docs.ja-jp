---
title: コンパイラ エラー C2439
ms.date: 11/04/2016
f1_keywords:
- C2439
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
ms.openlocfilehash: f71112d3f37f3e4d1a4f41bade95726d7aa0a0bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644360"
---
# <a name="compiler-error-c2439"></a>コンパイラ エラー C2439

'identifier': メンバーを初期化できませんでした

クラス、構造体または共用体メンバーを初期化することはできません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 間接基底クラスまたは構造体を初期化しようとしています。

1. クラスまたは構造体の継承されたメンバーを初期化しようとしています。 継承されたメンバーは、クラスまたは構造体のコンス トラクターで初期化する必要があります。