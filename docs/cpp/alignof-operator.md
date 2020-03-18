---
title: __alignof 演算子
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
ms.openlocfilehash: b3764e95846d48d293991d69d04bc71c6b3aed90
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443606"
---
# <a name="__alignof-operator"></a>__alignof 演算子

C++ 11 では、指定された型のアラインメントをバイト単位で返す**alignof**演算子が導入されています。 移植性を最大にするため、Microsoft 固有の __alignof 演算子ではなく、alignof 演算子を使用してください。

**Microsoft 固有の仕様**

型のアラインメント要件である `size_t` 型の値を返します。

## <a name="syntax"></a>構文

```cpp
  __alignof( type )
```

## <a name="remarks"></a>コメント

例 :

|式|値|
|----------------|-----------|
|**__alignof (char)**|1|
|**__alignof (短い)**|2|
|**__alignof (int)**|4|
|**__alignof (\__int64)**|8|
|**__alignof (float)**|4|
|**__alignof (double)**|8|
|**__alignof (char\*)**|4|

**__Alignof**値は、基本型の `sizeof` の値と同じです。 ただし、次の例を検討します。

```cpp
typedef struct { int a; double b; } S;
// __alignof(S) == 8
```

この場合、 **__alignof**値は、構造体内の最大の要素のアラインメント要件です。

同様に、

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`__alignof(S)` と `32`が等価です。

**__Alignof**の1つの用途は、独自のメモリ割り当てルーチンの1つにパラメーターとして使用することです。 たとえば、次の定義済みの構造体 `S` を指定して、`aligned_malloc` という名前のメモリ割り当てルーチンを呼び出し、特定の配置境界にメモリを割り当てることができます。

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));
```

以前のバージョンとの互換性のために、コンパイラオプション[/za \(無効になっている言語拡張)](../build/reference/za-ze-disable-language-extensions.md)が指定されていない場合、 **_alignof**は **__alignof**のシノニムになります。

配置の変更の詳細については、次を参照してください。

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)

- [構造体のアラインメントの例](../build/x64-software-conventions.md#examples-of-structure-alignment)(x64 固有)

x86 と x64 用のコード内の配置の違いの詳細については、

- [x86 コンパイラとの競合](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)