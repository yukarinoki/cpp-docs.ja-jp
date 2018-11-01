---
title: コンパイラ エラー C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: 32a04c2c49f8d9d974c3423756c4c9fc59a46495
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661982"
---
# <a name="compiler-error-c3481"></a>コンパイラ エラー C3481

'var': ラムダ キャプチャ変数が見つかりません

コンパイラはラムダ式のキャプチャ リストに渡された変数の定義を見つけられませんでした。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- ラムダ式のキャプチャ リストから変数を削除します。

## <a name="example"></a>例

次の例では、変数 `n` が定義されていないため、C3481 が生成されます。

```
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)