---
title: '/Zc: _ _cplusplus (更新された _ _cplusplus マクロを有効にする)'
ms.date: 05/30/2018
f1_keywords:
- /Zc:__cplusplus
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
ms.openlocfilehash: 89545f541f32374a47dce7f87958e61873c1b47c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810095"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>/Zc: _ _cplusplus (更新された _ _cplusplus マクロを有効にする)

**/Zc: _ _cplusplus**コンパイラ オプションにより、  **\_ \_cplusplus**プリプロセッサ マクロを最新の C++ 言語標準サポートの更新後の値を報告します。 既定では、Visual Studio 常の値を返す"199711 L"、  **\_ \_cplusplus**プリプロセッサ マクロ。

## <a name="syntax"></a>構文

> **/Zc:__cplusplus**[**-**]

## <a name="remarks"></a>Remarks

 **\_ \_Cplusplus**プリプロセッサ マクロはサポートされているレポートを C++ 標準の特定のバージョン。 多数の既存のコードの"199711 L"に一致するこのマクロの値に依存するため、コンパイラは変わりませんマクロの値を明示的にオプトインを使用していない限り、 **/zc: _ _cplusplus**コンパイラ オプション。 **/Zc: _ _cplusplus**オプションは、以降では、Visual Studio 2017 バージョン 15.7 では、利用可能とは既定で無効です。 以前のバージョンの Visual Studio で、既定では、場合、または **/Zc:__cplusplus-** が指定されて、Visual Studio は、"199711 L"の値を返します、  **\_ \_cplusplus**プリプロセッサ マクロです。 [/Permissive -](permissive-standards-conformance.md)オプションが有効にしない **/zc: _ _cplusplus**します。

ときに、 **/zc: _ _cplusplus**オプションを有効にすると、によって報告される値、  **\_ \_cplusplus**マクロによって異なります、 [/std](std-specify-language-standard-version.md)バージョン スイッチ設定です。 次の表では、マクロの値を示します。

|/Zc: _ _cplusplus スイッチ|/std:c++ スイッチ|__cplusplus value|
|-|-|-|
Zc:__cplusplus|/std:c + + 14 (既定値)|201402L
Zc:__cplusplus|/std:c + + 17|201703L
Zc:__cplusplus|/std:c + + 最新|201704L
Zc:__cplusplus-(無効)|任意の値|199711 L
指定されていません|任意の値|199711 L

コンパイラは c++ 98 や c++ 03、c++ 11 の標準スイッチをサポートしていません。

細かい単位のコンパイラ ツールセットの変更の検出を使用して、 [_MSC_VER](../../preprocessor/predefined-macros.md)定義済みマクロ。 この組み込みのマクロの値は、Visual Studio 2017 およびそれ以降のバージョンのツールセットの更新のたびに増加します。 [_MSVC_LANG](../../preprocessor/predefined-macros.md)定義済みマクロがかどうか、標準のバージョンを報告、 **/zc: _ _cplusplus**オプションを有効または無効になっています。 ときに **/zc: _ _cplusplus**が有効になって`__cplusplus == _MSVC_LANG`します。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 追加 **/zc: _ _cplusplus**または **/Zc:__cplusplus-** を**追加オプション:** ウィンドウ。

## <a name="see-also"></a>関連項目

- [/Zc (準拠)](zc-conformance.md)
- [/std (指定言語標準バージョン)](std-specify-language-standard-version.md)
- [定義済みマクロ](../../preprocessor/predefined-macros.md)
