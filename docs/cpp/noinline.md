---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: 3a8dce21aa707a1a52c647c9efee5ab806511ca8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454562"
---
# <a name="noinline"></a>noinline

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

**__declspec(noinline)** 特定のメンバー関数 (クラス内の関数) をインラインにしないようにコンパイラに指示します。

コードのパフォーマンスにとって大きな意味がなく、重要でなければ、関数をインラインにしない方がよい場合があります。 つまり、関数が小さく、頻繁に呼び出されないと考えられる場合 (エラー条件を処理する関数など)。

注意する関数がマークされている場合**noinline**、呼び出し元の関数が小さくなり、自体の対象となるコンパイラのインライン化します。

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

