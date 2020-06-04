---
title: align (C++)
ms.date: 12/17/2018
f1_keywords:
- align_cpp
helpviewer_keywords:
- align __declspec keyword
- __declspec keyword [C++], align
ms.assetid: 9cb63f58-658b-4425-ac47-af8eabfc5878
ms.openlocfilehash: 227053fbfa4190dc6227ba7096a7c76aef30bb54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181552"
---
# <a name="align-c"></a>align (C++)

Visual Studio 2015 以降では、C++ 11 標準 `alignas` 指定子を使用して、アラインメントを制御します。 詳細については、「[アラインメント](../cpp/alignment-cpp-declarations.md)」を参照してください。

**Microsoft 固有の仕様**

ユーザー定義データ (関数の静的割り当てや自動データなど) のアラインメントを正確に制御するには、`__declspec(align(#))` を使用します。

## <a name="syntax"></a>構文

> **__declspec (align (** *#* **))** *宣言子*

## <a name="remarks"></a>解説

最新のプロセッサ命令を使用するアプリケーションの記述では、いくつかの新しい制約や問題があります。 特に、多くの新しい命令では、データを 16 バイト境界にアラインする必要があります。 また、頻繁に使用されるデータを特定のプロセッサのキャッシュ ラインのサイズにアラインすることで、キャッシュ パフォーマンスが向上します。 たとえば、サイズが 32 バイト未満の構造体を定義する場合、その構造体型のオブジェクトが効率的にキャッシュされるように、その構造体を 32 バイトにアラインできます。

\# はアラインメントの値です。 有効なエントリは、1 ～ 8192 (バイト) の 2 の整数乗 (2、4、8、16、32、64 など) です。 `declarator` は、aligned として宣言するデータです。

型のアラインメント要件である `size_t` 型の値を返す方法については、「 [__alignof](../cpp/alignof-operator.md)」を参照してください。 64ビットプロセッサを対象とする場合に、整列されていないポインターを宣言する方法については、「 [__unaligned](../cpp/unaligned.md)」を参照してください。

`__declspec(align(#))` は、**構造体**、**共用体**、または**クラス**を定義するとき、または変数を宣言するときに使用できます。

コンパイラは、コピーまたはデータ変換の処理中に、データのアラインメント属性の保持を保証したり、保持しようとしません。 たとえば、 [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)は、`__declspec(align(#))` で宣言された構造体を任意の場所にコピーできます。 通常のアロケーター ( [malloc](../c-runtime-library/reference/malloc.md)、 C++ [operator new](new-operator-cpp.md)、Win32 アロケーターなど) では、通常、構造体または構造体の配列に `__declspec(align(#))` 対して十分にアラインメントされていないメモリが返されることに注意してください。 コピーまたはデータ変換操作の転送先が正しく配置されていることを保証するには、 [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)を使用するか、独自のアロケーターを記述します。

関数パラメーターのアラインメントは指定できません。 アラインメント属性を持つデータがスタック上で値によって渡されるときに、そのアラインメントは呼び出し規則によって制御されます。 呼び出された関数でデータのアラインメントが重要な場合は、使用する前にパラメーターを正常にアラインされたメモリにコピーします。

`__declspec(align(#))`を使用しない場合、コンパイラは一般に、ターゲットプロセッサとデータサイズ、32ビットプロセッサで最大4バイトの境界、64ビットプロセッサの8バイト境界に基づいて、自然な境界にデータを配置します。 クラスまたは構造体のデータは、自然なアラインメントと現在のパッキング設定 (#pragma `pack` または `/Zp` コンパイラ オプションから) のうちの最小値でクラスまたは構造体内でアラインされます。

`__declspec(align(#))` を使用する例を次に示します。

```cpp
__declspec(align(32)) struct Str1{
   int a, b, c, d, e;
};
```

この型には、32 バイト アラインメント属性が設定されました。 これは、すべての静的および自動インスタンスが 32 バイト境界で開始されることを意味します。 この型でメンバーとして宣言された追加の構造体型は、この型のアラインメント属性を保持します。つまり、要素として `Str1` を持つ構造体は、少なくとも32のアラインメント属性を持ちます。

`sizeof(struct Str1)` が 32 と等しいことに注意してください。 このため、Str1 オブジェクトの配列が作成されて、配列のベース アドレスが 32 バイトでアラインされる場合、配列の各メンバーも 32 バイトでアラインされます。 動的メモリにベースが正しくアラインされた配列を作成するには、 [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)を使用するか、独自のアロケーターを記述します。

構造体の `sizeof` 値は、最後のメンバーのオフセットにメンバーのサイズを加え、最大サイズのメンバーのアラインメント値の倍数か、構造体全体のアラインメント値のどちらか大きい方に切り上げた値です。

コンパイラは、構造体のアラインメントにこれらの規則を使用します。

- `__declspec(align(#))` でオーバーライドしない限り、スカラー構造体のメンバーのアラインメントは、そのサイズと現在のパッキング設定の最小値になります。

- `__declspec(align(#))` でオーバーライドされない限り、構造体のアラインメントは、そのメンバーの個々のアラインメントの最大値になります。

- 構造体のメンバーが配置される、親の構造体の先頭からのオフセットは、アラインメントの最小倍数であり、かつ前のメンバーの最後のオフセットに等しいかそれよりも大きくなります。

- 構造体のサイズは、アラインメントの最小倍数であり、かつ最後のメンバーの最後のオフセットに等しいかそれよりも大きくなります。

`__declspec(align(#))` では、単にアラインメントの制限が多くなることがあります。

詳細については、次を参照してください。

- [整列の例](#vclrfalignexamples)

- [__Declspec を使用した新しい型の定義 (align (#))](#vclrf_declspecaligntypedef)

- [スレッドローカルストレージでのデータの整列](#vclrfthreadlocalstorageallocation)

- [データパッキングとの整列の連携](#vclrfhowalignworkswithdatapacking)

- [構造体のアラインメントの例](../build/x64-software-conventions.md#examples-of-structure-alignment)(x64 固有)

## <a name="align-examples"></a><a name="vclrfalignexamples"></a>整列の例

次の例では、`__declspec(align(#))` がデータ構造体のサイズとアラインメントにどのような影響を与えるかを示します。 この例では、次の定義を前提とします。

```cpp
#define CACHE_LINE  32
#define CACHE_ALIGN __declspec(align(CACHE_LINE))
```

次の例では、`S1` 構造体は `__declspec(align(32))` を使用して定義されます。 変数定義または他の型宣言で `S1` を使用すると、すべて 32 バイトでアラインされます。 `sizeof(struct S1)` は 32 を返し、`S1` では 4 つの整数の保持に必要な 16 バイトの後に 16 バイトのパディングが挿入されます。 各**int**メンバーには4バイトのアラインメントが必要ですが、構造体自体のアラインメントは32として宣言されています。 そのため、全体的なアラインメントは 32 になります。

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

次の例では、`a` で自然なアラインメントが行われる (この場合は 4 バイトにアラインされる) ことに注意してください。 ただし、`S1` は 32 バイトでアラインする必要があります。 `a` がオフセット 32 で開始するように、`s1` の次の 28 バイトがパディングされます。 次に、`S4` は `S1` のアラインメント要件を継承します。そのアラインメントが構造体に必要な最大アラインメントであるためです。 `sizeof(struct S4)` は 64 を返します。

```cpp
struct S4 {
   int a;
   // 28 bytes padding
    struct S1 s1;      // S4 inherits cache alignment requirement of S1
};
```

次の 3 つの変数宣言も `__declspec(align(#))` を使用します。 それぞれの場合で、変数は 32 バイトでアラインする必要があります。 配列の場合、配列の各メンバーではなく、配列のベース アドレスが 32 バイトでアラインされます。 配列の各メンバーの `sizeof` 値は `__declspec(align(#))` の使用による影響を受けません。

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

メモリがヒープ上に割り当てられる場合のアラインメントは、どの割り当て関数が呼び出されるかによって異なります。  たとえば、`malloc` を使用する場合、結果はオペランドのサイズによって決まります。 *Arg* > が8の場合、返されるメモリは8バイトでアラインされます。 *Arg* < 8 の場合、返されるメモリのアラインメントは、最初の2の累乗で、 *arg*より小さい値になります。 たとえば、malloc(7) を使用すると、アラインメントは 4 バイトになります。

## <a name="defining-new-types-with-__declspecalign"></a><a name="vclrf_declspecaligntypedef"></a>__Declspec を使用した新しい型の定義 (align (#))

型のアラインメントを定義できます。

たとえば、次のようにアラインメント値を指定して `struct` を定義できます。

```cpp
struct aType {int a; int b;};
typedef __declspec(align(32)) struct aType bType;
```

現在、`aType` と `bType` は同じサイズ (8 バイト) ですが、`bType` 型の変数は32バイトでアラインされています。

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

## <a name="how-align-works-with-data-packing"></a><a name="vclrfhowalignworkswithdatapacking"></a>データパッキングとの整列の連携

`/Zp` コンパイラオプションと `pack` プラグマは、構造体と共用体のメンバーのデータをパッキングする効果を持ちます。この例では、`/Zp` と `__declspec(align(#))` を連携させる方法を示します。

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

次の表に、さまざまな `/Zp` (または #pragma `pack`) 値での各メンバーのオフセットと共に、それらの値とオフセットの関係を示します。

|変数|/Zp1|/Zp2|/Zp4|/Zp8|
|--------------|-----------|-----------|-----------|-----------|
|a|0|0|0|0|
|b|1|2|2|2|
|c|3|4|4|8|
|d|32|32|32|32|
|e|40|40|40|40|
|f|41|42|44|48|
|sizeof(S)|64|64|64|64|

詳細については、「[/Zp (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)」を参照してください。

オブジェクトのオフセットは、前のオブジェクトのオフセットと現在のパッキング設定に基づきます。ただし、オブジェクトに `__declspec(align(#))` 属性が設定されていない場合です。その場合は、アラインメントは前のオブジェクトのオフセットとオブジェクトの `__declspec(align(#))` 値に基づきます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)<br/>
[ARM ABI 規則の概要](../build/overview-of-arm-abi-conventions.md)<br/>
[x64 ソフトウェア規約](../build/x64-software-conventions.md)
