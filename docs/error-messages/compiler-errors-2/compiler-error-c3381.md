---
title: コンパイラ エラー C3381
description: Microsoft C++ コンパイラエラー C3381、その原因、およびその解決方法について説明します。
ms.date: 09/28/2020
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: 48a6c81f9506c532333b5353b8b194d17c91043f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510150"
---
# <a name="compiler-error-c3381"></a>コンパイラ エラー C3381

> '*identifier*': アセンブリアクセス指定子は、/clr オプションでコンパイルされたコードでのみ使用できます

型がアクセス指定子を使用して宣言または定義されました。これは、を使用してコンパイルされたコードでのみ許可され **`/clr`** ます。

## <a name="remarks"></a>注釈

このエラーは、、、またはキーワードが間違っていたか、または **`public`** **`protected`** 内の **`private`** アクセス指定子の後にコロン () がないことが原因で発生する可能性があり **`:`** **`class`** **`struct`** ます。

C++/CLI では、ネイティブ型はアセンブリの外部で参照できますが、コンパイル時にはネイティブ型に対してのみアセンブリアクセスを指定でき **`/clr`** ます。 詳細については、「[型の可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)」と「 [ `/clr` (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3381 が生成されます。 この問題を解決するには、最初に定義から指定子を削除するか、 **`public`** `class A` オプションを使用してコンパイルし **`/clr`** ます。 次に、の後にコロンを追加し **`private`** て、へのアクセスを指定し `class B {} b;` ます。 これは、入れ子になったクラスは、宣言の一部としてアセンブリアクセス指定子を持つことができないためです。

```cpp
// C3381.cpp
// compile with: /c
public class A {   // C3381
    private class B {} b;   // C3381
};
```
