---
title: /std (言語標準バージョンの指定)
ms.date: 11/26/2018
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: 03f7e095dc8b09b743d42cd6df0aaeb1a1dd3f02
ms.sourcegitcommit: e9568560cdb95e83a8fba1e9bca21ece910d20b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "52453912"
---
# <a name="std-specify-language-standard-version"></a>/std (言語標準バージョンの指定)

有効にするには、標準の C++ 言語の指定したバージョンの C++ 言語の機能がサポートされています。

## <a name="syntax"></a>構文

> /std:\[c++ 14\|c++ 17\|最新の c++]

## <a name="remarks"></a>Remarks

**/Std**オプションは、Visual Studio 2017 以降で利用可能です。 コードのコンパイル時に使用するISO C++ プログラミング言語 のバージョンの指定に使用されます。 このオプションを使用すると、言語の特定のバージョンの標準に準拠している既存のコードを壊すかもしれない言語とライブラリの新しい機能を無効にすることができます。 既定では **/std:c + + 14**が指定され、標準 C++ 言語 以降のバージョンで見つかった言語と標準ライブラリの機能を無効にします。 **/std:c + + 17** の使用では、c++ 17 標準の固有機能と動作を有効にします。 現在実装されているコンパイラと標準ライブラリの機能が、[次へ] のドラフト標準に向けた提案を明示的に有効にするには使用 **/std:c + + 最新**します。

最新のコンパイラと標準ライブラリ機能の使用を明示的に有効にするには **/std:c + + latent**を使用します。 このオプションは、コンパイラと標準ライブラリのサポートが変更された機能または新しい言語のいくつかの C++ 17 機能 Visual C コンパイラの以前のリリースで既に実装されてを除き、標準の最近のバージョンで無効にします。 Visual Studio 2015 Update 2 の時点で利用できる機能の依存関係を既に取得したユーザーの変更が壊れないように、これらの機能のまま有効になっているときに、 **/std:c + + 14**オプションを指定します。

- [囲まれた初期化リストを持つ auto の規則](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [テンプレートのテンプレート パラメーターの typename](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [トライグラフの削除](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [名前空間と列挙子の属性](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [u8 文字リテラル](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

**/std:c + + + 14**オプションを指定した場合に有効な C++ 14 と C++ 17 の機能についてはノートを参照してください。 [Visual C 言語への準拠](../../visual-cpp-language-conformance.md)

**/Std:c + + 17**オプションを指定した場合、Visual C++ コンパイラに実装されたすべての C++ 17 の機能を使用できます。 このオプションによって、C++17 より後のバージョンの C++ 標準のワーキング ドラフトおよび不具合の更新で変更または更新されたコンパイラと標準ライブラリの機能が無効になります。

**/Std:c + + 最新**オプションは、post を使用できます。-c++ 17 コンパイラとライブラリで現在実装されている言語とライブラリの機能です。 C++ 20 ワーキング ドラフトおよび不具合の更新から C++ 標準の c++ 17 とドラフト標準の実験用の提案に含まれていない機能が含まれます。 サポートされている言語とライブラリの機能の一覧は、次を参照してください。 [Visual c の新](../../what-s-new-for-visual-cpp-in-visual-studio.md)します。 **/Std:c + + 最新**オプションが守られている機能を有効にしない、 **]、[実験用**スイッチしますが、有効にする必要があります。

> [!IMPORTANT]
> 有効になっているコンパイラとライブラリの機能 **/std:c + + 最新**として提供されます-をサポートしていないとします。 これらが重大な変更や削除の通知もなし適用されます。 として、標準の次のバージョンで表示される言語機能のプレビューのものが、標準は進行中の作業です。 使用して、 **/std:c + + 17**最新の ISO C 標準で機能を使用します。

C++ のコンパイル時に影響する **/Std** オプションは [\_MSVC\_LANG](../../preprocessor/predefined-macros.md)プリプロセッサ マクロを使用することで検出できます。 詳細については、[プリプロセッサ マクロ](../../preprocessor/predefined-macros.md)を参照してください。

**/Std:c + + + 14** と **/std:c + + latent**  オプションは、Visual C++ 2015 Update 3 以降で使用可能です。 **/Std:c + + 17** オプションは、Visual C++ 2017 バージョン 15.3 以降で使用できます。 上述したようにいくつかのC++17の標準的な機能は **/std:c + + + 14** オプションで使用可能ですが、 **/std:c + + 17** オプションでその他のすべてのC++17の機能が使用可能になります。

> [!NOTE]
> Visual C++ のコンパイラのバージョンまたは更新が不十分な場合は、 **/std:c + + 14** または **/std:c + + 17** オプションを指定すると、C++ 14 または c++ 17 の特定の機能は完全な実装や準拠したものではないかもしれません。 例えば、Visual C++ 2017 RTM コンパイラは `constexpr`、SFINAE 式、2-phase name lookupについて、c++ 14 の準拠が不完全です。 Visual C++ のリリース バージョンでの C++ 言語準拠の概要については、[Visual c 言語への準拠](../../visual-cpp-language-conformance.md)を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択 **構成プロパティ**、 **C/C++**、 **言語** を選択します。

1. **C++ 言語標準**を選択し、ボックスの一覧から、サポート言語標準 **/std:c++ 14 | c++ 17 | c++ latent** を選択 **OK** または **適用** 変更を保存します。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
