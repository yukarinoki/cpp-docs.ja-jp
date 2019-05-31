---
title: アラインメント (C++ の宣言)
description: 最新のデータのアラインメントを指定する方法C++します。
ms.date: 05/30/2019
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: b6e03ac2b89624a0eb6602183d4ff4bf8b518f8d
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450774"
---
# <a name="alignment-c-declarations"></a>アラインメント (C++ の宣言)

C++ の低レベルの機能の 1 つは、特定のハードウェア アーキテクチャを最大活用するために、メモリ内のオブジェクトの正確な配置を指定できる機能です。 既定では、コンパイラはクラスと構造体のメンバーのサイズの値で:`bool`と`char`1 バイト境界に`short`2 バイト境界に`int`、 `long`、および`float`4 バイト境界、および`long long`、 `double`、および`long double`8 バイト境界にします。 ほとんどのシナリオでは、ことはありません、ため、既定の配置は既に最適な配置を考慮する必要があります。 場合によっては、ただし、実現できます大幅なパフォーマンスの向上、またはメモリ使用率の削減、データ構造のカスタム配置を指定することで。 Visual Studio 2015 より前に、Microsoft 固有キーワードを使用することが`__alignof`と`declspec(alignas)`を既定値を超える配置を指定します。 C++ 11 標準のキーワードを使用して Visual Studio 2015 で開始する必要があります[alignof と alignas](../cpp/alignof-and-alignas-cpp.md)最大コードの移植性を考慮します。 新しいキーワードは、Microsoft 固有の拡張機能と、内部で同じ方法で動作します。 これらの拡張機能のドキュメントは、新しいキーワードにも適用されます。 詳細については、次を参照してください。 [_ _alignof 演算子](../cpp/alignof-operator.md)と[align](../cpp/align-cpp.md)します。 C++標準は、Microsoft #pragma を使用する必要がありますに、対象プラットフォームのコンパイラの既定値よりも小さい境界での配置のパッキング動作を指定しない[パック](../preprocessor/pack.md)場合。

使用して、 [aligned_storage クラス](../standard-library/aligned-storage-class.md)カスタム配置を伴うデータ構造のメモリの割り当て。 [Aligned_union クラス](../standard-library/aligned-union-class.md)は自明でないコンス トラクターまたはデストラクターで共用体の配置を指定するためです。

## <a name="about-alignment"></a>配置について

配置は、2 の累乗の数値のアドレスの剰余として表現される、メモリ アドレスのプロパティです。 たとえば、0x0001103F 4 のアドレスには 3 です。 そのアドレスは 4n + 3、4 に選択した 2 の累乗が示す位置に配置されると言います。 アドレスのアラインメントは、2 の選択した機能によって異なります。 同じアドレスの 8 の剰余は 7 です。 配置が Xn+0 の場合、アドレスが X に配置されると言われます。

Cpu はメモリに格納されたデータを操作する手順を実行します。 データは、メモリ内のアドレスによって識別されます。 単一のデータは、サイズもあります。 呼び出してデータム*自然に配置*場合、そのアドレスがそのサイズに合わせて配置します。 呼び出された*不整合*それ以外の場合。 たとえば、8 バイト浮動小数点のデータが自然に配置識別に使用するアドレス、8 バイト アラインメントがある場合。

## <a name="compiler-handling-of-data-alignment"></a>データの整列のコンパイラ処理

コンパイラは、データの不整合を避ける方法でデータの割り当てを作成しようとします。

単純なデータ型の場合、コンパイラは、データ型のバイト単位のサイズの倍数であるアドレスを割り当てます。 たとえば、コンパイラが型の変数にアドレスを割り当てる`long`下部にあるアドレスの 2 つのビットを 0 に設定されている 4 の倍数であります。

また、コンパイラは、当然ながら、構造体の各要素を整列するように、構造を埋めます。 構造体を検討してください。`struct x_`で次のコード例。

```cpp
struct x_
{
   char a;     // 1 byte
   int b;      // 4 bytes
   short c;    // 2 bytes
   char d;     // 1 byte
} MyStruct;
```

コンパイラは自然な配置を強制するようにこの構造体を埋めます。

次のコード例では、コンパイラがメモリ内に埋め込み構造体を格納する方法を示します。

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
}
```

1. 両方の宣言を返す`sizeof(struct x_)`12 バイトとして。

1. 2 番目の宣言には、埋め込みの 2 つの要素が含まれています。

1. `char _pad0[3]` 配置する、 `int b` 4 バイト境界でメンバー

1. `char _pad1[1]` 構造体の配列要素を配置するには `struct _x bar[3];`

1. 要素を配置、余白`bar[3]`自然なアクセスを許可するようにします。

次のコード例は、`bar[3]`配列レイアウト。

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

[データ構造体の配置](https://en.wikipedia.org/wiki/Data_structure_alignment)
