---
description: '詳細情報:/Zc: alignedNew (C++ 17 の過剰配置割り当て)'
title: /Zc:alignedNew (C++17 のオーバーアライン割り当て)
ms.date: 05/18/2019
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: 149272e29a9b54f5b3ec7cddaaab8d3d969c0287
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114742"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (C++17 のオーバーアライン割り当て)

**`new`** 最大サイズの標準固定型 ( **max \_ align \_ t**) の既定値を超える境界に合わせて、c++ 17 のオーバーアライン固定、動的メモリ割り当てのサポートを有効にします。

## <a name="syntax"></a>構文

> **/Zc: alignedNew** \[-]

## <a name="remarks"></a>解説

MSVC コンパイラとライブラリは、C++17 の標準オーバーアライン動的メモリ割り当てをサポートします。 **/Zc: alignedNew** オプションが指定されている場合、などの動的割り当てでは、 `new Example;` よりも大きい場合でも、*たとえば* `max_align_t` 、基本型に必要な最大のアラインメントを尊重します。 割り当てられた型のアラインメントが、元の演算子によって保証されるアラインメントを超えない場合 **`new`** 、定義済みマクロ **\_ \_ STDCPP の \_ 既定の \_ 新しい \_ \_ \_ アラインメント** の値として使用できます。このステートメントは、 `new Example;` `::operator new(size_t)` c++ 14 と同様にを呼び出します。 配置が STDCPP の既定の **\_ \_ \_ \_ 新しい \_ 配置 \_ \_** よりも大きい場合、実装はを使用してメモリを取得し `::operator new(size_t, align_val_t)` ます。 同様に、オーバーアラインされた型の削除によって `::operator delete(void*, align_val_t)` またはサイズ設定された delete のシグネチャ `::operator delete(void*, size_t, align_val_t)` が呼び出されます。

**/Zc:alignedNew** オプションは、[/std:c++17](std-specify-language-standard-version.md) または [/std:c++latest](std-specify-language-standard-version.md) が有効な場合にのみ使用できます。 **/std:c++17** または **/std:c++latest** では、ISO の C++17 標準に準拠するために既定で **/Zc:alignedNew** が有効になっています。 演算子を実装する唯一の理由で、 **`new`** **`delete`** 過剰にアラインされた割り当てをサポートする必要がある場合は、c++ 17 モードではこのコードが不要になることがあります。 このオプションをオフにして、の C++ 14 の動作に戻し、/ **`new`** **`delete`** **std:: c++ 17** または **/std: C + + latest** を使用する場合は、 **/zc: alignedNew-** を指定します。 演算子とを実装して **`new`** **`delete`** も、パラメーターを持つオーバーアラされた演算子とオーバーロードを実装する準備ができていない場合は、 **`new`** **`delete`** `align_val_t` **/zc: alignedNew** を使用して、コンパイラと標準ライブラリが過剰にアラインされたオーバーロードの呼び出しを生成しないようにします。 [/permissive-](permissive-standards-conformance.md) オプションでは、**/Zc:alignedNew** の既定の設定は変更されません。

**/Zc:alignedNew** のサポートは、Visual Studio 2017 バージョン 15.5 から開始します。

## <a name="example"></a>例

このサンプルでは **`new`** **`delete`** 、 **/zc: alignedNew** オプションが設定されている場合に演算子と演算子がどのように動作するかを示します。

```cpp
// alignedNew.cpp
// Compile by using: cl /EHsc /std:c++17 /W4 alignedNew.cpp
#include <iostream>
#include <malloc.h>
#include <new>

// "old" unaligned overloads
void* operator new(std::size_t size) {
    auto ptr = malloc(size);
    std::cout << "unaligned new(" << size << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size) {
    std::cout << "unaligned sized delete(" << ptr << ", " << size << ")\n";
    free(ptr);
}

void operator delete(void* ptr) {
    std::cout << "unaligned unsized delete(" << ptr << ")\n";
    free(ptr);
}

// "new" over-aligned overloads
void* operator new(std::size_t size, std::align_val_t align) {
    auto ptr = _aligned_malloc(size, static_cast<std::size_t>(align));
    std::cout << "aligned new(" << size << ", " <<
        static_cast<std::size_t>(align) << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size, std::align_val_t align) {
    std::cout << "aligned sized delete(" << ptr << ", " << size <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

void operator delete(void* ptr, std::align_val_t align) {
    std::cout << "aligned unsized delete(" << ptr <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

struct alignas(256) OverAligned {}; // warning C4324, structure is padded

int main() {
    delete new int;
    delete new OverAligned;
}
```

この出力は、32 ビットのビルドで一般的なものです。 ポインター値は、メモリ内でアプリケーションが実行される場所によって変わる可能性があります。

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Visual C++ の準拠に関する問題について詳しくは、「[非標準動作](../../cpp/nonstandard-behavior.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **/Zc:alignedNew** または **/Zc:alignedNew-** が含まれるように **[追加オプション]** プロパティを変更し、**[OK]** をクリックします。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)
