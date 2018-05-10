---
title: CLR 参照クラス オブジェクトの宣言 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- types [C++], reference types
- reference types, CLR
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 12cead3a142c69da56390ca6f5bf32cecc3b0075
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="declaration-of-a-clr-reference-class-object"></a>CLR 参照クラスのオブジェクトの宣言
宣言や参照クラス型のオブジェクトのインスタンスを作成する構文は、Visual C を c++ マネージ拡張から変更されました。  
  
 オプションの使用に ISO C ポインターの構文を使用して、マネージ拡張で、参照クラス型のオブジェクトが宣言されている、`__gc`星の左にキーワード (`*`)。 たとえば、ここでは、さまざまな参照をマネージ拡張構文では、クラス型オブジェクト宣言です。  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   Button __gc *button1;  
   DataGrid __gc *myDataGrid;     
   DataSet __gc *myDataSet;  
  
   void PrintValues( Array* myArr ) {  
      System::Collections::IEnumerator* myEnumerator =   
         myArr->GetEnumerator();  
  
      Array *localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);  
   }  
};  
```  
  
 新しい構文では、新しい宣言型トークンを使用して、参照クラス型のオブジェクトを宣言する (`^`) と呼ばれる正式に、*追跡ハンドル*より非公式として、 *hat*です。 (参照型が、CLR ヒープ内に存在し、したがって透過的に移動できます場所ガベージ コレクション ヒープの圧縮中に追跡形容詞を意味します。 追跡ハンドルは透過的に実行時に更新されます。 2 つのような概念は、*追跡参照*(`%`)、および*内部ポインター* (`interior_ptr<>`) で説明したように、[値型のセマンティクス](../dotnet/value-type-semantics.md)です。  
  
 宣言の構文、構文の再利用、ISO C のポインターから離れた場所に移行する主な理由は次のとおりです。  
  
-   ポインターの構文の使用は、参照オブジェクトに直接適用されるオーバー ロードされた演算子を許可していません。 代わりに、1 つが、演算子などの内部名を使用して、`rV1->op_Addition(rV2)`より直感的ではなく`rV1+rV2`です。  
  
-   ガベージに格納されているオブジェクトに対して許可されていないポインターの算術演算、キャストなどのポインターの操作の数は、ヒープを収集します。 優れた追跡ハンドルの概念は、CLR 参照型の性質をキャプチャします。  
  
 `__gc`追跡ハンドルで修飾子は不要であり、サポートされていません。 オブジェクト自体の使用は変更されません。ポインター メンバー選択演算子を介してメンバーがまだアクセス (`->`)。 たとえば、新しい構文に変換前のマネージ拡張コード サンプルを次に示します。  
  
```  
public ref class Form1: public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container^ components;  
   Button^ button1;  
   DataGrid^ myDataGrid;  
   DataSet^ myDataSet;  
  
   void PrintValues( Array^ myArr ) {  
      System::Collections::IEnumerator^ myEnumerator =  
         myArr->GetEnumerator();  
  
      Array ^localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);   }  
};  
```  
  
## <a name="dynamic-allocation-of-an-object-on-the-clr-heap"></a>CLR ヒープ上のオブジェクトの動的割り当て  
 マネージ拡張で 2 つの存在`new`式、ネイティブおよびマネージ ヒープの間を割り当てることがきわめて透過的です。 ほぼすべてのインスタンスで、コンパイラは、ネイティブまたはマネージ ヒープからメモリを割り当てるかどうかを決定するコンテキストを使用することです。 たとえば、オブジェクトに適用された  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 いずれかと、コンパイラに指示するでしたコンテキスト ヒープ割り当てしたくない場合に、`__gc`または`__nogc`キーワード。 新しい構文では 2 つの新しい式の個別の性質が明示の導入に伴い、`gcnew`キーワード。 たとえば、前の 3 つの宣言は、新しい構文のようになります。  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 マネージ拡張で初期化をここでは、`Form1`前のセクションで宣言されたメンバー。  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 新しい構文に再キャスト、同じ初期化を次に示します。 対象となっているときに、hat は参照型に必要ないことに注意してください、`gcnew`式。  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## <a name="a-tracking-reference-to-no-object"></a>ないオブジェクトへの追跡参照  
 新しい構文で`0`不要になった null アドレスを表しますが、同じ整数として扱われます`1`、 `10`、または`100`です。 新しい特殊なトークンでは、追跡参照に null 値を表します。 たとえば、マネージ拡張で次のようにオブジェクトをアドレスなしに参照型を初期化します。  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 新しい構文の初期化や値の割り当てへの入力、`Object`その値型の暗黙のボックス化が発生します。 新しい構文では両方とも`obj`と`obj2`アドレス指定それぞれ 0 と 1 の値を保持するボックス化された Int32 オブジェクトに初期化されます。 例えば:  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 そのため、明示的な初期化、割り当て、および追跡ハンドルを null の比較を実行するために、新しいキーワードを使用して`nullptr`です。  正しいリビジョンの元の例は次のようになります。  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 これは、ある程度移植既存のコードの新しい構文に複雑になります。 たとえば、次の値クラスの宣言があるとします。  
  
```  
__value struct Holder {  
   Holder( Continuation* c, Sexpr* v ) {  
      cont = c;  
      value = v;  
      args = 0;  
      env = 0;  
   }  
  
private:  
   Continuation* cont;  
   Sexpr * value;  
   Environment* env;  
   Sexpr * args __gc [];  
};  
```  
  
 ここでは、両方とも`args`と`env`は CLR 参照型です。 これら 2 つのメンバーを初期化`0`コンス トラクターでは、新しい構文への移行では変更されないことはできません。 代わりを変更する必要があります`nullptr`:  
  
```  
value struct Holder {  
   Holder( Continuation^ c, Sexpr^ v )  
   {  
      cont = c;  
      value = v;  
      args = nullptr;  
      env = nullptr;  
   }  
  
private:  
   Continuation^ cont;  
   Sexpr^ value;  
   Environment^ env;  
   array<Sexpr^>^ args;  
};  
```  
  
 同様に、これらのメンバーにテスト`0`との比較にも変更する必要があります`nullptr`です。 マネージ拡張構文を次に示します。  
  
```  
Sexpr * Loop (Sexpr* input) {  
   value = 0;  
   Holder holder = Interpret(this, input, env);  
  
   while (holder.cont != 0) {  
      if (holder.env != 0) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != 0) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 ここでは、リビジョン、それぞれ置き換える`0`インスタンスを`nullptr`です。 含むすべての出現回数を使用しない場合、翻訳ツールにより、この変換では多くを自動化することを`NULL`マクロです。  
  
```  
Sexpr ^ Loop (Sexpr^ input) {  
   value = nullptr;  
   Holder holder = Interpret(this, input, env);  
  
   while ( holder.cont != nullptr ) {  
      if ( holder.env != nullptr ) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != nullptr ) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 `nullptr`は任意の追跡のポインターまたはハンドル型に変換されますが、整数型には昇格されません。 たとえば、初期化の次のセットで、`nullptr`最初の 2 つに、初期値としてのみ有効です。  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0  
int ival = nullptr;  
```  
  
 同様に、次などのメソッドのオーバー ロードされたセットを指定します。  
  
```  
void f( Object^ ); // (1)  
void f( char* );   // (2)  
void f( int );     // (3)  
```  
  
 メソッドを`nullptr`次のように、リテラル  
  
```  
// Error: ambiguous: matches (1) and (2)  
f(  nullptr );  
```  
  
 あいまいなため、`nullptr`追跡ハンドルと、ポインターの両方に一致し、その中に 1 つの型指定された基本設定はありません。 (このような状況が必要、明示的なキャストあいまいさを解消するためにします。)  
  
 メソッドを`0`正確に一致するインスタンス (3)。  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 `0`が整数型。 された`f(int)`、存在していない呼び出しが明確に一致する`f(char*)`標準変換です。 照合ルールでは、標準変換と完全に一致の優先順位を付けます。 厳密な一致がない場合は、標準の変換よりも優先、値の型の暗黙的なボックス化します。 あいまいでないためにです。  
  
## <a name="see-also"></a>関連項目  
 [マネージ型 (C + + CL)](../dotnet/managed-types-cpp-cl.md)   
 [クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)   
 [オブジェクト演算子 (^) へのハンドルします。](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)