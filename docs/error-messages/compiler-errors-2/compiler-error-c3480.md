---
description: 詳細については、「コンパイラエラー C3480」を参照してください。
title: コンパイラ エラー C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: dbeed462410d36b466e807d576549c1b73ee4917
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113416"
---
# <a name="compiler-error-c3480"></a>コンパイラ エラー C3480

'var': ラムダ キャプチャ変数は、外側の関数スコープの変数である必要があります

ラムダ キャプチャ変数が外側の関数スコープの変数ではありません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- ラムダ式のキャプチャ リストから変数を削除します。

## <a name="examples"></a>例

変数 `global` が外側の関数スコープではないため、次の例では C3480 が生成されます。

```cpp
// C3480a.cpp

int global = 0;
int main()
{
   [&global] { global = 5; }(); // C3480
}
```

次の例では、ラムダ式のキャプチャ リストから変数 `global` を削除することによって C3480 を解決しています。

```cpp
// C3480b.cpp

int global = 0;
int main()
{
   [] { global = 5; }();
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
