---
title: -std (言語標準バージョンの指定) |Microsoft Docs
ms.custom: ''
ms.date: 11/16/2017
ms.topic: reference
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
dev_langs:
- C++
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32bbcd47c4ce22882941b6fa9c02373bab32eeb1
ms.sourcegitcommit: 938d118d02543c822a5f58c84d6119d23339e43c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2018
ms.locfileid: "50135995"
---
# <a name="std-specify-language-standard-version"></a>/std (言語標準バージョンの指定)

有効にするには、標準の C++ 言語の指定したバージョンの C++ 言語の機能がサポートされています。

## <a name="syntax"></a>構文

> /std: [c++ 14 | c++ 17 | c++ latent]

## <a name="remarks"></a>Remarks

**/Std**オプションは、Visual Studio 2017 以降で利用可能です。 コードのコンパイル時に使用するISO C++ プログラミング言語 のバージョンの指定に使用されます。 このオプションを使用すると、言語の特定のバージョンの標準に準拠している既存のコードを壊すかもしれない言語とライブラリの新しい機能を無効にすることができます。既定では **/std:c + + 14**が指定され、標準 C++ 言語 以降のバージョンで見つかった言語と標準ライブラリの機能を無効にします。
 **/std:c + + 17** の使用では、c++ 17 標準の固有機能と動作を有効にします。 最新のコンパイラと標準ライブラリ機能の使用を明示的に有効にするには **/std:c + + latent**を使用します。

既定の **/std:c + + + 14**オプションは、Visual C++ コンパイラに実装された C++ 14 の機能を使用できます。 このオプションは、より新しい言語規格のコンパイラと標準ライブラリで変更、追加された機能を無効にします。ただし例外として、Visual C++ コンパイラの以前のリリースで既に実装されている C++ 17 の機能は無効にしません。Visual Studio 2015 Update 2 の時点で利用できる機能に既に依存しているユーザーの 破壊的変更を避けるために、 **/std:c + + 14**オプションを指定されているなら、これらの機能を有効にします。

- [囲まれた初期化リストを持つ auto の規則](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [テンプレートのテンプレート パラメーターの typename](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [トライグラフの削除](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [名前空間と列挙子の属性](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [u8 文字リテラル](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

**/std:c + + + 14**オプションを指定した場合に有効な C++ 14 と C++ 17 の機能についてはノートを参照してください。 [Visual C 言語への準拠](../../visual-cpp-language-conformance.md)

**/Std:c + + 17**オプションを指定した場合、Visual C++ コンパイラに実装されたすべての C++ 17 の機能を使用できます。 このオプションによって、C++17 より後のバージョンの C++ 標準のワーキング ドラフトおよび不具合の更新で変更または更新されたコンパイラと標準ライブラリの機能が無効になります。

**/Std:c + + latent**オプションは、 Visual C++ に実装された C++ 言語とライブラリの最新機能を使用できます。 c++ 17 には含まれてない、C++ 標準の最新 c++ 20 ワーキング ドラフトの追跡および不具合の更新が含まれます 。このオプションの使用で、コンパイラと標準ライブラリでサポートされている後期 c++ 17 の言語機能が使用できます。 サポートされている言語とライブラリの機能の一覧は、次を参照してください。 [Visual c の新](../../what-s-new-for-visual-cpp-in-visual-studio.md)します。 **/experimental** オプションによって保護された機能は **/Std:c + + latent** で有効にはなりません。

C++ のコンパイル時に影響する **/Std** オプションは [ \_MSVC\_LANG](../../preprocessor/predefined-macros.md)プリプロセッサ マクロを使用することで検出できます。 詳細については、[プリプロセッサ マクロ](../../preprocessor/predefined-macros.md)を参照してください。

**/Std:c + + + 14** と **/std:c + + latent ** オプションは、Visual C++ 2015 Update 3 以降で使用可能です。 **/Std:c + + 17** オプションは、Visual C++ 2017 バージョン 15.3 以降で使用できます。 上述したようにいくつかのC++17の標準的な機能は **/std:c + + + 14** オプションで使用可能ですが、 **/std:c + + 17** オプションでその他のすべてのC++17の機能が使用可能になります。

> [!NOTE]
> Visual C++ のコンパイラのバージョンまたは更新が不十分な場合は、 **/std:c + + 14** または **/std:c + + 17** オプションを指定すると、C++ 14 または c++ 17 の特定の機能は完全な実装や準拠したものではないかもしれません。 例えば、Visual C++ 2017 RTM コンパイラは `constexpr`、SFINAE 式、2-phase name lookupについて、c++ 14 の準拠が不完全です。 Visual C++ のリリース バージョンでの C++ 言語準拠の概要については、[Visual c 言語への準拠](../../visual-cpp-language-conformance.md)を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択 **構成プロパティ**、 **C/C++**、 **言語** を選択します。

1. **C++ 言語標準**を選択し、ボックスの一覧から、サポート言語標準 **/std:c++ 14 | c++ 17 | c++ latent** を選択 **OK** または **適用** 変更を保存します。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
