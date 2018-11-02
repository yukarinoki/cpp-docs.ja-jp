---
title: コンパイラ エラー C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: c958eee234d25b008eb8cb03f40b45b8aaba81a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573460"
---
# <a name="compiler-error-c3483"></a>コンパイラ エラー C3483

'var' は既にラムダ キャプチャ リストに含まれています

ラムダ式のキャプチャ リストに同じ変数を複数回渡しました。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- キャプチャ リストから変数のすべての追加インスタンスを削除します。

## <a name="example"></a>例

次の例では、変数 `n` がラムダ式のキャプチャ リストに複数回出現するため、C3483 が生成されます。

```
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)