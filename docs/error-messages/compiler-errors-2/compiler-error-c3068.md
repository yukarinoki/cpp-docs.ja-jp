---
description: 詳細については、「コンパイラエラー C3068」を参照してください。
title: コンパイラ エラー C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: a73c525f017a3d571600e31d4c9ea875d0b25662
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281674"
---
# <a name="compiler-error-c3068"></a>コンパイラ エラー C3068

' function ': ' 生 ' 関数は、C++ 例外が発生した場合にアンワインドを必要とするオブジェクトを含むことはできません

関数に一時オブジェクトが作成され、C++ 例外処理 ([/ehsc](../../build/reference/eh-exception-handling-model.md)) が指定されているため、コンパイラは例外をスローした[生](../../cpp/naked-cpp.md)の関数でスタックアンワインドを実行できませんでした。

このエラーを解決するには、次のうち少なくとも1つを実行します。

- /EHsc. でコンパイルしない

- 関数をとしてマークしないで `naked` ください。

- 関数に一時オブジェクトを作成しないでください。

関数がスタックに一時オブジェクトを作成する場合、関数が例外をスローし、C++ 例外処理が有効になっていると、例外がスローされた場合、コンパイラはスタックをクリーンアップします。

例外がスローされると、コンパイラによって生成されたコードがプロローグおよびエピローグと呼ばれ、生の関数に存在しない場合は、関数に対してが実行されます。

## <a name="example"></a>例

次の例では、C3068 が生成されます。

```cpp
// C3068.cpp
// compile with: /EHsc
// processor: x86
class A {
public:
   A(){}
   ~A(){}
};

void b(A){}

__declspec(naked) void c() {
   b(A());   // C3068
};
```
