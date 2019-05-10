---
title: コンパイラ エラー C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: 0f7e049bc3f96e0a8e2b0a8cd306afeff52f7a5f
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447328"
---
# <a name="compiler-error-c2084"></a>コンパイラ エラー C2084

関数 '*関数*'、本文には既に

関数は既に定義されています。

Visual Studio の 2002 年の前に

- 追加の定義を使用可能にすることはならないが、コンパイラが同じの実際の型に解決される複数のテンプレートの特殊化を使用するは。 コンパイラは、今すぐこれら複数の定義を検出します。

- `__int32` `int`個別の型として扱われました。 コンパイラはこれで扱います`__int32`のシノニムとして`int`します。 これは、コンパイラでは、両方の関数がオーバー ロードの場合、複数の定義がによって検出されたことを意味`__int32`と`int`エラーとなります。

## <a name="example"></a>例

次の例では、C2084 が生成されます。

```cpp
// C2084.cpp
void Func(int);
void Func(int) {}   // define function
void Func(int) {}   // C2084 second definition
```

このエラーを修正するには、重複する定義を削除します。

```
// C2084b.cpp
// compile with: /c
void Func(int);
void Func(int) {}
```