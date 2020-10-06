---
title: 構造体とクラスに注釈を付ける
ms.date: 06/28/2019
ms.topic: conceptual
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
- _Field_z_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
ms.openlocfilehash: fe177e6afea088b59b16bfbd0bff6fa00b526222
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765120"
---
# <a name="annotating-structs-and-classes"></a>構造体とクラスに注釈を付ける

インバリアントとして機能する注釈を使用して、構造体とクラスのメンバーに注釈を付けることができます。これらは、外側の構造体をパラメーターまたは結果値として含む関数の呼び出しまたは関数の開始/終了時に true と見なされます。

## <a name="struct-and-class-annotations"></a>構造体とクラスの注釈

- `_Field_range_(low, high)`

     フィールドはからまでの範囲に `low` あります (を含む) `high` 。  `_Satisfies_(_Curr_ >= low && _Curr_ <= high)`適切な事前条件または事後条件を使用して、注釈付きオブジェクトに適用されると同じです。

- `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`

     で指定されたように、要素 (またはバイト) 内の書き込み可能サイズを持つフィールド `size` 。

- `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`

     によって指定された要素 (またはバイト) 内の書き込み可能サイズを持つフィールド、 `size` および `count` 読み取り可能な要素 (バイト) の。

- `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`

     で指定された要素 (またはバイト) 内の読み取り可能なサイズと書き込み可能なサイズの両方を持つフィールド `size` 。

- `_Field_z_`

     Null で終わる文字列を含むフィールド。

- `_Struct_size_bytes_(size)`

     構造体またはクラスの宣言に適用されます。  この型の有効なオブジェクトが、で指定されているバイト数を使用して、宣言された型よりも大きくなる可能性があることを示し `size` ます。  次に例を示します。

    ```cpp

    typedef _Struct_size_bytes_(nSize)
    struct MyStruct {
        size_t nSize;
        ...
    };

    ```

     次に、型のパラメーターのバッファーサイズ (バイト単位) を `pM` `MyStruct *` 次のように取得します。

    ```cpp
    min(pM->nSize, sizeof(MyStruct))
    ```

## <a name="example"></a>例

```cpp
#include <sal.h>

// This _Struct_size_bytes_ is equivalent to what below _Field_size_ means.
_Struct_size_bytes_(__builtin_offsetof(MyBuffer, buffer) + bufferSize * sizeof(int))
struct MyBuffer
{
    static int MaxBufferSize;

    _Field_z_
    const char* name;

    int firstField;

    // ... other fields

    _Field_range_(1, MaxBufferSize)
    int bufferSize;

    _Field_size_(bufferSize)        // Preferred way - easier to read and maintain.
    int buffer[]; // Using C99 Flexible array member
};
```

この例のメモ:

- `_Field_z_` は `_Null_terminated_` に相当します。  `_Field_z_` [名前] フィールドには、[名前] フィールドが null で終わる文字列であることを指定します。
- `_Field_range_` の場合 `bufferSize` 、の値は `bufferSize` 1 から (両方を含む) の範囲内であることを指定し `MaxBufferSize` ます。
- `_Struct_size_bytes_`注釈と注釈の最終的 `_Field_size_` な結果は等価です。 同様のレイアウトを持つ構造体またはクラスの場合、 `_Field_size_` は、同等の注釈よりも参照と計算が少なくなるため、読み取りと保守が簡単になり `_Struct_size_bytes_` ます。 `_Field_size_` バイトサイズへの変換は必要ありません。 たとえば、void ポインターフィールドの場合など、バイトサイズが唯一のオプションである場合は、を `_Field_size_bytes_` 使用できます。 との両方が存在する場合は `_Struct_size_bytes_` `_Field_size_` 、ツールで両方とも使用できます。 2つの注釈が一致しない場合の対処方法は、ツールによって異なります。

## <a name="see-also"></a>関連項目

- [C/C++ コードの欠陥を減らすための SAL 注釈の使用](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL について](../code-quality/understanding-sal.md)
- [関数パラメーターおよび戻り値の注釈設定](../code-quality/annotating-function-parameters-and-return-values.md)
- [関数の動作に注釈を付ける](../code-quality/annotating-function-behavior.md)
- [ロック動作に注釈を付ける](../code-quality/annotating-locking-behavior.md)
- [注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [組み込み関数](../code-quality/intrinsic-functions.md)
- [ベスト プラクティスと例](../code-quality/best-practices-and-examples-sal.md)
