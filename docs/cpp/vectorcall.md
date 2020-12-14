---
description: '詳細については、次を参照してください: __vectorcall'
title: __vectorcall
ms.date: 12/17/2018
f1_keywords:
- __vectorcall_cpp
- __vectorcall
- _vectorcall
helpviewer_keywords:
- __vectorcall keyword
- __vectorcall
ms.assetid: 1c95ed59-86c6-4857-b4ed-10519193f851
ms.openlocfilehash: 223576b7aec37434cb9574d744e9ebc1b9aa88f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210973"
---
# <a name="__vectorcall"></a>__vectorcall

**Microsoft 固有の仕様**

**`__vectorcall`** 呼び出し規則は、可能であれば、関数への引数をレジスタに渡すことを指定します。 **`__vectorcall`** は、引数により多くのレジスタを使用 [`__fastcall`](../cpp/fastcall.md) するか、既定の [x64 呼び出し規約](../build/x64-calling-convention.md) を使用します。 **`__vectorcall`** 呼び出し規則は、ストリーミング SIMD 拡張命令 2 (SSE2) 以上を含む x86 および x64 プロセッサのネイティブコードでのみサポートされています。 **`__vectorcall`** 複数の浮動小数点または SIMD ベクター引数を渡し、レジスタに読み込まれた引数を活用する操作を実行する関数を高速化するために使用します。 次の一覧は、の x86 および x64 実装に共通の機能を示して **`__vectorcall`** います。 相違点については、このトピックで後ほど説明します。

|要素|実装|
|-------------|--------------------|
|C の名前装飾規約|関数名の末尾には、2つの "at" 記号 ( \@ \@ ) の後に、パラメーターリストのバイト数 (10 進数) が続きます。|
|大文字と小文字の変換規約|大文字小文字は変換されません。|

コンパイラオプションを使用すると、 [`/Gv`](../build/reference/gd-gr-gv-gz-calling-convention.md) 関数がメンバー関数でない場合、競合する呼び出し規約属性を使用して宣言した場合、 **`__vectorcall`** 可変引数リストを使用する場合、または名前を持つ場合を除き、モジュール内の各関数がとしてコンパイルされ `vararg` `main` ます。

関数に登録すると、 **`__vectorcall`** *整数型* の値、 *ベクター型* の値、および *同種の vector aggregate* (hva) 値の3種類の引数を渡すことができます。

整数型は、2 つの条件を満たしています。まずプロセッサのネイティブなレジスタ サイズ (たとえば、x86 コンピューターでは 4 バイト、x64 コンピューターでは 8 バイト) に収まります。また、そのビット表現を変更せずにレジスタ長の整数値に変換し、再度元に戻すことができます。 たとえば、x86 (x64) でに昇格できる任意の型 (たとえば、または)、または **`int`** **`long long`** **`char`** **`short`** **`int`** ( **`long long`** x64 の場合) にキャストして、変更せずに元の型に戻すことができる型は、整数型です。 整数型には、ポインター、参照、 **`struct`** または **`union`** 4 バイト (x64 では8バイト) 以下の型が含まれます。 X64 プラットフォームでは、より大きい **`struct`** **`union`** 型と型が呼び出し元によって割り当てられたメモリに参照によって渡されます。 x86 プラットフォームでは、これらはスタック上の値によって渡されます。

ベクター型は、浮動小数点型 (やなど) **`float`** **`double`** または SIMD ベクター型 (やなど) のいずれかです **`__m128`** **`__m256`** 。

HVA 型は、同一のベクター型を持つ最大 4 個のデータ メンバーから成る複合型です。 HVA 型のアラインメント要件は、そのメンバーのベクター型のアラインメント要件と同じになります。 これは、 **`struct`** 3 つの同じベクター型を含み、32バイトのアラインメントを持つ HVA 定義の例です。

```cpp
typedef struct {
   __m256 x;
   __m256 y;
   __m256 z;
} hva3;    // 3 element HVA type on __m256
```

ヘッダーファイルでキーワードを使用して関数を明示的に宣言し、 **`__vectorcall`** 個別にコンパイルされたコードがエラーなしでリンクされるようにします。 関数はを使用するためにプロトタイプ宣言されている必要があり、 **`__vectorcall`** 可変長の引数リストを使用することはできません `vararg` 。

メンバー関数は、指定子を使用して宣言でき **`__vectorcall`** ます。 非表示の **`this`** ポインターは、最初の整数型引数としてレジスタによって渡されます。

ARM コンピューターで **`__vectorcall`** は、はコンパイラによって受け入れられ、無視されます。

静的でないクラスのメンバー関数が行外で宣言されている場合、行外の宣言で呼び出し規則の修飾子を指定する必要はありません。 つまり、クラスの非静的なメンバーの場合は、宣言時に指定された呼び出し規則が定義の時点で仮定されます。 次のクラス定義があるとします。

```cpp
struct MyClass {
   void __vectorcall mymethod();
};
```

ここで、

```cpp
void MyClass::mymethod() { return; }
```

は次の記述と同じです。

```cpp
void __vectorcall MyClass::mymethod() { return; }
```

**`__vectorcall`** 呼び出し規約修飾子は、関数へのポインターが作成されるときに指定する必要があり **`__vectorcall`** ます。 次の例では、 **`typedef`** **`__vectorcall`** 4 つの引数を受け取り **`double`** 、値を返す関数へのポインターのを作成し **`__m256`** ます。

```cpp
typedef __m256 (__vectorcall * vcfnptr)(double, double, double, double);
```

以前のバージョンとの互換性のために、 **`_vectorcall`** **`__vectorcall`** コンパイラオプションの [ [ `/Za` \( 言語拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されていない場合、はのシノニムになります。

## <a name="__vectorcall-convention-on-x64"></a>x64 での __vectorcall 規約

**`__vectorcall`** X64 での呼び出し規約は、追加のレジスタを利用するために、標準の x64 呼び出し規約を拡張したものです。 整数型引数とベクター型引数の両方が、引数リスト内の位置に基づいてレジスタにマップされます。 HVA 引数は、未使用のベクター レジスタに割り当てられます。

最初の 4 個の引数がすべて整数型引数の場合、それらの引数は左から順にその位置に対応するレジスタ (RCX、RDX、R8、R9) に渡されます。 非表示の **`this`** ポインターは、最初の整数型引数として扱われます。 最初の 4 個の引数のうちの 1 個が HVA 引数であって、使用可能なレジスタに渡すことができない場合は、その代わりに、呼び出し元が割り当てたメモリへの参照が、その引数に対応する整数型のレジスタに渡されます。 5 番目以降のパラメーター位置にある整数型引数は、スタックに渡されます。

最初の 6 個の引数がすべてベクター型引数の場合、それらの引数はその位置に従って、左から順に SSE ベクター レジスタの 0 ～ 5 に値で渡されます。 浮動小数点 **`__m128`** 型と型は XMM レジスタで渡され、 **`__m256`** 型は ymm レジスタに渡されます。 この点は標準の x64 呼び出し規約と異なり、ベクター型が参照渡しではなく値渡しされ、追加のレジスタが使用されます。 ベクター型引数に割り当てられるシャドウスタック領域は8バイトで固定され、 [`/homeparams`](../build/reference/homeparams-copy-register-parameters-to-stack.md) オプションは適用されません。 7 番目以降のパラメーター位置にあるベクター型引数は、呼び出し元が割り当てられたメモリへの参照によってスタックに渡されます。

ベクター引数に対してレジスタが割り当てられた後、hva 引数のデータメンバーは、 **`__m256`** hva 全体に使用できるレジスタが十分にある限り、未使用のベクターレジスタ XMM0 から XMM5 (または ymm0 ~ ymm5 TO ある場合い) に割り当てられます。 十分なレジスタが使用できない場合、HVA 引数は、呼び出し元が割り当てたメモリへの参照によって渡されます。 HVA 引数用のスタック シャドウ領域は 8 バイトに固定され、内容は未定義です。 HVA の引数は、パラメーター リストの左から順にレジスタに割り当てられますが、任意の位置に割り当てることもできます。 最初の 4 個の引数位置のいずれかに、ベクター レジスタに割り当てられていない HVA 引数がある場合、その位置に対応する整数レジスタに参照によって渡されます。 5 番目以降のパラメーター位置にあり、参照によって渡された HVA 引数はスタックにプッシュされます。

関数の結果 **`__vectorcall`** は、可能な場合はレジスタの値によって返されます。 8 バイト以下の構造体や共用体を含む整数型の結果は、値によって RAX に返されます。 ベクター型の結果は、サイズに応じて XMM0 または YMM0 に値によって返されます。 HVA の結果は、要素のサイズに応じて、各データ要素がレジスタ XMM0:XMM3 またはレジスタ YMM0:YMM3 に値によって返されます。 対応するレジスタに収まらない結果の型は、呼び出し元が割り当てたメモリへの参照によって返されます。

スタックは、の x64 実装では、呼び出し元によって保持され **`__vectorcall`** ます。 呼び出された関数のためのスタックは、呼び出し元のプロローグ コードとエピローグ コードによって割り当てられ、クリアされます。 引数はスタックで右から左へプッシュされます。レジスタに渡された引数には、シャドウ スタック領域が割り当てられます。

例 :

```cpp
// crt_vc64.c
// Build for amd64 with: cl /arch:AVX /W3 /FAs crt_vc64.c
// This example creates an annotated assembly listing in
// crt_vc64.asm.

#include <intrin.h>
#include <xmmintrin.h>

typedef struct {
   __m128 array[2];
} hva2;    // 2 element HVA type on __m128

typedef struct {
   __m256 array[4];
} hva4;    // 4 element HVA type on __m256

// Example 1: All vectors
// Passes a in XMM0, b in XMM1, c in YMM2, d in XMM3, e in YMM4.
// Return value in XMM0.
__m128 __vectorcall
example1(__m128 a, __m128 b, __m256 c, __m128 d, __m256 e) {
   return d;
}

// Example 2: Mixed int, float and vector parameters
// Passes a in RCX, b in XMM1, c in R8, d in XMM3, e in YMM4,
// f in XMM5, g pushed on stack.
// Return value in YMM0.
__m256 __vectorcall
example2(int a, __m128 b, int c, __m128 d, __m256 e, float f, int g) {
   return e;
}

// Example 3: Mixed int and HVA parameters
// Passes a in RCX, c in R8, d in R9, and e pushed on stack.
// Passes b by element in [XMM0:XMM1];
// b's stack shadow area is 8-bytes of undefined value.
// Return value in XMM0.
__m128 __vectorcall example3(int a, hva2 b, int c, int d, int e) {
   return b.array[0];
}

// Example 4: Discontiguous HVA
// Passes a in RCX, b in XMM1, d in XMM3, and e is pushed on stack.
// Passes c by element in [YMM0,YMM2,YMM4,YMM5], discontiguous because
// vector arguments b and d were allocated first.
// Shadow area for c is an 8-byte undefined value.
// Return value in XMM0.
float __vectorcall example4(int a, float b, hva4 c, __m128 d, int e) {
   return b;
}

// Example 5: Multiple HVA arguments
// Passes a in RCX, c in R8, e pushed on stack.
// Passes b in [XMM0:XMM1], d in [YMM2:YMM5], each with
// stack shadow areas of an 8-byte undefined value.
// Return value in RAX.
int __vectorcall example5(int a, hva2 b, int c, hva4 d, int e) {
   return c + e;
}

// Example 6: HVA argument passed by reference, returned by register
// Passes a in [XMM0:XMM1], b passed by reference in RDX, c in YMM2,
// d in [XMM3:XMM4].
// Register space was insufficient for b, but not for d.
// Return value in [YMM0:YMM3].
hva4 __vectorcall example6(hva2 a, hva4 b, __m256 c, hva2 d) {
   return b;
}

int __cdecl main( void )
{
   hva4 h4;
   hva2 h2;
   int i;
   float f;
   __m128 a, b, d;
   __m256 c, e;

   a = b = d = _mm_set1_ps(3.0f);
   c = e = _mm256_set1_ps(5.0f);
   h2.array[0] = _mm_set1_ps(6.0f);
   h4.array[0] = _mm256_set1_ps(7.0f);

   b = example1(a, b, c, d, e);
   e = example2(1, b, 3, d, e, 6.0f, 7);
   d = example3(1, h2, 3, 4, 5);
   f = example4(1, 2.0f, h4, d, 5);
   i = example5(1, h2, 3, h4, 5);
   h4 = example6(h2, h4, c, h2);
}
```

## <a name="__vectorcall-convention-on-x86"></a>x86 での __vectorcall 規約

**`__vectorcall`** 呼び出し規約は、 **`__fastcall`** 32 ビット整数型引数の規約に従い、ベクター型と hva 引数の SSE ベクターレジスタを利用します。

パラメーター リストの最初の 2 個の整数型引数は、左から順にそれぞれ ECX と EDX に配置されます。 非表示の **`this`** ポインターは、最初の整数型引数として扱われ、ECX で渡されます。 最初の 6 個のベクター型引数は、SSE ベクター レジスタ 0 ～ 5 を介し、引数のサイズに応じて YMM または XMM レジスタに値によって渡されます。

最初の 6 個のベクター型引数は、左から順に SSE ベクター レジスタの 0 ～ 5 に値で渡されます。 浮動小数点 **`__m128`** 型と型は XMM レジスタで渡され、 **`__m256`** 型は ymm レジスタに渡されます。 シャドウ スタック領域は、レジスタで渡されるベクター型引数に対して割り当てられます。 7 番目以降のベクター型引数は、呼び出し元が割り当てられたメモリへの参照によってスタックに渡されます。 コンパイラエラー [C2719](../error-messages/compiler-errors-2/compiler-error-c2719.md) の制限は、これらの引数には適用されません。

ベクター引数にレジスタが割り当てられた後、hva 引数のデータメンバーは、 **`__m256`** hva 全体に使用できるレジスタが十分にある限り、未使用のベクターレジスタ XMM0 から XMM5 (または ymm0 ~ ymm5 からある場合いへのアクセス) に昇順で割り当てられます。 十分なレジスタが使用できない場合、HVA 引数は、呼び出し元が割り当てたメモリへの参照によってスタックに渡されます。 HVA 引数には、スタック シャドウ領域は割り当てられません。 HVA の引数は、パラメーター リストの左から順にレジスタに割り当てられますが、任意の位置に割り当てることもできます。

関数の結果 **`__vectorcall`** は、可能な場合はレジスタの値によって返されます。 4 バイト以下の構造体や共用体を含む整数型の結果は、値によって EAX に返されます。 8 バイト以下の整数型の構造体や共用体は、値によって EDX:EAX に返されます。 ベクター型の結果は、サイズに応じて XMM0 または YMM0 に値によって返されます。 HVA の結果は、要素のサイズに応じて、各データ要素がレジスタ XMM0:XMM3 またはレジスタ YMM0:YMM3 に値によって返されます。 他の結果の型は、呼び出し元が割り当てたメモリへの参照によって返されます。

の x86 実装は、 **`__vectorcall`** 呼び出し元によってスタックに右から左にプッシュされる引数の規則に従います。呼び出された関数は、返される直前にスタックをクリアします。 スタックには、レジスタに配置されていない引数のみがプッシュされます。

例 :

```cpp
// crt_vc86.c
// Build for x86 with: cl /arch:AVX /W3 /FAs crt_vc86.c
// This example creates an annotated assembly listing in
// crt_vc86.asm.

#include <intrin.h>
#include <xmmintrin.h>

typedef struct {
   __m128 array[2];
} hva2;    // 2 element HVA type on __m128

typedef struct {
   __m256 array[4];
} hva4;    // 4 element HVA type on __m256

// Example 1: All vectors
// Passes a in XMM0, b in XMM1, c in YMM2, d in XMM3, e in YMM4.
// Return value in XMM0.
__m128 __vectorcall
example1(__m128 a, __m128 b, __m256 c, __m128 d, __m256 e) {
   return d;
}

// Example 2: Mixed int, float and vector parameters
// Passes a in ECX, b in XMM0, c in EDX, d in XMM1, e in YMM2,
// f in XMM3, g pushed on stack.
// Return value in YMM0.
__m256 __vectorcall
example2(int a, __m128 b, int c, __m128 d, __m256 e, float f, int g) {
   return e;
}

// Example 3: Mixed int and HVA parameters
// Passes a in ECX, c in EDX, d and e pushed on stack.
// Passes b by element in [XMM0:XMM1].
// Return value in XMM0.
__m128 __vectorcall example3(int a, hva2 b, int c, int d, int e) {
   return b.array[0];
}

// Example 4: HVA assigned after vector types
// Passes a in ECX, b in XMM0, d in XMM1, and e in EDX.
// Passes c by element in [YMM2:YMM5].
// Return value in XMM0.
float __vectorcall example4(int a, float b, hva4 c, __m128 d, int e) {
   return b;
}

// Example 5: Multiple HVA arguments
// Passes a in ECX, c in EDX, e pushed on stack.
// Passes b in [XMM0:XMM1], d in [YMM2:YMM5].
// Return value in EAX.
int __vectorcall example5(int a, hva2 b, int c, hva4 d, int e) {
   return c + e;
}

// Example 6: HVA argument passed by reference, returned by register
// Passes a in [XMM1:XMM2], b passed by reference in ECX, c in YMM0,
// d in [XMM3:XMM4].
// Register space was insufficient for b, but not for d.
// Return value in [YMM0:YMM3].
hva4 __vectorcall example6(hva2 a, hva4 b, __m256 c, hva2 d) {
   return b;
}

int __cdecl main( void )
{
   hva4 h4;
   hva2 h2;
   int i;
   float f;
   __m128 a, b, d;
   __m256 c, e;

   a = b = d = _mm_set1_ps(3.0f);
   c = e = _mm256_set1_ps(5.0f);
   h2.array[0] = _mm_set1_ps(6.0f);
   h4.array[0] = _mm256_set1_ps(7.0f);

   b = example1(a, b, c, d, e);
   e = example2(1, b, 3, d, e, 6.0f, 7);
   d = example3(1, h2, 3, 4, 5);
   f = example4(1, 2.0f, h4, d, 5);
   i = example5(1, h2, 3, h4, 5);
   h4 = example6(h2, h4, c, h2);
}
```

**End Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
