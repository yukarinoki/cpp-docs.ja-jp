---
title: '方法: ネイティブ型のハンドルを宣言する'
ms.custom: get-started-article
ms.date: 11/04/2016
f1_keywords:
- gcroot
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
ms.openlocfilehash: 11dbc196a89a224afe02312fbe4dff99d8467f4c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545037"
---
# <a name="how-to-declare-handles-in-native-types"></a>方法: ネイティブ型のハンドルを宣言する

ネイティブ型でハンドル型を宣言することはできません。 vcclr .h は、 C++ヒープから CLR オブジェクトを参照する `gcroot` タイプセーフなラッパーテンプレートを提供します。 このテンプレートを使用すると、仮想ハンドルをネイティブ型に埋め込んで、基になる型であるかのように扱うことができます。 ほとんどの場合、キャストなしで埋め込み型として `gcroot` オブジェクトを使用できます。 ただし、[それぞれに対し](../dotnet/for-each-in.md)て、では、`static_cast` を使用して、基になるマネージ参照を取得する必要があります。

`gcroot` テンプレートは、値クラス System:: Runtime:: InteropServices:: GCHandle の機能を使用して実装されます。このクラスは、ガベージコレクトされたヒープに "ハンドル" を提供します。 ハンドル自体はガベージコレクションされず、`gcroot` クラスのデストラクターによって使用されなくなったときに解放されることに注意してください (このデストラクターは手動で呼び出すことはできません)。 ネイティブヒープで `gcroot` オブジェクトをインスタンス化する場合は、そのリソースに対して delete を呼び出す必要があります。

ランタイムは、それが参照するハンドルと CLR オブジェクトの間の関連付けを維持します。 CLR オブジェクトがガベージコレクションヒープを使用して移動すると、ハンドルはオブジェクトの新しいアドレスを返します。 変数は、`gcroot` テンプレートに割り当てる前に固定する必要はありません。

## <a name="example"></a>例

このサンプルでは、ネイティブスタックに `gcroot` オブジェクトを作成する方法を示します。

```cpp
// mcpp_gcroot.cpp
// compile with: /clr
#include <vcclr.h>
using namespace System;

class CppClass {
public:
   gcroot<String^> str;   // can use str as if it were String^
   CppClass() {}
};

int main() {
   CppClass c;
   c.str = gcnew String("hello");
   Console::WriteLine( c.str );   // no cast required
}
```

```Output
hello
```

## <a name="example"></a>例

このサンプルでは、ネイティブヒープに `gcroot` オブジェクトを作成する方法を示します。

```cpp
// mcpp_gcroot_2.cpp
// compile with: /clr
// compile with: /clr
#include <vcclr.h>
using namespace System;

struct CppClass {
   gcroot<String ^> * str;
   CppClass() : str(new gcroot<String ^>) {}

   ~CppClass() { delete str; }

};

int main() {
   CppClass c;
   *c.str = gcnew String("hello");
   Console::WriteLine( *c.str );
}
```

```Output
hello
```

## <a name="example"></a>例

このサンプルでは、ボックス化された型で `gcroot` を使用して、ネイティブ型の値型 (参照型ではない) への参照を保持するために `gcroot` を使用する方法を示します。

```cpp
// mcpp_gcroot_3.cpp
// compile with: /clr
#include < vcclr.h >
using namespace System;

public value struct V {
   String^ str;
};

class Native {
public:
   gcroot< V^ > v_handle;
};

int main() {
   Native native;
   V v;
   native.v_handle = v;
   native.v_handle->str = "Hello";
   Console::WriteLine("String in V: {0}", native.v_handle->str);
}
```

```Output
String in V: Hello
```

## <a name="see-also"></a>参照

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
