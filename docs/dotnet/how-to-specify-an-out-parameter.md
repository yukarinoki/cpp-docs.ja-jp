---
title: '方法: 出力を指定するパラメーター |Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3af9c1d10206e89b0ad8462bd95fdf3b6062d713
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419504"
---
# <a name="how-to-specify-an-out-parameter"></a>方法: out パラメーターを指定する

このサンプルでは、関数のパラメーターを out パラメーターに指定する方法と、c# プログラムからその関数を呼び出す方法を示します。

Visual C で out パラメーターが指定された<xref:System.Runtime.InteropServices.OutAttribute>します。

## <a name="example"></a>例

このサンプルの最初の部分では、out パラメーターを持つ関数を含む型での Visual C DLL です。

```
// cpp_out_param.cpp
// compile with: /LD /clr:safe
using namespace System;
public value struct TestStruct {
   static void Test([Runtime::InteropServices::Out] String^ %s) {
      s = "a string";
   }
};
```

## <a name="example"></a>例

これは、前の例で作成した Visual C コンポーネントを使用する c# クライアントです。

```
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