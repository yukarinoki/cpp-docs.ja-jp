---
title: '方法: out パラメーターを指定する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: 4bd6ad1d3009adcc124bdeb90d9d67de07112de2
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "79545445"
---
# <a name="how-to-specify-an-out-parameter"></a>方法: out パラメーターを指定する

このサンプルでは、関数パラメーターが `out` パラメーターであることを指定する方法と、その関数をC#プログラムから呼び出す方法を示します。

でC++は、<xref:System.Runtime.InteropServices.OutAttribute> を使用して `out` パラメーターを指定しています。

## <a name="example"></a>例

このサンプルの最初の部分ではC++ 、DLL を作成します。 `out` パラメーターを持つ関数を含む型を定義します。

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

このソースファイルは、 C#前の例でC++作成したコンポーネントを使用するクライアントです。

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

## <a name="see-also"></a>参照

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
