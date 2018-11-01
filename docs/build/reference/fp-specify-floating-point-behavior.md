---
title: /fp (浮動小数点の動作の指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
ms.openlocfilehash: 8b948edba3244eb22089b2ef5b4c8131736e1fb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452573"
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (浮動小数点の動作の指定)

ソース コード ファイルの浮動小数点の動作を指定します。

## <a name="syntax"></a>構文

> **/fp:**[**正確な** | **を除く**[**-**] |**高速** | **strict**]

### <a name="arguments"></a>引数

#### <a name="precise"></a>正確です

既定値 **/fp**は **/fp: 正確な**します。

**/Fp: 正確な**フラグは、浮動小数点演算の精度に影響する最適化を無効にして等号または不等号の浮動小数点テストの一貫性を向上させます。 (ANSI 基準に厳密に従うには、特定の精度を保持する必要があります)。既定では、x86 のコード アーキテクチャで使用 x87 コプロセッサ手順は、コンパイラは、コプロセッサの 80 ビット浮動小数点演算の中間結果を保持するために登録します。 これにより、プログラムの実行速度が向上し、プログラムのサイズも小さくなります。 ただし、浮動小数点演算では、80 ビット未満のメモリで表される浮動小数点データ型も使用されるため、処理内容の多い演算では、このように余分な精度ビット、つまり、80 ビットと実際の浮動小数点データ型のビット数との差があると、演算結果の一貫性が失われることがあります。

**/Fp: 正確な**x86 プロセッサでは、コンパイラは型の変数の丸めを実行`float`の割り当てとキャスト、およびパラメーターが関数に渡された場合の適切な有効桁数にします。 この丸めにより、データが型の容量を大幅に上回らないようにします。 コンパイルされたプログラム **/fp: 正確な**できる速度が遅く、なしでコンパイル 1 より大きい **/fp: 正確な**します。 **/fp: 正確な**組み込みを無効には、標準のランタイム ライブラリ ルーチンが代わりに使用されます。 詳細については、「[/Oi (組み込み関数の生成)](../../build/reference/oi-generate-intrinsic-functions.md)」を参照してください。

次の浮動小数点の動作が有効になっている **/fp: 正確な**:

- 短縮操作、つまり、最後に 1 回だけ丸め処理を行う複合演算を使用して、複数の演算を置き換える操作。

- 特殊な値 (NaN、+infinity、-infinity、+0、-0) に対して無効な式の最適化は使用できません。 最適化の x x > 0 = x * 0 > 0、x-0 を = = > x、x + 0 = > x、および 0 x = > さまざまな理由で、x が有効でないです。 (詳細については、IEEE 754 および C99 標準を参照してください)。

- コンパイラは、NaN が含まれている比較を適切に処理します。 たとえば、x! = に評価される x **true**場合`x`nan し、NaN に関連する順序の比較は例外を発生させます。

- 式の評価は C99 FLT_EVAL_METHOD=2 に従いますが、1 つだけ例外があります。x86 プロセッサに対するプログラミングでは、FPU は 53 ビット精度に設定されるため、long double 精度と見なされます。

- 厳密な 1.0 での乗算では他の係数に変換されます。 x * y\*1.0 が x に変換される\*y です。 同様に、x\*1.0\*y が x に変換される\*y です。

- 厳密な 1.0 での除算では被除数が使用されます。 x * x に変換する y/1.0\*y です。 同様に、x 1.0/\*y が x に変換される\*y です。

使用して **/fp: 正確な**とき[fenv_access](../../preprocessor/fenv-access.md)はコンパイル時の浮動小数点式の評価などの最適化を無効にします。 たとえば、 [_control87、_controlfp、 \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)丸めモードと、コンパイラを変更する浮動小数点計算を実行する、指定した丸めモードが無効にしない限り、 `fenv_access`は ON です。

**/fp: 正確な**置換、 **/Op**コンパイラ オプション。

#### <a name="fast"></a>高速します。

**/Fp:fast**オプションは、浮動小数点演算を最適化するための規則を緩和することでほとんどの場合、最も高速なコードを作成します。 これにより、コンパイラは速度のために精度と正確性を犠牲にして、浮動小数点コードを最適化できます。 ときに **/fp:fast**が指定されて、コンパイラが代入ステートメントで正しく丸め可能性があります、丸めない、または関数呼び出し、および中間式の丸め処理を行わない場合があります。 そして、有限の精度の結果に対する影響を考慮せずに、たとえば、結合規則および分配規則に従って、演算の順序を変更するか、代数変換を実行する可能性があります。 また、C++ の型の上位変換規則に従う代わりに、演算とオペランドを単精度に変更する場合があります。 浮動小数点固有の短縮形の最適化が常に有効になっている ([fp_contract](../../preprocessor/fp-contract.md)は ON です)。 浮動小数点例外および FPU 環境のアクセスが無効になっています (**/fp: を除く-** が暗黙的に指定し、 [fenv_access](../../preprocessor/fenv-access.md)は OFF です)。

**/fp:fast**では使用できません **/fp: 厳密な**または **/fp: 正確な**します。 コマンド ラインに指定された最後のオプションが使用されます。 両方を指定する **/fp:fast**と **/fp: 除く**コンパイラ エラーが発生します。

指定する[/Za、/Ze (言語拡張を無効にする)](../../build/reference/za-ze-disable-language-extensions.md) (ANSI 互換性) と **/fp:fast**予期しない動作が発生する可能性があります。 たとえば、単精度の浮動小数点演算が単精度に丸められない場合があります。

#### <a name="except"></a>除く

**/Fp: 除く**オプションは、信頼性の高い浮動小数点例外モデルを使用できます。 例外は発生直後にスローされます。 このオプションの既定値はオフです。 オプションにマイナス記号を付ける (**/fp: 除く-**) 明示的に無効にします。

#### <a name="strict"></a>strict

**/Fp: 厳密な**オプションは、最も厳密な浮動小数点モデルを使用できます。 **/fp: 厳密な**により[fp_contract](../../preprocessor/fp-contract.md)を OFF および[fenv_access](../../preprocessor/fenv-access.md) ON にします。 **/fp: を除く**が暗黙的に指定して、明示的に指定することで無効にできます **/fp: 除く-** します。 使用すると **/fp: を除く-**、 **/fp: 厳密な**で厳密な浮動小数点セマンティクスを適用せず例外イベントは無視します。

## <a name="remarks"></a>Remarks

複数 **/fp**同じコンパイルでオプションを指定できます。

関数では、浮動小数点の動作を制御するを参照してください。、 [float_control](../../preprocessor/float-control.md)プラグマ。 これよりも優先、 **/fp**コンパイラ設定します。 優れたエンジニアリング手法として、ローカル浮動小数点の動作を保存して、元に戻すことをお勧めします。

```cpp
#pragma float_control(precise, on, push)
// Code that uses /fp:precise mode
#pragma float_control(pop)
```

ほとんどの浮動小数点の最適化に関連する **/fp: 厳密な**、 **/fp: を除く**(とそれに対応するプラグマ) と`fp_contract`プラグマはマシンに依存します。 **/fp: 厳密な**と **/fp: 除く**と互換性がない **/clr**します。

**/fp: 正確な**ほとんどのアプリケーションの浮動小数点要件に対処する必要があります。 使用することができます **/fp: を除く**と **/fp: 厳密な**パフォーマンスが低下があります。 パフォーマンスが最も重要な場合は、使用するかどうかを検討 **/fp:fast**します。

**/fp: 厳密な**、 **/fp:fast**、および **/fp: 正確な**モードは精密 (正確)。 一度に 1 つのモードだけを使用できます。 両方 **/fp: 厳密な**と **/fp: 正確な**は指定すると、コンパイラは最後に処理した 1 つを使用します。 両方 **/fp: 厳密な**と **/fp:fast**は指定できません。

詳細については、次を参照してください。 [Visual C++ 浮動小数点の最適化の Microsoft](floating-point-optimization.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 展開、**構成プロパティ** > **C/C++** > **コード生成**プロパティ ページ。

1. 変更、**浮動小数点モデル**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>

## <a name="see-also"></a>関連項目

- [コンパイラ オプション](compiler-options.md)
- [コンパイラ オプションの設定](setting-compiler-options.md)
- [Microsoft Visual C 浮動小数点の最適化](floating-point-optimization.md)