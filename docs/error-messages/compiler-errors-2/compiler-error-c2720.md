---
title: コンパイラエラー C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: 24f4329ee631eafc7c2670d9ebf28609c22e7592
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202136"
---
# <a name="compiler-error-c2720"></a>コンパイラエラー C2720

> '*identifier*': '*指定*子 ' ストレージクラスの指定子がメンバーに対して無効です。

ストレージ クラスは、宣言の外側のクラス メンバーに対して使用することはできません。 このエラーを解決するには、クラス宣言の外部にあるメンバーの定義から不要な[ストレージクラス](../../cpp/storage-classes-cpp.md)指定子を削除します。

## <a name="example"></a>例

次の例では、C2720 を生成し、その修正方法を示しています。

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```
