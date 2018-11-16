---
title: 定義済みマクロ
ms.custom: update_every_version
ms.date: 11/12/2018
f1_keywords:
- _ATL_VER
- __ATOM__
- __AVX__
- __AVX2__
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
ms.openlocfilehash: 9ebc23545817de0f249185700454237c66610c13
ms.sourcegitcommit: d441305fb19131afbd7fc259d8cda63ea26f2343
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51678355"
---
# <a name="predefined-macros"></a>定義済みマクロ

Visual C コンパイラは、言語 (C または C++)、コンパイル ターゲット、および選択したコンパイラ オプションによって、特定のプリプロセッサ マクロが組み込まれています。

Visual C では、ANSI/ISO C99 標準と c++ 14 標準 ISO によって指定された必須の定義済みプリプロセッサ マクロをサポートします。 実装には、その他のいくつかの Microsoft 固有プリプロセッサ マクロもサポートしています。 いくつかのマクロは、特定のビルド環境またはコンパイラ オプションでのみ定義されます。 として指定された場合に、翻訳単位全体で、マクロが定義されて、記載されていない場合 **/D**コンパイラ オプションの引数。 定義されている場合、マクロは、コンパイル前に、プリプロセッサによって指定された値に展開されます。 定義済みマクロは引数を受け取らず、再定義できません。

## <a name="standard-predefined-identifier"></a>標準の定義済みの識別子

コンパイラは、ISO C99 と c++ 11 で指定されたこの事前定義の識別子をサポートします。

- **&#95;&#95;func&#95; &#95;** 関数ローカルとして外側の関数の非修飾かつ非装飾名**static const**の配列**char**します。

    ```cpp
    void example(){
        printf("%s\n", __func__);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>標準の定義済みマクロ

コンパイラには、ISO C99 および ISO c++ 17 標準で指定されたこれらの定義済みマクロがサポートしています。

- **&#95;&#95;cplusplus**翻訳単位が C++ としてコンパイルされるときに、整数リテラル値として定義します。 それ以外の場合、定義されていません。

- **&#95;&#95;日付&#95;&#95;** 現在のソース ファイルのコンパイル日付。 日付が固定長の文字列形式のリテラル*Mmm dd yyyy*します。 月の名前*Mmm* C ランタイム ライブラリによって生成される日付の月の省略名と同じは[asctime](../c-runtime-library/reference/asctime-wasctime.md)関数。 日付の最初の文字*dd*値が 10 未満の場合はのスペースです。 このマクロは常に定義します。

- **&#95;&#95;ファイル&#95;&#95;** 現在のソース ファイルの名前。 **&#95;&#95;ファイル&#95;&#95;** 文字の文字列リテラルに展開します。 ファイルへの完全パスが表示されることを確認するには使用[/FC (完全なソース コード ファイルのパスで診断)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)します。 このマクロは常に定義します。

- **&#95;&#95;行&#95;&#95;** 現在のソース ファイル内の整数の行番号として定義されています。 値、 **&#95;&#95;行&#95;&#95;** マクロを使用して変更することができます、`#line`ディレクティブ。 このマクロは常に定義します。

- **&#95;&#95;STDC&#95; &#95;**  C としてコンパイルされる場合、および 1 として定義されている、 [/Za](../build/reference/za-ze-disable-language-extensions.md)コンパイラ オプションを指定します。 それ以外の場合、定義されていません。

- **&#95;&#95;STDC&#95;ホステッド&#95;&#95;** 実装がある場合は、1 として定義されている、*実装がホストされている*、必要な標準ライブラリ全体をサポートしています。 それ以外の場合、0 として定義されます。

- **&#95;&#95;STDCPP&#95;スレッド&#95;&#95;** プログラムは、実行の 1 つ以上のスレッドを持つことができる場合にのみ、1 として定義されており、C++ としてコンパイルします。 それ以外の場合、定義されていません。

- **&#95;&#95;時間&#95;&#95;** 前処理された翻訳単位の変換のとき。 時間は、文字の文字列形式のリテラル*hh:mm:ss*、C ランタイム ライブラリによって返されるときと同じ[asctime](../c-runtime-library/reference/asctime-wasctime.md)関数。 このマクロは常に定義します。

## <a name="microsoft-specific-predefined-macros"></a>Microsoft 固有の定義済みマクロ

Microsoft Visual C には、これらの追加の定義済みマクロがサポートしています。

- **&#95;&#95;ATOM&#95; &#95;**  1 として定義されている、 [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md)コンパイラ オプションを設定し、コンパイラのターゲットは x86 または x64 です。 それ以外の場合、定義されていません。

- **&#95;&#95;AVX&#95; &#95;**  1 として定義されている、 [/arch:AVX](../build/reference/arch-x86.md)または[/arch:AVX2](../build/reference/arch-x86.md)コンパイラ オプションを設定し、コンパイラのターゲットは x86 または x64 です。 それ以外の場合、定義されていません。

- **&#95;&#95;AVX2&#95; &#95;**  1 として定義されている、 [/arch:AVX2](../build/reference/arch-x86.md)コンパイラ オプションを設定し、コンパイラのターゲットは x86 または x64 です。 それ以外の場合、定義されていません。

- **&#95;CHAR&#95;未署名**既定の場合は 1 として定義されている**char**型が符号なし。 ときにこの設定は、 [/J (既定の char 型の unsigned)](../build/reference/j-default-char-type-is-unsigned.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;&#95;CLR&#95;VER**アプリケーションがコンパイルされたときに使用される共通言語ランタイムのバージョンを表す整数リテラルとして定義されています。 値が形式でエンコードされた`Mmmbbbbb`ここで、 `M` 、ランタイムのメジャー バージョン`mm`、ランタイムのマイナー バージョンと`bbbbb`ビルド番号です。 **&#95;&#95;CLR&#95;VER**が定義されている場合、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(__CLR_VER);
    }
    ```

- **&#95;コントロール&#95;フロー&#95;ガード**1 として定義されている、 [/guard:cf (有効にする制御フロー ガード)](../build/reference/guard-enable-control-flow-guard.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;&#95;カウンター&#95; &#95;** は 0 から始まるまたはソース ファイルで使用されるたびに 1 ずつインクリメントされますおよびソース ファイルのヘッダーに追加する整数リテラルに展開します。 **&#95;&#95;カウンター&#95; &#95;** プリコンパイル済みヘッダーを使用すると、その状態を記憶します。 このマクロは常に定義します。

  この例では`__COUNTER__`同じ型の 3 つの異なるオブジェクトに一意の識別子を割り当てます。 `exampleClass`コンス トラクターはパラメーターとして整数を受け取ります。 `main`、アプリケーションは、型の 3 つのオブジェクトを宣言します。`exampleClass`を使用して、`__COUNTER__`一意識別子のパラメーターとして。

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

- **&#95;&#95;cplusplus&#95;cli** 200406 C++ としてコンパイルするときの整数リテラル値として定義されていると、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。 定義と、  **&#95; &#95;cplusplus&#95;cli**翻訳単位全体では有効です。

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

- **&#95;&#95;cplusplus&#95;winrt** 201009 C++ としてコンパイルするときの整数リテラル値として定義されていると、 [/ZW (Windows ランタイムのコンパイル)](../build/reference/zw-windows-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;CPPRTTI**場合は 1 として定義されている、 [/GR (ランタイム型情報の有効化)](../build/reference/gr-enable-run-time-type-information.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;CPPUNWIND** 1 つ以上の場合は、1 として定義されている、 [/GX (例外処理を有効にする)](../build/reference/gx-enable-exception-handling.md)、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)、または[/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;デバッグ**1 として定義されている、 [/LDd](../build/reference/md-mt-ld-use-run-time-library.md)、 [/MDd](../build/reference/md-mt-ld-use-run-time-library.md)、または[/MTd](../build/reference/md-mt-ld-use-run-time-library.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;DLL** 1 として定義されている、 [/MD](../build/reference/md-mt-ld-use-run-time-library.md)または[/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (マルチ スレッド DLL を) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;&#95;FUNCDNAME&#95; &#95;** を含む文字列リテラルとして定義されている、[装飾名](../build/reference/decorated-names.md)外側の関数。 マクロは、関数内でのみ定義されます。 **&#95; &#95;FUNCDNAME&#95; &#95;** を使用する場合、マクロが展開されていない、 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)または[/P](../build/reference/p-preprocess-to-a-file.md)コンパイラ オプション。

   この例では、 `__FUNCDNAME__`、 `__FUNCSIG__`、および`__FUNCTION__`マクロの関数の情報を表示します。

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- **&#95;&#95;FUNCSIG&#95; &#95;**  、外側の関数のシグネチャを格納する文字列リテラルとして定義されています。 マクロは、関数内でのみ定義されます。 **&#95; &#95;FUNCSIG&#95; &#95;** を使用する場合、マクロが展開されていない、 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)または[/P](../build/reference/p-preprocess-to-a-file.md)コンパイラ オプション。 呼び出し規約は、64 ビット ターゲット コンパイルされると、`__cdecl`既定。 使用状況の例は、次を参照してください。、`__FUNCDNAME__`マクロ。

- **&#95;&#95;関数&#95;&#95;**  、外側の関数の非装飾名を含む文字列リテラルとして定義されます。 マクロは、関数内でのみ定義されます。 **&#95;&#95;関数&#95;&#95;** を使用する場合、マクロが展開されていない、 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)または[/P](../build/reference/p-preprocess-to-a-file.md)コンパイラ オプション。 使用状況の例は、次を参照してください。、`__FUNCDNAME__`マクロ。

- **&#95;整数&#95;最大&#95;ビット**64 整数リテラル値として定義された、ベクター以外の整数型の最大サイズ (ビット) にします。 このマクロは常に定義します。

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", _INTEGRAL_MAX_BITS);
   }
   ```

- **&#95;&#95;INTELLISENSE&#95; &#95;**  Visual Studio IDE で IntelliSense コンパイラを中に 1 を渡すように定義されています。 それ以外の場合、定義されていません。 IntelliSense コンパイラが理解するには、またはそれを使用して、ビルドと IntelliSense のコンパイラの間で切り替えるしていないコードを保護するため、このマクロを使用することができます。 詳細については、次を参照してください。 [IntelliSense パフォーマンスの低下のトラブルシューティングのヒント](https://blogs.msdn.microsoft.com/vcblog/2011/03/29/troubleshooting-tips-for-intellisense-slowness/)します。

- **&#95;ISO&#95;揮発性**場合は 1 として定義されている、 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;カーネル&#95;モード**場合は 1 として定義されている、 [/kernel (カーネル モード バイナリの作成)](../build/reference/kernel-create-kernel-mode-binary.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;AMD64**値のコンパイルの場合 100 x64 を対象とするプロセッサは、整数リテラルとして定義します。 それ以外の場合、定義されていません。

- **&#95;M&#95;ARM**が ARM プロセッサをターゲットのコンパイルの整数リテラル値 7 として定義されています。 それ以外の場合、定義されていません。

- **&#95;M&#95;ARM&#95;ARMV7VE** 1 として定義されている、 [/arch:ARMv7VE](../build/reference/arch-arm.md)が ARM プロセッサをターゲットのコンパイルのコンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;ARM&#95;FP**を指定する整数リテラル値として定義されている[/arch](../build/reference/arch-arm.md)コンパイル ターゲットが、ARM プロセッサの場合、コンパイラ オプションが設定されています。 それ以外の場合、定義されていません。

  - ない場合は 30-39 の範囲の`/arch`ARM オプションが指定されました、ARM の既定のアーキテクチャを示す設定されました (`VFPv3`)。

  - 範囲の場合は 40 ~ 49`/arch:VFPv4`設定されました。

  - 参照してください[/arch (ARM)](../build/reference/arch-arm.md)詳細についてはします。

- **&#95;M&#95;ARM64**が 64 ビット ARM プロセッサをターゲットのコンパイルの場合は 1 として定義されています。 それ以外の場合、定義されていません。

- **&#95;M&#95;CEE** 001 として定義されたいずれか[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;CEE&#95;純粋**以降 Visual Studio 2015 で非推奨とされます。 場合は 001 として定義されている、 [/clr: 純粋な](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;CEE&#95;セーフ**以降 Visual Studio 2015 で非推奨とされます。 場合は 001 として定義されている、 [/clr:safe](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;FP&#95;EXCEPT**場合は 1 として定義されている、 [/fp: 除く](../build/reference/fp-specify-floating-point-behavior.md)または[/fp: 厳密な](../build/reference/fp-specify-floating-point-behavior.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;FP&#95;高速**場合は 1 として定義されている、 [/fp:fast](../build/reference/fp-specify-floating-point-behavior.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;FP&#95;精度**場合は 1 として定義されている、 [/fp: 正確な](../build/reference/fp-specify-floating-point-behavior.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;FP&#95;STRICT**場合は 1 として定義されている、 [/fp: 厳密な](../build/reference/fp-specify-floating-point-behavior.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;M&#95;IX86**値 600 のコンパイルの場合そのターゲット x86 プロセッサは、整数リテラルとして定義します。 X64 または ARM コンパイル ターゲットに対しては、このマクロが定義されていません。

- **&#95;M&#95;IX86&#95;FP**を示す整数リテラル値として定義されている、 [/arch](../build/reference/arch-arm.md)セット、または既定値がコンパイラ オプション。 コンパイル ターゲットが x86 の場合このマクロが常に定義されているプロセッサ。 それ以外の場合、定義されていません。 定義されているときに、値には。

  - 0 の場合、`/arch:IA32`コンパイラ オプションを設定します。

  - 場合は 1、`/arch:SSE`コンパイラ オプションを設定します。

  - 場合は 2、 `/arch:SSE2`、`/arch:AVX`または`/arch:AVX2`コンパイラ オプションを設定します。 この値には、既定値がある場合、`/arch`コンパイラ オプションが指定されていません。 ときに`/arch:AVX`が指定されているマクロ **&#95; &#95;AVX&#95; &#95;** も定義されています。 ときに`/arch:AVX2`が指定されている両方 **&#95; &#95;AVX&#95; &#95;** と **&#95; &#95;AVX2&#95; &#95;** も定義されています。

  - 参照してください[/arch (x86)](../build/reference/arch-x86.md)詳細についてはします。

- **&#95;M&#95;X64**値のコンパイルの場合 100 x64 を対象とするプロセッサは、整数リテラルとして定義します。 それ以外の場合、定義されていません。

- **&#95;マネージ**1 として定義されている、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;MSC&#95;ビルド**コンパイラのバージョン番号のリビジョン番号要素を格納する整数リテラルとして定義されています。 リビジョン番号は、ピリオド区切りのバージョン番号の 4 番目の要素です。 たとえば、Visual C コンパイラのバージョン番号が 15.00.20706.01 ある場合、  **&#95;MSC&#95;ビルド**マクロが 1 に評価されます。 このマクロは常に定義します。

- **&#95;MSC&#95;拡張**場合は 1 として定義されている、 [/Ze (言語拡張を有効にする)](../build/reference/za-ze-disable-language-extensions.md)コンパイラ オプションを設定すると、これは、既定値。 それ以外の場合、定義されていません。

- **&#95;MSC&#95;完全&#95;VER**メジャーをエンコードする整数リテラルとして定義されている、マイナー、およびコンパイラのバージョン番号の数の要素を構築します。 メジャー番号はピリオド区切りのバージョン番号の最初の要素、マイナー番号が 2 番目の要素、およびビルド番号が 3 番目の要素。 たとえば、Visual C コンパイラのバージョン番号が 15.00.20706.01 ある場合、  **&#95;MSC&#95;完全&#95;VER**マクロは 150020706 に評価されます。 入力`cl /?`コンパイラのバージョン番号を表示するのには、コマンドラインでします。 このマクロは常に定義します。

- **&#95;MSC&#95;VER**コンパイラのバージョン番号のメジャーおよびマイナー番号要素をエンコードする整数リテラルとして定義されています。 メジャー番号はピリオド区切りのバージョン番号の最初の要素と、マイナー番号は 2 番目の要素。 たとえば、Visual C コンパイラのバージョン番号が 17.00.51106.1 である、  **&#95;MSC&#95;VER**マクロは 1700 に評価されます。 入力`cl /?`コンパイラのバージョン番号を表示するのには、コマンドラインでします。 このマクロは常に定義します。

   |Visual Studio のバージョン|&AMP;#95;MSC&AMP;#95;VER|
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
   |Visual Studio 2017 バージョン 15.9|1916|

   コンパイラのリリースまたは特定のバージョンの Visual Studio、または後で更新プログラム、使用をテストする、 **>=** (大きいか等しい) 演算子と比較する **&#95;MSC&#95;VER**に対して既知バージョン。 相互に排他的な方法で比較するいくつかのバージョンがある場合は、バージョン番号の降順で比較を注文することをお勧めします。 たとえば、このコードは、コンパイラ、Visual Studio 2013 以降にリリースされた Visual Studio 2013 より前にリリースされたすべてのコンパイラの処理を行うし、リリースの Visual Studio 2015 以降では、コンパイラのチェックします。

   ```cpp
   #if _MSC_VER >= 1900
   // . . .
   #elif _MSC_VER >= 1800
   // . . .
   #else
   // . . .
   #endif
   ```

   詳細については、次を参照してください。 [Visual c コンパイラ バージョン](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/)Visual c チーム ブログでします。

- **&#95;MSVC&#95;LANG**対象となる、コンパイラは C++ 言語標準を指定する整数リテラルとして定義されています。 場合、マクロは整数リテラル値 201402 L C++ としてコンパイルすると、 [/std:c + + + 14](../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを設定すると、または既定に設定されて 201703 L 場合、 [/std:c + + + 17](../build/reference/std-specify-language-standard-version.md)コンパイラ オプションが設定されているしに設定されている、高い、指定されていないときの値、 [/std:c + + 最新](../build/reference/std-specify-language-standard-version.md)します。 それ以外の場合、マクロは定義されません。 **&#95;MSVC&#95;LANG**マクロと[/std (言語標準バージョンの指定)](../build/reference/std-specify-language-standard-version.md)コンパイラ オプションで、Visual Studio 2015 Update 3 以降を使用できます。

- **&#95;&#95;MSVC&#95;ランタイム&#95;チェック**1 と 1 つとして定義されているの[/RTC](../build/reference/rtc-run-time-error-checks.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;MT** 1 として定義されている[/MD または/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (マルチ スレッド DLL) または[/MT または/MTd](../build/reference/md-mt-ld-use-run-time-library.md) (マルチ スレッド) を指定します。 それ以外の場合、定義されていません。

- **&#95;ネイティブ&#95;WCHAR&#95;T&#95;定義**1 として定義されている、 [/Zc:wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;OPENMP**場合に、Visual C によって実装される OpenMP 仕様の日付を表す整数リテラルの 200203 として定義されている、 [/openmp (OpenMP 2.0 サポートの有効化)](../build/reference/openmp-enable-openmp-2-0-support.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

   ```cpp
   // _OPENMP_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", _OPENMP);
   }
   ```

- **&#95;PREFAST&#95;**  1 として定義されている、 [/analyze](../build/reference/analyze-code-analysis.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;&#95;タイムスタンプ&#95;&#95;**  C ランタイム ライブラリによって返される省略形、定数値の形式で、現在のソース ファイルの最終変更日時を含む文字列リテラルとして定義されている[asctime](../c-runtime-library/reference/asctime-wasctime.md)関数は、たとえば、`Fri 19 Aug 13:32:58 2016`します。 このマクロは常に定義します。

- **&#95;VC&#95;NODEFAULTLIB** 1 として定義されている、 [/Zl (Omit Default Library Name)](../build/reference/zl-omit-default-library-name.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

- **&#95;WCHAR&#95;T&#95;定義**1 として定義されている既定の[/Zc:wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)コンパイラ オプションを設定します。 **&#95;WCHAR&#95;T&#95;定義**マクロが定義されていますが、値が存在しない場合、`/Zc:wchar_t-`コンパイラ オプションを設定すると、および**wchar_t**に含まれるシステム ヘッダー ファイルで定義されているが、プロジェクトです。 それ以外の場合、定義されていません。

- **&#95;WIN32** x 64 またはコンパイル ターゲットが 32 ビット ARM、64 ビット ARM、x86、1 として定義します。 それ以外の場合、定義されていません。

- **&#95;WIN64**コンパイル ターゲットが 64 ビット ARM または x64 の場合は、1 として定義します。 それ以外の場合、定義されていません。

- **&#95;WINRT&#95;DLL**定義すると 1 としては、C++、およびその両方としてコンパイル[/ZW (Windows ランタイムのコンパイル)](../build/reference/zw-windows-runtime-compilation.md)と[/LD または/LDd](../build/reference/md-mt-ld-use-run-time-library.md)コンパイラ オプションを設定します。 それ以外の場合、定義されていません。

ATL または MFC ライブラリのバージョンを判断するために使用するプリプロセッサのマクロは、コンパイラによっては事前定義されていません。 これらのマクロは、必須のヘッダーが含まれる前にプリプロセッサ ディレクティブで未定義、ため、ライブラリのヘッダーで定義されます。

- **&#95;ATL&#95;VER**で定義されている\<atldef.h > ATL バージョン番号をエンコードする整数リテラルとして。

- **&#95;MFC&#95;VER**で定義されている\<afxver_.h > MFC のバージョン番号をエンコードする整数リテラルとして。

## <a name="see-also"></a>関連項目

[マクロ (C/C++)](../preprocessor/macros-c-cpp.md)<br/>
[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)<br/>
[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)