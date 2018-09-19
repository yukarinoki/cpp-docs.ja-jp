---
title: コンパイラ エラー C3481 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3481
dev_langs:
- C++
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25634bb455a032ceff51d5e35f7a16e00e020326
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066896"
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