---
title: コンパイラ エラー C2030
ms.date: 11/04/2016
f1_keywords:
- C2030
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
ms.openlocfilehash: 217f97d205e1da075277b8b0bc22ff3baab13482
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602177"
---
# <a name="compiler-error-c2030"></a>コンパイラ エラー C2030

アクセシビリティが 'protected private' であるデストラクターは、'sealed' として宣言されたクラスのメンバーになることはできません

`sealed` として宣言された Windows ランタイム クラスは、protected private デストラクターを持つことはできません。 sealed 型では、パブリック仮想デストラクターとプライベート非仮想デストラクターだけが許可されています。 詳細については、次を参照してください。 [Ref クラスと構造体](../../cppcx/ref-classes-and-structs-c-cx.md)します。

このエラーを解決するには、デストラクターのアクセシビリティを変更します。