---
title: ジェネリック型制約パラメーター (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- where
dev_langs:
- C++
helpviewer_keywords:
- where keyword [C++]
- constraints, C++
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c9787eb87ab701d067762a436d92b2fba3fabcbb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883343"
---
# <a name="constraints-on-generic-type-parameters-ccli"></a>ジェネリック型パラメーターの制約 (C++/CLI)
ジェネリック型またはメソッドの宣言では、制約と型パラメーターを修飾することができます。 制約は、型引数として使用される型が満たす必要がある要件です。 たとえば、型引数が特定のインターフェイスを実装するか、特定のクラスから継承する必要があります、制約があります。  
  
 制約は、省略可能です。パラメーターに制約を指定しないはそのパラメーターの制約に相当<xref:System.Object>です。  
  
## <a name="syntax"></a>構文  
  
```  
  
where type-parameter: constraint list  
```  
  
#### <a name="parameters"></a>パラメーター  
 *型パラメーター*  
 制約が適用される、型パラメーターの 1 つ。  
  
 *制約リスト*  
 *制約リスト*制約仕様のコンマ区切り一覧を示します。 一覧には、型パラメーターによって実装されるインターフェイスを含めることができます。  
  
 一覧には、クラスを含めることもできます。 型の引数の基本クラスの制約を満たすために、制約としてクラスが同じか、制約から派生が必要があります。  
  
 指定することも`gcnew()`型引数、パブリック パラメーターなしコンス トラクターが必要ですを示すためにまたは`ref class`型引数はすべてのクラス、インターフェイス、デリゲート、または配列型を含む、参照型である必要がありますを示すために、または`value class`に。型引数は値型である必要がありますを指定します。 値は null 値以外の種類の\<T > を指定できます。  
  
 制約としてジェネリック パラメーターを指定することもできます。 制約は、型指定された型引数は、するか、制約の型から派生する必要があります。 これには、生の型制約は呼び出されます。  
  
## <a name="remarks"></a>コメント  
 制約句で構成されます**場所**型パラメーター、コロンを続けて (**:**)、および、制約は、型パラメーターに、制限の種類を指定します。 **ここで**状況依存のキーワードです。 を参照してください[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)詳細についてはします。 複数の個別**場所**スペースで句。  
  
 制約は、ジェネリック型またはメソッドの引数として使用できる型に制限を配置するパラメーターの型に適用されます。  
  
 クラスとインターフェイスの制約は、引数の型必要があるまたは指定したクラスから継承するかを指定したインターフェイスを実装を指定します。  
  
 制約のジェネリック型またはメソッドへのアプリケーションでは、制約付きの型の既知の機能を活用するためにその型またはメソッドでコードを許可します。 型パラメーターを実装するように、ジェネリック クラスを宣言するなど、 **IComparable\<T >** インターフェイス。  
  
```  
// generics_constraints_1.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : IComparable<T>  
ref class List {};  
```  
  
 この制約は、型引数に使用されることが必要です`T`実装`IComparable<T>`コンパイル時にします。 また、インターフェイス メソッドなど**CompareTo**、呼び出されます。 インターフェイス メソッドの呼び出しに型パラメーターのインスタンスのキャストは必要ありません。  
  
 型パラメーターを型引数のクラスで静的メソッドを呼び出すことができません。これらは、実際の名前付きの型を介してのみ呼び出すことができます。  
  
 制約などの組み込み型を含む、値型であることはできません`int`または**二重**です。 値の型には、クラスを派生できませんが、以降 1 つのクラスができる制約を満たすです。 その場合は、特定の値の型によって置き換え型パラメーター、ジェネリックを書き直すことができます。  
  
 制約は、コンパイラは許可しないメソッドを使用または不明な型の他の機能制約意味不明な型には、そのメソッドまたはインターフェイスがサポートしている場合を除き、ために、場合によっては必要があります。  
  
 コンマ区切りの一覧で、同じ型パラメーターに対して複数の制約を指定することができます。  
  
```  
// generics_constraints_2.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
generic <typename T>  
where T : List<T>, IComparable<T>  
ref class List {};  
```  
  
 複数の型パラメーターを持つ 1 つを使用して**場所**それぞれの型パラメーターの句。 例えば:  
  
```  
// generics_constraints_3.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
  
generic <typename K, typename V>  
   where K: IComparable<K>  
   where V: IComparable<K>  
ref class Dictionary {};  
```  
  
 要約すると、次の規則に従って、コード内の制約を使用します。  
  
-   複数の制約がある場合、制約は任意の順序で表示されます。  
  
-   制約では、抽象基本クラスなどのクラス型もあります。 ただし、制約は、値の型またはシール クラスにすることはできません。  
  
-   自身の制約が、型パラメーターをすることはできませんが、オープン構築型の型パラメーターが含まれることができます。 例えば:  
  
    ```  
    // generics_constraints_4.cpp  
    // compile with: /c /clr  
    generic <typename T>  
    ref class G1 {};  
  
    generic <typename Type1, typename Type2>  
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter  
    ref class G2{};  
    ```  
  
## <a name="example"></a>例  
 次の例では、制約を使用して、型パラメーターのインスタンス メソッドを呼び出すことを示します。  
  
```  
// generics_constraints_5.cpp  
// compile with: /clr  
using namespace System;  
  
interface class IAge {  
   int Age();  
};  
  
ref class MyClass {  
public:  
   generic <class ItemType> where ItemType : IAge   
   bool isSenior(ItemType item) {  
      // Because of the constraint,  
      // the Age method can be called on ItemType.  
      if (item->Age() >= 65)   
         return true;  
      else  
         return false;  
   }  
};  
  
ref class Senior : IAge {  
public:  
   virtual int Age() {  
      return 70;  
   }  
};  
  
ref class Adult: IAge {  
public:  
   virtual int Age() {  
      return 30;  
   }  
};  
  
int main() {  
   MyClass^ ageGuess = gcnew MyClass();  
   Adult^ parent = gcnew Adult();  
   Senior^ grandfather = gcnew Senior();  
  
   if (ageGuess->isSenior<Adult^>(parent))  
      Console::WriteLine("\"parent\" is a senior");  
   else  
      Console::WriteLine("\"parent\" is not a senior");  
  
   if (ageGuess->isSenior<Senior^>(grandfather))  
      Console::WriteLine("\"grandfather\" is a senior");  
   else  
      Console::WriteLine("\"grandfather\" is not a senior");  
}  
```  
  
```Output  
"parent" is not a senior  
"grandfather" is a senior  
```  
  
## <a name="example"></a>例  
 ジェネリック型パラメーターは、制約として使用される、生の型制約は呼び出されます。 生の型制約は、独自の型パラメーターを持つメンバー関数は、そのパラメーターを含む型の型パラメーターに制約する必要がある場合に便利です。  
  
 次の例では、T は、Add メソッドのコンテキストで生の型制約です。  
  
 生の型制約は、ジェネリック クラスの定義でも使用できます。 コンパイラと見なすことが、naked 型の制約について何もから派生する点を除いてために、ジェネリック クラスを生の型制約の有用性が制限されて<xref:System.Object>です。 2 つの型パラメーターの間の継承関係を適用するシナリオでは、ジェネリック クラスの生の型制約を使用します。  
  
```  
// generics_constraints_6.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct List {  
   generic <class U>  
   where U : T  
   void Add(List<U> items)  {}  
};  
  
generic <class A, class B, class C>  
where A : C  
ref struct SampleClass {};  
```  
  
## <a name="see-also"></a>関連項目  
 [ジェネリック](../windows/generics-cpp-component-extensions.md)