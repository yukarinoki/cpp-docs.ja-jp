---
title: コンパイラ エラー C2946
ms.date: 11/04/2016
f1_keywords:
- C2946
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
ms.openlocfilehash: 0f61d047fcd070f3deea662cd3bd193f8e133659
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459086"
---
# <a name="compiler-error-c2946"></a>コンパイラ エラー C2946

明示的なインスタンス生成。'class' はテンプレート クラスの特殊化ではありません

非テンプレート クラスは明示的にインスタンス化できません。

## <a name="example"></a>例

次の例では C2946 が生成されます。

```
// C2946.cpp
class C {};
template C;  // C2946
int main() {}
```