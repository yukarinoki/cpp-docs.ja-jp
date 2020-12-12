---
description: 詳細については、「コンパイラエラー C3519」を参照してください。
title: コンパイラ エラー C3519
ms.date: 11/04/2016
f1_keywords:
- C3519
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
ms.openlocfilehash: f8eb90620894627beab450275c6725d665d837e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113087"
---
# <a name="compiler-error-c3519"></a>コンパイラ エラー C3519

' invalid_param ': embedded_idl 属性に対する無効なパラメーターです

パラメーターが #import の属性に渡されました `embedded_idl` が、コンパイラはパラメーターを認識し[](../../preprocessor/hash-import-directive-cpp.md)ませんでした。

に使用できるパラメーター `embedded_idl` は、とだけ `emitidl` です `no_emitidl` 。

次の例では、C3519 が生成されます。

```cpp
// C3519.cpp
// compile with: /LD
[module(name="MyLib2")];
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")
// C3519
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")
// OK
```
