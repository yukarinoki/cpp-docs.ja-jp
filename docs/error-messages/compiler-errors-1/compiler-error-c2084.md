---
title: コンパイラエラー C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: f217e0b94e27c0f85879e80b3ae887cb4f76f486
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216363"
---
# <a name="compiler-error-c2084"></a>コンパイラエラー C2084

関数 '*function*' には既に本体があります

関数は既に定義されています。

Visual Studio 2002 より前の場合

- コンパイラは、同じ実際の型に解決される複数のテンプレートの特殊化を受け入れますが、追加の定義は使用できません。 コンパイラは、これらの複数の定義を検出するようになりました。

- **`__int32`** とは **`int`** 別々の型として扱われました。 コンパイラは、 **`__int32`** のシノニムとしてを処理するようになりました **`int`** 。 つまり、関数がとの両方でオーバーロードされている場合、コンパイラは複数の定義を検出し、 **`__int32`** **`int`** エラーが発生します。

## <a name="example"></a>例

次の例では、C2084 が生成されます。

```cpp
// C2084.cpp
void Func(int);
void Func(int) {}   // define function
void Func(int) {}   // C2084 second definition
```

このエラーを修正するには、重複する定義を削除します。

```cpp
// C2084b.cpp
// compile with: /c
void Func(int);
void Func(int) {}
```
