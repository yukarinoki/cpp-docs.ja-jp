---
title: -Qifist (_ftol を呼び出さない) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /qifist
dev_langs:
- C++
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77ec65e330cebb1de718330ba129e960383b31c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378406"
---
# <a name="qifist-suppress-ftol"></a>/QIfist (_ftol を呼び出さない)
非推奨。 浮動小数点型から整数型への変換が必要なときには、ヘルパー関数 `_ftol` を呼び出しません。  
  
## <a name="syntax"></a>構文  
  
```  
/QIfist  
```  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  **/Qifist**はでのみ使用 x86 を対象とするコンパイラは、このコンパイラ オプションは、コンパイラで使用可能な[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]orARM です。  
  
 `_ftol` 関数では、浮動小数点型から整数型への変換に加えて、浮動小数点制御ワードのビット 10 と 11 を設定して、FPU (Floating-Point Unit) の丸めモードをゼロ (切り捨て) にします。 したがって、浮動小数点型から整数型への変換は、ANSI C 規格どおりに行われ、小数部分を破棄することが保証されます。 使用する場合 **/QIfist**、この保証が適用されません。 丸めモードは、Intel 社のリファレンス マニュアルに示されたとおり、次の 4 とおりのうちのいずれかになります。  
  
-   一番近い値に丸める (中間の場合は偶数)。  
  
-   負の無限大に丸める。  
  
-   正の無限大に丸める。  
  
-   ゼロに丸める。  
  
 使用することができます、 [_control87、_controlfp、 \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C ランタイム関数を FPU の丸め動作を変更します。 FPU の既定の丸めモードでは、一番近い値に丸められます。 使用して **/QIfist**リスクが伴いますが、アプリケーションのパフォーマンスを向上させることができます。 ビルドされたコードを使用する前に、丸めモードと小文字を区別する、コードの部分を十分にテストする必要があります **/QIfist**実稼働環境でします。  
  
 [/arch (x86)](../../build/reference/arch-x86.md)と **/QIfist**同じコンパイル単位では使用できません。  
  
> [!NOTE]
>  **/Qifist**が有効で既定では丸めビット浮動小数点の浮動小数点への影響にもあるために指していません丸め処理を行う (これが発生するすべての計算後) ため、C スタイル (0) の方向に丸め処理を行うためのフラグを設定するときに、浮動小数点計算が異なる可能性があります。 **/Qifist**は、浮動小数点数の小数部の切り捨てについて予想される動作時に、コードが依存している場合、使用できません。 不明な場合は使用しないで **/QIfist**です。  
  
 **/QIfist**オプションには、Visual Studio 2005 以降では推奨されません。 浮動小数点型から整数型への変換処理の速度が飛躍的に向上しました。 非推奨のコンパイラ オプションの一覧は、次を参照してください。**廃止予定とコンパイラ オプションの削除**で[コンパイラ オプションの一覧をカテゴリ別](../../build/reference/compiler-options-listed-by-category.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)