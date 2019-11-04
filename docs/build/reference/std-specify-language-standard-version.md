---
title: /std (言語の標準バージョンの指定)
ms.date: 05/16/2019
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: 9bdeb92e03b3ae00258ac48a29cec42ef7e18e81
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68241214"
---
# <a name="std-specify-language-standard-version"></a>/std (言語の標準バージョンの指定)

指定したバージョンの C++ 言語標準でサポートされる C++ 言語機能を有効にします。

## <a name="syntax"></a>構文

> /std:\[c++14\|c++17\|c++latest]

## <a name="remarks"></a>Remarks

**/std**オプションは、Visual Studio 2017 以降で利用可能です。 コードのコンパイル時に使用するISO C++ プログラミング言語 のバージョンの指定に使用されます。 このオプションを使用すると、言語の特定のバージョンの標準に準拠している既存のコードを壊すかもしれない言語とライブラリの新しい機能を無効にすることができます。 既定では **/std:c++14**が指定され、標準 C++ 言語 以降のバージョンで見つかった言語と標準ライブラリの機能を無効にします。 **/std:c++17** の使用では、c++ 17 標準の固有機能と動作を有効にします。 次の標準の草案で提案されている、現在導入されているコンパイラおよび標準のライブラリ機能を明示的に有効にするには、 **/std:c++latest** を使用します。 すべて c++ 20 機能が必要です **/std:c++latest**; 実装が完了したら、新しい **/std:c++20**オプションが有効になります。

既定の **/std:c++14** オプションを使用すると、MSVC コンパイラで実装される C++14 の一連の機能が有効になります。 このオプションでは、言語標準のより新しいバージョンで変更になるコンパイラおよび標準ライブラリの機能、または新機能のサポートが無効になります。ただし、MSVC コンパイラの以前のリリースで既に実装済みの C++17 の一部の機能は除きます。 Visual Studio 2015 Update 2 時点の機能の依存関係を既に使用しているユーザーが **/std:c++14** オプションを指定すると、以下の機能を有効のままにして、破壊的な変更を避けることができます。

- [かっこ付き初期化リストがある auto の規則](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [テンプレートのテンプレート パラメーターの typename](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [トライグラフの削除](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [名前空間と列挙子の属性](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [u8 文字リテラル](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

**/std:c++14**オプションを指定した場合に有効な C++ 14 と C++ 17 の機能についてはノートを参照してください。 [Visual C 言語への準拠](../../overview/visual-cpp-language-conformance.md)

**/std:c++17** オプションを使用すると、MSVC コンパイラで実装された C++17 のすべての機能が有効になります。 このオプションによって、C++17 より後のバージョンの C++ 標準のワーキング ドラフトおよび不具合の更新で変更または更新されたコンパイラと標準ライブラリの機能が無効になります。

**/std:c++latest** オプションでは、現在コンパイラおよびライブラリに実装されている C++17 以降の言語およびライブラリ機能が有効になります。 これらには、C++17 には含まれない C++20 の作業草案、C++ 標準の不具合の更新、ドラフト標準の実験的提案も含まれる場合があります。 サポートされている言語とライブラリの機能の一覧は、[Visual c の新](../../overview/what-s-new-for-visual-cpp-in-visual-studio.md)を参照してください。 **/std:c++latest** オプションでは、 **/experimental** スイッチでカードされている機能は有効にはなりませんが、それらを有効にする必要がある場合があります。

> [!IMPORTANT]
> **/std:c++latest** で有効になるコンパイラおよびライブラリ機能は、今後の C++ 標準および承認済みの C++20 の機能になる場合があります。 承認されていない機能では、破壊的変更や通知なしでの削除が起こる可能性があり、これは無保証で提供されています。 

C++ のコンパイル時に有効な **/std** オプションは、[\_MSVC\_LANG](../../preprocessor/predefined-macros.md) プリプロセッサ マクロを使用して検出できます。 詳細については、[プリプロセッサ マクロ](../../preprocessor/predefined-macros.md)に関するページを参照してください。

**/std:c++14** オプションおよび **/std:c++latest** オプションは、Visual Studio 2015 Update 3 から利用できます。 **/std:c++17** オプションは、Visual Studio 2017 バージョン 15.3 から利用できます。 前述のとおり、C++17 標準の一部の動作は **/std:c++14** オプションで有効にできますが、その他の C++17 のすべての機能は **/std:c++17** で有効になります。 C++20 の機能は、実装が完了するまで、 **/std:latest** で有効になります。

> [!NOTE]
> MSVC コンパイラのバージョンや更新プログラムのレベルに応じて、 **/std:c++17** のオプションを指定しても、C++17 の機能が完全に実装されなかったり、完全に準拠されない場合があります。 Visual C++ のリリース バージョンごとの C++ 言語への準拠の概要については、「[Visual C++ 言語の準拠](../../overview/visual-cpp-language-conformance.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. 選択 **構成プロパティ**、 **C/C++** 、 **言語** を選択します。

1. **C++ 言語標準**を選択し、ボックスの一覧から、サポート言語標準 **/std:c++14 | c++17 | c++latent** を選択 **OK** または **適用** 変更を保存します。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
