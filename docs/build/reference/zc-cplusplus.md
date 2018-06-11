---
title: /Zc:__cplusplus (有効にする更新された _ _cplusplus マクロ)
ms.custom: ''
ms.date: 05/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:__cplusplus
dev_langs:
- C++
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a796794c0086b09c15ee88442e0fea4d1b114d98
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705715"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>/Zc:__cplusplus (有効にする更新された _ _cplusplus マクロ)

**/Zc:__cplusplus**コンパイラ オプションにより、  **\_ \_cplusplus**プリプロセッサ マクロを最新の C++ 言語標準のサポートの値が更新を報告します。 既定では、Visual Studio 常に、値"199711 L"を返します、  **\_ \_cplusplus**プリプロセッサ マクロです。

## <a name="syntax"></a>構文

> **/Zc:__cplusplus**[**-**]

## <a name="remarks"></a>コメント

**\_ \_Cplusplus**プリプロセッサ マクロはサポートされているレポートを C++ 標準の特定のバージョン。 既存のコードの多くの"199711 L"に一致するこのマクロの値に依存するため、コンパイラは変わりませんマクロの値を明示的にオプトインを使用していない限り、 **/Zc:__cplusplus**コンパイラ オプション。 **/Zc:__cplusplus**オプションの Visual Studio 2017 15.7 のバージョンで利用可能でありは既定で無効です。 以前のバージョンの Visual Studio で、既定では、場合、または **/Zc:__cplusplus-** が指定されて、Visual Studio は、"199711 L"の値を返します、  **\_ \_cplusplus**プリプロセッサ マクロです。 [寛容/-](permissive-standards-conformance.md)オプションが有効にしません **/Zc:__cplusplus**です。

ときに、 **/Zc:__cplusplus**オプションを有効にすると、によって報告される値、  **\_ \_cplusplus**マクロによって異なります、 [/std](std-specify-language-standard-version.md)バージョン スイッチ設定しています。 次の表は、マクロの値を示します。

|/Zc:__cplusplus スイッチ|/std:c++ スイッチ|_ _cplusplus 値|
|-|-|-|
Zc:__cplusplus|/std:c + + 14 (既定値)|201402 L
Zc:__cplusplus|/std:c + + 17|201703 L
Zc:__cplusplus|/std:c + + 最新|201704 L
Zc:__cplusplus-(無効)|任意の値|199711 L
指定されていません|任意の値|199711 L

コンパイラでは、c++ 98、c++ 03、または c++ 11 の標準スイッチはサポートしません。

細かいコンパイラ ツールセットの変更の検出、使用、 [_MSC_VER](../../preprocessor/predefined-macros.md)定義済みマクロです。 この組み込みのマクロの値は、Visual Studio 2017 およびそれ以降のバージョンのツールセット更新のたびにインクリメントされます。 [_MSVC_LANG](../../preprocessor/predefined-macros.md)定義済みマクロがかどうか、標準バージョンを報告、 **/Zc:__cplusplus**オプションを有効または無効にします。 ときに **/Zc:__cplusplus**が有効になって`__cplusplus == _MSVC_LANG`です。

### <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 追加 **/Zc:__cplusplus**または **/Zc:__cplusplus-** を**追加オプション:** ウィンドウです。

## <a name="see-also"></a>関連項目

- [/Zc (準拠)](zc-conformance.md)
- [/std (を指定する言語の標準的なバージョン)](std-specify-language-standard-version.md)
- [定義済みマクロ](../../preprocessor/predefined-macros.md)
