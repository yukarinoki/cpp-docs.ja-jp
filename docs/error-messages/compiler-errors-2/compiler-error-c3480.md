---
title: コンパイラ エラー C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: 2ebcce496fd06c30420558d80cc0a0c9318d4376
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173425"
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