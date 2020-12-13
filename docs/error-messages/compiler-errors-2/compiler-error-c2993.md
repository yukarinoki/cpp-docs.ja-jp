---
description: 詳細については、「コンパイラエラー C2993」を参照してください。
title: コンパイラ エラー C2993
ms.date: 11/04/2016
f1_keywords:
- C2993
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
ms.openlocfilehash: 2c43d4f3e54378d419f1945b1f6b38e9ee4d9758
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136423"
---
# <a name="compiler-error-c2993"></a>コンパイラ エラー C2993

' identifier ': 非型テンプレートパラメーター ' parameter ' の型が正しくありません。

構造体または共用体の引数を持つテンプレートを宣言することはできません。 ポインターを使用して、構造体と共用体をテンプレートパラメーターとして渡します。

次の例では、C2993 が生成されます。

```cpp
// C2993.cpp
// compile with: /c
// C2993 expected
struct MyStruct {
   int a;char b;
};

template <class T, struct MyStruct S>   // C2993

// try the following line instead
// template <class T, struct MyStruct * S>
class CMyClass {};
```

このエラーは、Visual Studio .NET 2003 で実行されたコンパイラ準拠作業の結果としても生成されます。浮動小数点の非型テンプレートパラメーターは使用できなくなりました。 C++ 標準では、浮動小数点型以外のテンプレートパラメーターは許可されません。

関数テンプレートの場合は、関数の引数を使用して、浮動小数点型以外のテンプレートパラメーターを渡します (このコードは、Visual Studio .NET 2003 および Visual Studio .NET バージョンの Visual C++ で有効になります)。 クラステンプレートの場合は、簡単な回避策はありません。

```cpp
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```
