---
description: 詳細については、「コンパイラエラー C2720」を参照してください。
title: コンパイラエラー C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: 187142af02289374235725340a206f35b6a42493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155658"
---
# <a name="compiler-error-c2720"></a>コンパイラエラー C2720

> '*identifier*': '*指定* 子 ' ストレージクラスの指定子がメンバーに対して無効です。

ストレージ クラスは、宣言の外側のクラス メンバーに対して使用することはできません。 このエラーを解決するには、クラス宣言の外部にあるメンバーの定義から不要な [ストレージクラス](../../cpp/storage-classes-cpp.md) 指定子を削除します。

## <a name="example"></a>例

次の例では、C2720 を生成し、その修正方法を示しています。

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```
