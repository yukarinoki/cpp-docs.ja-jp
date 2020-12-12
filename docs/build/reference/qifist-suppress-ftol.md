---
description: 詳細情報:/QIfist (非表示 _ftol)
title: /QIfist (_ftol を呼び出さない)
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: 79e9242d66b532f558307d05b222b2fd8cfd43ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225649"
---
# <a name="qifist-suppress-_ftol"></a>/QIfist (_ftol を呼び出さない)

非推奨になりました。 浮動小数点型から整数型への変換が必要なときには、ヘルパー関数 `_ftol` を呼び出しません。

## <a name="syntax"></a>構文

```
/QIfist
```

## <a name="remarks"></a>解説

> [!NOTE]
> **/QIfist** は、x86 を対象とするコンパイラでのみ使用できます。このコンパイラオプションは、x64 orARM を対象とするコンパイラでは使用できません。

`_ftol` 関数では、浮動小数点型から整数型への変換に加えて、浮動小数点制御ワードのビット 10 と 11 を設定して、FPU (Floating-Point Unit) の丸めモードをゼロ (切り捨て) にします。 したがって、浮動小数点型から整数型への変換は、ANSI C 規格どおりに行われ、小数部分を破棄することが保証されます。 **/QIfist** を使用する場合、この保証は適用されなくなります。 丸めモードは、Intel 社のリファレンス マニュアルに示されたとおり、次の 4 とおりのうちのいずれかになります。

- 一番近い値に丸める (中間の場合は偶数)。

- 負の無限大に丸める。

- 正の無限大に丸める。

- ゼロに丸める。

[_Control87、_controlfp、 \_ _control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C Run-Time 関数を使用すると、FPU の丸め動作を変更できます。 FPU の既定の丸めモードでは、一番近い値に丸められます。 **/QIfist** を使用すると、アプリケーションのパフォーマンスを向上させることができますが、リスクはありません。 運用環境で **/QIfist** を使用して構築されたコードに依存する前に、丸めモードに敏感なコード部分を十分にテストする必要があります。

[/arch (x86)](arch-x86.md) と **/QIfist** は、同じコンパイル単位では使用できません。

> [!NOTE]
> **/QIfist** は既定では有効になっていません。丸め処理のビットは浮動小数点から浮動小数点値への丸め処理 (すべての計算の後に発生します) にも影響するため、C スタイル (0 方向) の丸めのフラグを設定すると、浮動小数点の計算が異なる場合があります。 **/QIfist** は、浮動小数点数の小数部分を切り捨てることが予想される動作にコードが依存している場合は使用しないでください。 わからない場合は、 **/QIfist** を使用しないでください。

**/QIfist** オプションは、Visual Studio 2005 以降では非推奨とされます。 浮動小数点型から整数型への変換処理の速度が飛躍的に向上しました。 非推奨のコンパイラオプションの一覧については、「[カテゴリ別に一覧表示さ](compiler-options-listed-by-category.md)れたコンパイラオプションの **非推奨のコンパイラオプション**」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/Q オプション (低レベルの操作)](q-options-low-level-operations.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
