---
title: -std (言語の標準的なバージョンの指定) |Microsoft ドキュメント
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
ms.openlocfilehash: 7fed80f0f9763b7e988c40a9d9f38f4e0f18eeb1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378848"
---
# <a name="std-specify-language-standard-version"></a>/std (言語の標準的なバージョンの指定)

有効にするには、指定されたバージョン C++ 言語の標準の C++ 言語の機能がサポートされています。

## <a name="syntax"></a>構文

> /std: [c++ 14 | c++ 17 | 最新の c++]

## <a name="remarks"></a>コメント

**/Std**プログラミング言語の標準的な機能、コードのコンパイル時に有効になっているバージョンに固有の ISO C を制御するオプションを使用します。 このオプションでは、新しい言語とライブラリの機能の一部の言語の特定のバージョンに準拠している既存のコードを標準的な中断をサポートを無効にすることができます。 既定では、 **/std:c + + 14**が指定されている言語および標準 C++ 言語の以降のバージョンで見つかった標準ライブラリの機能を無効にします。 使用して **/std:c + + 17** c++ 17 標準に固有の機能と動作を有効にします。 サポートされている最新バージョンのコンパイラおよび標準ライブラリの機能を明示的に有効にするには使用 **/std:c + + 最新**です。

既定値 **/std:c + + 14**できます。 また、一連の c++ 14 機能 Visual c コンパイラによって実装されます。 このオプションは、コンパイラおよび標準ライブラリのサポートの変更された機能または新しい一部 c++ 17 の機能、Visual C コンパイラの以前のリリースで既に実装されてを除き、標準の言語のより新しいバージョンでは無効にします。 最新の Visual Studio 2015 Update 2 の時点で利用できる機能の依存関係はすでに実行しているユーザーの変更を避けるため、これらの機能のまま有効になっているときに、 **/std:c + + 14**オプションを指定します。

- [かっこ付き初期化リストを持つ auto の規則](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [テンプレートのテンプレート パラメーターの typename](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [トライグラフの削除](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [名前空間と列挙子の属性](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [u8 文字リテラル](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

追加情報をどの c++ 14、c++ 17 機能では有効になっているときに **/std:c + + 14**はでノートを参照して指定すると、 [Visual の C++ 言語準拠](../../visual-cpp-language-conformance.md)です。
  
**/Std:c + + 17** c++ 17 機能 Visual C コンパイラによって実装の完全なセットを有効にします。 このオプションによって、C++17 後の C++ 標準のワーキング ドラフトおよび不具合の更新のバージョンで変更または更新された機能に対するコンパイラと標準ライブラリのサポートが無効になります。  
  
**/Std:c + + 最新**オプションを使用する、C++ の言語とライブラリ機能を最大限に追跡するために Visual C によって実装される最新 c++ 20 下書きの作業と欠陥の更新、C++ 標準の c++ 17 で含まれていません。 このスイッチを使用して、通知の取得のコンパイラおよび標準ライブラリでサポートされている c++ 17 言語機能。 サポートされている言語とライブラリの機能の一覧は、次を参照してください。 [Visual c の新](../../what-s-new-for-visual-cpp-in-visual-studio.md)です。 **/Std:c + + 最新**オプションが守られている機能を有効にしない、**実験/** スイッチします。  
  
**/Std** C++ のコンパイル時に有効でオプションを使用して検出できる、 [ \_MSVC\_LANG](../../preprocessor/predefined-macros.md)プリプロセッサ マクロです。 詳細については、次を参照してください。[プリプロセッサ マクロ](../../preprocessor/predefined-macros.md)です。

**/Std:c + + 14**と **/std:c + + 最新**オプションは、Visual C++ 2015 Update 3 以降を使用できます。 **/Std:c + + 17**オプションは、以降 Visual C++ 2017 15.3 のバージョンで使用できます。 動作が有効になっている前述のような c++ 17 規格、 **/std:c + + 14**オプションが他のすべての c++ 17 機能が有効にされます **/std:c + + 17**です。
  
> [!NOTE]
> Visual C コンパイラのバージョンまたは更新プログラム レベルに応じて、特定 c++ 14 または c++ 17 の機能は完全に実装されない、または完全に準拠するを指定すると、 **/std:c + + 14**または **/std:c + + 17**オプション。 たとえば、Visual C 2017 RTM コンパイラ部分的にサポート c++ 14 準拠`constexpr`、式 SFINAE、または 2 段階名前検索します。 Visual C のリリース バージョンでの C++ 言語準拠の概要については、次を参照してください。 [Visual の C++ 言語準拠](../../visual-cpp-language-conformance.md)です。 
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択**構成プロパティ**、 **C/C++**、**言語**します。  
  
3.  **C++ 言語標準**を選択し、ドロップダウン リスト コントロールから、サポートする言語標準を選ぶ**OK**または**適用**変更を保存します。  
  
## <a name="see-also"></a>関連項目  
  
[コンパイラ オプション](../../build/reference/compiler-options.md)   
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
