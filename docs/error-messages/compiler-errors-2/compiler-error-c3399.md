---
title: コンパイラ エラー C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: d05a861a2baedb86482503b6860098f12c41bd78
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776458"
---
# <a name="compiler-error-c3399"></a>コンパイラ エラー C3399

'type' : ジェネリック パラメーターのインスタンスを作成するときに、引数を指定することはできません

`gcnew()` 制約を指定する場合は、制約型にパラメーターなしのコンストラクターがあることを指定します。 したがって、この型のインスタンスを作成してパラメーターを渡そうとすると、エラーになります。

参照してください[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)詳細についてはします。

## <a name="example"></a>例

次の例では C3399 が生成されます。

```
// C3399.cpp
// compile with: /clr /c
generic <class T>
where T : gcnew()
void f() {
   T t = gcnew T(1);   // C3399
   T t2 = gcnew T();   // OK
}
```