---
title: /clr の制約 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], restrictions
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34d21939f51fc3d4800d5cdd887b283b7e690db6
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704270"
---
# <a name="clr-restrictions"></a>/clr の制約

使用は、次の制限に注意してください **/clr**:

- 構造化例外ハンドラーでは、使用に関する制限事項`_alloca`でコンパイルするときに **/clr**です。 詳細については、次を参照してください。 [_alloca](../../c-runtime-library/reference/alloca.md)です。

- 実行時エラー チェックの使用では無効です **/clr**です。 詳細については、「[How to: Use Native Run-Time Checks (方法: ネイティブ ランタイム チェックを使用する)](/visualstudio/debugger/how-to-use-native-run-time-checks)」をご覧ください。

- ときに **/clr**はのみ C++ の標準構文を使用するプログラムをコンパイルするため、インライン アセンブリの使用に次のガイドラインが適用されます。

  - ネイティブのスタックのレイアウトの知識を前提としているインライン アセンブラー コードを呼び出し、現在の関数、またはコンピューターに関するその他の低レベルの情報の外部で規則がエラー ナレッジは、マネージ関数のスタック フレームに適用されています。 せずにコンパイルされた個別のモジュール内に置かれた場合に、アンマネージ関数は、インライン アセンブラー コードを含む関数が生成された **/clr**です。

  - インライン アセンブラー コードのコピーで構築された関数のパラメーターを渡す関数内ではサポートされていません。

- [Vprintf 系関数](../../c-runtime-library/vprintf-functions.md)でコンパイルされたプログラムから呼び出すことができません **/clr**です。

- [Naked](../../cpp/naked-cpp.md) [_ _declspec](../../cpp/declspec.md)修飾子は/clr で無視されます。

- 変換関数を設定[_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)アンマネージ コードでキャッチのみに影響されます。 参照してください[例外処理](../../windows/exception-handling-cpp-component-extensions.md)詳細についてはします。

- 関数ポインターの比較が下で許可されていない **/clr**です。

- 完全なプロトタイプではない関数の使用は許可されません **/clr**です。

- 次のコンパイラ オプションはサポートされていません **/clr**:

  - **/EHsc**と **/EHs** (**/clr**意味 **/EHa** (を参照してください[/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md))

  - **/fp: 厳密な**と **/fp: 除く**(を参照してください[/fp (浮動小数点の動作を指定)](../../build/reference/fp-specify-floating-point-behavior.md))

  - [/Zd](../../build/reference/z7-zi-zi-debug-information-format.md)

  - [/Gm](../../build/reference/gm-enable-minimal-rebuild.md)

  - [/MT](../../build/reference/md-mt-ld-use-run-time-library.md)

  - [/RTC](../../build/reference/rtc-run-time-error-checks.md)

  - [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)

- 組み合わせ、`_STATIC_CPPLIB`プリプロセッサ定義 (`/D_STATIC_CPPLIB`) および **/clr**コンパイラ オプションはサポートされていません。 これはそのため、定義は、静的なマルチ スレッド C++ 標準ライブラリ、サポートされていないとリンクするアプリケーションになるためです。 詳細については、次を参照してください。、 [/MD、/MT、/LD (ランタイム ライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md)トピックです。

- 使用する場合 **/Zi**で **/clr**パフォーマンスに影響があります。 詳細については、次を参照してください。 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)です。

- .NET Framework にはワイド文字を渡すことも指定せずルーチンを出力[/Zc:wchar_t](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)または対象の文字にキャストせず`__wchar_t`として表示される出力になります、`unsigned short int`です。 例えば:

    ```cpp
    Console::WriteLine(L' ')              // Will output 32.
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.
    ```

- [/GS](../../build/reference/gs-buffer-security-check.md)でコンパイルする場合は無視されます **/clr**関数は、下にある場合を除き、 `#pragma` [アンマネージ](../../preprocessor/managed-unmanaged.md)いる場合、コンパイラは生成場合は、関数は、ネイティブにコンパイルする必要があります、または警告 C4793 で、既定ではオフです。

- 参照してください[/ENTRY](../../build/reference/entry-entry-point-symbol.md)関数署名の要件に、マネージ アプリケーションです。

- コンパイルされたアプリケーション **/openmp**と **/clr**単一の appdomain のプロセスでのみ実行できます。  参照してください[/openmp (OpenMP 2.0 サポートの有効にする)](../../build/reference/openmp-enable-openmp-2-0-support.md)詳細についてはします。

- 可変個の引数 (vararg) を受け取る関数は、ネイティブ関数として生成されます。 可変個引数の位置が、マネージ データ型は、ネイティブ型にマーシャ リングされます。 なお<xref:System.String?displayProperty=fullName>型が実際にはワイド文字列が、それらが 1 バイト文字の文字列をマーシャ リングします。 したがって、printf 関数指定子が %S (wchar_t *) の場合にマーシャ リング %s 文字列に代わりにします。

- Va_arg マクロを使用する場合でコンパイルするときに予期しない結果を取得することがあります **/clr: 純粋な**します。 詳細については、次を参照してください。 [va_arg、va_copy、va_end、va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)です。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。 「純粋」または「安全」にする必要があるコードは、c# に移植する必要があります。

- 呼び出す必要はありません、マネージ コード、パラメーター情報 (関数の引数) を取得するスタック ウォークを任意の関数からP/invoke レイヤーにより、その情報をスタックをさらに取得します。  たとえばとプロキシ/スタブをコンパイルできない **/clr**です。

- 関数は、可能な限り、マネージ コードにコンパイルされますが、すべての C++ コンストラクトは、マネージ コードに変換することができます。  関数によってごとに決定されます。 場合は、関数の任意の部分は、マネージ コードに変換できない、関数全体に変換されますネイティブ コード代わりにします。 次の場合は、コンパイラがマネージ コードを生成するようにします。

  - コンパイラによって生成されたサンクまたはヘルパー関数。 仮想関数の呼び出しなど、関数ポインターを通じて関数呼び出しでは、ネイティブなサンクが生成されます。

  - 関数を呼び出す`setjmp`または`longjmp`です。

  - マシン リソースを直接操作する特定の組み込みルーチンを使用する関数。 たとえばの使用`__enable`と`__disable`、`_ReturnAddress`と`_AddressOfReturnAddress`、マルチ メディアの組み込み関数は、ネイティブ コード内のすべての結果。

  - その次の機能、`#pragma unmanaged`ディレクティブです。 (なお、逆`#pragma managed`もサポートされています)。

  - 参照を含む関数配置の種類、つまり、型宣言を使用して`__declspec(align(...))`です。

## <a name="see-also"></a>関連項目

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)
