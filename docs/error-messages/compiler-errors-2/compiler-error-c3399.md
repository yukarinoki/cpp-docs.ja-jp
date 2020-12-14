---
description: 詳細については、「コンパイラエラー C3399」を参照してください。
title: コンパイラ エラー C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: a950857e88c5cfcad50ac2efb064af4d7a5c0cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316428"
---
# <a name="compiler-error-c3399"></a>コンパイラ エラー C3399

'type' : ジェネリック パラメーターのインスタンスを作成するときに、引数を指定することはできません

`gcnew()` 制約を指定する場合は、制約型にパラメーターなしのコンストラクターがあることを指定します。 したがって、この型のインスタンスを作成してパラメーターを渡そうとすると、エラーになります。

詳細については、「 [ジェネリック型パラメーターの制約 (C++/cli)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3399 が生成されます。

```cpp
// C3399.cpp
// compile with: /clr /c
generic <class T>
where T : gcnew()
void f() {
   T t = gcnew T(1);   // C3399
   T t2 = gcnew T();   // OK
}
```
