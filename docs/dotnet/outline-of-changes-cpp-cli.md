---
title: 変更の概要 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2a9662f73844013a944fc2b04ce6d3627d4e4b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="outline-of-changes-ccli"></a>変更の概略 (C++/CLI)
このアウトライン例を示す変更のいくつかのマネージ拡張からの言語で Visual c の C++ の。 詳細については、各項目に付属しているリンクを辿ってください。  
  
## <a name="no-double-underscore-keywords"></a>キーワードは二重アンダー スコア  
 すべてのキーワードの前にある二重のアンダー スコアは削除されました、1 つの例外。 したがって、`__value`になります`value`と`__interface`なります`interface`のようにします。 キーワードとユーザー コード内で識別子名の競合を防ぐためには、キーワードは、主に扱われますとコンテキスト。  
  
 参照してください[言語のキーワード (C + + CLI)](../dotnet/language-keywords-cpp-cli.md)詳細についてはします。  
  
## <a name="class-declarations"></a>クラスの宣言  
 マネージ拡張構文:  
  
```  
__gc class Block {};                           // reference class  
__value class Vector {};                       // value class  
__interface I {};                        // interface class  
__gc __abstract class Shape {};                // abstract class  
__gc __sealed class Shape2D : public Shape {}; // derived class  
```  
  
 新しい構文:  
  
```  
ref class Block {};                // reference class  
value class Vector {};             // value class  
interface class I {};        // interface class  
ref class Shape abstract {};       // abstract class  
ref class Shape2D sealed: Shape{}; // derived class  
```  
  
 参照してください[マネージ型 (C + + CL)](../dotnet/managed-types-cpp-cl.md)詳細についてはします。  
  
## <a name="object-declaration"></a>オブジェクトの宣言  
 マネージ拡張構文:  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   System::Windows::Forms::Button   __gc *button1;  
   System::Windows::Forms::DataGrid __gc *myDataGrid;     
   System::Data::DataSet  __gc *myDataSet;  
};  
```  
  
 新しい構文:  
  
```  
public ref class Form1 : System::Windows::Forms::Form {  
   System::ComponentModel::Container^ components;  
   System::Windows::Forms::Button^ button1;  
   System::Windows::Forms::DataGrid^ myDataGrid;  
   System::Data::DataSet^ myDataSet;  
};  
```  
  
 参照してください[CLR 参照クラス オブジェクトの宣言](../dotnet/declaration-of-a-clr-reference-class-object.md)詳細についてはします。  
  
### <a name="managed-heap-allocation"></a>マネージ ヒープの割り当て  
 マネージ拡張構文:  
  
```  
Button* button1 = new Button; // managed heap  
int *pi1 = new int;           // native heap  
Int32 *pi2 = new Int32;       // managed heap  
```  
  
 新しい構文:  
  
```  
Button^ button1 = gcnew Button;        // managed heap  
int * pi1 = new int;                   // native heap  
Int32^ pi2 = gcnew Int32;              // managed heap  
```  
  
 参照してください[CLR 参照クラス オブジェクトの宣言](../dotnet/declaration-of-a-clr-reference-class-object.md)詳細についてはします。  
  
### <a name="a-tracking-reference-to-no-object"></a>ないオブジェクトへの追跡参照  
 マネージ拡張構文:  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 新しい構文:  
  
```  
// Incorrect Translation  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
  
// Correct Translation  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to an Int32^  
Object ^ obj2 = 1;  
```  
  
 参照してください[CLR 参照クラス オブジェクトの宣言](../dotnet/declaration-of-a-clr-reference-class-object.md)詳細についてはします。  
  
## <a name="array-declaration"></a>配列の宣言  
 CLR 配列が再設計されました。 Stl に似ています`vector`テンプレート コレクションが、基になるマップ`System::Array`クラス: つまりはテンプレートの実装です。  
  
 参照してください[CLR 配列の宣言](../dotnet/declaration-of-a-clr-array.md)詳細についてはします。  
  
### <a name="array-as-parameter"></a>パラメーターとして配列  
 マネージ拡張配列の構文:  
  
```  
void PrintValues( Object* myArr __gc[]);   
void PrintValues( int myArr __gc[,,]);   
```  
  
 新しい配列の構文:  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
### <a name="array-as-return-type"></a>戻り値の型として配列  
 マネージ拡張配列の構文:  
  
```  
Int32 f() [];   
int GetArray() __gc[];  
```  
  
 新しい配列の構文:  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
### <a name="shorthand-initialization-of-local-clr-array"></a>ローカルの CLR 配列の略式の初期化  
 マネージ拡張配列の構文:  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = { __box(26), __box(27), __box(28),  
                                 __box(29), __box(30) };  
  
   return a1;  
}  
```  
  
 新しい配列の構文:  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
  
   return a1;  
}  
```  
  
### <a name="explicit-clr-array-declaration"></a>明示的な CLR 配列の宣言  
 マネージ拡張配列の構文:  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 新しい配列の構文:  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 初めて使用する言語: gcnew を明示的な配列の初期化  
  
```  
// explicit initialization list follow gcnew   
// is not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## <a name="scalar-properties"></a>スカラー プロパティ  
 マネージ拡張プロパティの構文:  
  
```  
public __gc __sealed class Vector {  
   double _x;  
  
public:  
   __property double get_x(){ return _x; }  
   __property void set_x( double newx ){ _x = newx; }  
};  
```  
  
 新しいプロパティの構文:  
  
```  
public ref class Vector sealed {   
   double _x;  
  
public:  
   property double x   
   {  
      double get()             { return _x; }  
      void   set( double newx ){ _x = newx; }  
   } // Note: no semi-colon  
};  
```  
  
 初めて使用する言語: 単純なプロパティ  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   // backing store is not accessible  
   property double x;   
};  
```  
  
 参照してください[プロパティ宣言](../dotnet/property-declaration.md)詳細についてはします。  
  
## <a name="indexed-properties"></a>インデックス付きプロパティ  
 マネージ拡張のインデックス付きプロパティの構文。  
  
```  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }  
   __property int get_Item( int r, int c ) { return mat[r,c]; }  
};  
```  
  
 新しいインデックス付きプロパティの構文:  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 初めて使用する言語: インデックス付きプロパティをクラス レベル  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //     Matrix mat;  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer  
  
   property float default [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 参照してください[プロパティ インデックスの宣言](../dotnet/property-index-declaration.md)詳細についてはします。  
  
## <a name="overloaded-operators"></a>オーバーロードされた演算子  
 マネージ拡張演算子のオーバー ロードの構文:  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
};  
  
int main() {  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc = Vector::op_Division( pa, 4.8916 );  
  
   if ( Vector::op_Equality( pa, pc ))  
      ;  
}  
```  
  
 新しい演算子のオーバー ロードの構文:  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
};  
  
int main() {  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475, 4.8916, -1.23 );  
  
   Vector^ pc = pa / 4.8916;  
   if ( pc == pa )  
      ;  
}  
```  
  
 参照してください[オーバー ロードされた演算子](../dotnet/overloaded-operators.md)詳細についてはします。  
  
## <a name="conversion-operators"></a>変換演算子  
 マネージ拡張変換演算子の構文:  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 新しい変換演算子の構文:  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 参照してください[変換演算子に変更](../dotnet/changes-to-conversion-operators.md)詳細についてはします。  
  
## <a name="explicit-override-of-an-interface-member"></a>インターフェイス メンバーの明示的なオーバーライド  
 マネージ拡張の明示的なオーバーライド構文  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 新しい明示的なオーバーライド構文:  
  
```  
public ref class R : public ICloneable {  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R   
   virtual R^ Clone();  
};  
```  
  
 参照してください[インターフェイス メンバーの明示的なオーバーライド](../dotnet/explicit-override-of-an-interface-member.md)詳細についてはします。  
  
## <a name="private-virtual-functions"></a>プライベート仮想関数  
 マネージ拡張プライベート仮想関数の構文:  
  
```  
__gc class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
__gc class Derived : public Base {  
public:  
   // ok: g() overrides Base::g()  
   virtual void g();  
};  
```  
  
 新しいプライベート仮想関数の構文  
  
```  
ref class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
ref class Derived : public Base {  
public:  
   // error: cannot override: Base::g() is inaccessible  
   virtual void g() override;  
};  
```  
  
 参照してください[プライベート仮想関数](../dotnet/private-virtual-functions.md)詳細についてはします。  
  
## <a name="clr-enum-type"></a>CLR 列挙型  
 マネージ拡張列挙型の構文:  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};    
```  
  
 新しい列挙型の構文:  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 この小さな構文変更とは別には、CLR 列挙型の動作をさまざまな方法で変更されています。  
  
-   CLR 列挙型の事前宣言がサポートされていません。  
  
-   組み込みの数値型とオブジェクトのクラス階層間でオーバー ロードの解決は、管理されている拡張機能と Visual C 間に戻されました。 副作用として、としては、CLR 列挙型は数値型に不要になった暗黙的に変換します。  
  
-   新しい構文では、CLR 列挙型は、マネージ拡張の場合はそれ自体のスコープを維持します。 以前は、列挙子でした; 列挙型のコンテナーのスコープ内に表示されます。ここで、列挙子は列挙型のスコープ内にカプセル化します。  
  
 参照してください[CLR 列挙型](../dotnet/clr-enum-type.md)詳細についてはします。  
  
## <a name="removal-of-box-keyword"></a>_ _Box キーワードの削除  
 マネージ拡張構文をボックス化します。  
  
```  
Object *o = __box( 1024 ); // explicit boxing  
```  
  
 新しいボックス化の構文:  
  
```  
Object ^o = 1024; // implicit boxing  
```  
  
 参照してください[のボックス化された値を識別するハンドルを追跡](../dotnet/a-tracking-handle-to-a-boxed-value.md)詳細についてはします。  
  
## <a name="pinning-pointer"></a>固定ポインター  
 マネージ拡張のポインターの構文を固定します。  
  
```  
__gc struct H { int j; };  
  
int main() {  
   H * h = new H;  
   int __pin * k = & h -> j;  
};  
```  
  
 新しい固定ポインターの構文:  
  
```  
ref struct H { int j; };  
  
int main() {  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
}  
```  
  
 参照してください[値型セマンティクス](../dotnet/value-type-semantics.md)詳細についてはします。  
  
## <a name="typeof-keyword-becomes-typeid"></a>_ _typeof キーワード typeid になります  
 マネージ拡張 typeof 構文:  
  
```  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 新しい typeid 構文:  
  
```  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
 参照してください[typeof が t::typeid へ移動](../dotnet/typeof-goes-to-t-typeid.md)詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [C + +/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)   
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)


