---
description: 詳細情報:/GS (バッファーセキュリティチェック)
title: /GS (バッファーのセキュリティ チェック)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BufferSecurityCheck
- VC.Project.VCCLCompilerTool.BufferSecurityCheck
helpviewer_keywords:
- buffers [C++], buffer overruns
- buffer overruns, compiler /GS switch
- GS compiler option [C++]
- /GS compiler option [C++]
- security check compiler option [C++]
- -GS compiler option [C++]
- buffers [C++], avoiding overruns
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
ms.openlocfilehash: 4d7fa3c2220260914c9ff931c2f2e7c76bf12ea1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191876"
---
# <a name="gs-buffer-security-check"></a>/GS (バッファーのセキュリティ チェック)

関数のリターン アドレス、例外ハンドラーのアドレス、または特定の型のパラメーターを上書きするバッファー オーバーランを検出します。 ハッカーは、バッファー オーバーランを発生させるという方法を使用して、バッファー サイズ制限を強制しないコードを攻撃します。

## <a name="syntax"></a>構文

```
/GS[-]
```

## <a name="remarks"></a>解説

**/Gs** は既定でオンになっています。 アプリケーションにセキュリティ上の危険が生じることが予想される場合は、 **/GS-** を使用します。 バッファーオーバーランの検出を抑制する方法の詳細については、「 [safebuffers](../../cpp/safebuffers.md)」を参照してください。

## <a name="security-checks"></a>セキュリティの検査

バッファー オーバーランの問題を起こしやすいとコンパイラが判断した関数には、スタックのリターン アドレスの前に記憶領域が割り当てられます。 関数の入力時に、割り当てられた領域には、モジュールの読み込み時に1回計算された *セキュリティクッキー* が読み込まれます。 関数の実行の終了時に、および 64 ビット オペレーティング システムでのフレームのアンワインド時に、ヘルパー関数が呼び出されてクッキーの値が変更されていないかどうかが確認されます。 異なる値は、スタックの上書きが発生した可能性があることを示します。 異なる値が検出された場合、プロセスは終了します。

## <a name="gs-buffers"></a>GS バッファー

バッファーオーバーランのセキュリティチェックは *GS バッファー* で実行されます。 GS バッファーは、次のいずれかを使用できます。

- 4 バイトを超える配列で、3 つ以上の要素を持ち、要素型がポインター型ではない配列。

- サイズが 8 バイトを超え、ポインターを含まないデータ構造体。

- [_Alloca](../../c-runtime-library/reference/alloca.md)関数を使用して割り当てられたバッファー。

- GS バッファーを含むクラスまたは構造体。

たとえば、次のステートメントで GS バッファーを宣言します。

```cpp
char buffer[20];
int buffer[20];
struct { int a; int b; int c; int d; } myStruct;
struct { int a; char buf[20]; };
```

ただし、次のステートメントでは GS バッファーは宣言されません。 最初の 2 つの宣言には、ポインター型の要素が含まれます。 3 番目と 4 番目のステートメントでは、サイズが非常に小さい配列を宣言しています。 5 番目のステートメントでは、x86 プラットフォームでサイズが 8 バイトを超えない構造体を宣言しています。

```cpp
char *pBuf[20];
void *pv[20];
char buf[4];
int buf[2];
struct { int a; int b; };
```

## <a name="initialize-the-security-cookie"></a>セキュリティ クッキーの初期化

**/Gs** コンパイラオプションでは、cookie を使用する関数が実行される前に、セキュリティクッキーを初期化する必要があります。 セキュリティクッキーは、EXE または DLL のエントリですぐに初期化する必要があります。 これは、既定の VCRuntime エントリポイント mainCRTStartup、wmainCRTStartup、WinMainCRTStartup、wWinMainCRTStartup、または _DllMainCRTStartup を使用した場合に自動的に実行されます。 別のエントリポイントを使用する場合は、 [__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md)を呼び出すことによって、セキュリティ cookie を手動で初期化する必要があります。

## <a name="what-is-protected"></a>保護される対象

**/Gs** コンパイラオプションは、次の項目を保護します。

- 関数呼び出しの戻りアドレス。

- 関数の例外ハンドラーのアドレス。

- Vulnerable 関数パラメーター。

すべてのプラットフォームで、 **/gs** は、リターンアドレスへのバッファーオーバーランの検出を試みます。 バッファー オーバーランは、関数呼び出しのリターン アドレスをスタックに格納する呼び出し規則を使用する、x86、x64 などのプラットフォームでの方が簡単に攻撃されます。

x86 で、関数が例外ハンドラーを使用する場合、コンパイラはセキュリティ クッキーを挿入して、例外ハンドラーのアドレスを保護します。 このクッキーは、フレームのアンワインド時にチェックされます。

**/Gs** は、関数に渡される *脆弱なパラメーター* を保護します。 脆弱なパラメーターとは、ポインター、C++ 参照、内部にポインターを含む C 構造体 (C++ POD 型)、または GS バッファーです。

脆弱なパラメーターは、クッキーおよびローカル変数より前に割り当てられます。 バッファー オーバーランによって、これらのパラメーターが上書きされることがあります。 また、これらのパラメーターを使用する関数のコードでは、関数から制御が戻る前、およびセキュリティ チェックが実行される前に、攻撃を受ける可能性があります。 この危険を最小化するために、コンパイラは、関数プロローグで、脆弱なパラメーターのコピーを作成し、任意のバッファーのストレージ領域の下に配置します。

コンパイラは、次の場合は脆弱なパラメーターのコピーを作成しません。

- GS バッファーを含まない関数の場合。

- 最適化 ([/o オプション](o-options-optimize-code.md)) が有効になっていません。

- 可変個引数リスト (...) を持つ関数の場合。

- " [生](../../cpp/naked-cpp.md)" とマークされている関数。

- 最初のステートメントにインライン アセンブラー コードを含む関数の場合。

- パラメーターが、バッファー オーバーランが発生したときに攻撃される可能性が低い方法でのみ使用されている場合。

## <a name="what-is-not-protected"></a>保護されない対象

**/Gs** コンパイラオプションでは、すべてのバッファーオーバーランセキュリティ攻撃を防ぐことはできません。 たとえば、バッファーと vtable が同じオブジェクトにある場合、バッファー オーバーランによって vtable が破損する可能性があります。

**/Gs** を使用する場合でも、バッファーオーバーランのない安全なコードを作成するようにしてください。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. **ソリューションエクスプローラー** で、プロジェクトを右クリックし、[**プロパティ**] をクリックします。

   詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [ **プロパティページ** ] ダイアログボックスで、[ **C/c + +** ] フォルダーをクリックします。

1. [ **コード生成** ] プロパティページをクリックします。

1. **バッファーセキュリティチェック** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck%2A>

## <a name="example"></a>例

この例では、バッファー オーバーランが発生します。 このため、実行時にアプリケーションで障害が発生します。

```C
// compile with: /c /W1
#include <cstring>
#include <stdlib.h>
#pragma warning(disable : 4996)   // for strcpy use

// Vulnerable function
void vulnerable(const char *str) {
   char buffer[10];
   strcpy(buffer, str); // overrun buffer !!!

   // use a secure CRT function to help prevent buffer overruns
   // truncate string to fit a 10 byte buffer
   // strncpy_s(buffer, _countof(buffer), str, _TRUNCATE);
}

int main() {
   // declare buffer that is bigger than expected
   char large_buffer[] = "This string is longer than 10 characters!!";
   vulnerable(large_buffer);
}
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
