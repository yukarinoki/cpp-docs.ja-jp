---
title: アラインメント (C++ の宣言)
description: 最新C++のでデータの配置を指定する方法。
ms.date: 09/19/2019
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: 67debc00343b8bee4184e020c9269011e2fcebc9
ms.sourcegitcommit: f907b15f50a6b945d0b87c03af0050946157d701
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "71158744"
---
# <a name="alignment-c-declarations"></a>アラインメント (C++ の宣言)

C++ の低レベルの機能の 1 つは、特定のハードウェア アーキテクチャを最大活用するために、メモリ内のオブジェクトの正確な配置を指定できる機能です。 既定では、コンパイラは、クラスと構造体のメンバーのサイズ`bool`値`char`を、1バイト境界、 `short` 2 バイト`int`境界、、 `long`、および`float` 4 バイト境界上に配置します。`long long`8 `double`バイト境界`long double`上の、、および。 ほとんどのシナリオでは、既定の配置が既に最適化されているため、配置について心配する必要はありません。 ただし、場合によっては、データ構造にカスタム配置を指定することで、パフォーマンスを大幅に向上させたり、メモリを節約したりすることができます。 Visual Studio 2015 より前では、Microsoft 固有のキーワード`__alignof`と`declspec(alignas)`を使用して、既定値よりも大きいアラインメントを指定できました。 Visual Studio 2015 以降では、コードの移植性を最大にするために、C++ 11 標準のキーワード[alignof と](../cpp/alignof-and-alignas-cpp.md)位置指定 nas を使用する必要があります。 新しいキーワードは、内部的には Microsoft 固有の拡張機能と同じように動作します。 これらの拡張機能のドキュメントは、新しいキーワードにも適用されます。 詳細については、「 [__Alignof Operator](../cpp/alignof-operator.md) and [align](../cpp/align-cpp.md)」を参照してください。 標準C++では、ターゲットプラットフォームのコンパイラの既定値よりも小さい境界に対してパッキング動作が指定されていないため、その場合も Microsoft #pragma[パック](../preprocessor/pack.md)を使用する必要があります。

カスタム配置でのデータ構造のメモリ割り当てには、 [aligned_storage クラス](../standard-library/aligned-storage-class.md)を使用します。 [Aligned_union クラス](../standard-library/aligned-union-class.md)は、重要なコンストラクターまたはデストラクターを持つ共用体のアラインメントを指定するためのものです。

## <a name="about-alignment"></a>配置について

配置は、2 の累乗の数値のアドレスの剰余として表現される、メモリ アドレスのプロパティです。 たとえば、0x0001103F モジュロ4というアドレスは3です。 このアドレスは、のようになります。ここで、4は選択された2の累乗を示します。 アドレスの配置は、選択した2の累乗によって異なります。 同じアドレスの 8 の剰余は 7 です。 配置が Xn+0 の場合、アドレスが X に配置されると言われます。

Cpu は、メモリに格納されているデータを操作する命令を実行します。 データは、メモリ内のアドレスによって識別されます。 1つの datum にもサイズがあります。 そのアドレスがサイズに合わせて調整されている場合は、*自然にアラ*インされた datum を呼び出します。 それ以外の場合は、*ミスアライメント*と呼ばれます。 たとえば、8バイトの浮動小数点の datum は、それを識別するために使用されるアドレスに8バイトのアラインメントがある場合に、自然にアラインされます。

## <a name="compiler-handling-of-data-alignment"></a>データ配置のコンパイラ処理

コンパイラは、データの不整合を防ぐようにデータの割り当てを試行します。

単純なデータ型の場合、コンパイラは、データ型のバイト単位のサイズの倍数であるアドレスを割り当てます。 たとえば、コンパイラは、4の倍数である型`long`の変数にアドレスを割り当てます。この場合、アドレスの下2ビットを0に設定します。

コンパイラは、構造体の各要素を自然に配置するように構造体を埋め込みます。 次のコード`struct x_`例では、構造について考えてみます。

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

どちらの宣言`sizeof(struct x_)`も12バイトとして返されます。

2 番目の宣言には、埋め込みの 2 つの要素が含まれています。

1. `char _pad0[3]`4バイト境界`int b`上にメンバーを配置する場合は。

1. `char _pad1[1]`構造体`struct _x bar[3];`の配列要素を4バイト境界に揃える場合は。

パディングは、自然なアクセス`bar[3]`を可能にするようにの要素を配置します。

次のコード例は、 `bar[3]`配列のレイアウトを示しています。

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

## <a name="see-also"></a>関連項目

[データ構造の配置](https://en.wikipedia.org/wiki/Data_structure_alignment)
