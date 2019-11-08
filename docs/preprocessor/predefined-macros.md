---
title: 定義済みマクロ
ms.custom: update_every_version
ms.date: 10/01/2019
f1_keywords:
- _ATL_VER
- __ATOM__
- __AVX__
- __AVX2__
- __AVX512BW__
- __AVX512CD__
- __AVX512DQ__
- __AVX512F__
- __AVX512VL__
- _CHAR_UNSIGNED
- __CLR_VER
- _CONTROL_FLOW_GUARD
- __COUNTER__
- __cplusplus
- __cplusplus_cli
- __cplusplus_winrt
- _CPPRTTI
- _CPPUNWIND
- __DATE__
- _DEBUG
- _DLL
- __FILE__
- __FUNCDNAME__
- __FUNCSIG__
- __FUNCTION__
- _INTEGRAL_MAX_BITS
- _ISO_VOLATILE
- _KERNEL_MODE
- __LINE__
- _M_AMD64
- _M_ARM
- _M_ARM_ARMV7VE
- _M_ARM_FP
- _M_ARM64
- _M_CEE
- _M_CEE_PURE
- _M_CEE_SAFE
- _M_FP_EXCEPT
- _M_FP_FAST
- _M_FP_PRECISE
- _M_FP_STRICT
- _M_IX86
- _M_IX86_FP
- _M_X64
- _MANAGED
- _MFC_VER
- _MSC_BUILD
- _MSC_EXTENSIONS
- _MSC_FULL_VER
- _MSC_VER
- _MSVC_LANG
- __MSVC_RUNTIME_CHECKS
- _MT
- _NATIVE_WCHAR_T_DEFINED
- _NO_SIZED_DEALLOCATION
- _OPENMP
- _PREFAST_
- _RESUMABLE_FUNCTIONS_SUPPORTED
- _RTC_CONVERSION_CHECKS_ENABLED
- __STDC__
- __STDC_HOSTED__
- __STDCPP_THREADS__
- __TIME__
- __TIMESTAMP__
- __VA_ARGS__
- _VC_NODEFAULTLIB
- _WCHAR_T_DEFINED
- _WIN32
- _WIN64
- _WINRT_DLL
- __func__
helpviewer_keywords:
- timestamps, preprocessor macro
- cl.exe compiler, version number
- version numbers, C/C++ compiler (cl.exe)
- macros, predefined C++
- preprocessor, macros
- predefined macros
- _ATL_VER macro
- __ATOM__ macro
- __AVX__ macro
- __AVX2__ macro
- __AVX512BW__ macro
- __AVX512CD__ macro
- __AVX512DQ__ macro
- __AVX512F__ macro
- __AVX512VL__ macro
- _CHAR_UNSIGNED macro
- __CLR_VER macro
- _CONTROL_FLOW_GUARD macro
- __COUNTER__ macro
- __cplusplus macro
- __cplusplus_cli macro
- __cplusplus_winrt macro
- _CPPRTTI macro
- _CPPUNWIND macro
- __DATE__ macro
- _DEBUG macro
- _DLL macro
- __FILE__ macro
- __FUNCDNAME__ macro
- __FUNCSIG__ macro
- __FUNCTION__ macro
- _INTEGRAL_MAX_BITS macro
- _ISO_VOLATILE macro
- _KERNEL_MODE macro
- __LINE__ macro
- _M_AMD64 macro
- _M_ARM macro
- _M_ARM_ARMV7VE macro
- _M_ARM_FP macro
- _M_ARM64 macro
- _M_CEE macro
- _M_CEE_PURE macro
- _M_CEE_SAFE macro
- _M_FP_EXCEPT macro
- _M_FP_FAST macro
- _M_FP_PRECISE macro
- _M_FP_STRICT macro
- _M_IX86 macro
- _M_IX86_FP macro
- _M_X64 macro
- _MANAGED macro
- _MFC_VER macro
- _MSC_BUILD macro
- _MSC_EXTENSIONS macro
- _MSC_FULL_VER macro
- _MSC_VER macro
- _MSVC_LANG macro
- __MSVC_RUNTIME_CHECKS macro
- _MT macro
- _NATIVE_WCHAR_T_DEFINED macro
- _NO_SIZED_DEALLOCATION macro
- _OPENMP macro
- _PREFAST_ macro
- _RESUMABLE_FUNCTIONS_SUPPORTED macro
- _RTC_CONVERSION_CHECKS_ENABLED macro
- __STDC__ macro
- __STDC_HOSTED__ macro
- __STDCPP_THREADS__ macro
- __TIME__ macro
- __TIMESTAMP__ macro
- __VA_ARGS__ macro
- _VC_NODEFAULTLIB macro
- _WCHAR_T_DEFINED macro
- _WIN32 macro
- _WIN64 macro
- _WINRT_DLL macro
- __func__ identifier
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
ms.openlocfilehash: eb75273bc8cbe5ccbf62edc82a1e7deccc605757
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816604"
---
# <a name="predefined-macros"></a>定義済みマクロ

Microsoft C/C++コンパイラ (MSVC) は、言語 (C またはC++)、コンパイルターゲット、および選択されたコンパイラオプションに応じて、特定のプリプロセッサマクロを事前します。

MSVC は、ANSI/ISO C99 標準および ISO C++ 14 および C++ 17 標準で必要とされる定義済みのプリプロセッサマクロをサポートしています。 実装では、いくつかの Microsoft 固有のプリプロセッサマクロもサポートされています。 一部のマクロは、特定のビルド環境またはコンパイラオプションに対してのみ定義されています。 メモしている場合を除き、マクロは、 **/d**コンパイラオプションの引数として指定されているかのように、翻訳単位全体を通じて定義されます。 定義されている場合、コンパイルの前にプリプロセッサによって、マクロが指定された値に拡張されます。 定義済みマクロは引数を取らず、再定義することはできません。

## <a name="standard-predefined-identifier"></a>標準の定義済み識別子

コンパイラは、ISO C99 および ISO C++ 11 によって指定された定義済みの識別子をサポートしています。

- **&#95;&#95;func&#95;&#95;** 関数ローカルとして外側の関数の非修飾かつ非装飾名**static const**の配列**char**します。

    ```cpp
    void example(){
        printf("%s\n", __func__);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>標準の定義済みマクロ

コンパイラは、ISO C99 および ISO C++ 17 標準によって指定されたこれらの定義済みマクロをサポートしています。

- **&#95;cplusplus &#95;** 翻訳単位をとC++してコンパイルするときに整数リテラル値として定義されます。 それ以外の場合、定義されていません。

- **&#95;&#95;DATE&#95;&#95;** 現在のソース ファイルのコンパイル日付。 日付は、 *Mmm dd yyyy*という形式の定数長の文字列リテラルです。 月の名前*Mmm*は、C ランタイムライブラリ (CRT) の[asctime](../c-runtime-library/reference/asctime-wasctime.md)関数によって生成される月の省略名と同じです。 日付*dd*の最初の文字は、値が10未満の場合は空白になります。 このマクロは常に定義します。

- **&#95;&#95;FILE&#95;&#95;** 現在のソース ファイルの名前。 **&#95;&#95;FILE&#95;&#95;** 文字の文字列リテラルに展開します。 ファイルへの完全パスが表示されるようにするには、 [/fc (診断でソースコードファイルの完全パス)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)を使用します。 このマクロは常に定義します。

- **&#95;&#95;LINE&#95;&#95;** 現在のソース ファイル内の整数の行番号として定義されています。 値、 **&#95;&#95;LINE&#95;&#95;** マクロを使用して変更することができます、`#line`ディレクティブ。 このマクロは常に定義します。

- **&#95;&#95;STDC&#95;&#95;** C としてコンパイルされる場合、および 1 として定義されている、 [/Za](../build/reference/za-ze-disable-language-extensions.md)コンパイラ オプションを指定します。 それ以外の場合、定義されていません。

- **&#95;&#95;STDC&#95;HOSTED&#95;&#95;** 実装がある場合は、1 として定義されている、*実装がホストされている*、必要な標準ライブラリ全体をサポートしています。 それ以外の場合は0として定義されます。

- **&#95;&#95;STDCPP&#95;THREADS&#95;&#95;** プログラムは、実行の 1 つ以上のスレッドを持つことができる場合にのみ、1 として定義されており、C++ としてコンパイルします。 それ以外の場合、定義されていません。

- **&#95;&#95;TIME&#95;&#95;** 前処理された翻訳単位の変換のとき。 時刻は*hh: mm: ss*形式の文字列リテラルで、CRT [asctime](../c-runtime-library/reference/asctime-wasctime.md)関数によって返される時刻と同じです。 このマクロは常に定義します。

## <a name="microsoft-specific-predefined-macros"></a>Microsoft 固有の定義済みマクロ

MSVC では、これらの追加の定義済みマクロがサポートされます。

- **&#95;&#95;ATOM&#95;&#95;** 1 として定義されている、 [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md)コンパイラ オプションを設定し、コンパイラのターゲットは x86 または x64 です。 それ以外の場合、定義されていません。

- **&#95; AVX &#95; &#95;** [/Arch: AVX](../build/reference/arch-x86.md)、 [/arch: AVX2](../build/reference/arch-x86.md) 、または[/arch: AVX512](../build/reference/arch-x86.md)コンパイラオプションが設定され、コンパイラターゲットが x86 または x64 の場合、1として定義されます。 それ以外の場合、定義されていません。

- **&#95; AVX2 &#95; &#95;** [/Arch: AVX2](../build/reference/arch-x86.md)または[/arch: AVX512](../build/reference/arch-x86.md)コンパイラオプションが設定され、コンパイラターゲットが x86 または x64 の場合、1として定義されます。 それ以外の場合、定義されていません。

- **&#95; AVX512BW &#95; &#95;** [/Arch: AVX512](../build/reference/arch-x86.md)コンパイラオプションが設定され、コンパイラターゲットが x86 または x64 の場合、1として定義されます。 それ以外の場合、定義されていません。

- **&#95; AVX512CD &#95; &#95;** [/Arch: AVX512](../build/reference/arch-x86.md)コンパイラオプションが設定され、コンパイラターゲットが x86 または x64 の場合、1として定義されます。 それ以外の場合、定義されていません。

- **&#95; AVX512DQ &#95; &#95;** [/Arch: AVX512](../build/reference/arch-x86.md)コンパイラオプションが設定され、コンパイラターゲットが x86 または x64 の場合、1として定義されます。 それ以外の場合、定義されていません。

- **&#95; AVX512F &#95; &#95;** [/Arch: AVX512](../build/reference/arch-x86.md)コンパイラオプションが設定され、コンパイラターゲットが x86 または x64 の場合、1として定義されます。 それ以外の場合、定義されていません。

- **&#95; AVX512VL &#95; &#95;** [/Arch: AVX512](../build/reference/arch-x86.md)コンパイラオプションが設定され、コンパイラターゲットが x86 または x64 の場合、1として定義されます。 それ以外の場合、定義されていません。

- **&#95;CHAR&#95;UNSIGNED** 既定の場合は 1 として定義されている**char**型が符号なし。 この値が定義されているときに、 [/J (既定の char 型の unsigned)](../build/reference/j-default-char-type-is-unsigned.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;CLR VER &#95;&#95;** アプリのコンパイルに使用される共通言語ランタイム (CLR) のバージョンを表す整数リテラルとして定義されます。 値は`Mmmbbbbb`、と`mm` `M` いう`bbbbb`形式でエンコードされます。ここで、はランタイムのメジャーバージョン、はランタイムのマイナーバージョン、はビルド番号です。 **&#95;&#95;CLR&#95;VER**は、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラオプションが設定されている場合に定義されます。 それ以外の場合、定義されていません。

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(__CLR_VER);
    }
    ```

- **&#95;CONTROL&#95;FLOW&#95;GUARD**1 として定義されている、 [/guard:cf (有効にする制御フロー ガード)](../build/reference/guard-enable-control-flow-guard.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;&#95;COUNTER&#95; &#95;** 0 から始まる整数リテラルに展開します。 たびに、ソース ファイルで使用が含まれているソース ファイルのヘッダーまたは 1 で、値が増加します。 **&#95;&#95;COUNTER&#95;&#95;** プリコンパイル済みヘッダーを使用すると、その状態を記憶します。 このマクロは常に定義します。

  この例で`__COUNTER__`は、を使用して、同じ型の3つの異なるオブジェクトに一意の識別子を割り当てます。 コンストラクター `exampleClass`は、パラメーターとして整数を受け取ります。 で`main`は、アプリケーションは、一意の識別子`exampleClass`パラメーターと`__COUNTER__`してを使用して、型の3つのオブジェクトを宣言します。

    ```cpp
    // macro__COUNTER__.cpp
    // Demonstration of __COUNTER__, assigns unique identifiers to
    // different objects of the same type.
    // Compile by using: cl /EHsc /W4 macro__COUNTER__.cpp
    #include <stdio.h>

    class exampleClass {
        int m_nID;
    public:
        // initialize object with a read-only unique ID
        exampleClass(int nID) : m_nID(nID) {}
        int GetID(void) { return m_nID; }
    };

    int main()
    {
        // __COUNTER__ is initially defined as 0
        exampleClass e1(__COUNTER__);

        // On the second reference, __COUNTER__ is now defined as 1
        exampleClass e2(__COUNTER__);

        // __COUNTER__ is now defined as 2
        exampleClass e3(__COUNTER__);

        printf("e1 ID: %i\n", e1.GetID());
        printf("e2 ID: %i\n", e2.GetID());
        printf("e3 ID: %i\n", e3.GetID());

        // Output
        // ------------------------------
        // e1 ID: 0
        // e2 ID: 1
        // e3 ID: 2

        return 0;
    }
    ```

- **&#95;&#95;と&#95;** してコンパイルされ、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラオプションが設定されてC++いる場合に、整数リテラル値200406として定義される cplusplus cli。 それ以外の場合、定義されていません。 定義されている場合、  **&#95; &#95;cplusplus&#95;cli**は翻訳単位全体を通じて有効になります。

    ```cpp
    // cplusplus_cli.cpp
    // compile by using /clr
    #include "stdio.h"
    int main() {
       #ifdef __cplusplus_cli
          printf("%d\n", __cplusplus_cli);
       #else
          printf("not defined\n");
       #endif
    }
    ```

- **&#95;&#95;と&#95;** してC++コンパイルされ、 [/ZW (Windows ランタイムコンパイル)](../build/reference/zw-windows-runtime-compilation.md)コンパイラオプションが設定されている場合、整数リテラル値201009として定義される cplusplus winrt。 それ以外の場合、定義されていません。

- **&#95;CPPRTTI** 場合は 1 として定義されている、 [/GR (ランタイム型情報の有効化)](../build/reference/gr-enable-run-time-type-information.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;Cppunwind ワインド**1つ以上の[/gx (例外処理の有効化)](../build/reference/gx-enable-exception-handling.md)、 [/Clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)、または[/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md)コンパイラオプションが設定されている場合は、1として定義されます。 それ以外の場合、定義されていません。

- **&#95;DEBUG** 1 として定義されている、 [/LDd](../build/reference/md-mt-ld-use-run-time-library.md)、 [/MDd](../build/reference/md-mt-ld-use-run-time-library.md)、または[/MTd](../build/reference/md-mt-ld-use-run-time-library.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- [/MD](../build/reference/md-mt-ld-use-run-time-library.md) または [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (マルチスレッド DLL) コンパイラオプションが設定されている場合、DLL は1として定義されます。  **&#95;** それ以外の場合、定義されていません。

- **&#95;&#95;ファンク&#95;dname**外側の関数の[装飾名](../build/reference/decorated-names.md)を格納する文字列リテラルとして定義されます。 マクロは、関数内でのみ定義されます。 [/Ep](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)または[/p](../build/reference/p-preprocess-to-a-file.md)コンパイラオプションを使用する場合、ファンク **&#95; &#95;dname&#95;** マクロは展開されません。

   この例では`__FUNCDNAME__`、 `__FUNCSIG__`、、 `__FUNCTION__`およびの各マクロを使用して、関数の情報を表示します。

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- **&#95;&#95;ファンク&#95;sig**外側の関数のシグネチャを格納する文字列リテラルとして定義されます。 マクロは、関数内でのみ定義されます。 [/Ep](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)または[/p](../build/reference/p-preprocess-to-a-file.md)コンパイラオプションを使用する場合、ファンク **&#95; &#95;sig&#95;** マクロは展開されません。 64ビットターゲット用にコンパイルされた場合、呼び出し規約`__cdecl`は既定でになります。 使用状況の例は、次を参照してください、`__FUNCDNAME__`マクロ。

- **&#95;&#95;FUNCTION&#95;&#95;** 、外側の関数の非装飾名を含む文字列リテラルとして定義されます。 マクロは、関数内でのみ定義されます。 **&#95;&#95;FUNCTION&#95;&#95;** を使用する場合、マクロが展開されていない、 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)または[/P](../build/reference/p-preprocess-to-a-file.md)コンパイラ オプション。 使用状況の例は、次を参照してください、`__FUNCDNAME__`マクロ。

- **&#95;INTEGRAL&#95;MAX&#95;BITS**64 整数リテラル値として定義された、ベクター以外の整数型の最大サイズ (ビット) にします。 このマクロは常に定義します。

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", _INTEGRAL_MAX_BITS);
   }
   ```

- **&#95; INTELLISENSE &#95; &#95;** IntelliSense コンパイラが Visual Studio IDE に渡すときに、1として定義されます。 それ以外の場合、定義されていません。 このマクロを使用して、IntelliSense コンパイラで認識されないコードを保護したり、ビルドと IntelliSense のコンパイラを切り替えるために使用したりできます。 詳細については、「 [IntelliSense のパフォーマンス低下のトラブルシューティングのヒント](https://devblogs.microsoft.com/cppblog/troubleshooting-tips-for-intellisense-slowness/)」を参照してください。

- **&#95;ISO&#95;VOLATILE** 場合は 1 として定義されている、 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;KERNEL&#95;MODE** 場合は 1 として定義されている、 [/kernel (カーネル モード バイナリの作成)](../build/reference/kernel-create-kernel-mode-binary.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;AMD64** 値のコンパイルの場合 100 x64 を対象とするプロセッサは、整数リテラルとして定義します。 それ以外の場合、定義されていません。

- **&#95;M&#95;ARM** が ARM プロセッサをターゲットのコンパイルの整数リテラル値 7 として定義されています。 それ以外の場合、定義されていません。 それ以外の場合、定義されていません。

- **&#95;ARMV7VE&#95;は、arm プロセッサを対象とするコンパイルに [/arch:ARMv7VE](../build/reference/arch-arm.md) コンパイラオプションが設定されている場合に1と定義されてい&#95;** ます。 それ以外の場合、定義されていません。

- **&#95;M&#95;ARM&#95;FP** を指定する整数リテラル値として定義されている[/arch](../build/reference/arch-arm.md)コンパイラ オプションは、ARM プロセッサを対象に設定されています。 それ以外の場合、定義されていません。

  - Arm オプションが指定されてい`/arch`ない場合は30-39 の範囲の値。 arm の既定のアーキテクチャ`VFPv3`() が設定されていることを示します。

  - が設定されている場合`/arch:VFPv4`は、40-49 の範囲の値。

  - 詳細については、[/arch (ARM)](../build/reference/arch-arm.md)を参照してください。

- **&#95;M&#95;ARM64** が 64 ビット ARM プロセッサをターゲットのコンパイルの場合は 1 として定義されています。 それ以外の場合、定義されていません。

- **&#95;任意&#95;** の[/Clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)コンパイラオプションが設定されている場合、M CEE は001として定義されます。 それ以外の場合、定義されていません。

- **&#95;M&#95;CEE&#95;PURE** 以降 Visual Studio 2015 で非推奨とされます。 場合は 001 として定義されている、 [/clr:pure](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;CEE&#95;SAFE** 以降 Visual Studio 2015 で非推奨とされます。 場合は 001 として定義されている、 [/clr:safe](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;FP&#95;EXCEPT** 場合は 1 として定義されている、 [/fp: 除く](../build/reference/fp-specify-floating-point-behavior.md)または[/fp: 厳密な](../build/reference/fp-specify-floating-point-behavior.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;FP&#95;FAST** 場合は 1 として定義されている、 [/fp:fast](../build/reference/fp-specify-floating-point-behavior.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;FP&#95;PRECISE** 場合は 1 として定義されている、 [/fp: 正確な](../build/reference/fp-specify-floating-point-behavior.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;FP&#95;STRICT** 場合は 1 として定義されている、 [/fp: 厳密な](../build/reference/fp-specify-floating-point-behavior.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;IX86** 値 600 のコンパイルの場合そのターゲット x86 プロセッサは、整数リテラルとして定義します。 このマクロは、x64、または ARM コンパイル ターゲット定義されていません。

- **&#95;M&#95;IX86&#95;FP** を示す整数リテラル値として定義されている、 [/arch](../build/reference/arch-arm.md)セット、または既定値がコンパイラ オプション。 コンパイル ターゲットが x86 の場合このマクロが常に定義されているプロセッサ。 それ以外の場合、定義されていません。 定義されているときに、値には。

  - コンパイラオプションが`/arch:IA32`設定されている場合は0。

  - コンパイラオプションが`/arch:SSE`設定されている場合は1。

  - `/arch:SSE2`、`/arch:AVX`、`/arch:AVX2`、または `/arch:AVX512` コンパイラオプションが設定されている場合は2。 この値は、 `/arch`コンパイラオプションが指定されていない場合の既定値です。 @No__t-0 が指定されている場合、マクロ **&#95; &#95;AVX&#95;** も定義されます。 @No__t-0 を指定すると、 **&#95; &#95;AVX&#95;** と **&#95; &#95;AVX2&#95;** の両方も定義されます。 @No__t-0 が指定さ **&#95; &#95;&#95;** れている場合、AVX、  **&#95; &#95;&#95;AVX2**、  **&#95; &#95;AVX512BW&#95;** 、  **&#95; &#95;AVX512CD&#95;** 、  **&#95;AVX512DQ&#95;、 &#95;** **AVX512F&#95;および&#95;AVX512VL も定義されています。 &#95;** **&#95; &#95;&#95;**

  - 詳細については、「[/arch (x86)](../build/reference/arch-x86.md)」を参照してください。

- **&#95;M&#95;X64** 値のコンパイルの場合 100 x64 を対象とするプロセッサは、整数リテラルとして定義します。 それ以外の場合、定義されていません。

- **&#95;MANAGED** 1 として定義されている、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;MSC&#95;BUILD** コンパイラのバージョン番号のリビジョン番号要素を格納する整数リテラルとして定義されています。 リビジョン番号は、ピリオド区切りのバージョン番号の 4 番目の要素です。 たとえば、Microsoft C と C++ コンパイラのバージョン番号が 15.00.20706.01 ある場合、 **&#95;MSC&#95;BUILD**マクロが 1 に評価されます。 このマクロは常に定義します。

- **&#95;MSC&#95;EXTENSIONS** 既定でオンの場合は 1 として定義されている[/Ze (言語拡張を有効にする)](../build/reference/za-ze-disable-language-extensions.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;MSC&#95;FULL&#95;VER** メジャーをエンコードする整数リテラルとして定義されている、マイナー、およびコンパイラのバージョン番号の数の要素を構築します。 メジャー番号はピリオド区切りのバージョン番号の最初の要素、マイナー番号が 2 番目の要素、およびビルド番号が 3 番目の要素。 たとえば、Microsoft C と C++ コンパイラのバージョン番号が 15.00.20706.01 ある場合、 **&#95;MSC&#95;FULL&#95;VER**マクロは 150020706 に評価されます。 入力`cl /?`コンパイラのバージョン番号を表示するのには、コマンドラインでします。 このマクロは常に定義します。

- **&#95;MSC&#95;VER** コンパイラのバージョン番号のメジャーおよびマイナー番号要素をエンコードする整数リテラルとして定義されています。 メジャー番号はピリオド区切りのバージョン番号の最初の要素と、マイナー番号は 2 番目の要素。 たとえば、Microsoft C と C++ コンパイラのバージョン番号が 17.00.51106.1 である、 **&#95;MSC&#95;VER**マクロは 1700 に評価されます。 入力`cl /?`コンパイラのバージョン番号を表示するのには、コマンドラインでします。 このマクロは常に定義します。

   |Visual Studio のバージョン|**&#95;MSC&#95;VER**|
   |-|-|
   |Visual Studio 6.0|1200|
   |Visual Studio .NET 2002 (7.0)|1300|
   |Visual Studio .NET 2003 (7.1)|1310|
   |Visual Studio 2005 (8.0)|1400|
   |Visual Studio 2008 (9.0)|1500|
   |Visual Studio 2010 (10.0)|1600|
   |Visual Studio 2012 (11.0)|1700|
   |Visual Studio 2013 (12.0)|1800|
   |Visual Studio 2015 (14.0)|1900|
   |Visual Studio 2017 RTW (15.0)|1910|
   |Visual Studio 2017 バージョン 15.3|1911|
   |Visual Studio 2017 バージョン 15.5|1912|
   |Visual Studio 2017 バージョン 15.6|1913|
   |Visual Studio 2017 バージョン 15.7|1914|
   |Visual Studio 2017 バージョン 15.8|1915|
   |Visual Studio 2017 バージョン15.9|1916|
   |Visual Studio 2019 RTW (16.0)|1920|
   |Visual Studio 2019 バージョン 16.1|1921|
   |Visual Studio 2019 バージョン 16.2|1922|
   |Visual Studio 2019 バージョン16.3|1923|

   特定のバージョンの Visual Studio またはその後に、コンパイラのリリースまたは更新プログラムをテストするには、 **>=** 演算子を使用します。 これを条件付きディレクティブで使用して、  **&#95;MSC&#95;VER**をその既知のバージョンと比較することができます。 比較対象として相互に排他的な複数のバージョンがある場合は、バージョン番号の降順で比較します。 たとえば、このコードは Visual Studio 2017 以降でリリースされたコンパイラをチェックします。 次に、Visual Studio 2015 以降でリリースされたコンパイラがあるかどうかを確認します。 次に、Visual Studio 2015 より前にリリースされたすべてのコンパイラがあるかどうかを確認します。

   ```cpp
   #if _MSC_VER >= 1910
   // . . .
   #elif _MSC_VER >= 1900
   // . . .
   #else
   // . . .
   #endif
   ```

   詳細については、Microsoft C++チームブログの「 [Visual C++ Compiler Version](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/) 」を参照してください。

- **&#95;MSVC&#95;LANG** 対象となる、コンパイラは C++ 言語標準を指定する整数リテラルとして定義されています。 C++ としてコンパイルされたコードでのみ設定されます。 マクロは、整数リテラル 201402 L を既定では、値とき、または、 [/std:c++14](../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを指定します。 場合 201703 L にマクロが設定されて、 [/std:c++17](../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを指定します。 高い、指定されていない値に設定されているときに、 [/std:c++latest](../build/reference/std-specify-language-standard-version.md)オプションを指定します。 それ以外の場合、マクロは定義されません。 **&#95;MSVC&#95;LANG**マクロと[/std (言語標準バージョンの指定)](../build/reference/std-specify-language-standard-version.md)コンパイラ オプションで、Visual Studio 2015 Update 3 以降を使用できます。

- **&#95;&#95;MSVC&#95;RUNTIME&#95;CHECKS** 1 と 1 つとして定義されているの[/RTC](../build/reference/rtc-run-time-error-checks.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;プリ&#95;** プロセッサ準拠モード[/実験的: プリプロセッサ](../build/reference/rtc-run-time-error-checks.md)コンパイラオプションが設定されている場合、MSVC は0として定義されます。 既定では1として定義されます。または、 [/実験的: プリ](../build/reference/rtc-run-time-error-checks.md)プロセッサコンパイラオプションが設定されている場合は、従来のプリプロセッサが使用されていることを示します。 **&#95;MSVC&#95;従来**のマクロと[/実験的: プリプロセッサ (プリプロセッサ準拠モードの有効化)](../build/reference/experimental-preprocessor.md)コンパイラオプションは、Visual Studio 2017 バージョン15.8 以降で使用できます。

   ```cpp
   #if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
   // Logic using the traditional preprocessor
   #else
   // Logic using cross-platform compatible preprocessor
   #endif
   ```

- **&#95;MT**[/Md または/mdd](../build/reference/md-mt-ld-use-run-time-library.md) (マルチスレッド DLL) または[/Mt または/MTd](../build/reference/md-mt-ld-use-run-time-library.md) (マルチスレッド) が指定されている場合は、1として定義されます。 それ以外の場合、定義されていません。

- **&#95;ネイティブ&#95;WCHAR&#95;T&#95;定義** 1 として定義されている、 [/Zc:wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;OPENMP** 場合は、整数リテラルの 200203 として定義されている、 [/openmp (OpenMP 2.0 サポートの有効化)](../build/reference/openmp-enable-openmp-2-0-support.md)コンパイラ オプションを設定します。 この値は、MSVC によって実装される OpenMP 仕様の日付を表します。 それ以外の場合、定義されていません。

   ```cpp
   // _OPENMP_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", _OPENMP);
   }
   ```

- **&#95;PREFAST&#95;** [/Analyze](../build/reference/analyze-code-analysis.md)コンパイラオプションが設定されている場合は、1として定義されます。 それ以外の場合、定義されていません。

- **&#95;&#95;タイム&#95;スタンプ**現在のソースファイルが最後に変更された日時を含む文字列リテラルとして定義されます。これには、CRT [asctime](../c-runtime-library/reference/asctime-wasctime.md)関数によって返される、省略形の定数長 (`Fri 19 Aug 13:32:58 2016` など) が含まれます。 このマクロは常に定義します。

- **&#95;&#95;** [/Zl (既定のライブラリ名の省略)](../build/reference/zl-omit-default-library-name.md)コンパイラオプションが設定されている場合、VC NODEFAULTLIB は1と定義されます。 それ以外の場合、定義されていません。

- **&#95;WCHAR&#95;T&#95;DEFINED** 1 として定義されている既定の[/Zc:wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)コンパイラ オプションを設定します。 **&#95;WCHAR&#95;T&#95;定義**マクロが定義されていますが、値が存在しない場合、`/Zc:wchar_t-`コンパイラ オプションを設定すると、および**wchar_t**に含まれるシステム ヘッダー ファイルで定義されているが、プロジェクトです。 それ以外の場合、定義されていません。

- **&#95;WIN32**コンパイルターゲットが32ビット ARM、64ビット ARM、x86、または x64 の場合、1として定義されます。 それ以外の場合、定義されていません。

- **&#95;WIN64** コンパイル ターゲットが 64 ビット ARM または x64 の場合は、1 として定義します。 それ以外の場合、定義されていません。

- **&#95;WINRT&#95;DLL** 定義すると 1 としては、C++、およびその両方としてコンパイル[/ZW (Windows ランタイムのコンパイル)](../build/reference/zw-windows-runtime-compilation.md)と[/LD または/LDd](../build/reference/md-mt-ld-use-run-time-library.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

ATL または MFC ライブラリのバージョンを識別するプリプロセッサマクロは、コンパイラによって事前に定義されていません。 ATL および MFC ライブラリヘッダーは、これらのバージョンマクロを内部で定義します。 必須のヘッダーが含まれる前に作成されたプリプロセッサディレクティブには定義されていません。

- **&#95;ATL&#95;VER** で定義されている\<atldef.h > ATL バージョン番号をエンコードする整数リテラルとして。

- **&#95;MFC&#95;VER** で定義されている\<afxver_.h > MFC のバージョン番号をエンコードする整数リテラルとして。

## <a name="see-also"></a>関連項目

[マクロ (C/C++)](../preprocessor/macros-c-cpp.md)<br/>
[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)<br/>
[プリプロセッサディレクティブ](../preprocessor/preprocessor-directives.md)
