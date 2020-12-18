---
title: アラインメント (C11)
description: Microsoft Visual C の型のアラインメントについて説明します
ms.date: 12/10/2020
helpviewer_keywords:
- _Alignof keyword [C]
- _Alignas keyword [C]
- memory, alignment
ms.openlocfilehash: 051987ae705f84d7d4972398f742143f14b53e2b
ms.sourcegitcommit: be469dd87453255b0e35e333712c8207b09b3dd4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2020
ms.locfileid: "97438892"
---
# <a name="alignment-c11"></a>アラインメント (C11)

C の低レベルの機能の 1 つは、ハードウェア アーキテクチャを最大活用するために、メモリ内のオブジェクトの正確なアラインメントを指定できる機能です。

データがそのデータ サイズの倍数であるアドレスに格納されていると、CPU の読み取りと書き込みの効率が向上します。 たとえば、4 バイトの整数が 4 の倍数であるアドレスに格納されていると、より効率的にアクセスできます。 データがアラインされていないと、CPU ではデータにアクセスするためにより多くの処理を行います。

既定では、コンパイラによって、サイズに基づいてデータがアラインされます。つまり、 **`char`** は 1 バイト境界、 **`short`** は 2 バイト境界、 **`int`** 、 **`long`** 、 **`float`** は 4 バイト境界、 **`double`** は 8 バイト境界と続きます。

また、頻繁に使用されるデータをプロセッサのキャッシュ ラインのサイズにアラインすることで、キャッシュ パフォーマンスを改善できます。 たとえば、サイズが 32 バイト未満の構造体を定義する場合、その構造体のインスタンスが効率的にキャッシュされるように、32 バイトにアライメントすることをお勧めします。

通常は、アラインメントについて心配する必要はありません。 コンパイラでは通常、ターゲット プロセッサとデータのサイズに基づいて、自然な境界にデータをアラインします。 データは、32 ビット プロセッサでは最大で 4 バイト境界、64 ビット プロセッサでは最大で 8 バイト境界にアラインされます。 ただし、場合によっては、データ構造にカスタム アラインメントを指定することで、パフォーマンスの向上やメモリの節約を実現できます。

C11 キーワード **`_Alignof`** を使用して、型または変数の適切なアラインメントを取得したり、 **`_Alignas`** を使用して、変数またはユーザー定義型のカスタム アラインメントを指定したりします。

`<stdalign.h>` で定義されている支援マクロ **`alignof`** と **`alignas`** は、それぞれ **`_Alignof`** と **`_Alignas`** に直接マップされます。 これらのマクロは、C++ で使用されるキーワードと一致します。 そのため、2 つの言語間でコードを共有する場合は、コードの移植性を確保するために、C のキーワードではなく、そのマクロを使用すると役立つことがあります。

## <a name="alignas-and-_alignas-c11"></a>`alignas` と `_Alignas` (C11)

**`alignas`** または **`_Alignas`** を使用して、変数またはユーザー定義型のカスタム アラインメントを指定します。 これらは、構造体、共用体、列挙型、または変数に適用できます。

### <a name="alignas-syntax"></a>`alignas` の構文

```c
alignas(type)
alignas(constant-expression)
_Alignas(type)
_Alignas(constant-expression)
```

### <a name="remarks"></a>解説

`_Alignas` は、`register` 指定子で宣言された typedef、ビットフィールド、関数、関数パラメーター、オブジェクトの宣言では使用できません。

1、2、4、8、16 などの 2 の累乗であるアラインメントを指定します。 型のサイズよりも小さい値は使用しないでください。

構造体と共用体のアラインメントは、任意のメンバーの最大のアラインメントと同じになります。 各メンバーのアラインメント要件が満たされるように、構造体の中に埋め込みバイトが追加されます。

宣言に複数の **`alignas`** 指定子が存在する場合 (たとえば、 **`alignas`** 指定子がそれぞれ異なる複数のメンバーを持つ構造体)、その構造体のアラインメントはその最も大きな値になります。

### <a name="alignas-example"></a>`alignas` の例

この例では、C++ に移植可能であるため、支援マクロ **`alignof`** を使用します。 動作は `_Alignof` を使用する場合と同じです。

```c
// Compile with /std:c11

#include <stdio.h>
#include <stdalign.h>

typedef struct 
{
    int value; // aligns on a 4-byte boundary. There will be 28 bytes of padding between value and alignas
    alignas(32) char alignedMemory[32]; // assuming a 32 byte friendly cache alignment
} cacheFriendly; // this struct will be 32-byte aligned because alignedMemory is 32-byte alligned and is the largest alignment specified in the struct

int main()
{
    printf("sizeof(cacheFriendly): %d\n", sizeof(cacheFriendly)); // 4 bytes for int value + 32 bytes for alignedMemory[] + padding to ensure  alignment
    printf("alignof(cacheFriendly): %d\n", alignof(cacheFriendly)); // 32 because alignedMemory[] is aligned on a 32-byte boundary

    /* output
        sizeof(cacheFriendly): 64
        alignof(cacheFriendly): 32
    */
}
```

## <a name="alignof-and-_alignof-c11"></a>`alignof` と `_Alignof` (C11)

`_Alignof` は指定された型のアラインメントをバイト単位で返します。 型 `size_t` の値を返します。

### <a name="alignof-syntax"></a>`alignof` の構文

```cpp
alignof(type)
_Alignof(type)
```

### <a name="alignof-example"></a>`alignof` の例

この例では、C++ に移植可能であるため、支援マクロ **`alignof`** を使用します。 動作は `_Alignof` を使用する場合と同じです。

```c
// Compile with /std:c11

#include <stdalign.h>
#include <stdio.h>

int main()
{
    size_t alignment = alignof(short);
    printf("alignof(short) = %d\n", alignment); // 2
    printf("alignof(int) = %d\n", alignof(int)); // 4
    printf("alignof(long) = %d\n", alignof(long)); // 4
    printf("alignof(float) = %d\n", alignof(float)); // 4
    printf("alignof(double) = %d\n", alignof(double)); // 8

    typedef struct
    {
        int a;
        double b;
    } test;

    printf("alignof(test) = %d\n", alignof(test)); // 8 because that is the alignment of the largest element in the structure

    /* output
        
       alignof(short) = 2
       alignof(int) = 4
       alignof(long) = 4
       alignof(float) = 4
       alignof(double) = 8
       alignof(test) = 8
    */
}
```

## <a name="requirements"></a>要件

[std: c++ 11](../build/reference/std-specify-language-standard-version.md) 以降が必要です。

Windows SDK バージョン 10.0.20201.0 以降。 このバージョンは、現在 Insider ビルドです。「[Windows Insider Preview のダウンロード](https://www.microsoft.com/software-download/windowsinsiderpreviewSDK)」からダウンロードできます。 この SDK のインストールと使用の手順については、「[C11 と C17: はじめに](https://devblogs.microsoft.com/cppblog/c11-and-c17-standard-support-arriving-in-msvc/#c11-and-c17-getting-started)」を参照してください。

## <a name="see-also"></a>関連項目

[`/std` (言語の標準バージョンの指定)](../build/reference/std-specify-language-standard-version.md)\
[C++ `alignof` と `alignas`](../cpp/alignment-cpp-declarations.md#alignof-and-alignas)\
[コンパイラによるデータ アラインメントの処理](../cpp/alignment-cpp-declarations.md#compiler-handling-of-data-alignment)