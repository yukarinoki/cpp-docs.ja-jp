---
title: alignof 演算子
ms.date: 12/17/2018
f1_keywords:
- __alignof_cpp
- alignof_cpp
- __alignof
- _alignof
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
ms.openlocfilehash: 6a2046774674858211ae89abb9b4cfc7b09c0a6d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227635"
---
# <a name="alignof-operator"></a>alignof 演算子

演算子は、 **`alignof`** 型の値として、指定された型のアラインメントをバイト単位で返し **`size_t`** ます。

## <a name="syntax"></a>構文

```cpp
alignof( type )
```

## <a name="remarks"></a>解説

次に例を示します。

| 正規表現 | 値 |
|--|--|
| **`alignof( char )`** | 1 |
| **`alignof( short )`** | 2 |
| **`alignof( int )`** | 4 |
| **`alignof( long long )`** | 8 |
| **`alignof( float )`** | 4 |
| **`alignof( double )`** | 8 |

**`alignof`** 値は、基本型のの値と同じです **`sizeof`** 。 ただし、次の例を検討します。

```cpp
typedef struct { int a; double b; } S;
// alignof(S) == 8
```

この場合、 **`alignof`** 値は、構造体内の最大の要素のアラインメント要件です。

同様に、

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`alignof(S)` と `32` が等価です。

の1つの用途は、 **`alignof`** 独自のメモリ割り当てルーチンの1つに対するパラメーターとなります。 たとえば、次の定義済みの構造体 `S` を指定して、`aligned_malloc` という名前のメモリ割り当てルーチンを呼び出し、特定の配置境界にメモリを割り当てることができます。

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), alignof(S));
```

配置の変更の詳細については、次を参照してください。

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (構造体メンバーのアラインメント)](../build/reference/zp-struct-member-alignment.md)

- [構造体のアラインメントの例](../build/x64-software-conventions.md#examples-of-structure-alignment)(x64 固有)

x86 と x64 用のコード内の配置の違いの詳細については、

- [X86 コンパイラとの競合](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

### <a name="microsoft-specific"></a>Microsoft 固有の仕様

**`alignof`** と **`__alignof`** は、Microsoft コンパイラのシノニムです。 C++ 11 の標準の一部になる前に、Microsoft 固有の演算子によっ **`__alignof`** てこの機能が提供されました。 移植性を最大にするには、Microsoft 固有の演算子の代わりに演算子を使用する必要があり **`alignof`** **`__alignof`** ます。

以前のバージョンとの互換性のために、 **`_alignof`** **`__alignof`** コンパイラオプションの [ [ `/Za` \( 言語拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されていない場合、はのシノニムになります。

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
