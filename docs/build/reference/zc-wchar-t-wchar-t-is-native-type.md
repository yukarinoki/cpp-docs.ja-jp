---
title: /Zc:wchar_t (wchar_t をネイティブ型) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/01/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 061aa4a70412a0b51450470e690bea5633b764ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381285"
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t をネイティブ型として認識)

`wchar_t` を、C++ 標準に従って組み込み型として解析します。

## <a name="syntax"></a>構文

> **/Zc:wchar_t**[**-**]

## <a name="remarks"></a>コメント

場合 **/Zc:wchar_t**が有効になって`wchar_t`は C++ としてコンパイルされたコードで組み込みの整数型のキーワードです。 場合 **/Zc:wchar_t-** (マイナス記号) で指定された、またはコードを C としてコンパイルされた、`wchar_t`組み込み型ではありません。 代わりに、`wchar_t`として定義されて、`typedef`の`unsigned short`標準ヘッダー stddef.h でします。 (Microsoft による実装を定義、stddef.h に含まれている別のヘッダーとその他の標準ヘッダーでします。)

お勧めしません **/Zc:wchar_t-** C++ 標準を必要とするため`wchar_t`組み込み型を指定します。 `typedef` バージョンを使用すると、移植性の問題が発生することがあります。 Visual C の以前のバージョンからアップグレードし、コンパイラ エラーが発生したかどうかは[C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) 、コードが暗黙的に変換しようとしているため、`wchar_t`に`unsigned short`、代わりに、エラーを修正するコードを変更することをお勧めします。設定の **/Zc:wchar_t-** です。

**/Zc:wchar_t**オプションは C++ のコンパイルで既定でオンおよび C のコンパイルでは無視されます。 [寛容/-](permissive-standards-conformance.md)オプションには影響しません **/Zc:wchar_t**です。

Microsoft では、`wchar_t` が 2 バイトの符号なしの値として実装されます。 Microsoft 固有のネイティブ型にマップ`__wchar_t`です。 詳細については`wchar_t`を参照してください[データ型の範囲](../../cpp/data-type-ranges.md)と[基本的な型](../../cpp/fundamental-types-cpp.md)です。

現在も使用して以前のコードと相互運用する必要のある新しいコードを記述する場合、`typedef`バージョンの`wchar_t`、両方のオーバー ロードを提供することができます、`unsigned short`と`__wchar_t`のバリエーション`wchar_t`と、コードをリンクできるように、コードでコンパイルされた **/Zc:wchar_t**またはなしでコンパイルされたコード。 それ以外の場合となしのライブラリの 2 つの異なるビルドを提供する必要がある **/Zc:wchar_t**有効にします。 この場合も、以前のコードのビルドには、新しいコードをコンパイルするときに使用するコンパイラを使用することをお勧めします。 さまざまなコンパイラでコンパイルされたバイナリを混在させないでください。

ときに **/Zc:wchar_t**が指定されている **\_WCHAR\_T\_定義**と**\_ネイティブ\_WCHAR\_T\_定義**シンボルが定義されています。 詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。

コードがあるために、コンパイラ COM グローバル関数を使用する場合 **/Zc:wchar_t**で既定では、ことをお勧め comsupp.lib への明示的な参照を変更することが (いずれかから、[コメント プラグマ](../../preprocessor/comment-c-cpp.md)または、コマンド ライン) には、comsuppw.lib または comsuppwd.lib のいずれか。 (使用してコンパイルする必要がある場合 **/Zc:wchar_t-** comsupp.lib を使用します)。comdef.h のヘッダー ファイルを含めると、適切なライブラリが自動的に指定されます。 コンパイラ COM サポートについては、次を参照してください。[コンパイラ COM サポート](../../cpp/compiler-com-support.md)です。

`wchar_t` C コードをコンパイルするときに、組み込み型がサポートされていません。 Visual C の準拠の問題に関する詳細については、次を参照してください。[非標準動作](../../cpp/nonstandard-behavior.md)です。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **言語**ページ。

1. 変更、 **wchar_t をビルトイン型として扱う**プロパティです。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
