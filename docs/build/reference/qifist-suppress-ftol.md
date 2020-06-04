---
title: /QIfist (_ftol を呼び出さない)
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: 5d6e12a1003ea125b0da4bfef580d8096e97553a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336098"
---
# <a name="qifist-suppress-_ftol"></a>/QIfist (_ftol を呼び出さない)

非推奨になりました。 浮動小数点型から整数型への変換が必要なときには、ヘルパー関数 `_ftol` を呼び出しません。

## <a name="syntax"></a>構文

```
/QIfist
```

## <a name="remarks"></a>解説

> [!NOTE]
> **/QIfist**は x86 を対象とするコンパイラでのみ使用できます。このコンパイラ オプションは、x64 または ARM を対象とするコンパイラでは使用できません。

`_ftol` 関数では、浮動小数点型から整数型への変換に加えて、浮動小数点制御ワードのビット 10 と 11 を設定して、FPU (Floating-Point Unit) の丸めモードをゼロ (切り捨て) にします。 したがって、浮動小数点型から整数型への変換は、ANSI C 規格どおりに行われ、小数部分を破棄することが保証されます。 **/QIfist**を使用する場合、この保証は適用されなくなります。 丸めモードは、Intel 社のリファレンス マニュアルに示されたとおり、次の 4 とおりのうちのいずれかになります。

- 一番近い値に丸める (中間の場合は偶数)。

- 負の無限大に丸める。

- 正の無限大に丸める。

- ゼロに丸める。

[_control87、_controlfp、_control87_2 \_](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C ランタイム関数を使用して、FPU の丸め動作を変更できます。 FPU の既定の丸めモードでは、一番近い値に丸められます。 **/QIfist**を使用すると、アプリケーションのパフォーマンスを向上させることができますが、リスクがないわけではありません。 実稼働環境で **/QIfist**でビルドされたコードに依存する前に、丸めモードに敏感な部分を十分にテストする必要があります。

[/arch (x86)](arch-x86.md)と **/QIfist**は同じコンパイルで使用できません。

> [!NOTE]
> **/QIfist**は、丸めビットが浮動小数点から浮動小数点への丸め (計算のたびに発生する) にも影響するため、既定では有効ではありません。 **/QIfist**は、浮動小数点数の小数部分を切り捨てる動作にコードが依存している場合は使用しないでください。 不明な場合は **、/QIfist**を使用しないでください。

**/QIfist**オプションは、Visual Studio 2005 以降では使用されなくなりました。 浮動小数点型から整数型への変換処理の速度が飛躍的に向上しました。 非推奨のコンパイラ オプションの一覧については、「[カテゴリ別に一覧表示されるコンパイラ オプション](compiler-options-listed-by-category.md)」の「**廃止されたコンパイラ オプションと削除された**コンパイラ オプション」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション] **** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/Q オプション (低水準の操作)](q-options-low-level-operations.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
