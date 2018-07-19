---
title: フレンド アセンブリ (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cc39fa66a73f16f800f0c7f0e4bbc49730d4b9c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33113760"
---
# <a name="friend-assemblies-c"></a>フレンド アセンブリ (C++)
適用可能なランタイムは、の*フレンド アセンブリ*言語機能を使用する名前空間のスコープまたは 1 つまたは複数のクライアント アセンブリまたは .netmodule にアクセスできるアセンブリ コンポーネント内のグローバル スコープにある型です。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 **解説**  
  
 (この言語機能はサポートされていませんすべてのランタイムにします。)  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 **解説**  
  
 (この言語機能はサポートされていません、Windows ランタイムでします。)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **解説**  
  
#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>名前空間のスコープまたはグローバル スコープの種類をクライアント アセンブリまたは .netmodule にアクセスできるアセンブリ コンポーネント ように  
  
1.  コンポーネントでは、アセンブリの属性を指定<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>、クライアント アセンブリまたは名前空間のスコープまたはコンポーネント内のグローバル スコープの種類にアクセスする .netmodule の名前を渡します。  追加の属性を指定することによって、複数のクライアント アセンブリまたは .netmodule を指定できます。  
  
2.  クライアント アセンブリまたは .netmodule を使用して、コンポーネント アセンブリを参照するときに`#using`、渡す、`as_friend`属性。  指定した場合、`as_friend`属性で指定されていないアセンブリを`InternalsVisibleToAttribute`、名前空間のスコープまたはコンポーネント内のグローバル スコープでの種類にアクセスしようとする場合、ランタイム例外がスローされます。  
  
 アセンブリを格納している場合、ビルド エラーが発生、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>厳密な名前が使用するクライアント アセンブリは、属性がない、`as_friend`属性はします。  
  
 名前空間のスコープとグローバル スコープでの型がわかってクライアント アセンブリまたは .netmodule することができます、メンバーのアクセシビリティは引き続き有効です。  たとえば、プライベート メンバーにアクセスすることはできません。  
  
 アセンブリ内のすべての型へのアクセスを明示的に付与する必要があります。  たとえば、アセンブリ C がすべての型へのアクセス アセンブリ A アセンブリ C が B のアセンブリを参照し、アセンブリ B はアセンブリ A のすべての型へのアクセスを持つ場合  
  
 署名する方法について: に厳密な名前を付ける方法: Visual C コンパイラを使用して組み込まれているアセンブリを参照してください[厳密な名前のアセンブリ (アセンブリ署名) (C + + CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)です。  
  
 フレンド アセンブリの機能を使用する代わりに、使用することができます<xref:System.Security.Permissions.StrongNameIdentityPermission>個々 の型にアクセスを制限します。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 次のコード例では、コンポーネントの種類にアクセスできるクライアント アセンブリを指定するコンポーネントを定義します。  
  
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
  
 次のコード例では、コンポーネントにプライベート型にアクセスします。  
  
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
  
 次のコード例では、コンポーネントを定義していますが、コンポーネントの種類にアクセスがあるクライアント アセンブリが指定されていません。  
  
 使用して、コンポーネントがリンクされていることを確認 **/opt: noref**です。 これによりは不要な場合に、コンポーネントのメタデータでプライベート型が出力されること、`InternalsVisibleTo`属性が存在します。 詳細については、次を参照してください。 [/OPT (最適化)](../build/reference/opt-optimizations.md)です。  
  
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
  
 次のコード例では、許可しない、プライベート型にするコンポーネントにプライベート型にアクセスしようとするクライアントを定義します。 ランタイムの動作により、例外をキャッチする必要がありますしようとするヘルパー関数でプライベート型にアクセスします。  
  
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
  
 次のコード例は、厳密な名前を指定するコンポーネントをコンポーネントの種類へのアクセスを持つクライアント アセンブリを作成する方法を示しています。  
  
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
  
 コンポーネントが、公開キーを指定する必要がありますに注意してください。 次のコマンドをキーのペアを作成および公開キーを取得するコマンド プロンプトで、順番に実行することをお勧めします。  
  
 **sn-d friend_assemblies.snk**  
  
 **sn-k friend_assemblies.snk**  
  
 **sn-i friend_assemblies.snk friend_assemblies.snk**  
  
 **sn pc friend_assemblies.snk key.publickey**  
  
 **sn-tp key.publickey**  
  
 次のコード例では、厳密な名前のコンポーネントにプライベート型にアクセスします。  
  
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
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)