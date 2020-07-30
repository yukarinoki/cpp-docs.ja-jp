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
ms.openlocfilehash: 1aca21402122a0c8641a7e57ace2a3477ff96f01
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221342"
---
# <a name="how-to-declare-handles-in-native-types"></a>方法: ネイティブ型のハンドルを宣言する

ネイティブ型でハンドル型を宣言することはできません。 vcclr .h は、 `gcroot` C++ ヒープから CLR オブジェクトを参照するタイプセーフなラッパーテンプレートを提供します。 このテンプレートを使用すると、仮想ハンドルをネイティブ型に埋め込んで、基になる型であるかのように扱うことができます。 ほとんどの場合、 `gcroot` キャストを行わずにオブジェクトを埋め込み型として使用できます。 ただし、[それぞれに対し](../dotnet/for-each-in.md)て、では、基に **`static_cast`** なるマネージ参照を取得するためにを使用する必要があります。

この `gcroot` テンプレートは、値クラス System:: Runtime:: InteropServices:: GCHandle の機能を使用して実装されます。これにより、ガベージコレクトされたヒープに "ハンドル" が提供されます。 ハンドル自体はガベージコレクションではなく、クラスのデストラクターによって使用されなくなったときに解放されることに注意して `gcroot` ください (このデストラクターは手動で呼び出すことはできません)。 ネイティブヒープ上のオブジェクトをインスタンス化する場合は `gcroot` 、そのリソースに対して delete を呼び出す必要があります。

ランタイムは、それが参照するハンドルと CLR オブジェクトの間の関連付けを維持します。 CLR オブジェクトがガベージコレクションヒープを使用して移動すると、ハンドルはオブジェクトの新しいアドレスを返します。 変数は、テンプレートに割り当てる前に固定する必要はありません `gcroot` 。

## <a name="example"></a>例

このサンプル `gcroot` では、ネイティブスタックにオブジェクトを作成する方法を示します。

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

このサンプル `gcroot` では、ネイティブヒープ上にオブジェクトを作成する方法を示します。

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

このサンプルでは、を使用して、ボックス化され `gcroot` た型でを使用して、ネイティブ型の値型 (参照型ではない) への参照を保持する方法を示し `gcroot` ます。

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

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
