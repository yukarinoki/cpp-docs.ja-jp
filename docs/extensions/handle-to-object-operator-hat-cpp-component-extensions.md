---
title: オブジェクト演算子 (^) へのハンドル (C++/CLI および C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
ms.openlocfilehash: 3d08b2294da1599282feeb1739331c31d64a9e59
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358330"
---
# <a name="handle-to-object-operator---ccli-and-ccx"></a>オブジェクト演算子 (^) へのハンドル (C++/CLI および C++/CX)

*ハンドル宣言子*(`^`,"hat" と発音) は、オブジェクトがアクセスできなくなったと判断したときに、宣言されたオブジェクトが自動的に削除されるように型[指定子](../cpp/overview-of-declarators.md)を変更します。

## <a name="accessing-the-declared-object"></a>宣言されたオブジェクトへのアクセス

ハンドル宣言子を指定して宣言した変数は、オブジェクトへのポインターのように動作します。 ただし、変数はオブジェクト全体を指し示します。オブジェクトのメンバーを指すことはできません。また、ポインター演算をサポートしません。 オブジェクトにアクセスするには間接演算子 (`*`) を使用し、オブジェクトのメンバーにアクセスするには矢印のメンバー アクセス演算子 (`->`) を使用します。

## <a name="windows-runtime"></a>Windows ランタイム

コンパイラは、COM *参照カウント* メカニズムを使用して、オブジェクトがもう使用されず、削除してよいかどうかを判断します。 これが可能なのは、Windows ランタイム インターフェイスから派生するオブジェクトが実際に COM オブジェクトであるためです。 参照カウントは、オブジェクトが作成されるかコピーされるとインクリメントされ、オブジェクトが null に設定されるかスコープから外れるとデクリメントされます。 参照カウントがゼロになると、オブジェクトは直ちに自動的に削除されます。

ハンドル宣言子の利点は、煩雑でエラーが発生しやすいプロセスであるオブジェクトについて、COM では参照カウントを明示的に管理する必要があるということです。 つまり、参照カウントをインクリメントおよびデクリメントするには、オブジェクトの AddRef() メソッドと Release() メソッドを呼び出す必要があります。 ただし、ハンドル宣言子を使用してオブジェクトを宣言する場合、コンパイラでは、参照カウントを自動的に調整するコードを生成します。

オブジェクトをインスタンス化する方法の詳細については、「[ref new](ref-new-gcnew-cpp-component-extensions.md)」を参照してください。

## <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

システムは、CLR *ガベージ コレクター* メカニズムを使用して、オブジェクトがもう使用されず、削除してよいかどうかを判断します。 共通言語ランタイムが、オブジェクトを割り当てるヒープを保持し、プログラムでマネージド参照 (変数) を使用します。それによりヒープ内のオブジェクトの場所が示されます。 オブジェクトがもう使用されなくなると、オブジェクトがヒープで占有していたメモリが解放されます。 ガベージ コレクターは、解放済みメモリの使用を改善するために、定期的にヒープを圧縮します。 ヒープを圧縮すると、ヒープのオブジェクトを移動できます。これにより、マネージド参照によって参照される場所が無効になります。 ただし、ガベージ コレクターは、すべてのマネージド参照の場所を認識しており、ヒープ内のオブジェクトの現在の場所を示すようにマネージド参照を自動的に更新します。

ネイティブ C++ ポインター (`*`) と参照 (`&`) は、マネージド参照ではないため、それらが指し示すアドレスをガベージ コレクターは自動的に更新できません。 この問題を解決するには、ガベージ コレクターが認識しており自動的に更新できる変数を、ハンドル宣言子を使用して指定します。

詳細については、「[方法 : ネイティブ型でハンドルを宣言](../dotnet/how-to-declare-handles-in-native-types.md)する 」を参照してください。

### <a name="examples"></a>例

このサンプルは、マネージド ヒープ上で参照型のインスタンスを作成する方法を示しています。  また、このサンプルでは、1 つのハンドルを別のハンドルで初期化することができ、その結果、ガベージ コレクトされたマネージド ヒープ上で同じオブジェクトへの参照が 2 つ作成されることも示しています。 1 つのハンドルに [nullptr](nullptr-cpp-component-extensions.md) を割り当てても、オブジェクトはガベージ コレクションの対象としてマークされないことに注意してください。

```cpp
// mcppv2_handle.cpp
// compile with: /clr
ref class MyClass {
public:
   MyClass() : i(){}
   int i;
   void Test() {
      i++;
      System::Console::WriteLine(i);
   }
};

int main() {
   MyClass ^ p_MyClass = gcnew MyClass;
   p_MyClass->Test();

   MyClass ^ p_MyClass2;
   p_MyClass2 = p_MyClass;

   p_MyClass = nullptr;
   p_MyClass2->Test();
}
```

```Output
1
2
```

次の例では、マネージド ヒープ上のオブジェクト (オブジェクトの型はボックス化された値型) へのハンドルを宣言する方法を示しています。 また、このサンプルでは、ボックス化されたオブジェクトから値型を取得する方法も示します。

```cpp
// mcppv2_handle_2.cpp
// compile with: /clr
using namespace System;

void Test(Object^ o) {
   Int32^ i = dynamic_cast<Int32^>(o);

   if(i)
      Console::WriteLine(i);
   else
      Console::WriteLine("Not a boxed int");
}

int main() {
   String^ str = "test";
   Test(str);

   int n = 100;
   Test(n);
}
```

```Output
Not a boxed int
100
```

この例では、任意のオブジェクトを指し示す`void*` ポインターを使用した C++ の共通の表現形式が、任意の参照クラスへのハンドルも保持できる `Object^` で置き換えられることを示しています。 また、配列やデリゲートなど、すべての型がオブジェクト ハンドルに変換できることも示しています。

```cpp
// mcppv2_handle_3.cpp
// compile with: /clr
using namespace System;
using namespace System::Collections;
public delegate void MyDel();
ref class MyClass {
public:
   void Test() {}
};

void Test(Object ^ x) {
   Console::WriteLine("Type is {0}", x->GetType());
}

int main() {
   // handle to Object can hold any ref type
   Object ^ h_MyClass = gcnew MyClass;

   ArrayList ^ arr = gcnew ArrayList();
   arr->Add(gcnew MyClass);

   h_MyClass = dynamic_cast<MyClass ^>(arr[0]);
   Test(arr);

   Int32 ^ bi = 1;
   Test(bi);

   MyClass ^ h_MyClass2 = gcnew MyClass;

   MyDel^ DelInst = gcnew MyDel(h_MyClass2, &MyClass::Test);
   Test(DelInst);
}
```

```Output
Type is System.Collections.ArrayList

Type is System.Int32

Type is MyDel
```

このサンプルは、ハンドルが逆参照できること、および逆参照されるハンドル経由でメンバーにアクセスできることを示しています。

```cpp
// mcppv2_handle_4.cpp
// compile with: /clr
using namespace System;
value struct DataCollection {
private:
   int Size;
   array<String^>^ x;

public:
   DataCollection(int i) : Size(i) {
      x = gcnew array<String^>(Size);
      for (int i = 0 ; i < Size ; i++)
         x[i] = i.ToString();
   }

   void f(int Item) {
      if (Item >= Size)
      {
         System::Console::WriteLine("Cannot access array element {0}, size is {1}", Item, Size);
         return;
      }
      else
         System::Console::WriteLine("Array value: {0}", x[Item]);
   }
};

void f(DataCollection y, int Item) {
   y.f(Item);
}

int main() {
   DataCollection ^ a = gcnew DataCollection(10);
   f(*a, 7);   // dereference a handle, return handle's object
   (*a).f(11);   // access member via dereferenced handle
}
```

```Output
Array value: 7

Cannot access array element 11, size is 10
```

このサンプルでは、int が`&`ガベージ コレクション ヒープに格納され、ネイティブ参照がマネージ ヒープ内のオブジェクトの移動を追跡しない場合があるため、ネイティブ参照 ( ) がマネージ型の**int**メンバーにバインドできない場合を示します。 **int** 解決策は、ローカル変数を使用すること、または、`&` を `%` に変更して、追跡参照にすることです。

```cpp
// mcppv2_handle_5.cpp
// compile with: /clr
ref struct A {
   void Test(unsigned int &){}
   void Test2(unsigned int %){}
   unsigned int i;
};

int main() {
   A a;
   a.i = 9;
   a.Test(a.i);   // C2664
   a.Test2(a.i);   // OK

   unsigned int j = 0;
   a.Test(j);   // OK
}
```

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

## <a name="see-also"></a>関連項目

[NET および UWP 用のコンポーネント拡張機能](component-extensions-for-runtime-platforms.md)<br/>
[参照演算子の追跡](tracking-reference-operator-cpp-component-extensions.md)
