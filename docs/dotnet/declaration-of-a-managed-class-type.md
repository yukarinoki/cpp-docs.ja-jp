---
title: マネージ クラス型の宣言 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- classes [C++], managed
- class keyword [C++], CLR
- __value keyword
- value types, declaring
- value keyword [C++]
- managed classes
- interface class keyword
- ref keyword [C++]
ms.assetid: 16de9c94-91d7-492f-8ac7-f0729cc627e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5c821424d8b2669c78befa604bf2669399c89f75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112642"
---
# <a name="declaration-of-a-managed-class-type"></a>マネージ クラス型の宣言
Visual c、c++ マネージ拡張から変更、参照クラス型を宣言する方法。  
  
 マネージ拡張では、参照クラス型の前には `__gc` キーワードが付けられました。 新しい構文では、`__gc` キーワードは 2 つのスペース区切りキーワード、`ref class` または `ref struct` のいずれかに置き換わります。 `struct` または `class` のいずれが選択されるかは、型の本体の最初のラベルのない部分で宣言されるメンバーの既定のアクセス レベルが、パブリック (`struct` の場合) かプライベート (`class` の場合) かを示します。  
  
 同じように、マネージ拡張では、値クラス型の前には `__value` キーワードが付けられました。 新しい構文では、`__value` キーワードは 2 つのスペース区切りキーワード、`value class` または `value struct` のいずれかに置き換わります。  
  
 インターフェイス型は、マネージ拡張ではキーワード `__interface` で示されていました。 新しい構文ではこれは `interface class` に置き換わります。  
  
 たとえば、マネージ拡張で次のようなクラス宣言があるとします。  
  
```  
public __gc class Block {};     // reference class  
public __value class Vector {}; // value class  
public __interface IFooBar {};  // interface class  
```  
  
 新しい構文ではこれは次のように宣言されます。  
  
```  
public ref class Block {};         // reference class  
public value class Vector {};      // value class  
public interface class IFooBar {}; // interface class  
```  
  
## <a name="specifying-the-class-as-abstract"></a>abstract としてのクラスの指定  
 マネージ拡張では、キーワード `__abstract` が `class` キーワードの前 (`__gc` キーワードの前または後) に置かれ、クラスが不完全であること、およびそのクラスのオブジェクトをプログラムの中で作成できないことを示しました。  
  
```  
public __gc __abstract class Shape {};  
public __gc __abstract class Shape2D: public Shape {};  
```  
  
 新しい構文では、`abstract` コンテキスト キーワードが、クラス名の後、およびクラス本体、基底クラス派生リスト、またはセミコロンのいずれかの前に指定されます。  
  
```  
public ref class Shape abstract {};  
public ref class Shape2D abstract : public Shape{};  
```  
  
 もちろん、意味は変更されません。  
  
## <a name="specifying-the-class-as-sealed"></a>sealed としてのクラスの指定  
 マネージ拡張では、キーワード `__sealed` が `class` キーワードの前 (`__gc` キーワードの前または後) に置かれ、そのクラスのオブジェクトを継承できないことを示しました。  
  
```  
public __gc __sealed class String {};  
```  
  
 新しい構文では、`sealed` コンテキスト キーワードが、クラス名の後、およびクラス本体、基底クラス派生リスト、またはセミコロンのいずれかの前に指定されます。  
  
 クラスを派生させてシールすることもできます。 たとえば、`String` クラスは `Object` から暗黙的に派生します。 クラスをシールすると、シールされた参照クラス オブジェクトを通じて、すべての仮想関数呼び出しを (コンパイル時に) 静的に解決できるという利点があります。 その理由は、`sealed` 指定子により、呼び出される仮想メソッドのインスタンスをオーバーライドする可能性のある以降の派生クラスを `String` 追跡ハンドルが参照できなくなるためです。 新しい構文を使ったシール クラスの例を次に示します。  
  
```  
public ref class String sealed {};  
```  
  
 両方の抽象としてクラスを指定することも 1 つシール - これとは、静的クラスを示す特殊な条件。 これについては、CLR のドキュメントに次のように記述されています。  
  
 「`abstract` と `sealed` の両方である型は静的メンバーのみを持ち、一部の言語で名前空間と呼ばれる機能を提供します。」  
  
 abstract sealed クラスの宣言の例をマネージ拡張の構文で示します。  
  
```  
public __gc __sealed __abstract class State {  
public:  
   static State() {}  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
 この宣言を新しい構文に変換すると、次のようになります。  
  
```  
public ref class State abstract sealed {  
public:  
   static State();  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
## <a name="clr-inheritance-specifying-the-base-class"></a>CLR の継承 : 基底クラスの指定  
 CLR のオブジェクト モデルでは、単一のパブリック継承のみがサポートされています。 しかし、マネージ拡張では、基底クラスにアクセス キーワードがない場合、プライベート派生を指定していると見なす ISO-C++ の既定の解釈が保持されていました。 このため、各 CLR 継承宣言では、既定の解釈をオーバーライドするために `public` キーワードを指定する必要がありました。  
  
```  
// Managed Extensions: error: defaults to private derivation  
__gc class Derived : Base {};  
```  
  
 新しい構文の定義では、CLR 継承定義でアクセス キーワードがない場合はパブリック派生になります。 そのため、今後は `public` アクセス キーワードを省略することも可能です。 この変更は C++ マネージ拡張コードの修正を必要とするものではありませんが、完全を期すためここに紹介しています。  
  
```  
// New syntax: ok: defaults to public derivation  
ref class Derived : Base{};  
```  
  
## <a name="see-also"></a>関連項目  
 [マネージ型 (C + + CL)](../dotnet/managed-types-cpp-cl.md)   
 [クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)   
 [abstract](../windows/abstract-cpp-component-extensions.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)