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

> /std: [c++ 14 | c++ 17 | 最新の c++]

## <a name="remarks"></a>Remarks

**/Std**オプションは、Visual Studio 2017 で利用可能な以降。 プログラミング言語の標準的な機能が、コードのコンパイル時に有効になっているバージョンに固有の ISO C の制御に使用されます。 このオプションを使用すると、言語の特定のバージョンに準拠している既存のコードを標準的な中断新しい言語とライブラリ機能のサポートを無効にすることができます。 既定では、 **/std:c + + 14**が指定されている言語および標準 C++ 言語の以降のバージョンで見つかった標準ライブラリの機能を無効にします。 使用 **/std:c + + 17** c++ 17 標準固有機能と動作を有効にします。 最新のサポートされているコンパイラと標準ライブラリ機能を明示的に有効にするには使用 **/std:c + + 最新**します。

既定の **/std:c + + + 14**オプションは、C++ 14 機能 Visual C コンパイラによって実装されたのセットを使用できます。 このオプションは、コンパイラと標準ライブラリのサポートが変更された機能または新しい言語のいくつかの C++ 17 機能 Visual C コンパイラの以前のリリースで既に実装されてを除き、標準の最近のバージョンで無効にします。 Visual Studio 2015 Update 2 の時点で利用できる機能の依存関係を既に取得したユーザーの変更が壊れないように、これらの機能のまま有効になっているときに、 **/std:c + + 14**オプションを指定します。

- [囲まれた初期化リストを持つ auto の規則](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [テンプレートのテンプレート パラメーターの typename](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [トライグラフの削除](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [名前空間と列挙子の属性](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [u8 文字リテラル](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

追加情報をどの C++ 14 と c++ 17 機能では有効になっているときに **/std:c + + + 14**はでノートを参照して指定すると、 [Visual C 言語への準拠](../../visual-cpp-language-conformance.md)します。

**/Std:c + + 17**オプションは、C++ 17 機能 Visual C コンパイラによって実装の完全なセットを使用できます。 このオプションによって、C++17 後の C++ 標準のワーキング ドラフトおよび不具合の更新のバージョンで変更または更新された機能に対するコンパイラと標準ライブラリのサポートが無効になります。

**/Std:c + + 最新**オプションは、最も追跡するために Visual C によって実装される C++ 言語とライブラリの機能のセットを使用できます。 最新 c++ 20 ワーキング ドラフトおよび不具合の更新、C++ 標準の c++ 17 では含まれません。 このスイッチを使用して、取得、投稿のコンパイラと標準ライブラリでサポートされている c++ 17 の言語機能。 サポートされている言語とライブラリの機能の一覧は、次を参照してください。 [Visual c の新](../../what-s-new-for-visual-cpp-in-visual-studio.md)します。 **/Std:c + + 最新**オプションが守られている機能を有効にしない、 **]、[実験用**スイッチします。

**/Std** C++ のコンパイル時に有効なオプションを使用して検出できる、 [ \_MSVC\_LANG](../../preprocessor/predefined-macros.md)プリプロセッサ マクロ。 詳細については、次を参照してください。[プリプロセッサ マクロ](../../preprocessor/predefined-macros.md)します。

**/Std:c + + + 14**と **/std:c + + 最新**オプションは、使用可能な Visual C 2015 Update 3 以降。 **/Std:c + + 17**オプションは、Visual C 2017 バージョン 15.3 で以降を使用できます。 によって動作が有効な c++ 17 標準上に示した、 **/std:c + + + 14**オプションが他のすべての C++ 17 機能がで有効になって **/std:c + + 17**します。

> [!NOTE]
> Visual C のコンパイラ バージョンまたは更新プログラム レベルに応じて特定の C++ 14 または c++ 17 機能は完全に実装できませんまたは完全に準拠するを指定すると、 **/std:c + + 14**または **/std:c + + 17**オプション。 など、Visual C 2017 RTM コンパイラで c++ 14 の準拠が完全にサポートされていない`constexpr`、式 SFINAE、または 2 段階名前検索します。 Visual C のリリース バージョンでの C++ 言語準拠の概要については、次を参照してください。 [Visual c 言語への準拠](../../visual-cpp-language-conformance.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択**構成プロパティ**、 **C/C++**、**言語**します。

1. **C 言語標準**を選択し、ボックスの一覧から、サポート言語標準を選択**OK**または**適用**変更を保存します。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
