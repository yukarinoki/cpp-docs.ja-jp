---
description: 詳細については、「/fsanitize (enable sanitizers) コンパイラオプション」を参照してください。
title: /fsanitize (sanitizers の有効化)
ms.date: 02/24/2021
f1_keywords:
- /fsanitize
- -fsanitize
- /fsanitize=address
- /fsanitize-address-use-after-return
- -fsanitize-address-use-after-return
- /fno-sanitize-address-vcasan-lib
- -fno-sanitize-address-vcasan-lib
helpviewer_keywords:
- /fsanitize [C++]
- -fsanitize=address [C++]
- address sanitizer compiler option [C++]
- /fsanitize-address-use-after-return
- /fno-sanitize-address-vcasan-lib
ms.openlocfilehash: 820d39e54db29a5e06d119cbefc8a1980447e8cc
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470973"
---
# <a name="fsanitize-enable-sanitizers"></a>`/fsanitize` (Sanitizers を有効にする)

Sanitizers を **`/fsanitize`** 有効にするには、コンパイラオプションを使用します。 Visual Studio 2019 16.9 の場合、サポートされているサニタイザーは [AddressSanitizer](../../sanitizers/asan.md)だけです。

## <a name="syntax"></a>構文

> **`/fsanitize=address`**\
> **`/fsanitize-address-use-after-return`**\
> **`/fno-sanitize-address-vcasan-lib`**

## <a name="remarks"></a>解説

**`/fsanitize=address`** コンパイラオプションを使用すると、強力なコンパイラおよびランタイムテクノロジである [AddressSanitizer](../../sanitizers/asan.md)を使用して、発見し [にくいバグを見つける](../../sanitizers/asan.md#error-types)ことができます。

**`/fsanitize-address-use-after-return`** とコンパイラオプション、およびリンカーオプションでは、 **`/fno-sanitize-address-vcasan-lib`** [ `/INFERASANLIBS`](./inferasanlibs.md) **`/INFERASANLIBS:NO`** 上級ユーザー向けのサポートが提供されています。 詳細については、「 [AddressSanitizer build and language reference](../../sanitizers/asan-building.md)」を参照してください。

オプションは、 **`/fsanitize`** Visual Studio 2019 バージョン16.9 以降で使用できます。

### <a name="to-set-the-fsanitizeaddress-compiler-option-in-the-visual-studio-development-environment"></a>**`/fsanitize=address`** Visual Studio 開発環境でコンパイラオプションを設定するには

1. プロジェクトの [ **プロパティページ** ] ダイアログボックスを開きます。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[全般]** プロパティ ページを選択します。

1. **Enable Address サニタイザー** プロパティを変更します。 有効にするには、[はい] を選択します **(/fsanitize = address)**。

1. **[OK]** または [**適用**] を選択して、変更を保存します。

### <a name="to-set-the-advanced-compiler-options"></a>詳細コンパイラオプションを設定するには

1. プロジェクトの [ **プロパティページ** ] ダイアログボックスを開きます。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **追加オプション]** プロパティを変更して、 **/fsanitize-address-use-after-return** または **/fno-sanitize-address-vcasan-lib** を設定します。

1. **[OK]** または [**適用**] を選択して、変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md)\
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)\
[`/INFERASANLIBS` (推定サニタイザーライブラリを使用)](./inferasanlibs.md)\
[AddressSanitizer の概要](../../sanitizers/asan.md)\
[AddressSanitizer の既知の問題](../../sanitizers/asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](../../sanitizers/asan-building.md)
