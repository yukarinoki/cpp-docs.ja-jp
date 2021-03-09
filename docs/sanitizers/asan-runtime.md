---
title: AddressSanitizer ランタイム
description: Microsoft C/c + + 用 AddressSanitizer ランタイムの技術的な説明。
ms.date: 03/02/2021
helpviewer_keywords:
- AddressSanitizer runtime
- Address Sanitizer runtime
- clang_rt.asan
- Clang runtime
- ASan runtime
ms.openlocfilehash: 6ab27365ba6841dd5314f1eac65abd71b7d4170d
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471028"
---
# <a name="addresssanitizer-runtime"></a>AddressSanitizer ランタイム

AddressSanitizer ランタイムライブラリは、メモリアクセスの検査を有効にするために、一般的なメモリ割り当て関数と操作をインターセプトします。 コンパイラによって生成される可能性のあるさまざまな種類の実行可能ファイルをサポートするランタイムライブラリがいくつかあります。 コンパイラとリンカーは、コンパイル時にオプションを渡す限り、適切なランタイムライブラリを自動的にリンクし [`/fsanitize=address`](../build/reference/fsanitize.md) ます。 既定の動作をオーバーライドするには、 **`/NODEFAULTLIB`** リンク時にオプションを使用します。 詳細については、「 [AddressSanitizer 言語、ビルド、およびデバッグのリファレンス](./asan-building.md)」の[リンク](./asan-building.md#linker)に関するセクションを参照してください。

次に示すのは、AddressSanitizer ランタイムにリンクするためのランタイムライブラリのインベントリです *`{arch}`* 。はまたはのいずれか *`i386`* *`x86_64`* です。

> [!NOTE]
> これらのライブラリは、アーキテクチャ名に対して Clang 規約を保持します。 MSVC 規則は通常、i386 および x86_64 ではなく、x86 と x64 です。 同じアーキテクチャを参照します。

| CRT オプション | DLL または EXE | デバック? | AddressSanitizer ランタイムバイナリライブラリ |
|--|--|--|--|
| MT | EXE | NO | *`clang_rt.asan-{arch}`*, *`clang_rt.asan_cxx-{arch}`* |
| MT | [DLL] | NO | *`clang_rt.asan_dll_thunk-{arch}`* |
| MD | いずれか | NO | *`clang_rt.asan_dynamic-{arch}`*, *`clang_rt.asan_dynamic_runtime_thunk-{arch}`* |
| MT | EXE | YES | *`clang_rt.asan_dbg-{arch}`*, *`clang_rt.asan_dbg_cxx-{arch}`* |
| MT | [DLL] | YES | *`clang_rt.asan_dbg_dll_thunk-{arch}`* |
| MD | いずれか | YES | *`clang_rt.asan_dbg_dynamic-{arch}`*, *`clang_rt.asan_dbg_dynamic_runtime_thunk-{arch}`* |

を使用してコンパイルすると、コンパイラによって `cl /fsanitize=address` [シャドウバイト](./asan-shadow-bytes.md)を管理および確認するための命令が生成されます。 プログラムは、このインストルメンテーションを使用して、スタック、ヒープ、またはグローバルスコープのメモリアクセスを確認します。 また、コンパイラはスタック変数とグローバル変数を記述するメタデータも生成します。 このメタデータにより、ランタイムは、ソースコード内の関数名、行、および列を使用して、正確なエラー診断を生成できます。 また、コンパイラチェックとランタイムライブラリは、実行時に検出された場合に、さまざまな種類の [メモリ安全性バグ](./asan-error-examples.md) を正確に診断できます。

## <a name="function-interception"></a>関数のインターセプト

AddressSanitizer は、多くのホットパッチ手法を通じて関数のインターセプトを実現します。 これらの手法は [、ソースコード自体に記述](https://github.com/llvm/llvm-project/blob/1a2eaebc09c6a200f93b8beb37130c8b8aab3934/compiler-rt/lib/interception/interception_win.cpp#L11)することをお勧めします。

ランタイムライブラリは、多くの一般的なメモリ管理およびメモリ操作関数をインターセプトします。 リストについては、「 [AddressSanitizer list of インターセプト functions](#intercepted_functions)」を参照してください。 割り当てインターセプターは、各割り当て呼び出しに関連するメタデータとシャドウバイトを管理します。 またはのような CRT 関数 `malloc` `delete` が呼び出されるたびに、インターセプターは AddressSanitizer シャドウメモリ領域内の特定の値を設定して、それらのヒープ位置に現在アクセスできるかどうかと、割り当ての境界を示します。 これらのシャドウバイトにより、コンパイラによって生成される [シャドウバイト](./asan-shadow-bytes.md) のチェックによって、読み込みまたはストアが有効かどうかを判断できます。

インターセプトが成功するとは限りません。 関数のプロローグが短すぎてを `jmp` 書き込むことができない場合、インターセプトは失敗する可能性があります。 インターセプトエラーが発生した場合、プログラムはをスロー `debugbreak` して停止します。 デバッガーをアタッチすると、傍受の問題の原因が明確になります。 この問題が発生した場合は、 [バグを報告](https://aka.ms/feedback/report?space=62)してください。

> [!NOTE]
> ユーザーは、必要に応じて、環境変数を任意の値に設定して、失敗したインターセプトを続行することができ `ASAN_WIN_CONTINUE_ON_INTERCEPTION_FAILURE` ます。 インターセプトエラーが解消されると、その関数のバグレポートが失われる可能性があります。

## <a name="custom-allocators-and-the-addresssanitizer-runtime"></a>Custom アロケーターと AddressSanitizer runtime

AddressSanitizer ランタイムは、共通のアロケーターインターフェイス、、 `malloc` / `free` `new` / `delete` 、 `HeapAlloc` / `HeapFree` (via `RtlAllocateHeap` / `RtlFreeHeap` ) のインターセプターを提供します。 多くのプログラムは、何らかの理由でカスタムアロケーターを使用して `dlmalloc` います。たとえば、またはインターフェイスとを使用したソリューションを使用するプログラムがあり `std::allocator` `VirtualAlloc()` ます。 コンパイラは、シャドウメモリ管理の呼び出しをカスタムアロケーターに自動的に追加できません。 ユーザーは、 [提供された手動のポイズニングインターフェイス](#poisoning)を使用する必要があります。 この API により、これらのアロケーターは、既存の AddressSanitizer runtime および [shadow バイト](./asan-shadow-bytes.md) 表記規則と共に正常に機能するようになります。

## <a name="manual-addresssanitizer-poisoning-interface"></a><a name="poisoning"></a> 手動の AddressSanitizer ポイズニングインターフェイス

Enlightening のインターフェイスは単純ですが、ユーザーにアラインメントの制限が課せられます。 ユーザーは、インポートによってこれらのプロトタイプをインポートでき [`sanitizer/asan_interface.h`](https://github.com/llvm/llvm-project/blob/main/compiler-rt/include/sanitizer/asan_interface.h) ます。 インターフェイス関数のプロトタイプは次のとおりです。

```cpp
void __asan_poison_memory_region(void const volatile *addr, size_t size);
void __asan_unpoison_memory_region(void const volatile *addr, size_t size);
```

便宜上、 [AddressSanitizer インターフェイスヘッダーファイル](https://github.com/llvm/llvm-project/blob/main/compiler-rt/include/sanitizer/asan_interface.h) にはラッパーマクロが用意されています。 これらのマクロは、コンパイル中に AddressSanitizer 機能が有効になっているかどうかを確認します。 これにより、ソースコードが不要になったときにポイズニング関数呼び出しを省略できます。 上記の関数を直接呼び出すよりも、これらのマクロを使用することをお勧めします。

```cpp
#define ASAN_POISON_MEMORY_REGION(addr, size)
#define ASAN_UNPOISON_MEMORY_REGION(addr, size)
```

## <a name="alignment-requirements-for-addresssanitizer-poisoning"></a>AddressSanitizer ポイズニングのアラインメント要件

シャドウバイトの手動ポイズニングは、アラインメント要件を考慮する必要があります。 シャドウバイトがシャドウメモリ内のバイト境界で終了するように、必要に応じて余白を追加する必要があります。 AddressSanitizer shadow メモリ内の各ビットは、アプリケーションのメモリ内の1バイトの状態をエンコードします。 このエンコーディングは、各割り当ての合計サイズ (埋め込みを含む) を8バイト境界に揃える必要があることを意味します。 配置要件が満たされていない場合、正しくないバグ報告が発生する可能性があります。 不適切なレポートは、不足しているレポート (偽陽性) として、またはエラー以外 (偽陽性) を報告することがあります。

アラインメントの要件と潜在的な問題の図解は、提供されている [ASan アラインメントの例](https://github.com/mcgov/asan_alignment_example)を参照してください。 1つは、手動シャドウメモリのポイズニングに問題があることを示す小さなプログラムです。 2つ目は、インターフェイスを使用した手動ポイズニングの実装例です `std::allocator` 。

## <a name="run-time-options"></a>実行時オプション

Microsoft C/c + + (MSVC) は、 [llvm プロジェクトリポジトリの Clang AddressSanitizer ランタイム](https://github.com/llvm/llvm-project)に基づくランタイムを使用します。 このため、ほとんどのランタイムオプションは、2つのバージョン間で共有されます。 [Public Clang runtime オプションの完全な一覧については、こちらを参照して](https://github.com/google/sanitizers/wiki/SanitizerCommonFlags)ください。 以下のセクションでは、いくつかの違いについて説明します。 期待どおりに機能しないオプションが検出された場合は、 [バグを報告](https://aka.ms/feedback/report?space=62)します。

### <a name="unsupported-addresssanitizer-options"></a>サポートされていない AddressSanitizer オプション

- detect_container_overflow
- unmap_shadow_on_exit

> [!NOTE]
> AddressSanitizer runtime オプションは、 `halt_on_error` 期待どおりに機能しません。 Clang と MSVC の両方のランタイムライブラリでは、多くのエラーの種類は、ほとんどのメモリ破損エラーを含め、 **継続不可能** と見なされます。

詳細については、「 [Clang 12.0 との違い](./asan.md#differences) 」を参照してください。

### <a name="msvc-specific-addresssanitizer-runtime-options"></a>MSVC 固有の AddressSanitizer ランタイムオプション

- `windows_hook_legacy_allocators` ブール値。をに設定する `true` と、とアロケーターのインターセプトが有効に [`GlobalAlloc`](/windows/win32/api/winbase/nf-winbase-globalalloc) [`LocalAlloc`](/windows/win32/api/winbase/nf-winbase-localalloc) なります。

> [!NOTE]
> `windows_hook_legacy_allocators`この記事が書き込まれたときに、パブリック llvm プロジェクトランタイムでオプションを使用できませんでした。 このオプションは、最終的にパブリックプロジェクトに反映される可能性があります。ただし、コードレビューとコミュニティへの同意に依存しています。
>
> `windows_hook_rtl_allocators`以前は、AddressSanitizer が試験段階であったオプトイン機能であるオプションが既定で有効になりました。

## <a name="addresssanitizer-list-of-intercepted-functions-windows"></a><a name="intercepted_functions"></a> AddressSanitizer インターセプトした関数の一覧 (Windows)

AddressSanitizer ランタイムでは、実行時にメモリの安全性チェックを有効にするための多くの機能がホットパッチされています。 AddressSanitizer ランタイムが監視する関数の完全でない一覧を次に示します。

### <a name="default-interceptors"></a>既定のインターセプター

- [`__C_specific_handler` (x64 のみ)](/windows/win32/devnotes/--c-specific-handler2)
- [`_aligned_free`](../c-runtime-library/reference/aligned-free.md)
- [`_aligned_malloc`](../c-runtime-library/reference/aligned-malloc.md)
- [`_aligned_msize`](../c-runtime-library/reference/aligned-msize.md)
- [`_aligned_realloc`](../c-runtime-library/reference/aligned-realloc.md)
- [`_calloc_base`](../c-runtime-library/reference/calloc.md)
- [`_calloc_crt`](../c-runtime-library/reference/calloc.md)
- [`_calloc_dbg` (デバッグランタイムのみ)](../c-runtime-library/reference/calloc-dbg.md)
- [`_except_handler3` (x86 のみ)](../c-runtime-library/except-handler3.md)
- [ `_except_handler4` (x86 のみ)](../c-runtime-library/internal-crt-globals-and-functions.md) (非公開)
- [`_expand`](../c-runtime-library/reference/expand.md)
- `_expand_base` 未記載
- [`_expand_dbg` (デバッグランタイムのみ)](../c-runtime-library/reference/expand-dbg.md)
- [`_free_base`](../c-runtime-library/internal-crt-globals-and-functions.md) 未記載
- [`_free_dbg` (デバッグランタイムのみ)](../c-runtime-library/reference/free-dbg.md)
- [`_malloc_base`](../c-runtime-library/internal-crt-globals-and-functions.md) 未記載
- `_malloc_crt` 未記載
- [`_malloc_dbg` (デバッグランタイムのみ)](../c-runtime-library/reference/malloc-dbg.md)
- [`_msize`](../c-runtime-library/reference/msize.md)
- `_msize_base` 未記載
- [`_msize_dbg` (デバッグランタイムのみ)](../c-runtime-library/reference/msize-dbg.md)
- [`_realloc_base`](../c-runtime-library/internal-crt-globals-and-functions.md) 未記載
- `_realloc_crt` 未記載
- [`_realloc_dbg` (デバッグランタイムのみ)](../c-runtime-library/reference/realloc-dbg.md)
- [`_recalloc`](../c-runtime-library/reference/recalloc.md)
- `_recalloc_base` 未記載
- `_recalloc_crt` 未記載
- [`_recalloc_dbg` (デバッグランタイムのみ)](../c-runtime-library/reference/recalloc-dbg.md)
- [`_strdup`](../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)
- [`atoi`](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)
- [`atol`](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)
- [`calloc`](../c-runtime-library/reference/calloc.md)
- [`CreateThread`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread)
- [`free`](../c-runtime-library/reference/free.md)
- [`frexp`](../c-runtime-library/reference/frexp.md)
- [`longjmp`](../c-runtime-library/reference/longjmp.md)
- [`malloc`](../c-runtime-library/reference/malloc.md)
- [`memchr`](../c-runtime-library/reference/memchr-wmemchr.md)
- [`memcmp`](../c-runtime-library/reference/memcmp-wmemcmp.md)
- [`memcpy`](../c-runtime-library/reference/memcpy-wmemcpy.md)
- [`memmove`](../c-runtime-library/reference/memmove-wmemmove.md)
- [`memset`](../c-runtime-library/reference/memset-wmemset.md)
- [`RaiseException`](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception)
- [`realloc`](../c-runtime-library/reference/realloc.md)
- [`RtlAllocateHeap`](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap)
- [`RtlCreateHeap`](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateheap)
- [`RtlDestroyHeap`](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateheap)
- [`RtlFreeHeap`](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlfreeheap)
- [`RtlRaiseException`](/windows/win32/api/rtlsupportapi/nf-rtlsupportapi-rtlraiseexception)
- `RtlReAllocateHeap` 未記載
- `RtlSizeHeap` 未記載
- [`SetUnhandledExceptionFilter`](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setunhandledexceptionfilter)
- [`strcat`](../c-runtime-library/reference/strcat-wcscat-mbscat.md)
- [`strchr`](../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)
- [`strcmp`](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)
- [`strcpy`](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)
- [`strcspn`](../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)
- [`strdup`](../c-runtime-library/reference/strdup-wcsdup.md)
- [`strlen`](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
- [`strncat`](../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)
- [`strncmp`](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)
- [`strncpy`](../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)
- [`strnlen`](../c-runtime-library/reference/strnlen-strnlen-s.md)
- [`strpbrk`](../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)
- [`strspn`](../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
- [`strstr`](../c-runtime-library/reference/strstr-wcsstr-mbsstr-mbsstr-l.md)
- [`strtok`](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md)
- [`strtol`](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)
- [`wcslen`](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)
- [`wcsnlen`](../c-runtime-library/reference/strnlen-strnlen-s.md)

### <a name="optional-interceptors"></a>オプションのインターセプター

ここに記載されているインターセプターは、AddressSanitizer runtime オプションが有効になっている場合にのみインストールされます。 `windows_hook_legacy_allocators`レガシアロケーターインターセプトを有効にするには、に設定し `true` ます。
`set ASAN_OPTIONS=windows_hook_legacy_allocators=true`

- [`GlobalAlloc`](/windows/win32/api/winbase/nf-winbase-globalalloc)
- [`GlobalFree`](/windows/win32/api/winbase/nf-winbase-GlobalFree)
- [`GlobalHandle`](/windows/win32/api/winbase/nf-winbase-GlobalHandle)
- [`GlobalLock`](/windows/win32/api/winbase/nf-winbase-GlobalLock)
- [`GlobalReAlloc`](/windows/win32/api/winbase/nf-winbase-GlobalReAlloc)
- [`GlobalSize`](/windows/win32/api/winbase/nf-winbase-GlobalSize)
- [`GlobalUnlock`](/windows/win32/api/winbase/nf-winbase-GlobalUnlock)
- [`LocalAlloc`](/windows/win32/api/winbase/nf-winbase-LocalAlloc)
- [`LocalFree`](/windows/win32/api/winbase/nf-winbase-LocalFree)
- [`LocalHandle`](/windows/win32/api/winbase/nf-winbase-LocalHandle)
- [`LocalLock`](/windows/win32/api/winbase/nf-winbase-LocalLock)
- [`LocalReAlloc`](/windows/win32/api/winbase/nf-winbase-LocalReAlloc)
- [`LocalSize`](/windows/win32/api/winbase/nf-winbase-LocalSize)
- [`LocalUnlock`](/windows/win32/api/winbase/nf-winbase-LocalUnlock)

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)
