---
title: /Zc:wchar_t (wchar_t をネイティブ型として認識)
ms.date: 03/01/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
ms.openlocfilehash: 114ed4a279b66571c0dc81fc1139dcdc59c17eae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234316"
---
# <a name="zcwchar_t-wchar_t-is-native-type"></a>/Zc:wchar_t (wchar_t をネイティブ型として認識)

**`wchar_t`** C++ 標準に従って、組み込み型として解析します。

## <a name="syntax"></a>構文

> **/Zc: wchar_t**[ **-** ]

## <a name="remarks"></a>解説

**/Zc: wchar_t**が on の場合、 **`wchar_t`** は C++ としてコンパイルされたコード内の組み込みの整数型のキーワードです。 **/Zc: wchar_t-** (マイナス記号付き) が指定されている場合、または C としてコンパイルされたコードの場合、 **`wchar_t`** は組み込み型ではありません。 代わりに、 **`wchar_t`** は、 **`typedef`** 正規ヘッダー stddef.h ののとして定義されます **`unsigned short`** 。 (Microsoft の実装では、stddef.h およびその他の標準ヘッダーに含まれる別のヘッダーでそれを定義しています)。

**/Zc: wchar_t を**お勧めしません。 C++ 標準では、が組み込み型である必要があるためです **`wchar_t`** 。 バージョンを使用する **`typedef`** と、移植性の問題が発生する可能性があります。 以前のバージョンの Visual Studio からアップグレードするときに、コードがをに暗黙的に変換しようとしているためにコンパイラエラー [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md)が発生した場合は、 **`wchar_t`** **`unsigned short`** **/zc: wchar_t-** を設定するのではなく、コードを変更してエラーを修正することをお勧めします。

**/Zc: wchar_t**オプションは、C++ コンパイルでは既定でオンになっており、C コンパイルでは無視されます。 [/Permissive-](permissive-standards-conformance.md)オプションは、 **/zc: wchar_t**には影響しません。

Microsoft **`wchar_t`** では、2バイトの符号なしの値としてを実装します。 これは、Microsoft 固有のネイティブ型にマップさ **`__wchar_t`** れます。 の詳細について **`wchar_t`** は、「[データ型の範囲](../../cpp/data-type-ranges.md)」と「[基本型](../../cpp/fundamental-types-cpp.md)」を参照してください。

以前のバージョンのを使用している古いコードと相互運用する必要がある新しいコードを記述する場合は、 **`typedef`** **`wchar_t`** **`unsigned short`** **`__wchar_t`** **`wchar_t`** **/zc: wchar_t**でコンパイルしたコードまたはそれを使用せずにコンパイルされたコードとコードをリンクできるように、とのバリエーションの両方にオーバーロードを指定できます。 それ以外の場合は、ライブラリの2つの異なるビルドを提供する必要があります。1つはで、もう1つは **/zc: wchar_t**が有効になっていません。 この場合も、以前のコードのビルドには、新しいコードをコンパイルするときに使用するコンパイラを使用することをお勧めします。 さまざまなコンパイラでコンパイルされたバイナリを混在させないでください。

**/Zc: wchar_t**が指定されている場合、 ** \_ wchar の \_ \_ 定義**されたシンボルと** \_ ネイティブ \_ wchar の \_ \_ 定義**済みのシンボルが定義されます。 詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。

**/Zc: wchar_t**が既定でオンになっているため、コードでコンパイラ COM グローバル関数を使用する場合は、明示的な参照を (comment プラグマまたはコマンドラインで) 明示的に参照することをお勧めします ([コメントプラグマ](../../preprocessor/comment-c-cpp.md)またはコマンドラインから)。 ( **/Zc: wchar_t**を使用してコンパイルする必要がある場合は、comsupp .lib を使用します)。Comdef .h ヘッダーファイルをインクルードする場合は、適切なライブラリが指定されています。 コンパイラの COM サポートの詳細については、「[コンパイラの Com サポート](../../cpp/compiler-com-support.md)」を参照してください。

**`wchar_t`** 組み込み型は、C コードをコンパイルするときにはサポートされません。 Visual C++ の準拠に関する問題の詳細については、「[非標準動作](../../cpp/nonstandard-behavior.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **言語**] ページを選択します。

1. "**組み込み型として wchar_t を扱う**" プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)<br/>
