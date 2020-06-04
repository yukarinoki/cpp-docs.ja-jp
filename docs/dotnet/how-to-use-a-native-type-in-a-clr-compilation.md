---
title: 方法:-clr コンパイルでネイティブ型を使用する
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
ms.openlocfilehash: b506c3d825c4c26236a4ac3fc9682067a011315a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545205"
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>方法: /clr コンパイルでネイティブ型を使用する

**/Clr**コンパイルでネイティブ型を定義し、アセンブリ内からそのネイティブ型を使用することは有効です。 ただし、ネイティブ型は参照されたメタデータからは使用できません。

各アセンブリには、使用するすべてのネイティブ型の定義が含まれている必要があります。

詳細については、「[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

## <a name="example"></a>例

このサンプルでは、ネイティブ型を定義して使用するコンポーネントを作成します。

```cpp
// use_native_type_in_clr.cpp
// compile with: /clr /LD
public struct NativeClass {
   static int Test() { return 98; }
};

public ref struct ManagedClass {
   static int i = NativeClass::Test();
   void Test() {
      System::Console::WriteLine(i);
   }
};
```

## <a name="example"></a>例

このサンプルでは、コンポーネントを使用するクライアントを定義します。 コンパイル単位で定義されている場合を除き、ネイティブ型にアクセスする際のエラーであることに注意してください。

```cpp
// use_native_type_in_clr_2.cpp
// compile with: /clr
#using "use_native_type_in_clr.dll"
// Uncomment the following 3 lines to resolve.
// public struct NativeClass {
//    static int Test() { return 98; }
// };

int main() {
   ManagedClass x;
   x.Test();

   System::Console::WriteLine(NativeClass::Test());   // C2653
}
```

## <a name="see-also"></a>参照

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
