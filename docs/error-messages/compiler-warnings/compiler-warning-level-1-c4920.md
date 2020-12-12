---
description: '詳細情報: コンパイラの警告 (レベル 1) C4920'
title: コンパイラの警告 (レベル 1) C4920
ms.date: 11/04/2016
f1_keywords:
- C4920
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
ms.openlocfilehash: d9b0daab6ec08a39c928984fcbed720657a24de8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301959"
---
# <a name="compiler-warning-level-1-c4920"></a>コンパイラの警告 (レベル 1) C4920

enum enum member member=value は既に enum enum as member=value に示されています

#import に渡す .tlb に 2 つ以上の列挙型で定義された同じシンボルが含まれる場合、この警告は、後に続く同じシンボルが無視され、.tlh ファイル内でコメント アウトされることを示します。

次を含む .tlb を想定します。

```
library MyLib
{
    typedef enum {
        enumMember = 512
    } AProblem;

    typedef enum {
        enumMember = 1024
    } BProblem;
};
```

次の例では C4920 が生成されます。

```cpp
// C4920.cpp
// compile with: /W1
#import "t4920.tlb"   // C4920

int main() {
}
```
