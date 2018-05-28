---
title: -fp (浮動小数点の動作の指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
dev_langs:
- C++
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 520a6e2d675c55e47a0424ab93c6a76d521f2358
ms.sourcegitcommit: 5e932a0e110e80bc241e5f69e3a1a7504bfab1f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2018
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (浮動小数点の動作の指定)

ソース コード ファイルの浮動小数点の動作を指定します。

## <a name="syntax"></a>構文

> **/fp:**[**正確な** | **を除く**[**-**] |**高速** | **strict**]

### <a name="arguments"></a>引数

#### <a name="precise"></a>正確です

既定値の **/fp**は **/fp: 正確な**します。

**/Fp: 正確な**フラグ浮動小数点演算の精度に影響する最適化を無効にすると等値演算子および非等値の浮動小数点テストの一貫性が向上します。 (ANSI 基準に厳密に従うには、特定の精度を保持する必要があります)。既定では、x86 用のコードに x87 を使用してコプロセッサ手順については、コンパイラは、コプロセッサのアーキテクチャの 80 ビット浮動小数点演算の中間結果を格納するレジスタ。 これにより、プログラムの実行速度が向上し、プログラムのサイズも小さくなります。 ただし、浮動小数点演算では、80 ビット未満のメモリで表される浮動小数点データ型も使用されるため、処理内容の多い演算では、このように余分な精度ビット、つまり、80 ビットと実際の浮動小数点データ型のビット数との差があると、演算結果の一貫性が失われることがあります。

**/Fp: 正確な**x86 で型の変数で丸め処理を実行して、プロセッサ コンパイラ`float`の割り当ておよびキャスト関数にパラメーターが渡されたときに正しい有効桁数にします。 この丸めにより、データが型の容量を大幅に上回らないようにします。 コンパイルされたプログラム **/fp: 正確な**なしでコンパイルされる 1 つを超えると低速にすることができます **/fp: 正確な**します。 **/fp: 正確な**ルーチンが代わりに使用される標準ランタイム ライブラリは組み込みを無効にします。 詳細については、「[/Oi (組み込み関数の生成)](../../build/reference/oi-generate-intrinsic-functions.md)」を参照してください。

次の浮動小数点の動作が有効な **/fp: 正確な**:

- 短縮操作、つまり、最後に 1 回だけ丸め処理を行う複合演算を使用して、複数の演算を置き換える操作。

- 特殊な値 (NaN、+infinity、-infinity、+0、-0) に対して無効な式の最適化は使用できません。 最適化の x、x > 0 = x * 0 > 0、x-0 を = = > x、x + 0 = > x、および 0 x = >-x はさまざまな理由で無効です。 (詳細については、IEEE 754 および C99 標準を参照してください)。

- コンパイラは、NaN が含まれている比較を適切に処理します。 たとえば、x! = x の結果に**true**場合`x`NaN は、順序付け比較を NaN に関連する例外が発生します。

- 式の評価は C99 FLT_EVAL_METHOD=2 に従いますが、1 つだけ例外があります。x86 プロセッサに対するプログラミングでは、FPU は 53 ビット精度に設定されるため、long double 精度と見なされます。

- 厳密な 1.0 での乗算では他の係数に変換されます。 x * y\*1.0 が x に変換される\*y です。 同様に、x\*1.0\*y が x に変換される\*y です。

- 厳密な 1.0 での除算では被除数が使用されます。 x * x に変換する y/1.0\*y です。 同様に、x/1.0\*y が x に変換される\*y です。

使用して **/fp: 正確な**とき[fenv_access](../../preprocessor/fenv-access.md)コンパイル時の浮動小数点式の評価などの最適化が無効にします。 たとえば、使用する[_control87、_controlfp、 \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)丸めモードと、コンパイラを変更するには、浮動小数点計算を行い、指定した、丸めモードが無効にしない限り、 `fenv_access`は ON です。

**/fp: 正確な**置き換えます、 **/Op**コンパイラ オプション。

#### <a name="fast"></a>高速します。

**/Fp:fast**オプションでは、ほとんどの場合、最も高速のコードを作成浮動小数点演算を最適化するための規則を緩和することです。 これにより、コンパイラは速度のために精度と正確性を犠牲にして、浮動小数点コードを最適化できます。 ときに **/fp:fast**指定すると、コンパイラが代入ステートメントで正しく丸められない可能性があります、丸めない、または関数呼び出し、および中間式の丸め処理を行うことはできます。 そして、有限の精度の結果に対する影響を考慮せずに、たとえば、結合規則および分配規則に従って、演算の順序を変更するか、代数変換を実行する可能性があります。 また、C++ の型の上位変換規則に従う代わりに、演算とオペランドを単精度に変更する場合があります。 浮動小数点に固有の省略形の最適化が常に有効になっている ([fp_contract](../../preprocessor/fp-contract.md)は ON です)。 浮動小数点例外と FPU 環境のアクセスが無効になっています (**/fp: を除く-** は暗黙的に指定および[fenv_access](../../preprocessor/fenv-access.md)は OFF です。)。

**/fp:fast**では使用できません **/fp: 厳密な**または **/fp: 正確な**します。 コマンド ラインに指定された最後のオプションが使用されます。 両方を指定する **/fp:fast**と **/fp: 除く**コンパイラ エラーが発生します。

指定する[/Za、/Ze (言語拡張を無効にする)](../../build/reference/za-ze-disable-language-extensions.md) (ANSI 互換性) と **/fp:fast**予期しない動作が発生する可能性があります。 たとえば、単精度の浮動小数点演算が単精度に丸められない場合があります。

#### <a name="except"></a>点を除いて

**/Fp: 除く**できます。 また、信頼性の高い浮動小数点例外モデル。 例外は発生直後にスローされます。 このオプションの既定値はオフです。 オプションにマイナス記号を付ける (**/fp: を除く-**) それを明示的に無効にします。

#### <a name="strict"></a>strict

**/Fp: 厳密な**できます。 また、最も厳密な浮動小数点モデルです。 **/fp: 厳密な**により[fp_contract](../../preprocessor/fp-contract.md)をオフにすると[fenv_access](../../preprocessor/fenv-access.md) ON であります。 **/fp: を除く**は暗黙的および明示的に指定することによって無効にすることができます **/fp: 除く-** です。 使用すると **/fp: を除く-**、 **/fp: 厳密な**で厳密な浮動小数点セマンティクスを適用せず例外イベントに関してです。

## <a name="remarks"></a>コメント

複数 **/fp**同じコンパイルでオプションを指定することができます。

関数では、浮動小数点の動作を制御するを参照してください。、 [float_control](../../preprocessor/float-control.md)プラグマ。 これよりも優先、 **/fp**コンパイラ設定します。 優れたエンジニアリング手法として、ローカル浮動小数点の動作を保存して、元に戻すことをお勧めします。

```cpp
#pragma float_control(precise, on, push)
// Code that uses /fp:precise mode
#pragma float_control(pop)
```

関連するほとんどの浮動小数点の最適化 **/fp: 厳密な**、 **/fp: を除く**(とその対応するプラグマ)、および`fp_contract`プラグマはマシンに依存します。 **/fp: 厳密な**と **/fp: を除く**と互換性がない **/clr**です。

**/fp: 正確な**アプリケーションの浮動小数点要件のほとんどに対応する必要があります。 使用することができます **/fp: を除く**と **/fp: 厳密な**パフォーマンスが低下がある可能性がありますが、します。 パフォーマンスが最も重要な場合は、使用するかどうかを検討 **/fp:fast**です。

**/fp: 厳密な**、 **/fp:fast**、および **/fp: 正確な**モードは精密 (正確)。 一度に 1 つのモードだけを使用できます。 両方 **/fp: 厳密な**と **/fp: 正確な**指定すると、コンパイラが最後に処理する 1 つを使用します。 両方 **/fp: 厳密な**と **/fp:fast**は指定できません。

詳細については、次を参照してください。 [Visual C++ 浮動小数点の最適化の Microsoft](floating-point-optimization.md)です。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 展開、**構成プロパティ** > **C/C++** > **コード生成**プロパティ ページ。

1. 変更、**浮動小数点モデル**プロパティです。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>」を参照してください。

## <a name="see-also"></a>関連項目

- [コンパイラ オプション](compiler-options.md)
- [コンパイラ オプションの設定](setting-compiler-options.md)
- [Microsoft Visual C のポイントの最適化を浮動小数点](floating-point-optimization.md)