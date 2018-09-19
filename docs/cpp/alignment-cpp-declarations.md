---
title: 配置 (C++ の宣言) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c68708547187fd9c3dde450ad9be6e13e4adcde
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114606"
---
# <a name="alignment-c-declarations"></a>アラインメント (C++ の宣言)

C++ の低レベルの機能の 1 つは、特定のハードウェア アーキテクチャを最大活用するために、メモリ内のオブジェクトの正確な配置を指定できる機能です。 既定では、コンパイラはクラスと構造体メンバーのサイズの値: int は 4 バイト、long、double、および 8 バイトの long double は、2 つのバイトに対する簡単な 1 バイト境界にアライン bool と char です。 ほとんどのシナリオで、既定の配置は既に最適なので、配置を気にすることはありません。 ただし、場合によっては、大幅なパフォーマンスの向上、またはメモリの節約を、データ構造にカスタム配置を指定することで達成できます。 Visual Studio 2015 の前は、既定値を超える配列を指定するのに、Microsoft 固有キーワード __alignof と declspec(alignas) を使用できました。 C++ 11 標準のキーワードを使用して Visual Studio 2015 で開始する必要があります[alignof と alignas](../cpp/alignof-and-alignas-cpp.md)最大コードの移植性を考慮します。 新しいキーワードは、内部で Microsoft 固有の拡張機能として同じ方法で動作し、拡張機能のためのドキュメントが、新しいキーワードにも適用されます。 参照してください[_ _alignof 演算子](../cpp/alignof-operator.md)と[align](../cpp/align-cpp.md)詳細についてはします。 C++ 標準は Microsoft #pragma を使用する必要があるためにの配置のターゲット プラットフォームで、コンパイラの既定値よりも小さい境界では、パッキング動作を指定しない[パック](../preprocessor/pack.md)場合。

C++ 標準ライブラリを提供、 [aligned_storage クラス](../standard-library/aligned-storage-class.md)カスタムの配置を伴うデータ構造のメモリを割り当て、 [aligned_union クラス](../standard-library/aligned-union-class.md)を持つ共用体の配置を指定します。重要なコンス トラクターまたはデストラクター。

## <a name="about-alignment"></a>配置について

配置は、2 の累乗の数値のアドレスの剰余として表現される、メモリ アドレスのプロパティです。 たとえば、0x0001103F のアドレスを 4 で割ると 3 になり、アドレスが 4n+3 に配置されたということができます。ここで、4 は選択した 2 の累乗です。 アドレスの配置は、2 の選択した値の累乗に依存します。 同じアドレスの 8 の剰余は 7 です。 配置が Xn+0 の場合、アドレスが X に配置されると言われます。

CPU はメモリに格納されているデータを操作するインストラクターを実行し、データはメモリ内のアドレスによって特定されます。 アドレスに加えて、単一データはサイズも持っています。 アドレスがサイズに合わせて自然に配置されている場合は、データが自然に配置されるよう呼び出され、そうでない場合は適切に配置されません。 たとえば、識別のために使用されるアドレスが 8 に配置されている場合、8 バイト浮動小数点のデータが自然に配置されます。

データ alignmentDevice コンパイラのコンパイラ処理は、データの不整合を避ける方法でデータを割り当てようとします。

単純なデータ型の場合、コンパイラは、データ型のバイト単位のサイズの倍数であるアドレスを割り当てます。 そのため、コンパイラは、4 の倍数である long 型の変数にアドレスを割り当てて、アドレスの下の 2 つのビットをゼロに設定します。

さらに、コンパイラは構造の各要素が自然配置になるように、構造を埋めます。 次のコード例の構造体 struct x_ について考えてみます。

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

次のコード例は、コンパイラが memory:Copy に埋め込みの構造を配置する方法を示しています。

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

1. 両方の宣言は、sizeof(struct x_) を 12 バイトとして返します。

1. 2 番目の宣言には、埋め込みの 2 つの要素が含まれています。

1. char _pad0 [3] を 4 バイト境界で int b メンバーを整列するには

1. char _pad1 [1]、構造体 struct _x bar [3] の配列要素を配置するには。

1. 埋め込みは自然なアクセスを可能にする方法で bar[3] の要素を配置します。

bar[3] 配列のレイアウトを次のコード サンプルに示します。

```
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

[データ構造体の配置](http://en.wikipedia.org/wiki/Data_structure_alignment)