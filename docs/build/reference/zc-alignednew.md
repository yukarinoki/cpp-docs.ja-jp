---
title: /Zc:alignedNew (c++ 17 オーバーア ラインされている割り当て) |Microsoft ドキュメント
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
ms.openlocfilehash: 5f9527d63a9843bd4df90520e5b4759126d72fe1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378391"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (c++ 17 オーバーア ラインされている割り当て)

C++ 17 オーバーアラインメントのサポートを有効にする**新しい**、動的メモリ割り当ては最大サイズの標準固定された型での既定値より大きい境界にアライン**max\_整列\_t**.

## <a name="syntax"></a>構文

> **/Zc:alignedNew**[-]

## <a name="remarks"></a>コメント

Visual Studio バージョン 15.5 は、コンパイラと c++ 17 標準オーバーア ラインされている動的メモリ割り当てのライブラリのサポートを使用できます。 ときに、 **/Zc:alignedNew**オプションを指定するなどの動的割り当て`new Example;`の配置を尊重*例*でもある場合よりも大きい`max_align_t`、最大の配置任意の基本型が必要です。 割り当てられた型のアラインメントはよりも、元の演算子によって保証されているときに**新しい**定義済みのマクロの値として使用できる、  **\_ \_STDCPP\_既定\_新規\_配置\_\_**、ステートメント`new Example;`への呼び出しで結果`::operator new(size_t)`c++ 14 の場合と同様です。 配置が超える場合 **\_ \_STDCPP\_既定\_新規\_配置\_\_** 実装では、代わりに取得使用してメモリ`::operator new(size_t, align_val_t)`です。 同様に、オーバーア ラインされている型の削除を呼び出す`::operator delete(void*, align_val_t)`、サイズ設定された署名を削除または`::operator delete(void*, size_t, align_val_t)`です。

**/Zc:alignedNew**オプションは、のみ使用可能な場合に[/std:c + + 17](std-specify-language-standard-version.md)または[/std:c + + 最新](std-specify-language-standard-version.md)を有効にします。 **/Std:c + + 17**または **/std:c + + 最新**、 **/Zc:alignedNew** ISO c++ 17 規格に準拠するように既定で有効にします。 場合は、唯一の理由演算子を実装して**新しい**と**削除**オーバーア ラインされている割り当てをサポートするためには、c++ 17 モードでこのコードが不要になった可能性があります。 このオプションをオフにし、c++ 14 の動作に戻します**新しい**と**削除**とき **/std::c:operator++ 17**または **/std:c + + 最新**が指定されています。指定 **/Zc:alignedNew-** です。 演算子を実装する場合**新しい**と**削除**オーバーア ラインされている演算子を実装する準備ができていないが、**新しい**と**削除**持つオーバー ロード、`align_val_t`パラメーターを使用して、 **/Zc:alignedNew-** コンパイラおよび標準ライブラリが生成することを防止するオプションがオーバーア ラインされているオーバー ロードを呼び出します。 [寛容/-](permissive-standards-conformance.md)オプションが既定の設定を変更していない **/Zc:alignedNew**です。

## <a name="example"></a>例

このサンプルでは方法演算子**新しい**と演算子**削除**ときの動作、 **/Zc:alignedNew**オプションを設定します。

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

この出力は、32 ビット ビルド通常です。 値は異なるポインターは、メモリ内でアプリケーションを実行するに基づいています。

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Visual C の準拠の問題については、次を参照してください。[非標準動作](../../cpp/nonstandard-behavior.md)です。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:alignedNew**または **/Zc:alignedNew-** を選択し**OK**です。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)  
