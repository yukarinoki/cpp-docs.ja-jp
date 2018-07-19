---
title: abstract (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
dev_langs:
- C++
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dcaef98df96b54025cd44a52a2e27a7bc5a83545
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857556"
---
# <a name="abstract--c-component-extensions"></a>abstract (C++ コンポーネント拡張)
`abstract` キーワードは、次のいずれかを宣言します。  
  
-   型を基本データ型として使用できるが、型自体はインスタンス化できない。  
  
-   型のメンバー関数を派生型でのみ定義できる。  
  
## <a name="all-platforms"></a>すべてのプラットフォーム  
 **構文**  
  
```  
  
      class-declaration  
      class-identifier  
      abstract {}  
virtualreturn-typemember-function-identifier() abstract ;  
  
```  
  
 **解説**  
  
 最初の例の構文では、abstract (抽象) にするクラスを宣言します。 *クラス宣言*コンポーネントは、ネイティブ C++ の宣言を指定できます (`class`または`struct`)、または C++ の拡張宣言 (`ref class`または`ref struct`) 場合、 **/ZW**または **/clr**コンパイラ オプションを指定します。  
  
 2 つ目の例の構文では、仮想メンバー関数を抽象として宣言します。 関数を抽象として宣言することは、純粋仮想関数として宣言することと同じです。 メンバー関数を抽象として宣言すると、外側のクラスも抽象として宣言されます。  
  
 `abstract`キーワードがネイティブ コンパイルおよびプラットフォーム固有のコードでサポートされていません。 つまり、コンパイルの有無、 **/ZW**または **/clr**コンパイラ オプション。  
  
 型である抽象場合コンパイル時に検出できます、`__is_abstract(type)`型の特徴です。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)です。  
  
 `abstract` キーワードは状況依存のオーバーライド指定子です。 状況依存のキーワードの詳細については、次を参照してください。[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)です。 オーバーライド指定子の詳細については、次を参照してください。[する方法: オーバーライド指定子を宣言ネイティブ コンパイルで](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)です。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 詳細については、次を参照してください。 [Ref クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次のコード例では、`X` クラスに `abstract` が指定されているため、エラーが生成されます。  
  
```  
// abstract_keyword.cpp  
// compile with: /clr  
ref class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X;   // C3622  
}  
```  
  
 **例**  
  
 次のコード例では、`abstract` として指定されたネイティブ クラスがインスタンス化されるため、エラーが生成されます。 このエラーが発生の有無、 **/clr**コンパイラ オプション。  
  
```  
// abstract_keyword_2.cpp  
class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'  
                    // cannot be instantiated. See declaration of 'X'}  
  
```  
  
 **例**  
  
 次のコード例では、関数 `f` に定義が含まれている一方で `abstract` が指定されているため、エラーが生成されます。 この例の最後のステートメントで、抽象仮想関数を宣言することは純粋仮想関数を宣言することと同じであることを示しています。  
  
```  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)