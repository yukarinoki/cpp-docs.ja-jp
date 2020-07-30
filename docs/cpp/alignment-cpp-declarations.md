---
title: Alignment
description: 最新の C++ でデータの配置を指定する方法。
ms.date: 12/11/2019
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: 7f6bef061fee41389bad644d9ac5244f5644da76
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227648"
---
# <a name="alignment"></a>Alignment

C++ の低レベルの機能の 1 つは、特定のハードウェア アーキテクチャを最大活用するために、メモリ内のオブジェクトの正確な配置を指定できる機能です。 既定では、コンパイラは、クラスと構造体のメンバーのサイズ値を、2バイト境界、、、および4バイト境界 (、、、 **`bool`** **`char`** **`short`** **`int`** **`long`** **`float`** **`long long`** **`double`** および **`long double`** 8 バイト境界) に配置します。

ほとんどのシナリオでは、既定の配置が既に最適化されているため、配置について心配する必要はありません。 ただし、場合によっては、データ構造にカスタム配置を指定することで、パフォーマンスを大幅に向上させたり、メモリを節約したりすることができます。 Visual Studio 2015 より前では、Microsoft 固有のキーワードとを使用し **`__alignof`** て、 **`__declspec(align)`** 既定値よりも大きいアラインメントを指定できました。 Visual Studio 2015 以降では、 **`alignof`** **`alignas`** コードの移植性を最大にするために、c++ 11 の標準キーワードとを使用する必要があります。 新しいキーワードは、内部的には Microsoft 固有の拡張機能と同じように動作します。 これらの拡張機能のドキュメントは、新しいキーワードにも適用されます。 詳細については、「 [ `alignof` Operator](../cpp/alignof-operator.md) and [align](../cpp/align-cpp.md)」を参照してください。 C++ 標準では、ターゲットプラットフォームのコンパイラの既定値よりも小さい境界に対してはパッキング動作が指定されていないため、その場合でも Microsoft を使用する必要があり [`#pragma pack`](../preprocessor/pack.md) ます。

カスタム配置でのデータ構造のメモリ割り当てには、 [aligned_storage クラス](../standard-library/aligned-storage-class.md)を使用します。 [Aligned_union クラス](../standard-library/aligned-union-class.md)は、重要なコンストラクターまたはデストラクターを持つ共用体のアラインメントを指定するためのものです。

## <a name="alignment-and-memory-addresses"></a>アラインメントとメモリアドレス

配置は、2 の累乗の数値のアドレスの剰余として表現される、メモリ アドレスのプロパティです。 たとえば、0x0001103F モジュロ4というアドレスは3です。 このアドレスは、のようになります。ここで、4は選択された2の累乗を示します。 アドレスの配置は、選択した2の累乗によって異なります。 同じアドレスの 8 の剰余は 7 です。 配置が Xn+0 の場合、アドレスが X に配置されると言われます。

Cpu は、メモリに格納されているデータを操作する命令を実行します。 データは、メモリ内のアドレスによって識別されます。 1つの datum にもサイズがあります。 そのアドレスがサイズに合わせて調整されている場合は、*自然にアラ*インされた datum を呼び出します。 それ以外の場合は、*ミスアライメント*と呼ばれます。 たとえば、8バイトの浮動小数点の datum は、それを識別するために使用されるアドレスに8バイトのアラインメントがある場合に、自然にアラインされます。

## <a name="compiler-handling-of-data-alignment"></a>データ配置のコンパイラ処理

コンパイラは、データの不整合を防ぐようにデータの割り当てを試行します。

単純なデータ型の場合、コンパイラは、データ型のバイト単位のサイズの倍数であるアドレスを割り当てます。 たとえば、コンパイラは、4の倍数である型の変数にアドレスを割り当て **`long`** ます。この場合、アドレスの下2ビットを0に設定します。

コンパイラは、構造体の各要素を自然に配置するように構造体を埋め込みます。 次のコード例では、構造について考えてみ `struct x_` ます。

```cpp
struct x_
{
   char a;     // 1 byte
   int b;      // 4 bytes
   short c;    // 2 bytes
   char d;     // 1 byte
} bar[3];
```

コンパイラは自然な配置を強制するようにこの構造体を埋めます。

次のコード例は、コンパイラが埋め込まれた構造体をメモリ内に配置する方法を示しています。

```cpp
// Shows the actual memory layout
struct x_
{
   char a;            // 1 byte
   char _pad0[3];     // padding to put 'b' on 4-byte boundary
   int b;            // 4 bytes
   short c;          // 2 bytes
   char d;           // 1 byte
   char _pad1[1];    // padding to make sizeof(x_) multiple of 4
} bar[3];
```

どちらの宣言も `sizeof(struct x_)` 12 バイトとして返されます。

2 番目の宣言には、埋め込みの 2 つの要素が含まれています。

1. `char _pad0[3]``int b`4 バイト境界上にメンバーを配置する場合は。

1. `char _pad1[1]`構造体の配列要素を `struct _x bar[3];` 4 バイト境界に揃える場合は。

パディングは、 `bar[3]` 自然なアクセスを可能にするようにの要素を配置します。

次のコード例は、配列のレイアウトを示してい `bar[3]` ます。

```Output
adr offset   element
------   -------
0x0000   char a;         // bar[0]
0x0001   char pad0[3];
0x0004   int b;
0x0008   short c;
0x000a   char d;
0x000b   char _pad1[1];

0x000c   char a;         // bar[1]
0x000d   char _pad0[3];
0x0010   int b;
0x0014   short c;
0x0016   char d;
0x0017   char _pad1[1];

0x0018   char a;         // bar[2]
0x0019   char _pad0[3];
0x001c   int b;
0x0020   short c;
0x0022   char d;
0x0023   char _pad1[1];
```

## <a name="alignof-and-alignas"></a>`alignof` および `alignas`

**`alignas`** 型指定子は、変数およびユーザー定義型のカスタムアラインメントを指定するための移植可能な C++ 標準の方法です。 また、演算子は、 **`alignof`** 指定された型または変数のアラインメントを取得するための、標準の移植可能な方法です。

## <a name="example"></a>例

**`alignas`** は、クラス、構造体、共用体、または個々のメンバーに対して使用できます。 複数の **`alignas`** 指定子が検出されると、コンパイラは最も厳格なもの (最も大きな値を持つもの) を選択します。

```cpp
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar
{
    int i;       // 4 bytes
    int n;      // 4 bytes
    alignas(4) char arr[3];
    short s;          // 2 bytes
};

int main()
{
    std::cout << alignof(Bar) << std::endl; // output: 16
}
```

## <a name="see-also"></a>関連項目

[データ構造の配置](https://en.wikipedia.org/wiki/Data_structure_alignment)
