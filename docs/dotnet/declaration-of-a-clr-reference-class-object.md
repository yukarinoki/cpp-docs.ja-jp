---
title: CLR 参照クラス オブジェクトの宣言 |Microsoft Docs
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
ms.openlocfilehash: f3e8ec6407e12d0c26331d45dc1659277feed016
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444581"
---
# <a name="declaration-of-a-clr-reference-class-object"></a>CLR 参照クラスのオブジェクトの宣言

宣言および参照クラス型のオブジェクトをインスタンス化するための構文は、Visual c の C++ マネージ拡張から変更されました。

オプションの使用を ISO C ポインターの構文を使用してマネージ拡張で参照クラス型のオブジェクトが宣言されている、`__gc`星の左にキーワード (`*`)。 たとえば、次に示します、さまざまな参照をマネージ拡張構文では、クラス型オブジェクトの宣言。

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

新しい構文では、新しい宣言型のトークンを使用して参照クラス型のオブジェクトを宣言する (`^`) として正式に参照を*追跡ハンドル*より非公式として、 *hat*。 (追跡形容詞は、参照型が、CLR ヒープに配置し、できる透過的に場所はガベージ コレクション ヒープの圧縮中に移動したがってを意味します。 追跡ハンドルは、実行時に透過的に更新されます。 2 つのような概念は、*追跡参照*(`%`)、および*内部ポインター* (`interior_ptr<>`) で説明した、[値型セマンティクス](../dotnet/value-type-semantics.md)します。

ISO C ポインターの構文の再利用から宣言型構文に移行する主な理由は次のとおりです。

- ポインターの構文の使用は、参照オブジェクトに適用される直接オーバー ロードされた演算子を許可されていませんでした。 代わりに、いずれかの演算子を呼び出すなどの内部名を使用してする必要がある`rV1->op_Addition(rV2)`より直感的ではなく`rV1+rV2`します。

- ガベージに格納されているオブジェクトに対して許可されていないポインター操作、ポインターの算術演算、キャストなどの数には、ヒープが収集されます。 優れた追跡ハンドルの概念は CLR 参照型の性質をキャプチャします。

`__gc`追跡ハンドル修飾子は不要であり、サポートされていません。 オブジェクト自体の使用は変更されません。ポインターのメンバー選択演算子によってメンバーがまだアクセス (`->`)。 たとえば、新しい構文に変換前のマネージ拡張コード サンプルを次に示します。

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

マネージ拡張の 2 つが存在することで`new`式ネイティブおよびマネージ ヒープの間を割り当てることがきわめて透過的です。 ほぼすべてのインスタンスでは、コンパイラは、コンテキストを使用して、ネイティブまたはマネージ ヒープからメモリを割り当てるかどうかを決定すること。 たとえば、オブジェクトに適用された

```
Button *button1 = new Button; // OK: managed heap
int *pi1 = new int;           // OK: native heap
Int32 *pi2 = new Int32;       // OK: managed heap
```

コンテキストのヒープ割り当てしたくないときは、いずれかでコンパイラを指示することが、`__gc`または`__nogc`キーワード。 新しい構文では、2 つの新しい式の個別の性質の導入により明示的に行われます、`gcnew`キーワード。 たとえば、前の 3 つの宣言は、新しい構文のようになります。

```
Button^ button1 = gcnew Button;        // OK: managed heap
int * pi1 = new int;                   // OK: native heap
Int32^ pi2 = gcnew Int32; // OK: managed heap
```

マネージ拡張の初期化をここでは、`Form1`前のセクションで宣言されたメンバー。

```
void InitializeComponent() {
   components = new System::ComponentModel::Container();
   button1 = new System::Windows::Forms::Button();
   myDataGrid = new DataGrid();

   button1->Click +=
      new System::EventHandler(this, &Form1::button1_Click);
}
```

新しい構文に再キャスト同じ初期化を次に示します。 対象となっているときに、hat が参照型の必要ないことに注意してください、`gcnew`式。

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

新しい構文で`0`不要になった null アドレスを表しますが、同じ整数として扱われます`1`、 `10`、または`100`します。 新しい特殊なトークンは、追跡参照に null 値を表します。 たとえば、マネージ拡張でオブジェクトを次のようにアドレスなしに参照型を初期化します。

```
// OK: we set obj to refer to no object
Object * obj = 0;

// Error: no implicit boxing
Object * obj2 = 1;
```

初期化や値の割り当てをする入力の新しい構文では、`Object`値型の暗黙のボックス化を発生します。 新しい構文では両方とも`obj`と`obj2`アドレス指定それぞれ 0 と 1 の値を保持するボックス化の Int32 オブジェクトに初期化されます。 例えば:

```
// causes the implicit boxing of both 0 and 1
Object ^ obj = 0;
Object ^ obj2 = 1;
```

そのため、明示的な初期化、割り当て、および追跡ハンドルを null の比較を実行するために、新しいキーワードを使用して`nullptr`します。  正しいリビジョンの元の例は次のようになります。

```
// OK: we set obj to refer to no object
Object ^ obj = nullptr;

// OK: we initialize obj2 to a Int32^
Object ^ obj2 = 1;
```

これは、ある程度に移植する際の既存のコードを新しい構文に複雑になります。 たとえば、次の値クラスの宣言を検討してください。

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

ここでは、どちらも`args`と`env`は CLR 参照型です。 これら 2 つのメンバーの初期化`0`コンス トラクターでは、新しい構文への移行で変更されていないおくことはできません。 代わりに変更する必要があります`nullptr`:

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

同様に、これらのメンバーにに対してテスト`0`との比較にも変更する必要があります`nullptr`します。 マネージ拡張構文を次に示します。

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

ここでは、それぞれを置き換えて、リビジョン`0`インスタンス、`nullptr`します。 含むすべての出現箇所を使用していない場合に翻訳ツールにより、この変換では多くを自動化することで、`NULL`マクロ。

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

`nullptr`任意のポインターまたは追跡ハンドル型に変換されますが、整数型には昇格されません。 たとえば、次の一連の初期化ので、`nullptr`最初の 2 つに、初期値としてのみ有効です。

```
// OK: we set obj and pstr to refer to no object
Object^ obj = nullptr;
char*   pstr = nullptr; // 0 would also work here

// Error: no conversion of nullptr to 0
int ival = nullptr;
```

同様に、次などのメソッドのオーバー ロードされたセットを考えてみます。

```
void f( Object^ ); // (1)
void f( char* );   // (2)
void f( int );     // (3)
```

呼び出すと`nullptr`に次のように、リテラル

```
// Error: ambiguous: matches (1) and (2)
f(  nullptr );
```

あいまいなため、`nullptr`追跡ハンドルと、ポインターの両方に一致する、もう一方に 1 つの型指定された基本設定はありません。 (このような状況が必要、明示的なキャストあいまいさを解消するためにします。)

呼び出すと`0`正確に一致するインスタンス (3)。

```
// OK: matches (3)
f( 0 );
```

`0`は整数型です。 `f(int)`存在しない場合、呼び出しは明確に一致`f(char*)`標準変換を使用します。 照合ルールでは、標準変換と完全に一致の優先順位を付けます。 厳密な一致がない場合、標準の変換よりも優先、値の型の暗黙的なボックス化します。 あいまいさがないためにです。

## <a name="see-also"></a>関連項目

[マネージ型 (C +/cli CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[オブジェクト演算子 (^) へのハンドルします。](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)<br/>
[nullptr](../windows/nullptr-cpp-component-extensions.md)