---
title: コンパイラ エラー C2947
ms.date: 11/04/2016
f1_keywords:
- C2947
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
ms.openlocfilehash: 3738c257192134eedb8554b0d875023862441416
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227217"
---
# <a name="compiler-error-c2947"></a>コンパイラ エラー C2947

指定してください ' >' をコンストラクトを終了するには、'構文' が見つかりません

ジェネリックまたはテンプレートの引数リストが正しく終了がない可能性があります。

構文エラー C2947 を生成こともできます。

次の例では、C2947 が生成されます。

```
// C2947.cpp
// compile with: /c
template <typename T>=   // C2947
// try the following line instead
// template <typename T>
struct A {};
```