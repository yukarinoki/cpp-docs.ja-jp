---
title: コンパイラ エラー C3399 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3399
dev_langs:
- C++
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3cae3c038e4af4a58756ad7387472c081bf4c3d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016794"
---
# <a name="compiler-error-c3399"></a>コンパイラ エラー C3399

'type' : ジェネリック パラメーターのインスタンスを作成するときに、引数を指定することはできません

`gcnew()` 制約を指定する場合は、制約型にパラメーターなしのコンストラクターがあることを指定します。 したがって、この型のインスタンスを作成してパラメーターを渡そうとすると、エラーになります。

参照してください[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)詳細についてはします。

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