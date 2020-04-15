---
title: /EH (例外処理モデル)
ms.date: 08/14/2018
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
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
ms.openlocfilehash: 8546b14995317afb57e4cc23a5d6f81c2172a1a6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328295"
---
# <a name="eh-exception-handling-model"></a>/EH (例外処理モデル)

コンパイラで使用される例外処理の種類、例外チェックを最適化して除去するタイミング、および例外が原因でスコープを外れた C++ オブジェクトを破棄するかどうかを指定します。 **/EH**が指定されていない場合、コンパイラはコードで非同期構造化例外と C++ 例外の両方をキャッチできますが、非同期例外のためにスコープ外に出る C++ オブジェクトを破棄しません。

## <a name="syntax"></a>構文

> **/EH**{**s**|**a**}[**c**] [**r**]**-**]

## <a name="arguments"></a>引数

**A**<br/>
C++`catch(...)`構文を使用して非同期 (構造化) 例外と同期 (C++) 例外の両方をキャッチする例外処理モデル。

**S**<br/>
同期 (C++) 例外のみをキャッチし **、extern "C"** として宣言された関数が例外をスローする可能性があることを想定するようにコンパイラに指示する例外処理モデル。

**C**<br/>
**s** (**/EHsc**) と共に使用すると、C++ 例外のみをキャッチし **、extern "C"** として宣言された関数が C++ 例外をスローしないと想定するようにコンパイラに指示します。 **/EHca** は **/EHa**と同じです。

**R**<br/>
すべての noexcept 関数のランタイム終了チェックを常に生成するようにコンパイラ**に指示**します。 既定では、コンパイラがスローしない関数のみを呼び出す関数を決定した場合、ランタイムチェックで**noexcept**が最適化される可能性があります。

## <a name="remarks"></a>解説

**/EHa** コンパイラ オプションは、ネイティブ C++ `catch(...)` 句で非同期構造化例外処理 (SEH) をサポートするために使用されます。 **/EHa**を指定せずに SEH を実装するには **、__try** **、__except、****および __finally**構文を使用します。 Windows および Visual C++ は SEH をサポートしていますが、ISO 標準の C++ 例外処理 (**/EHs** または **/EHsc**) の方がコードの移植性と柔軟性に優れているため、こちらの例外処理を使用することを強くお勧めします。 ただし、既存のコードや特定の種類のプログラム (たとえば、共通言語ランタイムをサポートするためにコンパイルされたコード ([/clr (共通言語ランタイム コンパイル) )](clr-common-language-runtime-compilation.md)では、SEH を使用する必要があります。 詳細については、「 [Structured Exception Handling (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)」を参照してください。

**/EHa** を指定し、 `catch(...)` を使用してすべての例外を処理しようとするのは危険です。 非同期例外のほとんどが回復不能で、致命的であると見なされます。 こうした例外をキャッチして操作を続行すると、プロセスが破損し、検出して修正するのが難しいバグが発生する可能性があります。

**/EHs** または **/EHsc**を使用すると、 `catch(...)` 句では非同期構造化例外がキャッチされません。 アクセス違反およびマネージド <xref:System.Exception?displayProperty=fullName> 例外がキャッチされず、非同期例外が処理される場合も含め、非同期例外が生成されたときに、スコープ内のオブジェクトが破棄されることはありません。

**/EHa**を使用すると、コンパイラが**try**ブロックを積極的に最適化しないため、イメージのサイズが大きくなり、パフォーマンスが低下する可能性があります。 また、コンパイラが C++ 例外をスローする可能性のあるコードを確認しない場合でも、すべてのローカル オブジェクトのデストラクターを自動的に呼び出す例外フィルターが除去されません。 これにより、非同期例外および C++ 例外のセーフ スタック アンワインドが可能になります。 **/EHs**を使用すると、コンパイラは例外が**throw**ステートメントまたは関数呼び出しでのみ発生すると見なします。 これにより、アンワインド可能オブジェクトの有効期間を管理するコードを削除できるため、コード サイズをかなり小さくできます。

**/EHa**を使用してコンパイルされたオブジェクトと、同じ実行可能モジュールで **/EHs**または **/EHsc**を使用してコンパイルされたオブジェクトをリンクしないことをお勧めします。 モジュールの任意の場所で **/EHa** を使用して、非同期例外を処理する必要がある場合は、 **/EHa** を使用して、モジュール内のすべてのコードをコンパイルします。 **/EHs**を使用してコンパイルされたコードと同じモジュールで構造化例外処理構文を使用できますが、SEH 構文を**try** **、throw、** および**catch**と同じ関数で混在させることはできません。

**スロー**以外の何かによって発生した例外をキャッチする場合は **、/EHa**を使用します。 この例では、構造化例外が生成され、キャッチされます。

```cpp
// compiler_options_EHA.cpp
// compile with: /EHa
#include <iostream>
#include <excpt.h>
using namespace std;

void fail() {   // generates SE and attempts to catch it using catch(...)
   try {
      int i = 0, j = 1;
      j /= i;   // This will throw a SE (divide by zero).
      printf("%d", j);
   }
   catch(...) {   // catch block will only be executed under /EHa
      cout<<"Caught an exception in catch(...)."<<endl;
   }
}

int main() {
   __try {
      fail();
   }

   // __except will only catch an exception here
   __except(EXCEPTION_EXECUTE_HANDLER) {
      // if the exception was not caught by the catch(...) inside fail()
      cout << "An exception was caught in __except." << endl;
   }
}
```

**/EHc** オプションでは、 **/EHs** または **/EHa** を指定する必要があります。 **/clr**オプションは **/EHa**を意味します (つまり **、/clr** **/EHa**は冗長です)。 **/EHs または /EHsc** **/EHsc**が **/clr**の後に使用された場合、コンパイラはエラーを生成します。 最適化処理は、この動作に影響しません。 例外がキャッチされると、例外オブジェクトまたは例外と同じスコープ内にあるオブジェクトに対して、コンパイラが 1 つまたは複数のクラス デストラクターを呼び出します。 例外がキャッチされない場合は、これらのデストラクターは実行されません。

**/clr**に基づく例外処理の制約については、「 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)」を参照してください。

このオプションは、 記号**-** を使用してクリアできます。 たとえば **、/EHsc-** は **/EHs** **/EHc-** と解釈され **、/EHs**と等価です。

**/EHr**コンパイラ オプションは **、noexcept**属性を持つすべての関数で、ランタイムの終了チェックを強制します。 既定では、コンパイラがバックエンドで関数が *スローしない* 関数のみを呼び出すと判断した場合に、ランタイム チェックが最適化され、除去されます。 スローしない関数とは、属性で例外がスローされないことが指定された関数を指します。 これには **、/EHc**`throw()``__declspec(nothrow)`が指定されている場合に **、"C"** 関数**として指定されている**関数が含まれます。 スローしない関数には、コンパイラの検査でスローしないと判断された関数も含まれます。 **/EHr-** を使用して明示的に既定に設定することができます。

ただし、スローしない属性は、関数からどの例外もスローされないことを保証するわけではありません。 MSVC コンパイラは **、noexcept**関数の動作とは異なり、 、 、`throw()``__declspec(nothrow)`または**extern "C" を**使用して宣言された関数によってスローされる例外を未定義の動作と見なします。 この 3 つの宣言属性を使用する関数は、例外のランタイム終了チェックを強制しません。 **/EHr**オプションを使用すると **、noexcept**関数をエスケープするハンドルされない例外をランタイム チェックを生成するようにコンパイラに強制することで、この未定義の動作を識別するのに役立ちます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ** > **C/C++** > **コード生成**] を選択します。

1. **[C++ の例外を有効にする]** プロパティを変更します。

   または、 **[C++ の例外を有効にする]** を **[いいえ]** に設定してから **[コマンド ライン]** プロパティ ページをクリックし、 **[追加のオプション]** ボックスにコンパイラ オプションを追加します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[エラーと例外の処理](../../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[例外仕様 (スロー)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[構造化例外処理 (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
