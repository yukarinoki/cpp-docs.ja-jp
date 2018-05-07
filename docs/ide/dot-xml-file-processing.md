---
title: .Xml ファイルの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- XML documentation, processing XML file
ms.assetid: e70fdeae-80ac-4872-ab24-771c5635cfbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cf6f5660e1aaeaeff4050bb80009eda7d14c3ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="xml-file-processing"></a>.Xml ファイルの処理
コンパイラは、ドキュメントを生成するためにタグ付けされたコードのコンストラクトごとに、ID 文字列を生成します。 詳細については、次を参照してください。[タグ ドキュメントのコメントをお勧め](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)です。 ID 文字列によって、コンストラクトは一意に識別されます。 .Xml ファイルを処理するプログラムは、ドキュメントを適用するのに対象の .NET Framework メタデータやリフレクション項目を識別するのに ID 文字列を使用できます。  
  
 .Xml ファイルは、コードの階層表現ではありませんが、各要素に対して生成された ID を持つ単純なリスト。  
  
 コンパイラは、次の規則に基づいて ID 文字列を生成します。  
  
-   文字列内の空白文字は配置されません。  
  
-   ID 文字列の最初の部分では、その後にコロン、1 文字で識別されるメンバーの種類を識別します。 使用されるメンバー型は次のとおりです。  
  
    |文字|説明|  
    |---------------|-----------------|  
    |N|namespace<br /><br /> 名前空間にドキュメント コメントを追加することはできません、cref 参照の名前空間にも有効であります。|  
    |T|型: クラス、インターフェイス、構造体、列挙、デリゲート|  
    |D|typedef|  
    |F|フィールド|  
    |P|プロパティ (インデクサーまたはその他のインデックス付きプロパティを含む)|  
    |M|メソッド (コンストラクター、演算子などの特殊なメソッドを含む)|  
    |E|イベント|  
    |!|エラー文字列<br /><br /> あとに続く文字列で、エラーの情報を示します。 Visual C コンパイラでは、解決できないリンクのエラー情報を生成します。|  
  
-   文字列の 2 番目の部分は、項目の完全修飾名で、名前空間のルートから始まります。 アイテム、その外側の型または型、および名前空間の名前は、ピリオドで区切られます。 項目の名前自体にピリオドがある場合、名前のピリオドはハッシュ記号 ('#') に置き換えられます。 項目の名前にはハッシュ記号がないことが前提です。 たとえば、完全修飾名の`String`コンス トラクターは"System.String.#ctor"になります。  
  
-   プロパティおよびメソッドについては、メソッドに引数がある場合は、引数のリストをかっこで囲み、メソッドに続けて指定します。 引数がない場合は、かっこはありません。 引数はコンマで区切られます。 各引数のエンコードは、次に示す .NET Framework のシグネチャでの引数のエンコーディング方法にそのまま従います。  
  
    -   基本データ型。 通常の型 (ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE) は、型の完全修飾名で表されます。  
  
    -   組み込みの型 (たとえば、ELEMENT_TYPE_I4、ELEMENT_TYPE_OBJECT、ELEMENT_TYPE_STRING、ELEMENT_TYPE_TYPEDBYREF や、 および ELEMENT_TYPE_VOID) など、対応する完全な型の完全修飾名として表される**System.Int32**または**System.TypedReference**です。  
  
    -   ELEMENT_TYPE_PTR は、修飾される型に続けて '*' と表されます。  
  
    -   ELEMENT_TYPE_BYREF は、修飾される型に続けて '@' と表されます。  
  
    -   ELEMENT_TYPE_PINNED は、修飾される型に続けて '^' と表されます。 これは Visual C++ コンパイラでは生成されません。  
  
    -   ELEMENT_TYPE_CMOD_REQ は、修飾される型に続けて "&#124;" と修飾子クラスの完全修飾名で表されます。 これは Visual C++ コンパイラでは生成されません。  
  
    -   ELEMENT_TYPE_CMOD_OPT は、修飾される型に続けて "!" と修飾子クラスの完全修飾名で表されます。  
  
    -   ELEMENT_TYPE_SZARRAY は、配列の要素型に続けて "[]" と表されます。  
  
    -   ELEMENT_TYPE_GENERICARRAY は、配列の要素型に続けて "[?]" と表されます。 これは Visual C++ コンパイラでは生成されません。  
  
    -   ELEMENT_TYPE_ARRAY は、[*lowerbound*:`size`,*lowerbound*:`size`] の形式で表されます。ここで、コンマの個数はランク -1 個であり、各次元の下限とサイズは明らかな場合は、10 進数で表されます。 下限またはサイズの指定がない場合は省略されます。 特定の次元で下限およびサイズが省略されている場合は、':' も省略されます。 たとえば、ある 2 次元配列の下限が 1 で、サイズの指定がない場合は、[1:,1:] と表されます。  
  
    -   ELEMENT_TYPE_FNPTR は、"=FUNC:`type`(*signature*)" と表されます。ここで、`type` は戻り値の型であり、*signature* はメソッドの引数です。 引数がない場合、かっこは省略されます。 これは Visual C++ コンパイラでは生成されません。  
  
     次に示すシグネチャ コンポーネントは、オーバーロードされるメソッドの区別には使用されることがないため、表されません。  
  
    -   呼び出し規則  
  
    -   戻り値の型  
  
    -   ELEMENT_TYPE_SENTINEL  
  
-   変換演算子の場合のみ、メソッドの戻り値としてエンコード、' ~' 後にエンコードされる前に、戻り値の型。  
  
-   ジェネリック型では、型の名前の後に、バックチック、ジェネリック型パラメーターの数を示す数値が順に続きます。  たとえば、オブジェクトに適用された  
  
    ```  
    <member name="T:MyClass`2">  
    ```  
  
     として定義されている型の`public class MyClass<T, U>`します。  
  
     ジェネリック型パラメーターを受け取るメソッドでは、ジェネリック型パラメーターを指定して、バック ティックで始まる数値として (たとえば\`0、 \`1)。  各数値は、型のジェネリック パラメーターに対する、0 から始まる配列表記を表しています。  
  
## <a name="example"></a>例  
 次の例は、クラスの ID の文字列を表示して、そのメンバーが生成されます。  
  
```  
// xml_id_strings.cpp  
// compile with: /clr /doc /LD  
///   
namespace N {    
// "N:N"  
  
   /// <see cref="System" />  
   //  <see cref="N:System"/>  
   ref class X {      
   // "T:N.X"  
  
   protected:  
      ///   
      !X(){}     
      // "M:N.X.Finalize", destructor's representation in metadata  
  
   public:  
      ///   
      X() {}     
      // "M:N.X.#ctor"  
  
      ///   
      static X() {}     
      // "M:N.X.#cctor"  
  
      ///   
      X(int i) {}     
      // "M:N.X.#ctor(System.Int32)"  
  
      ///   
      ~X() {}     
      // "M:N.X.Dispose", Dispose function representation in metadata  
  
      ///   
      System::String^ q;     
      // "F:N.X.q"  
  
      ///   
      double PI;     
      // "F:N.X.PI"  
  
      ///   
      int f() { return 1; }     
      // "M:N.X.f"  
  
      ///   
      int bb(System::String ^ s, int % y, void * z) { return 1; }  
      // "M:N.X.bb(System.String,System.Int32@,System.Void*)"  
  
      ///   
      int gg(array<short> ^ array1, array< int, 2 >^ IntArray) { return 0; }   
      // "M:N.X.gg(System.Int16[], System.Int32[0:,0:])"  
  
      ///   
      static X^ operator+(X^ x, X^ xx) { return x; }  
     // "M:N.X.op_Addition(N.X,N.X)"  
  
      ///   
      property int prop;     
      // "M:N.X.prop"  
  
      ///   
      property int prop2 {     
      // "P:N.X.prop2"  
  
         ///   
         int get() { return 0; }  
         // M:N.X.get_prop2  
  
         ///   
         void set(int i) {}  
         // M:N.X.set_prop2(System.Int32)  
      }  
  
      ///   
      delegate void D(int i);   
      // "T:N.X.D"  
  
      ///   
      event D ^ d;   
      // "E:N.X.d"  
  
      ///   
      ref class Nested {};   
      // "T:N.X.Nested"  
  
      ///   
      static explicit operator System::Int32 (X x) { return 1; }   
      // "M:N.X.op_Explicit(N.X!System.Runtime.CompilerServices.IsByValue)~System.Int32"  
   };  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)