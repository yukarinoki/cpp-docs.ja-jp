---
title: align (C++)
ms.date: 12/17/2018
f1_keywords:
- align_cpp
helpviewer_keywords:
- align __declspec keyword
- __declspec keyword [C++], align
ms.assetid: 9cb63f58-658b-4425-ac47-af8eabfc5878
ms.openlocfilehash: 0a1212f1c78f49029f82be5a2f5d82ea1788b6e0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227661"
---
# <a name="align-c"></a>align (C++)

Visual Studio 2015 以降では、C++ 11 の標準指定子を使用して、 **`alignas`** アラインメントを制御します。 詳細については、「[アラインメント](../cpp/alignment-cpp-declarations.md)」を参照してください。

**Microsoft 固有の仕様**

ユーザー定義データ (関数の静的割り当てや自動データなど) のアラインメントを正確に制御するには、`__declspec(align(#))` を使用します。

## <a name="syntax"></a>構文

> **__declspec (align (** *#* **))** *宣言子*

## <a name="remarks"></a>解説

最新のプロセッサ命令を使用するアプリケーションの記述では、いくつかの新しい制約や問題があります。 多くの新しい命令では、16バイト境界にアラインされたデータが必要です。 また、頻繁に使用されるデータをプロセッサのキャッシュラインサイズに合わせて配置すると、キャッシュのパフォーマンスが向上します。 たとえば、サイズが32バイト未満の構造体を定義する場合は、その構造体型のオブジェクトが効率的にキャッシュされるように32バイトのアラインメントが必要になることがあります。

\#アラインメント値を指定します。 有効なエントリは、1 ～ 8192 (バイト) の 2 の整数乗 (2、4、8、16、32、64 など) です。 `declarator`は、固定されたものとして宣言しているデータです。

型のアラインメント要件である型の値を返す方法について `size_t` は、「」を参照してください [`alignof`](../cpp/alignof-operator.md) 。 64ビットプロセッサを対象とする場合に、整列されていないポインターを宣言する方法については、「」を参照してください [`__unaligned`](../cpp/unaligned.md) 。

は、、、またはを `__declspec(align(#))` 定義するとき **`struct`** **`union`** **`class`** 、または変数を宣言するときに使用できます。

コンパイラは、コピーまたはデータ変換操作中に、データのアラインメント属性を保証または保持しようとしません。 たとえば、では、 [`memcpy`](../c-runtime-library/reference/memcpy-wmemcpy.md) で宣言された構造体を `__declspec(align(#))` 任意の場所にコピーできます。 通常のアロケーター (、 [`malloc`](../c-runtime-library/reference/malloc.md) 、C++、Win32 アロケーターなど) は、通常、構造体 [`operator new`](new-operator-cpp.md) `__declspec(align(#))` または構造体の配列に対して十分にアラインされていないメモリを返します。 コピーまたはデータ変換操作の転送先が正しく配置されていることを保証するには、を使用し [`_aligned_malloc`](../c-runtime-library/reference/aligned-malloc.md) ます。 または、独自のアロケーターを記述します。

関数パラメーターにアラインメントを指定することはできません。 アラインメント属性を持つデータをスタック上の値で渡すと、そのアラインメントは呼び出し規約によって制御されます。 呼び出された関数でデータのアラインメントが重要な場合は、使用する前にパラメーターを正常にアラインされたメモリにコピーします。

を使用しない `__declspec(align(#))` 場合、コンパイラは一般に、ターゲットプロセッサとデータサイズ、32ビットプロセッサで最大4バイトの境界、64ビットプロセッサ上の8バイトの境界に基づいて、自然な境界にデータを配置します。 クラスまたは構造体のデータは、自然なアラインメントと現在のパッキング設定 (またはコンパイラオプションから) の最小値でクラスまたは構造体に配置され `#pragma pack` `/Zp` ます。

`__declspec(align(#))` を使用する例を次に示します。

```cpp
__declspec(align(32)) struct Str1{
   int a, b, c, d, e;
};
```

この型には、32 バイト アラインメント属性が設定されました。 これは、すべての静的インスタンスと自動インスタンスが32バイト境界で開始されることを意味します。 この型でメンバーとして宣言された追加の構造体型は、この型のアラインメント属性を保持します。つまり、要素としてを持つ構造体は、少なくとも `Str1` 32 のアラインメント属性を持ちます。

ここで `sizeof(struct Str1)` は、は32と等しくなります。 これは、オブジェクトの配列が `Str1` 作成され、配列のベースが32バイトでアラインされている場合、配列の各メンバーも32バイトでアラインされていることを意味します。 動的メモリにベースが正しくアラインされている配列を作成するには、を使用し [`_aligned_malloc`](../c-runtime-library/reference/aligned-malloc.md) ます。 または、独自のアロケーターを記述します。

**`sizeof`** 任意の構造体の値は、最後のメンバーのオフセットに、そのメンバーのサイズを加えたものであり、最も近いメンバーのアラインメント値の倍数または構造体のアラインメント値のどちらか大きい方に切り上げられます。

コンパイラは、構造体のアラインメントにこれらの規則を使用します。

- `__declspec(align(#))` でオーバーライドしない限り、スカラー構造体のメンバーのアラインメントは、そのサイズと現在のパッキング設定の最小値になります。

- `__declspec(align(#))` でオーバーライドされない限り、構造体のアラインメントは、そのメンバーの個々のアラインメントの最大値になります。

- 構造体メンバーは、その親構造体の先頭からのオフセット位置に配置されます。これは、その配置の最小倍数であり、前のメンバーの最後のオフセットに等しいかそれより大きい値になります。

- 構造体のサイズは、アラインメントの最小倍数であり、かつ最後のメンバーの最後のオフセットに等しいかそれよりも大きくなります。

`__declspec(align(#))` では、単にアラインメントの制限が多くなることがあります。

詳細については、次を参照してください。

- [`align`例](#vclrfalignexamples)

- [定義 (新しい型を)`__declspec(align(#))`](#vclrf_declspecaligntypedef)

- [スレッド ローカル ストレージのデータのアライン](#vclrfthreadlocalstorageallocation)

- [`align`データパッキングのしくみ](#vclrfhowalignworkswithdatapacking)

- [構造体のアラインメントの例](../build/x64-software-conventions.md#examples-of-structure-alignment)(x64 固有)

## <a name="align-examples"></a><a name="vclrfalignexamples"></a>整列の例

次の例では、`__declspec(align(#))` がデータ構造体のサイズとアラインメントにどのような影響を与えるかを示します。 この例では、次の定義を前提とします。

```cpp
#define CACHE_LINE  32
#define CACHE_ALIGN __declspec(align(CACHE_LINE))
```

次の例では、`S1` 構造体は `__declspec(align(32))` を使用して定義されます。 変数定義または他の型宣言で `S1` を使用すると、すべて 32 バイトでアラインされます。 `sizeof(struct S1)` は 32 を返し、`S1` では 4 つの整数の保持に必要な 16 バイトの後に 16 バイトのパディングが挿入されます。 各 **`int`** メンバーには4バイトのアラインメントが必要ですが、構造体自体のアラインメントは32として宣言されています。 次に、全体的なアラインメントは32です。

```cpp
struct CACHE_ALIGN S1 { // cache align all instances of S1
   int a, b, c, d;
};
struct S1 s1;   // s1 is 32-byte cache aligned
```

次の例では、`sizeof(struct S2)` は 16 を返します。これはメンバーのサイズの合計と一致します。この値が最大アラインメント要件の倍数 (8 の倍数) になっているためです。

```cpp
__declspec(align(8)) struct S2 {
   int a, b, c, d;
};
```

次の例では、`sizeof(struct S3)` は 64 を返します。

```cpp
struct S3 {
   struct S1 s1;   // S3 inherits cache alignment requirement
                  // from S1 declaration
   int a;         // a is now cache aligned because of s1
                  // 28 bytes of trailing padding
};
```

次の例では、`a` で自然なアラインメントが行われる (この場合は 4 バイトにアラインされる) ことに注意してください。 ただし、`S1` は 32 バイトでアラインする必要があります。 28バイトのパディングが続く `a` ため、は `s1` オフセット32から開始します。 `S4`は、のアラインメント要件を継承し `S1` ます。これは、構造体のアラインメント要件の最大値であるためです。 `sizeof(struct S4)` は 64 を返します。

```cpp
struct S4 {
   int a;
   // 28 bytes padding
   struct S1 s1;      // S4 inherits cache alignment requirement of S1
};
```

次の 3 つの変数宣言も `__declspec(align(#))` を使用します。 それぞれの場合で、変数は 32 バイトでアラインする必要があります。 配列では、配列の各メンバーではなく、配列のベースアドレスが32バイトでアラインされています。 **`sizeof`** を使用する場合、各配列メンバーの値は影響を受け `__declspec(align(#))` ません。

```cpp
CACHE_ALIGN int i;
CACHE_ALIGN int array[128];
CACHE_ALIGN struct s2 s;
```

配列の各メンバーをアラインするには、次のようなコードを使用する必要があります。

```cpp
typedef CACHE_ALIGN struct { int a; } S5;
S5 array[10];
```

次の例では、構造体自体のアラインメントと最初の要素のアラインメントによる影響が同じであることに注意してください。

```cpp
CACHE_ALIGN struct S6 {
   int a;
   int b;
};

struct S7 {
   CACHE_ALIGN int a;
               int b;
};
```

`S6` と `S7` では、アラインメント、割り当て、サイズの属性が同じです。

次の例では、a、b、c、および d の開始アドレスのアラインメントは、それぞれ 4、1、4、および 1 です。

```cpp
void fn() {
   int a;
   char b;
   long c;
   char d[10]
}
```

メモリがヒープ上に割り当てられる場合のアラインメントは、どの割り当て関数が呼び出されるかによって異なります。  たとえば、`malloc` を使用する場合、結果はオペランドのサイズによって決まります。 *Arg* >が8の場合、返されるメモリは8バイトでアラインされます。 *Arg* < 8 の場合、返されるメモリのアラインメントは、最初の2の累乗で、 *arg*より小さい値になります。 たとえば、を使用すると、 `malloc(7)` アラインメントは4バイトになります。

## <a name="defining-new-types-with-__declspecalign"></a><a name="vclrf_declspecaligntypedef"></a>定義 (新しい型を)`__declspec(align(#))`

型のアラインメントを定義できます。

たとえば、次のようにアラインメント値を指定してを定義でき **`struct`** ます。

```cpp
struct aType {int a; int b;};
typedef __declspec(align(32)) struct aType bType;
```

現在、 `aType` と `bType` は同じサイズ (8 バイト) ですが、型の変数 `bType` は32バイトでアラインされています。

## <a name="aligning-data-in-thread-local-storage"></a><a name="vclrfthreadlocalstorageallocation"></a>スレッドローカルストレージでのデータの整列

`__declspec(thread)` 属性を使用して作成され、イメージ内の TLS セクションに配置された静的なスレッド ローカル ストレージ (TLS: Thread-Local Storage) は、通常の静的データとまったく同じようにアラインメントされます。 TLS データを作成するために、オペレーティング システムは、TLS セクションのサイズのメモリを割り当て、TLS セクションのアラインメント属性に従います。

次の例では、アラインされたデータをスレッド ローカル ストレージに配置するさまざまな方法を示します。

```cpp
// put an aligned integer in TLS
__declspec(thread) __declspec(align(32)) int a;

// define an aligned structure and put a variable of the struct type
// into TLS
__declspec(thread) __declspec(align(32)) struct F1 { int a; int b; } a;

// create an aligned structure
struct CACHE_ALIGN S9 {
   int a;
   int b;
};
// put a variable of the structure type into TLS
__declspec(thread) struct S9 a;
```

## <a name="how-align-works-with-data-packing"></a><a name="vclrfhowalignworkswithdatapacking"></a>`align`データパッキングのしくみ

`/Zp`コンパイラオプションとプラグマには、 `pack` 構造体と共用体のメンバーのデータをパッキングする効果があります。 この例では `/Zp` 、との連携について説明し `__declspec(align(#))` ます。

```cpp
struct S {
   char a;
   short b;
   double c;
   CACHE_ALIGN double d;
   char e;
   double f;
};
```

次の表は、異なる (または) 値の下にある各メンバーのオフセットを示して `/Zp` `#pragma pack` います。これは、2つの相互作用を示しています。

|変数|/Zp1|/Zp2|/Zp4|/Zp8|
|--------------|-----------|-----------|-----------|-----------|
|a|0|0|0|0|
|b|1|2|2|2|
|c|3|4|4|8|
|d|32|32|32|32|
|e|40|40|40|40|
|f|41|42|44|48|
|sizeof(S)|64|64|64|64|

詳細については、「 [ `/Zp` (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)」を参照してください。

オブジェクトのオフセットは、前のオブジェクトのオフセットと現在のパッキング設定に基づきます。ただし、オブジェクトに `__declspec(align(#))` 属性が設定されていない場合です。その場合は、アラインメントは前のオブジェクトのオフセットとオブジェクトの `__declspec(align(#))` 値に基づきます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`__declspec`](../cpp/declspec.md)<br/>
[ARM ABI 規則の概要](../build/overview-of-arm-abi-conventions.md)<br/>
[x64 ソフトウェア規約](../build/x64-software-conventions.md)
