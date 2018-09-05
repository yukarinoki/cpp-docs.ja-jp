---
title: -sdl (追加のセキュリティ チェックを有効にする) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
dev_langs:
- C++
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6f88e254a49309c0ca44c330fdc71d32ee1a87d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686340"
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl (追加のセキュリティ チェックの有効化)
推奨される Security Development Lifecycle (SDL) のチェックを追加します。 これらのチェックには、エラーとしての追加のセキュリティ関連の警告、および追加の安全なコード生成機能が含まれます。  
  
## <a name="syntax"></a>構文  
  
```  
/sdl[-]  
```  
  
## <a name="remarks"></a>Remarks  
 **/sdl**によって提供されるベースライン セキュリティ チェックのスーパー セットの有効[/GS](../../build/reference/gs-buffer-security-check.md)と上書き **/GS-** します。 既定では、 **/sdl**はオフです。 **/sdl-** 追加のセキュリティ チェックを無効にします。  
  
## <a name="compile-time-checks"></a>コンパイル時のチェック  
 **/sdl**により、これらの警告をエラーとして。  
  
|/sdl で有効になる警告|同等のコマンド ラインスイッチ|説明|  
|------------------------------|-------------------------------------|-----------------|  
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|/we4146|単項マイナス演算子が符号なしの型に適用され、符号なしの結果になります。|  
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|/we4308|負の整数定数が符号なしの型に変換されて、多くの場合は意味のない結果になります。|  
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|/we4532|使用`continue`、`break`または`goto`内のキーワード、 `__finally` / `finally`ブロックが異常終了時の動作を定義されていません。|  
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|/we4533|変数の初期化コードが実行されません。|  
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|/we4700|初期化されていないローカル変数が使用されます。|  
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|/we4703|初期化されていない可能性のあるローカル ポインター変数が使用されます。|  
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|/we4789|特定の C ランタイム (CRT) 関数の使用時にバッファー オーバーランが発生します。|  
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|/we4995|プラグマでマークされた関数を使用[非推奨とされます](../../preprocessor/deprecated-c-cpp.md)します。|  
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|/we4996|としてマークされている関数を使用[非推奨とされます](../../cpp/deprecated-cpp.md)します。|  
  
## <a name="runtime-checks"></a>実行時のチェック  
 ときに **/sdl**が有効にすると、コンパイラは実行時にこれらのチェックを実行するコードが生成されます。  
  
-   Strict モードを有効に **/GS**実行時バッファー オーバーランの検出、使用したコンパイルと同じ`#pragma strict_gs_check(push, on)`します。  
  
-   制限付きでポインターのサニタイズを行います。 逆参照がない式でも、ユーザー定義のデストラクターがない型でも、ポインターの参照は、`delete` の呼び出し後、無効なアドレスに設定されます。 これは、古いポインター参照の再使用を防止するために役立ちます。  
  
-   クラス メンバーの初期化を実行します。 すべてのクラス メンバーをオブジェクトのインスタンス化時にゼロに自動的に初期化します (コンストラクターの実行前)。 これは、コンストラクターが明示的に初期化しないクラス メンバーに関連付けられた、初期化されていないデータの使用を防止するために役立ちます。  
  
## <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。[警告、/sdl、および初期化されていない変数の検出の向上](https://cloudblogs.microsoft.com/microsoftsecure/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/)します。  
  
#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  選択、 **C/C++** フォルダー。  
  
3.  **全般**からオプションを選択 ページで、 **SDL チェック**ドロップダウン リスト。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)