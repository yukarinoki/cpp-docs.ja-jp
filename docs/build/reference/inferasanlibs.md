---
description: /INFERASANLIBS (推定サニタイザーライブラリを使用) リンカーオプションの詳細
title: /INFERASANLIBS (推定サニタイザーライブラリの使用)
ms.date: 03/01/2021
f1_keywords:
- /INFERASANLIBS
- /INFERASANLIBS:NO
helpviewer_keywords:
- /INFERASANLIBS [C++]
- address sanitizer [C++] linker option
ms.openlocfilehash: 82337b5b77bab2a9066427662f3fd0956684c636
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470975"
---
# <a name="inferasanlibs-use-inferred-sanitizer-libs"></a>`/INFERASANLIBS` (推定サニタイザーライブラリを使用)

**`/INFERASANLIBS`** リンカーオプションを使用して、既定の AddressSanitizer ライブラリへのリンクを有効または無効にします。 Visual Studio 2019 16.9 の場合、サポートされているサニタイザーは [AddressSanitizer](../../sanitizers/asan.md)だけです。

## <a name="syntax"></a>構文

> **`/INFERASANLIBS`**\[**`:NO`**]

## <a name="remarks"></a>解説

リンカーオプションを使用すると、 **`/INFERASANLIBS`** 既定の [AddressSanitizer](../../sanitizers/asan.md) ライブラリが有効になります。 既定では、このオプションは有効になっています。

**`/INFERASANLIBS`** およびリンカーオプションでは、 **`/INFERASANLIBS:NO`** 上級ユーザーがサポートされています。 詳細については、「 [AddressSanitizer build and language reference](../../sanitizers/asan-building.md)」を参照してください。

この **`/INFERASANLIBS`** オプションは、Visual Studio 2019 バージョン16.9 以降で使用できます。

### <a name="to-set-the-inferasanlibs-linker-option-in-the-visual-studio-development-environment"></a>**`/INFERASANLIBS`** Visual Studio 開発環境でリンカーオプションを設定するには

1. プロジェクトの [ **プロパティページ** ] ダイアログボックスを開きます。

1. **[構成プロパティ]**  >  **[リンカー]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. [ **追加オプション]** プロパティを変更します。 既定のライブラリを有効にするには、編集ボックスに「 **/INFERASANLIBS** 」と入力します。 既定のライブラリを無効にするには、代わりに「 **/INFERASANLIBS: NO** 」と入力します。

1. **[OK]** または [**適用**] を選択して、変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーリファレンス](linking.md)\
[MSVC リンカーオプション](linker-options.md)\
[`/fsanitize` (Sanitizers を有効にする)](./fsanitize.md)\
[AddressSanitizer の概要](../../sanitizers/asan.md)\
[AddressSanitizer の既知の問題](../../sanitizers/asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](../../sanitizers/asan-building.md)
