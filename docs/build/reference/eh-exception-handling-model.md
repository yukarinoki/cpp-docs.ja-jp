---
title: /EH (例外処理モデル)
description: Visual Studio の Microsoft C++ /EH (例外処理モデル) コンパイラ オプションのリファレンス ガイド。
ms.date: 04/14/2020
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExceptionHandling
- /eh
- VC.Project.VCCLCompilerTool.ExceptionHandling
helpviewer_keywords:
- exception handling, compiler model
- cl.exe compiler, exception handling
- EH compiler option [C++]
- -EH compiler option [C++]
- /EH compiler option [C++]
no-loc:
- SEH
- try
- catch
- throw
- extern
- finally
- noexcept
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
ms.openlocfilehash: 68d6af657e7c20c0f5e84674dd91803beb35fba0
ms.sourcegitcommit: 0e4feb35b47c507947262d00349d4a893863a6d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81396291"
---
# <a name="eh-exception-handling-model"></a>/EH (例外処理モデル)

コンパイラによって生成される例外処理モデルのサポートを指定します。 引数は、構造化された`catch(...)`C++ 例外と標準 C++ 例外の両方に構文を適用するかどうかthrow**extern、"C"** コードが例外と**noexcept** 見なされるかどうか、および特定のチェックを最適化するかどうかを指定します。

## <a name="syntax"></a>構文

> **`/EHa`**[**`-`**]\
> **`/EHs`**[**`-`**]\
> **`/EHc`**[**`-`**]\
> **`/EHr`**[**`-`**]

## <a name="arguments"></a>引数

**`a`**\
標準の C++ スタックアンワインドを有効にします。 構文を使用`catch(...)`する場合、構造化 (非同期) 例外と標準 C++ (同期) 例外の両方をキャッチします。 **`/EHa`** は、引数**`/EHs`** と**`/EHc`** 引数の両方をオーバーライドします。

**`s`**\
標準の C++ スタックアンワインドを有効にします。 構文を使用`catch(...)`する場合は、標準 C++ 例外のみをキャッチします。 コンパイラ**`/EHc`** は、指定しない限り**extern、"C"** として宣言された関数throwが C++ 例外である可能性があると想定します。

**`c`**\
と共に**`/EHs`** 使用する場合、コンパイラは**extern"C"** としてthrow宣言された関数が C++ 例外であると想定します。 と共**`/EHa`** に使用しても効果はありません (つまり、**`/EHca`** と同等です**`/EHa`**)。 **`/EHc`** は、指定されていない**`/EHs`** 場合**`/EHa`** は無視されます。

**`r`**\
すべての**noexcept** 関数のランタイム終了チェックを常に生成するようにコンパイラに指示します。 既定では、コンパイラ**noexcept** がスローしない関数のみを呼び出す関数を決定した場合、ランタイム チェックが最適化される場合があります。 このオプションを使用すると、C++ の厳密な準拠性が生じ、余分なコードが生まれます。 **`/EHr`** は、指定されていない**`/EHs`** 場合**`/EHa`** は無視されます。

**`-`**\
前のオプション引数をクリアします。 たとえば、**`/EHsc-`** は**`/EHs /EHc-`** と解釈され、 と同**`/EHs`** じになります。

**`/EH`** 引数は、任意の順序で個別に指定するか、組み合わせて指定できます。 同じ引数の複数のインスタンスが指定されている場合、最後のインスタンスは以前のインスタンスよりも優先されます。  たとえば、**`/EHr- /EHc /EHs`** と同じ**`/EHscr-`** で、**`/EHscr- /EHr`** と同じ効果があります**`/EHscr`**。

## <a name="remarks"></a>解説

### <a name="default-exception-handling-behavior"></a>既定の例外処理動作

コンパイラは常に、非同期構造化例外処理 ( )SEHをサポートするコードを生成します。 既定では (つまり、 または**`/EHsc`****`/EHs`****`/EHa`** オプションが指定されていない場合)、コンパイラはSEHネイティブ C++`catch(...)`句のハンドラーをサポートします。 ただし、C++ 例外を部分的にしかサポートしていないコードも生成されます。 既定の例外アンワインド コードでは、例外のためにスコープ外に出る[try](../../cpp/try-throw-and-catch-statements-cpp.md)ブロックの外部にある自動 C++ オブジェクトは破棄されません。 C++ 例外がスローされると、リソース リークや未定義の動作が発生する場合があります。

### <a name="standard-c-exception-handling"></a>標準 C++ 例外処理

スタック オブジェクトを安全にアンウィンする標準 C++ 例外処理モデルの完全**`/EHsc`** なコンパイラ**`/EHs`** サポートには**`/EHa`**、 、、必要な (推奨)、または が必要です。

または**`/EHs`****`/EHsc`** を使用する場合、`catch(...)`句は構造化例外をcatch非同期化しません。 アクセス違反およびマネージ<xref:System.Exception?displayProperty=fullName>例外は、キャッチされません。 また、コードが非同期例外を処理する場合でも、非同期例外が発生したときにスコープ内のオブジェクトは破棄されません。 この動作は、構造化例外を未処理のままにするための引数です。 代わりに、これらの例外を致命的と考えてください。

または**`/EHs`****`/EHsc`** を使用すると、コンパイラは、ステートメントまたは関数呼び出し**throw** でのみ例外が発生すると想定します。 この前提により、コンパイラは、多数のアンワインド可能なオブジェクトの有効期間を追跡するコードを排除することができ、コード サイズを大幅に削減できます。 を使用**`/EHa`** すると、コンパイラがブロックを積極的に最適化**try** しないため、実行可能イメージのサイズが大きく、遅くなる可能性があります。 また、コンパイラに C++ 例外を起こすコードthrowが表示されない場合でも、ローカル オブジェクトを自動的にクリーンアップする例外フィルターも残ります。

### <a name="structured-and-standard-c-exception-handling"></a>構造化および標準の C++ 例外処理

コンパイラ**`/EHa`** オプションを使用すると、非同期例外と C++ 例外の両方に対して、スタックの安全なアンワインドが可能になります。 ネイティブ C++`catch(...)`句を使用して、標準 C++ と構造化例外の両方の処理をサポートします。 **`/EHa`** を指定SEHせずに実装するには **、__try** **、__except、****および __finally**構文を使用します。 詳しくは、[構造化例外処理を](../../cpp/structured-exception-handling-c-cpp.md)参照してください。

> [!IMPORTANT]
> を使用**`/EHa`**`catch(...)`してすべての例外を指定して処理しようとすると、危険な場合があります。 非同期例外のほとんどが回復不能で、致命的であると見なされます。 こうした例外をキャッチして操作を続行すると、プロセスが破損し、検出して修正するのが難しいバグが発生する可能性があります。
>
> Windows および Visual C++SEHがサポートされている場合でも、ISO 標準の C++ 例外**`/EHsc`** 処理**`/EHs`**( または ) を使用することを強くお勧めします。 これにより、コードの移植性と柔軟性が向上します。 レガシーコードや特定の種類のプログラムでSEH使用しなければならない場合があります。 たとえば、共通言語ランタイム ([/clr](clr-common-language-runtime-compilation.md)) をサポートするためにコンパイルされたコードで必要です。 詳しくは、[構造化例外処理を](../../cpp/structured-exception-handling-c-cpp.md)参照してください。
>
> を使用して**`/EHa`** コンパイルされたオブジェクト ファイルを、**`/EHs`** 同**`/EHsc`** じ実行可能モジュールでコンパイルされたものにリンクすることはお勧めしません。 モジュール内の任意の場所を使用**`/EHa`** して非同期例外を処理する必要がある**`/EHa`** 場合は、モジュール内のすべてのコードをコンパイルするために使用します。 構造化例外処理構文は、 を使用してコンパイルされたコードと同じモジュールで使用**`/EHs`** できます。 ただし、SEH構文を C++ **try**、、**throw** および 、および**catch** と同じ関数に混在させることはできません。

以外**`/EHa`** の機能によって発生catchする例外を処理する場合に使用します**throw**。 この例では、構造化例外が生成され、キャッチされます。

```cpp
// compiler_options_EHA.cpp
// compile with: /EHa
#include <iostream>
#include <excpt.h>
using namespace std;

void fail()
{
    // generates SE and attempts to catch it using catch(...)
    try
    {
        int i = 0, j = 1;
        j /= i;   // This will throw a SE (divide by zero).
        printf("%d", j);
    }
    catch(...)
    {
        // catch block will only be executed under /EHa
        cout << "Caught an exception in catch(...)." << endl;
    }
}

int main()
{
    __try
    {
        fail();
    }

    // __except will only catch an exception here
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        // if the exception was not caught by the catch(...) inside fail()
        cout << "An exception was caught in __except." << endl;
    }
}
```

### <a name="exception-handling-under-clr"></a>/clr での例外処理

この**`/clr`** オプションは、**`/EHa`** 冗長であることを**`/clr /EHa`** 示します。 コンパイラは、 の後**`/EHs`****`/EHsc`****`/clr`** に または を使用するとエラーを生成します。 最適化は、この動作に影響を与えません。 例外がキャッチされると、コンパイラは、例外と同じスコープ内にあるオブジェクトのクラスデストラクターを呼び出します。 例外がキャッチされない場合、それらのデストラクターは実行されません。

例外処理の制限については、 の「 **`/clr`**」[を参照](../../c-runtime-library/reference/set-se-translator.md)_set_se_translator。

### <a name="runtime-exception-checks"></a>ランタイム例外チェック

この**`/EHr`** オプションは、属性を持つすべての関数でランタイム**noexcept** 終了チェックを強制します。 既定では、コンパイラのバックエンドが関数が*スローしない*関数のみを呼び出していると判断した場合、ランタイム チェックは最適化される可能性があります。 スローしない関数とは、属性で例外がスローされないことが指定された関数を指します。 これらの関数には**noexcept**、"C"`throw()`関数が指定されている`__declspec(nothrow)`**`/EHc`****extern** 場合に、マーク付きの関数 、、および 、"C" 関数が含まれます。 スローしない関数には、コンパイラの検査でスローしないと判断された関数も含まれます。 を使用**`/EHr-`** して、既定の動作を明示的に設定できます。

スローされない属性は、関数が例外をスローできないという保証ではありません。 **noexcept** 関数の動作とは異なり、MSVC コンパイラは、 、`throw()``__declspec(nothrow)`または**extern"C" を**使用して宣言された関数によってスローされる例外を未定義の動作と見なします。 これら 3 つの宣言属性を使用する関数は、例外のランタイム終了チェックを強制しません。 このオプションを使用**`/EHr`** すると、関数をエスケープするハンドルされない例外のランタイム チェックをコンパイラが生成するように強制することで、この未定義の動作**noexcept** を識別できます。

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>オプションを Visual Studio で設定するか、プログラムで設定する

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ** > **C/C++** > **コード生成**] を選択します。

1. **[C++ の例外を有効にする]** プロパティを変更します。

   または、 **[C++ の例外を有効にする]** を **[いいえ]** に設定してから **[コマンド ライン]** プロパティ ページをクリックし、 **[追加のオプション]** ボックスにコンパイラ オプションを追加します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)\
[MSVC コンパイラ のコマンド ライン構文](compiler-command-line-syntax.md)\
[エラーと例外処理](../../cpp/errors-and-exception-handling-modern-cpp.md)\
[例外仕様throw( )](../../cpp/exception-specifications-throw-cpp.md)\
[構造化例外処理 (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
