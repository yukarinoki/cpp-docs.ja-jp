---
title: コンパイラ エラー C3394
ms.date: 11/04/2016
f1_keywords:
- C3394
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
ms.openlocfilehash: 826084d375c69ca289a858a29a12ae16874c1fbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328745"
---
# <a name="compiler-error-c3394"></a>コンパイラ エラー C3394

制約句の構文エラー: 'identifier' が見つかりましたが、型を指定しなければなりません

制約の形式が間違っています。  詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)します。

## <a name="example"></a>例

次の例では C3394 が生成されます。

```
// C3394.cpp
// compile with: /clr /c
ref class MyClass {};
ref class R {
   generic<typename T>
   where T : static   // C3394
   // try the following line instead
   // where T : MyClass
   void f() {}
};
```