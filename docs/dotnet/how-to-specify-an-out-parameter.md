---
description: '詳細については、「方法: out パラメーターを指定する」を参照してください。'
title: '方法: out パラメーターを指定する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: b43930557b4bdfd22bf902a6d9adf95eb8ba4d01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286339"
---
# <a name="how-to-specify-an-out-parameter"></a>方法: out パラメーターを指定する

このサンプルでは、関数パラメーターがパラメーターであることを指定する方法 `out` と、C# プログラムからその関数を呼び出す方法を示します。

`out`パラメーターは、C++ でを使用して指定し <xref:System.Runtime.InteropServices.OutAttribute> ます。

## <a name="example"></a>例

このサンプルの最初の部分では、C++ DLL を作成します。 パラメーターを持つ関数を含む型を定義 `out` します。

```cpp
// cpp_out_param.cpp
// compile with: /LD /clr
using namespace System;
public value struct TestStruct {
   static void Test([Runtime::InteropServices::Out] String^ %s) {
      s = "a string";
   }
};
```

このソースファイルは、前の例で作成した C++ コンポーネントを使用する C# クライアントです。

```csharp
// cpp_out_param_2.cs
// compile with: /reference:cpp_out_param.dll
using System;
class TestClass {
   public static void Main() {
      String t;
      TestStruct.Test(out t);
      System.Console.WriteLine(t);
   }
}
```

```Output
a string
```

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
