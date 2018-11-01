---
title: パラメーターの引き渡し
ms.date: 11/04/2016
ms.assetid: e838ee5f-c2fe-40b0-9a23-8023c949c820
ms.openlocfilehash: 1b7fb126ab3b140d0ab672067df35c5fc8df926e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648748"
---
# <a name="parameter-passing"></a>パラメーターの引き渡し

最初の 4 つの整数引数はレジスタで渡されます。 整数値は、RCX、RDX、R8、および R9 で (左右からの順序) で渡されます。 5 つの引数以上スタックに渡されるとします。 すべての引数が、レジスタで右揃えです。 場合、呼び出し先は、レジスタの上位ビットを無視できますのでこれは、する必要があるし、レジスタの必要な部分のみにアクセスできます。

引数と倍精度の浮動小数点引数は、XMM0 で渡される - カーディナル スロットになることに通常使用される整数スロット (RCX、RDX、R8、および R9) と (4) 最大 XMM3 に無視されます (例を参照)、またはその逆です。

[_ _m128](../cpp/m128.md)型、配列と文字列がイミディ エイト値によって渡されることはありませんが、呼び出し元が割り当てたメモリへのポインターが渡されるではなく、します。 場合と同じサイズの整数と同様に、サイズ 8、16、32、または 64 ビットおよび _ _m64 の構造体/共用体が渡されます。 これらのサイズ以外の構造体/共用体は、呼び出し元が割り当てたメモリへのポインターとして渡されます。 これらの集約型のポインターとして渡されます (を含む\__m128)、呼び出し元が割り当てたの一時的なメモリが 16 バイトでアラインされます。

スタック領域を割り当てないし、その他の関数を呼び出さないでくださいできる組み込み関数では、他 volatile レジスタを使用して、コンパイラと組み込み関数の実装の間の緊密なバインドが、追加のレジスタ引数を渡します。 これは、さらにパフォーマンスを向上させる機会です。

呼び出し先では、登録パラメーターに必要な場合は、そのシャドウ領域ダンプの責任を持ちます。

次の表では、パラメーターが渡される方法を示します。

|パラメーターの型|渡された方法|
|--------------------|----------------|
|浮動小数点数|最初に 4 つのパラメーター - XMM3 を通じて XMM0 します。 他のユーザーは、スタックで渡されます。|
|整数型|最初に 4 つのパラメーター - RCX、RDX、R8、R9。 他のユーザーは、スタックで渡されます。|
|集計 (8、16、32、または 64 ビット) と _ _m64|最初に 4 つのパラメーター - RCX、RDX、R8、R9。 他のユーザーは、スタックで渡されます。|
|集計 (その他)|ポインター。 まず、4 つのパラメーターが RCX、RDX、R8、および R9 のポインターとして渡されます|
|__m128|ポインター。 まず、4 つのパラメーターが RCX、RDX、R8、および R9 のポインターとして渡されます|

## <a name="example-of-argument-passing-1---all-integers"></a>1 - すべての整数を渡す引数の例

```
func1(int a, int b, int c, int d, int e);
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack
```

## <a name="example-of-argument-passing-2---all-floats"></a>2 - すべての浮動小数点値を渡す引数の例

```
func2(float a, double b, float c, double d, float e);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack
```

## <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>3 - 混合整数と浮動小数点数を渡す引数の例

```
func3(int a, double b, int c, float d);
// a in RCX, b in XMM1, c in R8, d in XMM3
```

## <a name="example-of-argument-passing-4--m64-m128-and-aggregates"></a>引数渡し 4 の例-、_ _m64 \__m128 と集計

```
func4(__m64 a, _m128 b, struct c, float d);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3
```

## <a name="see-also"></a>関連項目

[呼び出し規則](../build/calling-convention.md)