---
description: 詳細については、「参照型の C++ スタックセマンティクス」を参照してください。
title: 参照型の C++ スタック セマンティクス
ms.date: 11/04/2016
helpviewer_keywords:
- reference types, C++ stack semantics for
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
ms.openlocfilehash: a7f377225e70eff4093d4b9820a3d14644b96f58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124320"
---
# <a name="c-stack-semantics-for-reference-types"></a>参照型の C++ スタック セマンティクス

Visual Studio 2005 より前では、参照型のインスタンスは、 **`new`** ガベージコレクションヒープにオブジェクトを作成した演算子を使用してのみ作成できました。 ただし、スタックでネイティブ型のインスタンスを作成する場合と同じ構文を使用して、参照型のインスタンスを作成できるようになりました。 そのため、参照型のオブジェクトを作成するために [ref new, gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) を使用する必要はありません。 また、オブジェクトがスコープ外に出ると、コンパイラはオブジェクトのデストラクターを呼び出します。

## <a name="remarks"></a>解説

スタックセマンティクスを使用して参照型のインスタンスを作成すると、コンパイラは、ガベージコレクションヒープにインスタンスを内部で作成します (を使用 **`gcnew`** )。

関数のシグネチャまたは戻り値の型に値による参照型のインスタンスが含まれている場合、関数は、(modreq を使用した) 特別な処理を必要とするようにメタデータでマークされます。 この特別な処理は、現在 Visual C++ クライアントによってのみ提供されています。他の言語では、現在、スタックセマンティクスで作成された参照型を使用する関数またはデータの使用はサポートされていません。

**`gcnew`** スタックセマンティクスの代わりに (動的割り当て) を使用する理由の1つは、型にデストラクターがない場合です。 また、関数を Visual C++ 以外の言語で使用する場合は、関数シグネチャでスタックセマンティクスで作成された参照型を使用することはできません。

コンパイラは、参照型のコピーコンストラクターを生成しません。 そのため、シグネチャで値渡しの参照型を使用する関数を定義する場合は、参照型のコピーコンストラクターを定義する必要があります。 参照型のコピーコンストラクターには、という形式のシグネチャがあり `R(R%){}` ます。

コンパイラは、参照型の既定の代入演算子を生成しません。 代入演算子を使用すると、スタックセマンティクスを使用してオブジェクトを作成し、スタックセマンティクスを使用して作成された既存のオブジェクトを使用してオブジェクトを初期化できます。 参照型の代入演算子には、という形式のシグネチャがあり `void operator=( R% ){}` ます。

型のデストラクターが重要なリソースを解放し、参照型にスタックセマンティクスを使用する場合は、デストラクターを明示的に呼び出す必要はありません (またはを呼び出す必要はありません **`delete`** )。 参照型のデストラクターの詳細については、「 [方法: クラスと構造体を定義および使用する (C++/cli)」の「デストラクターとファイナライザー](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。

コンパイラによって生成された代入演算子は、次の追加機能を備えた通常の標準 C++ 規則に従います。

- 型が参照型へのハンドルである非静的データメンバーは、シャローコピーされます (型がポインターである非静的データメンバーのように扱われます)。

- 型が値型である非静的データメンバーは、シャローコピーされます。

- 型が参照型のインスタンスである非静的データメンバーは、参照型のコピーコンストラクターへの呼び出しを呼び出します。

また、コンパイラは、 `%` スタックセマンティクスを使用して作成された参照型のインスタンスを基になるハンドル型に変換する単項演算子も提供します。

次の参照型は、スタックセマンティクスでは使用できません。

- [delegate (C++ コンポーネント拡張)](../extensions/delegate-cpp-component-extensions.md)

- [配列](../extensions/arrays-cpp-component-extensions.md)

- <xref:System.String>

## <a name="example"></a>例

### <a name="description"></a>説明

次のコードサンプルは、スタックセマンティクスを使用して参照型のインスタンスを宣言する方法、代入演算子とコピーコンストラクターがどのように動作するか、およびスタックセマンティクスを使用して作成された参照型を使用して追跡参照を初期化する方法を示しています。

### <a name="code"></a>コード

```cpp
// stack_semantics_for_reference_types.cpp
// compile with: /clr
ref class R {
public:
   int i;
   R(){}

   // assignment operator
   void operator=(R% r) {
      i = r.i;
   }

   // copy constructor
   R(R% r) : i(r.i) {}
};

void Test(R r) {}   // requires copy constructor

int main() {
   R r1;
   r1.i = 98;

   R r2(r1);   // requires copy constructor
   System::Console::WriteLine(r1.i);
   System::Console::WriteLine(r2.i);

   // use % unary operator to convert instance using stack semantics
   // to its underlying handle
   R ^ r3 = %r1;
   System::Console::WriteLine(r3->i);

   Test(r1);

   R r4;
   R r5;
   r5.i = 13;
   r4 = r5;   // requires a user-defined assignment operator
   System::Console::WriteLine(r4.i);

   // initialize tracking reference
   R % r6 = r4;
   System::Console::WriteLine(r6.i);
}
```

### <a name="output"></a>出力

```Output
98
98
98
13
13
```

## <a name="see-also"></a>関連項目

[クラスと構造体](../extensions/classes-and-structs-cpp-component-extensions.md)
