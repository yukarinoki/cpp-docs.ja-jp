---
title: コンパイラ エラー C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: 4790c9caafd28722f3631104cfe5cfc762cf6426
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406887"
---
# <a name="compiler-error-c3068"></a>コンパイラ エラー C3068

'function': 'naked' 関数が C++ 例外が発生した場合に、アンワインディングを必要とするオブジェクトを含めることはできません

コンパイラでのスタックがアンワインドを実行できなかった、 [naked](../../cpp/naked-cpp.md)は一時オブジェクトが作成された関数と C++ 例外処理では、例外をスローした関数 ([/EHsc](../../build/reference/eh-exception-handling-model.md)) が指定されました。

このエラーを解決するには、次の少なくとも 1 つの操作を行います。

- /EHsc でコンパイルされません。

- 関数としてマークを付けないでください`naked`します。

- 関数では、一時オブジェクトを作成できません。

関数は、例外をスローし、C++ 例外処理が有効になっている場合、関数はスタックで、一時オブジェクトを作成する場合、コンパイラは、例外がスローされた場合、スタックをクリーンアップはします。

関数の場合は、例外がスローされ、コンパイラで生成されたプロローグと呼ばれる、コードとエピローグは、naked 関数に存在しないが実行されます。

## <a name="example"></a>例

次の例では、C3068 が生成されます。

```
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