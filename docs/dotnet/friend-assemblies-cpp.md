---
title: フレンド アセンブリ (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
ms.openlocfilehash: a42caaf07f6ec0c71f63d6a0df8a79fff6f737e6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221446"
---
# <a name="friend-assemblies-c"></a>フレンド アセンブリ (C++)

適用可能なランタイムの場合、*フレンドアセンブリ*言語機能を使用すると、アセンブリコンポーネント内の名前空間スコープまたはグローバルスコープにある型が、1つ以上のクライアントアセンブリまたは netmodule にアクセスできるようになります。

## <a name="all-runtimes"></a>すべてのランタイム

**解説**

(この言語機能は、すべてのランタイムでサポートされているわけではありません)。

## <a name="windows-runtime"></a>Windows ランタイム

**解説**

(Windows ランタイムでは、この言語機能はサポートされていません。)

### <a name="requirements"></a>必要条件

コンパイラ オプション: **/ZW**

## <a name="common-language-runtime"></a>共通言語ランタイム

**解説**

#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>アセンブリコンポーネント内の名前空間スコープまたはグローバルスコープで型をクライアントアセンブリまたは .netmodule にアクセスできるようにするには

1. コンポーネントでアセンブリの属性を指定し、コンポーネントの名前 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 空間スコープまたはグローバルスコープの型にアクセスするクライアントアセンブリまたは .netmodule の名前を渡します。  追加の属性を指定することによって、複数のクライアントアセンブリまたは. netmodule を指定できます。

1. クライアントアセンブリまたは .netmodule で、を使用してコンポーネントアセンブリを参照する場合は、 `#using` 属性を渡し **`as_friend`** ます。  **`as_friend`** を指定しないアセンブリの属性を指定すると `InternalsVisibleToAttribute` 、コンポーネントの名前空間スコープまたはグローバルスコープで型にアクセスしようとすると、ランタイム例外がスローされます。

属性を含むアセンブリに厳密な名前がなくて <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> も、属性を使用するクライアントアセンブリでは、ビルドエラーが発生 **`as_friend`** します。

名前空間スコープとグローバルスコープの型はクライアントアセンブリまたは .netmodule で認識されますが、メンバーアクセシビリティは引き続き有効です。  たとえば、プライベートメンバーにアクセスすることはできません。

アセンブリ内のすべての型へのアクセスは、明示的に許可する必要があります。  たとえば、アセンブリ c がアセンブリ B を参照し、アセンブリ B がアセンブリ A 内のすべての型にアクセスできる場合、アセンブリ C はアセンブリ A 内のすべての型にアクセスできません。

署名方法 (Microsoft C++ コンパイラを使用してビルドされるアセンブリ) に署名する方法については、「厳密な名前のアセンブリ[(アセンブリ署名) (C++/cli](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md))」を参照してください。

Friend アセンブリ機能を使用する代わりに、を使用して <xref:System.Security.Permissions.StrongNameIdentityPermission> 個々の型へのアクセスを制限することもできます。

### <a name="requirements"></a>必要条件

コンパイラ オプション: **/clr**

### <a name="examples"></a>例

コンポーネントの型にアクセスできるクライアントアセンブリを指定するコンポーネントを定義するコード例を次に示します。

```cpp
// friend_assemblies.cpp
// compile by using: /clr /LD
using namespace System::Runtime::CompilerServices;
using namespace System;
// an assembly attribute, not bound to a type
[assembly:InternalsVisibleTo("friend_assemblies_2")];

ref class Class1 {
public:
   void Test_Public() {
      Console::WriteLine("Class1::Test_Public");
   }
};
```

次のコード例では、コンポーネント内のプライベート型にアクセスします。

```cpp
// friend_assemblies_2.cpp
// compile by using: /clr
#using "friend_assemblies.dll" as_friend

int main() {
   Class1 ^ a = gcnew Class1;
   a->Test_Public();
}
```

```Output
Class1::Test_Public
```

次のコード例では、コンポーネントを定義していますが、コンポーネント内の型にアクセスできるクライアントアセンブリを指定していません。

コンポーネントが **/opt: noref**を使用してリンクされていることに注意してください。 これにより、属性が存在する場合には不要な、コンポーネントのメタデータでプライベート型が生成され `InternalsVisibleTo` ます。 詳細については、「[/OPT (最適化)](../build/reference/opt-optimizations.md)」を参照してください。

```cpp
// friend_assemblies_3.cpp
// compile by using: /clr /LD /link /opt:noref
using namespace System;

ref class Class1 {
public:
   void Test_Public() {
      Console::WriteLine("Class1::Test_Public");
   }
};
```

次のコード例では、プライベート型へのアクセスが許可されていないコンポーネントのプライベート型にアクセスしようとするクライアントを定義しています。 ランタイムの動作により、例外をキャッチする場合は、ヘルパー関数でプライベート型にアクセスしようとする必要があります。

```cpp
// friend_assemblies_4.cpp
// compile by using: /clr
#using "friend_assemblies_3.dll" as_friend
using namespace System;

void Test() {
   Class1 ^ a = gcnew Class1;
}

int main() {
   // to catch this kind of exception, use a helper function
   try {
      Test();
   }
   catch(MethodAccessException ^ e) {
      Console::WriteLine("caught an exception");
   }
}
```

```Output
caught an exception
```

次のコード例では、コンポーネント内の型にアクセスできるクライアントアセンブリを指定する厳密な名前のコンポーネントを作成する方法を示します。

```cpp
// friend_assemblies_5.cpp
// compile by using: /clr /LD /link /keyfile:friend_assemblies.snk
using namespace System::Runtime::CompilerServices;
using namespace System;
// an assembly attribute, not bound to a type

[assembly:InternalsVisibleTo("friend_assemblies_6, PublicKey=00240000048000009400000006020000002400005253413100040000010001000bf45d77fd991f3bff0ef51af48a12d35699e04616f27ba561195a69ebd3449c345389dc9603d65be8cd1987bc7ea48bdda35ac7d57d3d82c666b7fc1a5b79836d139ef0ac8c4e715434211660f481612771a9f7059b9b742c3d8af00e01716ed4b872e6f1be0e94863eb5745224f0deaba5b137624d7049b6f2d87fba639fc5")];

private ref class Class1 {
public:
   void Test_Public() {
      Console::WriteLine("Class1::Test_Public");
   }
};
```

コンポーネントで公開キーを指定する必要があることに注意してください。 キーペアを作成して公開キーを取得するには、コマンドプロンプトで次のコマンドを順番に実行することをお勧めします。

**sn-d friend_assemblies .snk**

**sn-k friend_assemblies .snk**

**sn-i friend_assemblies .snk friend_assemblies .snk**

**sn-pc friend_assemblies .snk**

**sn -tp key.publickey**

次のコード例では、厳密な名前のコンポーネントのプライベート型にアクセスします。

```cpp
// friend_assemblies_6.cpp
// compile by using: /clr /link /keyfile:friend_assemblies.snk
#using "friend_assemblies_5.dll" as_friend

int main() {
   Class1 ^ a = gcnew Class1;
   a->Test_Public();
}
```

```Output
Class1::Test_Public
```

## <a name="see-also"></a>関連項目

[ランタイム プラットフォームのコンポーネントの拡張機能](../extensions/component-extensions-for-runtime-platforms.md)
