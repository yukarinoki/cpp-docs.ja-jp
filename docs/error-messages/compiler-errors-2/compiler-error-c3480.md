---
title: コンパイラ エラー C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: b856f607d764ac0a42781a80787663d965748317
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626903"
---
# <a name="compiler-error-c3480"></a>コンパイラ エラー C3480

'var': ラムダ キャプチャ変数は、外側の関数スコープの変数である必要があります

ラムダ キャプチャ変数が外側の関数スコープの変数ではありません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- ラムダ式のキャプチャ リストから変数を削除します。

## <a name="example"></a>例

変数 `global` が外側の関数スコープではないため、次の例では C3480 が生成されます。

```
// C3480a.cpp

int global = 0;
int main()
{
   [&global] { global = 5; }(); // C3480
}
```

## <a name="example"></a>例

次の例では、ラムダ式のキャプチャ リストから変数 `global` を削除することによって C3480 を解決しています。

```
// C3480b.cpp

int global = 0;
int main()
{
   [] { global = 5; }();
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)