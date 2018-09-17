---
title: /Zc:alignedNew (c++ 17 オーバーア ラインされている割り当て) |Microsoft Docs
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:alignedNew
dev_langs:
- C++
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
author: corob-msft
ms.author: corob
ms.openlocfilehash: aba188a69af0449dd05df4bff14567f79a72c068
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721436"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (c++ 17 オーバーア ラインされている割り当て)

オーバーア ラインされた c++ 17 のサポートを有効にする**新しい**、動的メモリ割り当てが、最大サイズ標準的な配置の種類の既定値より大きい境界にアライン**max\_align\_t**.

## <a name="syntax"></a>構文

> **/Zc:alignedNew**[-]

## <a name="remarks"></a>Remarks

Visual Studio バージョン 15.5 では、コンパイラと c++ 17 標準オーバーア ラインされている動的メモリ割り当てのライブラリのサポートを使用できます。 ときに、 **/Zc:alignedNew**オプションを指定するなどの動的割り当て`new Example;`の配置を尊重*例*よりも大きいはいつでも`max_align_t`、最大の配置任意の基本的な型に必要です。 割り当てられた型の配置が元の演算子によって保証されているよりもなくなる場合**新しい**定義済みマクロの値として利用できる **\_ \_STDCPP\_既定\_新規\_配置\_\_**、ステートメント`new Example;`への呼び出しで結果`::operator new(size_t)`c++ 14 点が異なります。 配置がより大きい場合 **\_ \_STDCPP\_既定\_新規\_配置\_\_**、代わりに、実装を取得します使用してメモリ`::operator new(size_t, align_val_t)`します。 同様に、オーバーア ラインされている型の削除を呼び出す`::operator delete(void*, align_val_t)`、サイズが設定された署名を削除または`::operator delete(void*, size_t, align_val_t)`します。

**/Zc:alignedNew**場合オプションは使用のみ[/std:c + + + 17](std-specify-language-standard-version.md)または[/std:c + + + 最新](std-specify-language-standard-version.md)を有効にします。 **/Std:c + + + 17**または **/std:c + + + 最新**、 **/Zc:alignedNew** ISO C 17 標準に準拠するように既定で有効です。 場合は、唯一の理由演算子を実装して**新しい**と**削除**、オーバーア ラインされている割り当てをサポートするためには、c++ 17 モードでこのコードが不要になった可能性があります。 このオプションをオフにし、c++ 14 の動作に戻す**新しい**と**削除**とき **/std::c + + 17**または **/std:c + + + 最新**が指定されています。指定 **/Zc:alignedNew-** します。 演算子を実装する場合**新しい**と**削除**オーバーア ラインされている演算子を実装する準備ができていないが、**新しい**と**削除**オーバー ロードを持つ、`align_val_t`パラメーターを使用して、 **/Zc:alignedNew-** コンパイラと標準ライブラリを生成されないようにするオプションがオーバーア ラインされているオーバー ロードを呼び出します。 [/Permissive -](permissive-standards-conformance.md)オプションは既定の設定を変更してされません **/Zc:alignedNew**します。

## <a name="example"></a>例

このサンプルを示す方法演算子**新しい**と演算子**削除**ときの動作、 **/Zc:alignedNew**オプションを設定します。

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

この出力は、32 ビット ビルドの一般的なものです。 値は異なるポインターは、メモリ内でアプリケーションを実行するに基づいています。

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Visual C 準拠の問題については、次を参照してください。[非標準動作](../../cpp/nonstandard-behavior.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:alignedNew**または **/Zc:alignedNew-** 選び、 **OK**します。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)
