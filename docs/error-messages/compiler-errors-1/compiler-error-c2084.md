---
title: コンパイラ エラー C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: 9aaf3a88e63234dfb842e4b48afd6e55595e96ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391921"
---
# <a name="compiler-error-c2084"></a>コンパイラ エラー C2084

関数 '*関数*'、本文には既に

関数は既に定義されています。

バージョンの Visual Studio の 2002 年の前に Visual C

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