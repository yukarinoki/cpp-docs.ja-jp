---
title: pin_ptr (C +/cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
dev_langs:
- C++
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: af0cfe6f3a94aa1bc2afc4e4857864f81099567e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591732"
---
# <a name="pinptr-ccli"></a>pin_ptr (C++/CLI)

宣言を*固定ポインター*、共通言語ランタイムでのみ使用されます。

## <a name="all-runtimes"></a>すべてのランタイム

(この言語機能にはランタイムに適用される特記事項がありません。)

## <a name="windows-runtime"></a>Windows ランタイム

(この言語機能は Windows ランタイムでないサポート)。

## <a name="common-language-runtime"></a>共通言語ランタイム

A*固定ポインター*内部ポインターをオブジェクトを妨げる指していますが、ガベージ コレクトされたヒープに移動します。 つまり、固定ポインターの値は、共通言語ランタイムでは変更されません。 これは、機能は、アンマネージ関数呼び出しの解決中に、アドレスは予期せず変更されないようにするアンマネージ関数にマネージ クラスのアドレスを渡すときに必要です。

### <a name="syntax"></a>構文

```cpp
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;
```

### <a name="parameters"></a>パラメーター

*cv_qualifier*  
**const**または**揮発性**修飾子。 固定ポインターは、既定では、**揮発性**します。 ピンされたポインターを宣言するエラーではなく、冗長になる**揮発性**します。

*type*  
型*初期化子*します。

*var*  
名前、 **pin_ptr**変数。

*initializer*  
参照型、マネージ配列の場合、またはネイティブ ポインターに割り当てることができるその他のオブジェクトの要素のメンバー。

### <a name="remarks"></a>Remarks

A **pin_ptr**ネイティブ ポインターの機能のスーパー セットを表します。 そのため、何もネイティブ ポインターに割り当てることができますに割り当てることも、 **pin_ptr**します。 比較、ポインターの算術演算などのネイティブ ポインターとして同じ一連の操作を実行する内部ポインターが許可されます。

オブジェクトまたはサブオブジェクト マネージ クラスのピン留めできます、この場合、共通言語ランタイムは移動ガベージ コレクション中にします。 このプリンシパルの使用では、マネージ データへのポインターをアンマネージ関数呼び出しの実際のパラメーターとして渡します。 コレクション サイクル中には、ランタイムは、固定ポインター用に作成されたメタデータを検査しが指す項目に移動しません。

値フィールドをピン留めもオブジェクトをピン留めつまり、プリミティブ型のフィールドまたは値を入力します。 ただし、フィールドがハンドルを追跡することによって宣言 (`%`) がピン留めされていません。

マネージ オブジェクトで定義されている下位のオブジェクトをピン留めすると、オブジェクト全体をピン留めの効果があります。

新しい値を指すピン ポインターを再割り当てする場合、以前のインスタンスを指すと見なされなくピン留めします。

オブジェクトが固定されている中にのみ、 **pin_ptr**それを指しています。 固定ポインターがスコープ外になるかに設定されているときに不要になったオブジェクトが固定されている[nullptr](../windows/nullptr-cpp-component-extensions.md)します。 後に、 **pin_ptr**ガベージ コレクターによって、ヒープにピン留めされたオブジェクトのスコープ外を移動できます。 まだオブジェクトを指す任意のネイティブ ポインターは更新されませんし、うち 1 つを逆参照すると、回復不能な例外が生じる可能性があります。

オブジェクトを固定ポインターが指していない場合 (すべて固定ポインターがスコープ外の問題が発生しました、他のオブジェクトへのポイントに再割り当てされたまたは割り当てられていた[nullptr](../windows/nullptr-cpp-component-extensions.md))、オブジェクトにピン留めすることが保証されます。

固定ポインターは、参照ハンドル、値型またはボックス化された型のハンドル、マネージ配列の要素またはマネージ型のメンバーを指定できます。 参照型を指していることはできません。

アドレスの取得、 **pin_ptr**ネイティブ オブジェクトへのポインターが未定義の動作を発生します。

固定ポインターは、スタックの非静的ローカル変数としてだけ宣言できます。

固定ポインターとしてを使用できません。

- 関数パラメーター

- 関数の戻り値の型

- クラスのメンバー

- キャストの対象の型。

**pin_ptr**では、`cli`名前空間。 詳細については、次を参照してください。[プラットフォーム、既定では、および cli 名前空間](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)します。

内部ポインターの詳細については、次を参照してください。 [interior_ptr (C +/cli CLI)](../windows/interior-ptr-cpp-cli.md)します。

固定ポインターの詳細については、次を参照してください。[方法: ピン ポインターと配列](../windows/how-to-pin-pointers-and-arrays.md)と[方法: 固定ポインターの宣言と値型](../windows/how-to-declare-pinning-pointers-and-value-types.md)します。

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

次の例では**pin_ptr**配列の最初の要素の位置を制限します。

```cpp
// pin_ptr_1.cpp
// compile with: /clr
using namespace System;
#define SIZE 10

#pragma unmanaged
// native function that initializes an array
void native_function(int* p) {
   for(int i = 0 ; i < 10 ; i++)  
    p[i] = i;
}
#pragma managed

public ref class A {
private:
   array<int>^ arr;   // CLR integer array

public:
   A() {
      arr = gcnew array<int>(SIZE);
   }

   void load() {
   pin_ptr<int> p = &arr[0];   // pin pointer to first element in arr
   int* np = p;   // pointer to the first element in arr
   native_function(np);   // pass pointer to native function
   }

   int sum() {
      int total = 0;
      for (int i = 0 ; i < SIZE ; i++)  
         total += arr[i];
      return total;
   }
};

int main() {
   A^ a = gcnew A;
   a->load();   // initialize managed array using the native function
   Console::WriteLine(a->sum());
}
```

```Output
45
```

次の例は、内部ポインターをピン留めをポインターに変換できることと、address-of 演算子の戻り値の型を (`&`) 内部ポインターは、オペランドが、マネージ ヒープ上にある場合。

```cpp
// pin_ptr_2.cpp
// compile with: /clr
using namespace System;

ref struct G {
   G() : i(1) {}
   int i;
};

ref struct H {
   H() : j(2) {}
   int j;
};

int main() {
   G ^ g = gcnew G;   // g is a whole reference object pointer
   H ^ h = gcnew H;

   interior_ptr<int> l = &(g->i);   // l is interior pointer

   pin_ptr<int> k = &(h->j);   // k is a pinning interior pointer

   k = l;   // ok
   Console::WriteLine(*k);
};
```

```Output
1
```

次の例では、固定ポインターが別の型にキャストできることを示します。

```cpp
// pin_ptr_3.cpp
// compile with: /clr
using namespace System;

ref class ManagedType {
public:
   int i;
};

int main() {
   ManagedType ^mt = gcnew ManagedType;
   pin_ptr<int> pt = &mt->i;
   *pt = 8;
   Console::WriteLine(mt->i);

   char *pc = ( char* ) pt;
   *pc = 255;
   Console::WriteLine(mt->i);
}
```

```Output
8
255
```