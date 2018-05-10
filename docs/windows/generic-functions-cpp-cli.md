---
title: ジェネリック関数 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], generic
- generic methods
- generics [C++], functions
- methods [C++], generic
- generic functions
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 66eb27b28a1b18942c0a8a9a77a877a2f0b2ef8c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="generic-functions-ccli"></a>ジェネリック関数 (C++/CLI)
ジェネリック関数は、型パラメーターで宣言された関数です。 呼び出されると、実際の型が型パラメーターの代わりに使用されます。  
  
## <a name="all-platforms"></a>すべてのプラットフォーム  
 **解説**  
  
 この機能は、すべてのプラットフォームには適用されません。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 **解説**  
  
 この機能は、Windows ランタイムでサポートされていません。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 ジェネリック関数は、型パラメーターで宣言された関数です。 呼び出されると、実際の型が型パラメーターの代わりに使用されます。  
  
 **構文**  
  
```  
[attributes] [modifiers]  
return-type identifier<type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{function-body}  
```  
  
 **パラメーター**  
  
 *属性*(省略可能)  
 追加の宣言情報。 属性と属性クラスの詳細については、属性を参照してください。  
  
 *修飾子*(省略可能)  
 静的など、関数の修飾子です。  `virtual` 仮想メソッドをジェネリックにすることはできないためには許可されません。  
  
 *戻り値の型*  
 メソッドによって返される型。 戻り値の型が void の場合は、戻り値は必要ありません。  
  
 *identifier*  
 関数名。  
  
 *型パラメーターの識別子*  
 識別子のコンマ区切りの一覧です。  
  
 *正式なパラメーター* (省略可能)  
 パラメーターの一覧です。  
  
 *型パラメーターの制約句*  
 これは、型引数として使用できる型で制限を指定しの形式で指定された[ジェネリック型パラメーターの制約 (C + + CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)です。  
  
 *関数本体*  
 型パラメーターの識別子を参照する、メソッドの本体。  
  
 **解説**  
  
 ジェネリック関数は、ジェネリック型パラメーターで宣言された関数です。 クラスまたは構造体、またはスタンドアロン関数内のメソッドがあります。 1 つのジェネリック宣言は、のみが異なるさまざまな実際の型のジェネリック型パラメーターの代替関数のファミリを暗黙的に宣言します。  
  
 Visual c では、ジェネリック型パラメーターを持つ、クラスまたは構造体のコンス トラクターを宣言されていません可能性があります。  
  
 呼び出されると、そのジェネリック型パラメーターと、実際の型が置き換えられます。 山かっことテンプレート関数の呼び出しに似た構文を使用するのには、実際の型を明示的に指定する可能性があります。 型パラメーターを指定しないで呼び出されると、コンパイラは関数呼び出しで指定されたパラメーターから実際の型を推測しようとします。 目的の型引数は、使用されるパラメーターから推測できない、コンパイラでエラーが報告されます。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次のコード サンプルでは、ジェネリック関数を示します。  
  
```  
// generics_generic_function_1.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
ref struct A {  
   generic <typename ItemType>  
   void G(ItemType) {}  
  
   generic <typename ItemType>  
   static void H(int i) {}  
};  
  
int main() {  
   A myObject;  
  
   // generic function call  
   myObject.G<int>(10);  
  
   // generic function call with type parameters deduced  
   myObject.G(10);  
  
   // static generic function call  
   A::H<int>(10);  
  
   // global generic function call  
   G<int>(10);  
}  
```  
  
 **例**  
  
 ジェネリック関数は、署名またはアリティ、関数の型パラメーターの数に基づいてオーバー ロードすることができます。 また、ジェネリック関数はオーバー ロードできます、同じ名前の非ジェネリック関数と共にときは、型パラメーターの中に、関数がそれぞれ異なります。 たとえば、次の関数をオーバー ロードすることができます。  
  
```  
// generics_generic_function_2.cpp  
// compile with: /clr /c  
ref struct MyClass {  
   void MyMythod(int i) {}  
  
   generic <class T>   
   void MyMythod(int i) {}  
  
   generic <class T, class V>   
   void MyMythod(int i) {}  
};  
```  
  
 **例**  
  
 次の例では、ジェネリック関数を使用して、配列内の最初の要素を検索します。 宣言して`MyClass`、基本クラスから継承される`MyBaseClass`です。 `MyClass` ジェネリック関数を含む`MyFunction`、別のジェネリック関数を呼び出している`MyBaseClassFunction`、基底クラス内で。 **メイン**、ジェネリック関数`MyFunction`、異なる型引数を使用して呼び出されました。  
  
```  
// generics_generic_function_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyBaseClass {  
protected:  
   generic <class ItemType>  
   ItemType MyBaseClassFunction(ItemType item) {  
      return item;  
   }  
};  
  
ref class MyClass: public MyBaseClass {  
public:  
   generic <class ItemType>  
   ItemType MyFunction(ItemType item) {  
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);  
   }  
};  
  
int main() {  
   MyClass^ myObj = gcnew MyClass();  
  
   // Call MyFunction using an int.  
   Console::WriteLine("My function returned an int: {0}",  
                           myObj->MyFunction<int>(2003));  
  
   // Call MyFunction using a string.  
   Console::WriteLine("My function returned a string: {0}",  
   myObj->MyFunction<String^>("Hello generic functions!"));  
}  
```  
  
 **出力**  
  
```Output  
My function returned an int: 2003  
My function returned a string: Hello generic functions!  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)   
 [ジェネリック](../windows/generics-cpp-component-extensions.md)