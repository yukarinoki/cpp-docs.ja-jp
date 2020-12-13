---
description: 詳細については、「コンパイラエラー C2030」を参照してください。
title: コンパイラ エラー C2030
ms.date: 11/04/2016
f1_keywords:
- C2030
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
ms.openlocfilehash: b29996051a87f050e61c94b4134d046f52be6f09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175483"
---
# <a name="compiler-error-c2030"></a>コンパイラ エラー C2030

アクセシビリティが 'protected private' であるデストラクターは、'sealed' として宣言されたクラスのメンバーになることはできません

として宣言された Windows ランタイムクラスは、 **`sealed`** 保護されたプライベートデストラクターを持つことができません。 sealed 型では、パブリック仮想デストラクターとプライベート非仮想デストラクターだけが許可されています。 詳細については、「[Ref クラスと構造体](../../cppcx/ref-classes-and-structs-c-cx.md)」を参照してください。

このエラーを解決するには、デストラクターのアクセシビリティを変更します。
