---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: bedf17072c06ec893b9cbd83b46403dcd3bc1560
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186686"
---
# <a name="noinline"></a>noinline

**Microsoft 固有の仕様**

**`__declspec(noinline)`** 特定のメンバー関数 (クラス内の関数) をインラインにしないようにコンパイラに指示します。

コードのパフォーマンスにとって大きな意味がなく、重要でなければ、関数をインラインにしない方がよい場合があります。 つまり、関数が小さく、頻繁に呼び出されないと考えられる場合 (エラー条件を処理する関数など)。

関数がとしてマークされている場合は、 **`noinline`** 呼び出し元の関数が小さくなり、それ自体がコンパイラのインライン展開の候補になることに注意してください。

```cpp
class X {
   __declspec(noinline) int mbrfunc() {
      return 0;
   }   // will not inline
};
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[inline、__inline、\__forceinline](inline-functions-cpp.md)
