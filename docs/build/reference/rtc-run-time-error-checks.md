---
title: RTC (実行時エラー チェック) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rtc
- VC.Project.VCCLCompilerTool.SmallerTypeCheck
- VC.Project.VCCLCompilerTool.UninitializedVariableCheck
- VC.Project.VCCLCompilerTool.StackFrameCheck
- VC.Project.VCCLCompilerTool.BasicRuntimeChecks
dev_langs:
- C++
helpviewer_keywords:
- /RTCs compiler option [C++]
- -RTC1 compiler option [C++]
- run-time errors, error checks
- -RTCu compiler option [C++]
- /RTC1 compiler option [C++]
- /RTCc compiler option [C++]
- /RTCu compiler option [C++]
- __MSVC_RUNTIME_CHECKS macro
- -RTCs compiler option [C++]
- RTCs compiler option
- RTC1 compiler option
- run-time errors, run-time checks
- run-time checks, /RTC option
- RTCu compiler option
- RTCc compiler option
- -RTCc compiler option [C++]
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a135c9c4e32ea7a54c45719eff503ff99509d3e7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378458"
---
# <a name="rtc-run-time-error-checks"></a>/RTC (ランタイム エラー チェック)
組み合わせて、実行時エラー チェック機能を無効にするために使用、 [runtime_checks](../../preprocessor/runtime-checks.md)プラグマ。  
  
## <a name="syntax"></a>構文  
  
```  
/RTC1  
/RTCc  
/RTCs  
/RTCu  
```  
  
## <a name="arguments"></a>引数  
 `1`  
 等価の **/RTC**`su`です。  
  
 `c`  
 レポートの値は、小さいデータ型と、データが失われる結果に割り当てられます。 たとえば、値型の場合`short 0x101`型の変数に割り当てられた`char`です。  
  
 このオプションを報告する予定を切り捨てる、たとえば、最初の 8 ビットの場合の状況、`int`として返されます、`char`です。 **/RTC** `c` 、実行時エラーが発生の結果として、実行時エラーを避けるために必要な情報をマスクすることができます、情報が割り当ての結果として失われた場合は、 **/RTC** `c`. 例えば:  
  
```  
#include <crtdbg.h>  
  
char get8bits(int value, int position) {  
   _ASSERT(position < 32);  
   return (char)(value >> position);  
   // Try the following line instead:  
   // return (char)((value >> position) & 0xff);  
}  
  
int main() {  
   get8bits(12341235,3);  
}  
```  
  
 `s`  
 スタック フレーム ランタイム エラーの確認は、次のようを有効にします。  
  
-   0 以外の値にローカル変数の初期化します。 これにより、デバッグ モードで実行しているときに表示されないのバグを特定できます。 スタック変数は、リリース ビルドでは、スタック変数のコンパイラの最適化のため、リリース ビルドと比較して、デバッグ ビルドで 0 をされます大きい可能性があります。 プログラムには、そのスタックの領域が使用されるにリセットされることは 0 に、コンパイラによってです。 そのため、以降、初期化されていないスタック変数を同じスタック領域を使用することは、このスタック メモリを以前の使用から残された値を返すことができます。  
  
-   オーバーランや配列などのローカル変数のアンダーランを検出します。 **/RTC** `s`コンパイラの埋め込み構造体の内部から結果をメモリにアクセスするときにオーバーランが検出されません。 使用して発生する可能性の埋め込み[整列](../../cpp/align-cpp.md)、 [/Zp (構造体メンバーの配置)](../../build/reference/zp-struct-member-alignment.md)、または[パック](../../preprocessor/pack.md)、または余白を追加するコンパイラを必要とするように構造体の要素を注文する場合。  
  
-   スタック ポインターの検証は、スタック ポインターの破損を検出します。 スタック ポインターの破損は、呼び出し規約の不一致によって発生することができます。 エクスポートされた DLL に関数を呼び出す関数ポインターを使用して、たとえば、 [_ _stdcall](../../cpp/stdcall.md)として関数へのポインターを宣言するが、 [_ _cdecl](../../cpp/cdecl.md)です。  
  
 `u`  
 変数を使用してが割り当てられていないことを報告します。 たとえば、ある命令`C4701`下で実行時エラーが生成される場合も **/RTC**`u`です。 任意の命令を生成する[コンパイラの警告 (レベル 1 およびレベル 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)下で実行時エラーが生成される **/RTC**`u`です。  
  
 ただし、次のコード フラグメントについて考えてみます。  
  
```cpp  
int a, *b, c;  
if ( 1 )  
b = &a;  
c = a;  // No run-time error with /RTCu  
```  
  
 変数が初期化されている可能性がありますが場合に、報告されませんによって実行時に **/RTC**`u`です。 やなどの変数が、ポインターを使用してエイリアス化するとコンパイラはない変数を追跡初期化されていない使用を報告します。 実際には、そのアドレスを取得して変数を初期化することができます。 (& A) と同様にこのような状況で、代入演算子を演算子の動作です。  
  
## <a name="remarks"></a>コメント  
 実行時エラー チェックは、実行中のコードの問題を見つける方法です。詳細については、次を参照してください。[する方法: を使用してネイティブ ランタイム チェック](/visualstudio/debugger/how-to-use-native-run-time-checks)です。  
  
 いずれかを使用して、コマンドラインでプログラムをコンパイルする場合、 **/RTC**コンパイラ オプション、すべてのプラグマ[最適化](../../preprocessor/optimize.md)コード内の手順は失敗します。 これは、実行時エラー チェックが (最適化) リリース ビルドで有効ではないためです。  
  
 使用する必要があります **/RTC**は開発ビルドです。**/RTC**製品版をビルドは使用できません。 **/RTC**コンパイラの最適化では使用できません ([/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md))。 ビルドされたプログラム イメージ **/RTC**わずかに大きくなりでビルドされたイメージよりも少し遅くなります **/Od** (最大 5% よりも低速、 **/Od**ビルド)。  
  
 _ _Msvc_runtime_checks プリプロセッサ ディレクティブがいずれかを使用する場合に定義される **/RTC**オプションまたは[/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**コード生成**プロパティ ページ。  
  
4.  次のプロパティの一方または両方を変更:**基本ランタイム チェック**または**小さい型チェック**です。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> プロパティを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [方法 : ネイティブ ランタイム チェックを使用する](/visualstudio/debugger/how-to-use-native-run-time-checks)