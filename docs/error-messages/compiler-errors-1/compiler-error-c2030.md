---
title: コンパイラ エラー C2030
ms.date: 11/04/2016
f1_keywords:
- C2030
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
ms.openlocfilehash: f9090e098d7f523bf7bc12b7fa4d9312f6ca5466
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212905"
---
# <a name="compiler-error-c2030"></a>コンパイラ エラー C2030

アクセシビリティが 'protected private' であるデストラクターは、'sealed' として宣言されたクラスのメンバーになることはできません

として宣言された Windows ランタイムクラスは、 **`sealed`** 保護されたプライベートデストラクターを持つことができません。 sealed 型では、パブリック仮想デストラクターとプライベート非仮想デストラクターだけが許可されています。 詳細については、「[Ref クラスと構造体](../../cppcx/ref-classes-and-structs-c-cx.md)」を参照してください。

このエラーを解決するには、デストラクターのアクセシビリティを変更します。
