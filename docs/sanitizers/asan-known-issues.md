---
title: AddressSanitizer の既知の問題
description: AddressSanitizer for Microsoft C/c + + の既知の問題に関する技術的な説明。
ms.date: 03/02/2021
helpviewer_keywords:
- AddressSanitizer known issues
ms.openlocfilehash: 0bd8b8cc05265930b8ade514c4d1f8ea162bb304
ms.sourcegitcommit: dc77cf3b5b644d8e2adf595540b98194ab95c6e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "106377230"
---
# <a name="addresssanitizer-known-issues"></a>AddressSanitizer の既知の問題

> [!NOTE]
> 今後のリリースで表示する内容に関する [フィードバック](https://aka.ms/vsfeedback/browsecpp) を送信し、問題が発生した場合には [バグを報告](https://aka.ms/feedback/report?space=62) します。

## <a name="incompatible-options-and-functionality"></a><a name="incompatible-options"></a> 互換性のないオプションと機能

これらのオプションと機能はと互換性が [`/fsanitize=address`](../build/reference/fsanitize.md) なく、無効にするか、回避する必要があります。

- [`/RTC`](../build/reference/rtc-run-time-error-checks.md)オプションは AddressSanitizer と互換性がないため、無効にする必要があります。
- [インクリメンタルリンク](../build/reference/incremental-link-incrementally.md) はサポートされていないため、無効にする必要があります。
- [エディットコンティニュ](/visualstudio/debugger/edit-and-continue-visual-cpp) はサポートされていないため、無効にする必要があります。
- [コルーチン](https://devblogs.microsoft.com/cppblog/category/coroutine/) は AddressSanitizer と互換性がなく、再開可能な関数はインストルメンテーションから除外されます。
- [OpenMP](../build/reference/openmp-enable-openmp-2-0-support.md) はサポートされていないため、無効にする必要があります。
- [マネージ C++](../build/reference/clr-common-language-runtime-compilation.md) はサポートされていないため、無効にする必要があります。
- [C++ AMP](../parallel/amp/cpp-amp-overview.md) はサポートされていないため、無効にする必要があります。
- [特別なケースリスト](https://clang.llvm.org/docs/SanitizerSpecialCaseList.html) ファイルはサポートされていません。

## <a name="standard-library-support"></a>標準ライブラリのサポート

MSVC standard library (STL) は、AddressSanitizer を理解するための対応ではありません。 STL コードで AddressSanitizer 例外が発生すると、真のバグが識別されます。 ただし、これらは正確ではありません。

この例では、有効桁数が不足しています。

```cpp
// Compile with: cl /fsanitize=address /Zi
#include <vector>

int main() {   
    // Create a vector of size 10, but with a capacity of 20.    
    std::vector<int> v(10);
    v.reserve(20);

    // Currently, MSVC ASan does NOT raise an exception here.
    // While this is an out-of-bounds write to 'v', MSVC ASan
    // ensures the write is within the heap allocation size (20).
    v[10] = 1;

    // MSVC ASan DOES raise an exception here, as this write
    // is out of bounds from the heap allocation.
    v[20] = 1;
}
```

## <a name="windows-versions"></a>Windows のバージョン

特定の Windows バージョンとの依存関係があるため、サポートは Windows 10 に焦点を合わせています。 MSVC AddressSanitizer は、10.0.14393 (RS1) でテストされ、10.0.21323 (プレリリースの insider ビルド) をテストしました。 問題が発生した場合は[、バグを報告](https://aka.ms/feedback/report?space=62)します。

## <a name="memory-usage"></a>メモリ使用量

AddressSanitizer ランタイムは、実行中に OS に対してメモリを解放しません。 OS の観点から見ると、メモリリークが発生しているように見えるかもしれません。 この設計上の決定は意図的なものであるため、必要なすべてのメモリを事前に割り当てないようにしてください。

## <a name="addresssanitizer-runtime-dll-locations"></a>AddressSanitizer ランタイム DLL の場所

*`clang_rt.asan*.dll`* ランタイムファイルは、のコンパイラの横にインストールされ *`%VSINSTALLDIR%\VC\Tools\MSVC\<version>\bin\<host-arch>\<target-arch>\`* ます。 これらの場所は、デバッグセッションのパスにあり、Visual Studio の開発者コマンドプロンプトに表示されます。 これらのファイルは *`C:\Windows\System32`* 、またはには配置されません *`C:\Windows\SysWOW64`* 。

## <a name="custom-property-sheet-support"></a>カスタムプロパティシートのサポート

Visual Studio IDE の [プロパティマネージャー] ウィンドウを使用すると、カスタム *`.props`* ファイルをプロジェクトに追加できます。 **Enable Address サニタイザー** プロパティ () が表示されている場合でも、 `<EnableASAN>` ビルドでは受け入れられません。 これは、カスタムファイルがの後に追加されるためです *`.props`* 。これは、値を使用して *`Microsoft.cpp.props`* `<EnableASAN>` 他のプロパティを設定します。

回避策として、 *`Directory.Build.props`* プロジェクトのルートにファイルを作成して、プロパティを定義でき `<EnableASAN>` ます。 詳細については、「 [C++ ビルドをカスタマイズ](/visualstudio/msbuild/customize-your-build#customize-c-builds)する」を参照してください。

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer のエラー例](./asan-error-examples.md)
