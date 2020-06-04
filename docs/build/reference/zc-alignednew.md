---
title: /Zc:alignedNew (C++17 のオーバーアライン割り当て)
ms.date: 05/18/2019
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: 041f62bbbf5f7a2750960d21d1534cf6daf4b874
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335692"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (C++17 のオーバーアライン割り当て)

最大サイズの標準配置型である **max\_align\_t** の既定値を超える境界上で動的メモリ割り当てを行う、C++17 のオーバーアラインの **new** のサポートを有効にします。

## <a name="syntax"></a>構文

> **/Zc:整列新しい**\[-]

## <a name="remarks"></a>解説

MSVC コンパイラとライブラリは、C++17 の標準オーバーアライン動的メモリ割り当てをサポートします。 **/Zc:alignedNew**オプションを指定すると、たとえば、基本型に`new Example;`必要な最大の配置である`max_align_t`場合でも *、Example*の配置を考慮するなどの動的割り当てが行われます。 割`new Example;`り当てられた型の配置が、定義済みのマクロ`::operator new(size_t)`**\_\_STDCPP\_\_DEFAULT NEW\_ALIGNMENT\_** の値として使用可能な元の演算子**new**によって保証された配置以下の場合、ステートメントは C++14 で行ったように呼び出されます。 配置が**\_\_STDCPP\_DEFAULT\_NEW\_ALIGNMENT\_** より大きい場合、実装は代わりに を使用`::operator new(size_t, align_val_t)`してメモリを取得します。 同様に、オーバーアラインされた型の削除によって `::operator delete(void*, align_val_t)` またはサイズ設定された delete のシグネチャ `::operator delete(void*, size_t, align_val_t)` が呼び出されます。

**/Zc:alignedNew** オプションは、[/std:c++17](std-specify-language-standard-version.md) または [/std:c++latest](std-specify-language-standard-version.md) が有効な場合にのみ使用できます。 **/std:c++17** または **/std:c++latest** では、ISO の C++17 標準に準拠するために既定で **/Zc:alignedNew** が有効になっています。 オーバーアラインされた割り当てをサポートするためだけに **new** と **delete** の演算子を実装している場合、このコードは C++17 モードでは不要になる場合があります。 このオプションをオフにし、**/std:c++17** または **/std:c++latest** を使用したときの **new** と **delete** の動作を C++14 のものに戻すには、**/Zc:alignedNew-** を指定します。 **new** と **delete** の演算子を実装したものの、`align_val_t` パラメーターを持つオーバーアラインされた演算子 **new** と **delete** のオーバーロードを実装する準備ができていない場合は、**/Zc:alignedNew-** オプションを使用してコンパイラと標準ライブラリがオーバーアラインされたオーバーロードに対して呼び出しを行わないようにします。 [/permissive-](permissive-standards-conformance.md) オプションでは、**/Zc:alignedNew** の既定の設定は変更されません。

**/Zc:alignedNew** のサポートは、Visual Studio 2017 バージョン 15.5 から開始します。

## <a name="example"></a>例

このサンプルは、**/Zc:alignedNew** オプションが設定されているときの演算子 **new** と演算子 **delete** の動作を示しています。

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

1. **[構成プロパティ** > **C/C++** > **コマンド ライン**] プロパティ ページを選択します。

1. **/Zc:alignedNew** または **/Zc:alignedNew-** が含まれるように **[追加オプション]** プロパティを変更し、**[OK]** をクリックします。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)
