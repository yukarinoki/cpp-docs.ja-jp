---
title: -guard (有効にする Control Flow Guard) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /guard
- VC.Project.VCCLCompilerTool.ControlFlowGuard
dev_langs:
- C++
ms.assetid: be495323-f59f-4cf3-a6b6-8ee69e6a19dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5c60ff444189e9e6b7919b43649b75722ee7249
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377405"
---
# <a name="guard-enable-control-flow-guard"></a>/guard (制御フロー ガードを有効にする)
制御フロー ガードのセキュリティ チェックのコンパイラ生成を有効にします。  
  
## <a name="syntax"></a>構文  
  
```  
/guard:cf[-]  
```  
  
## <a name="remarks"></a>コメント  
 **/guard:cf** オプションにより、コンパイラがコンパイル時に間接的な呼び出しのターゲットに関する制御フローを分析し、実行時に、ターゲットを確認するコードを挿入します。 既定では、 **/guard:cf** は無効になっており、明示的に有効にする必要があります。 このオプションを明示的に無効にするには、 **/guard:cf-** を使用します。  
  
 **/guard:cf** 制御フローガード (CFG) オプションが指定されている場合、コンパイラとリンカーがランタイム セキュリティ チェックを追加で挿入して、コードを侵害する試みを検出します。 コンパイルとリンク中に、コードのすべての間接的な呼び出しが分析され、コードを正常に実行したときに到達可能なすべての場所が検索されます。 この情報は、バイナリのヘッダーの追加の構造に格納されます。 また、コンパイラは、コード内の間接的な各呼び出しの前に、ターゲットが検証済みの場所のいずれかにあることを確認するチェックを挿入します。 CFG 対応オペレーティング システム上の実行時にチェックに失敗した場合、オペレーティング システムはプログラムを閉じます。  
  
 ソフトウェアに対する一般的な攻撃は、極端なまたは予期しない入力の処理のバグを利用します。 アプリケーションに対する入念に作成された入力が、実行可能コードへのポインターを含む場所を上書きする能性があります。 これを使用して、攻撃者によって制御されるコードに制御フローをリダイレクトすることができます。 CFG の実行時チェックでは、実行可能ファイルで、データの破損バグは修正されません。 代わりに、攻撃者がそれらを使用して、任意のコードを実行することを難しくします。 CFG は、コード内の関数のエントリ ポイント以外の場所への呼び出しを防止する対応策ツールです。 それは、データ実行防止 (DEP) である  [/GS](../../build/reference/gs-buffer-security-check.md) スタックのチェック方法と似ていて、 [/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) と [/HIGHENTROPYVA](../../build/reference/highentropyva-support-64-bit-aslr.md) ASLR (Address Space Layout Randomization) で、コードが脆弱性攻撃ベクトルになる可能性を低減します。  
  
 **/guard:cf** オプションをコンパイラ オプションとリンカーの両方に渡して、CFG 攻撃の緩和テクニックを使用するコードを作成する必要があります。 1 つの `cl` コマンドを使用してバイナリが作成されている場合、コンパイラはリンカーにオプションを渡します。 コンパイルとリンクを分けて実行する場合は、コンパイラとリンカーの両方のコマンドで、オプションを設定する必要があります。 /DYNAMICBASE リンカー オプションも必要です。 バイナリが CFG データを持っていることを確認するには、 `dumpbin /headers /loadconfig` コマンドを使用します。 CFG が有効なバイナリが EXE または DLL の特性のリストに `Guard` を持っている場合、ガード フラグに `CF Instrumented` と `FID table present`を使用します。  
  
 **/guard:cf** オプションは [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) (エディット コンティニュ デバッグ情報) または [/clr](../../build/reference/clr-common-language-runtime-compilation.md) (共通言語ランタイムのコンパイル) とは互換性がありません。  
  
 **/guard:cf** を使用してコンパイルされたコードは、オプションを使用してコンパイルされないライブラリとオブジェクト ファイルにリンクできます。 **/guard:cf** オプションを使用してリンクされ、CFG に対応したオペレーティング システム上で実行されるとき、このコードのみが CFG に保護されます。 オプションを使用せずにコンパイルされたコードは攻撃を停止しないので、コンパイルするすべてのコードにオプションを使用することをお勧めします。 CFG チェックには実行時の負荷が少しありますが、コンパイラの分析は、間接的なジャンプでのチェックを除去するように最適化を試みるので、安全であることが証明されます。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[構成プロパティ]**、 **[C/C++]**、 **[コード生成]** の順に選択します。  
  
3.  **[制御フロー ガード]** プロパティを選択します。  
  
4.  ドロップダウン コントロールで、制御フロー ガードを有効にするには **[はい]** を選択し、無効にするには **[いいえ]** を選択します。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)