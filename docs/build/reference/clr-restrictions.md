---
title: /clr の制約
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], restrictions
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
ms.openlocfilehash: 21b7ead553871854c73021756eb2086f9e6e7393
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777819"
---
# <a name="clr-restrictions"></a>/clr の制約

使用には、次の制限に注意してください **/clr**:

- 構造化例外ハンドラーでは、使用に関する制限事項`_alloca`でコンパイルするときに **/clr**します。 詳細については、[_alloca](../../c-runtime-library/reference/alloca.md)を参照してください。

- 実行時エラー チェックの使用に無効な **/clr**します。 詳細については、「[方法 :ネイティブ ランタイム チェックを使用する](/visualstudio/debugger/how-to-use-native-run-time-checks)」を参照してください。

- ときに **/clr**はのみに C++ の標準構文を使用するプログラムをコンパイルするために使用、インライン アセンブリの使用に次のガイドラインが適用されます。

  - インライン アセンブリ コード、ネイティブ スタック レイアウトの知識を前提としていますが、呼び出し規則は、現在の関数、またはコンピューターに関するその他の低レベルの情報の外部ではエラーに関する知識は、マネージ関数のスタック フレームに適用されます。 せずにコンパイルされた個別のモジュール内に置かれた場合、アンマネージ関数は、インライン アセンブラー コードを含む関数が生成される **/clr**します。

  - コピーで構築される関数のパラメーターを渡す関数内でインライン アセンブリ コードがサポートされていません。

- [Vprintf 系関数](../../c-runtime-library/vprintf-functions.md)でコンパイルされたプログラムから呼び出すことができません **/clr**します。

- [Naked](../../cpp/naked-cpp.md) [_ _declspec](../../cpp/declspec.md)修飾子は/clr で無視されます。

- 変換関数を設定[_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)は、アンマネージ コードでキャッチのみに影響します。 参照してください[例外処理](../../extensions/exception-handling-cpp-component-extensions.md)詳細についてはします。

- 関数ポインターの比較が下で許可されていない **/clr**します。

- 完全にプロトタイプ宣言されていない関数の使用が許可されていません **/clr**します。

- 次のコンパイラ オプションはサポートされていません **/clr**:

  - **/EHsc**と **/EHs** (**/clr**意味 **/EHa** (を参照してください[/EH (例外処理モデル)](eh-exception-handling-model.md))

  - **/fp: 厳密な**と **/fp: 除く**(を参照してください[/fp (浮動小数点の動作の指定)](fp-specify-floating-point-behavior.md))

  - [/Zd](z7-zi-zi-debug-information-format.md)

  - [/Gm](gm-enable-minimal-rebuild.md)

  - [/MT](md-mt-ld-use-run-time-library.md)

  - [/RTC](rtc-run-time-error-checks.md)

  - [/ZI](z7-zi-zi-debug-information-format.md)

- 組み合わせ、`_STATIC_CPPLIB`プリプロセッサの定義 (`/D_STATIC_CPPLIB`) および **/clr**コンパイラ オプションはサポートされていません。 これは、定義は、静的なマルチ スレッド C++ 標準ライブラリ、サポートされていないとリンクするアプリケーションになるためです。 詳細については、次を参照してください。、 [/MD、/MT、/LD (ランタイム ライブラリの使用)](md-mt-ld-use-run-time-library.md)トピック。

- 使用する場合 **/Zi**で **/clr**パフォーマンスに影響があります。 詳細については、[/Zi](z7-zi-zi-debug-information-format.md)を参照してください。

- 指定しないルーチンを出力する .NET Framework にワイド文字を渡す[/Zc:wchar_t](zc-wchar-t-wchar-t-is-native-type.md)に文字をキャストしていない場合、または`__wchar_t`として表示される出力になります、`unsigned short int`します。 例:

    ```cpp
    Console::WriteLine(L' ')              // Will output 32.
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.
    ```

- [/GS](gs-buffer-security-check.md)でコンパイルする場合は無視されます **/clr**関数がある場合を除き、 `#pragma` [アンマネージ](../../preprocessor/managed-unmanaged.md)場合、コンパイラは生成場合は、関数は、ネイティブにコンパイルする必要があります、または警告 C4793 で、既定ではオフです。

- 参照してください[/ENTRY](entry-entry-point-symbol.md)のマネージ アプリケーションの関数署名要件。

- コンパイルされたアプリケーション **/openmp**と **/clr** 1 つの appdomain のプロセスでのみ実行できます。  参照してください[/openmp (OpenMP 2.0 サポートの有効化)](openmp-enable-openmp-2-0-support.md)詳細についてはします。

- ネイティブ関数としては、可変個の引数 (vararg) を受け取る関数が生成されます。 可変個引数の位置に任意のマネージ データ型は、ネイティブ型にマーシャ リングされます。 なお<xref:System.String?displayProperty=fullName>型は、実際にはワイド文字の文字列が、それらが 1 バイト文字の文字列をマーシャ リングします。 したがって、printf 関数指定子が %S (wchar_t *) の場合にマーシャ リング %s 文字列に代わりにします。

- コンパイルするときに予期しない結果が取得 va_arg マクロを使用して、 **/clr: 純粋な**します。 詳細については、[va_arg、va_copy、va_end、va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)を参照してください。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。 「純粋」または「安全」にする必要があるコードを移植する必要があるC#します。

- 呼び出す必要はありません、マネージ コード、パラメーター情報 (関数の引数) を取得するスタック ウォークをすべての関数からP/invoke レイヤーには、スタックをさらにその情報が原因です。  たとえば、プロキシ/スタブをコンパイルできない **/clr**します。

- 関数は可能であれば、マネージ コードにコンパイルされますが、すべての C++ 構造体をマネージ コードに変換できます。  関数ごとに決定されます。 関数の任意の部分は、マネージ コードに変換できない場合関数全体が変換をネイティブ コードに代わりにします。 次の場合は、コンパイラがマネージ コードを生成するようにします。

  - コンパイラによって生成されたサンクまたはヘルパー関数。 仮想関数の呼び出しなど、関数ポインターを通じて関数呼び出しでは、ネイティブのサンクが生成されます。

  - 関数を呼び出す`setjmp`または`longjmp`します。

  - 特定の組み込みルーチンを使用して、マシンのリソースを直接操作する関数。 使用例:`__enable`と`__disable`、`_ReturnAddress`と`_AddressOfReturnAddress`、マルチ メディアの組み込み関数は、ネイティブ コードですべての結果。

  - その次の関数、`#pragma unmanaged`ディレクティブ。 (なお、逆`#pragma managed`もサポートされています)。

  - 関数への参照を含む配置の種類は、型宣言を使用して`__declspec(align(...))`します。

## <a name="see-also"></a>関連項目

- [/clr (共通言語ランタイムのコンパイル)](clr-common-language-runtime-compilation.md)
