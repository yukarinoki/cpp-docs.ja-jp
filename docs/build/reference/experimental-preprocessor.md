---
title: '/実験的: プリプロセッサ (プリプロセッサ準拠モードの有効化)'
description: '標準準拠プリプロセッサの実験的なコンパイラサポートを有効にするには、/実験的: プリプロセッサコンパイラオプションを使用します。'
ms.date: 09/10/2020
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 9a98289434e7154d2ec8b8753d990876a8218acf
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042096"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>`/experimental:preprocessor` (プリプロセッサ準拠モードを有効にする)

このオプションは、Visual Studio 2019 バージョン16.5 以降では、コンパイラオプションによって置き換えられてい [`/Zc:preprocessor`](zc-preprocessor.md) ます。 **`/experimental:preprocessor`** C99 プリプロセッサ機能など、C++ 11 標準により厳密に準拠する実験的なトークンベースプリプロセッサを有効にします。 詳細については、「 [MSVC new プリプロセッサの概要](../../preprocessor/preprocessor-experimental-overview.md)」を参照してください。

## <a name="syntax"></a>構文

> **`/experimental:preprocessor`**\[**`-`**]

## <a name="remarks"></a>注釈

**`/experimental:preprocessor`** コンパイラオプションを使用して、試験的に準拠するプリプロセッサを有効にします。 オプションを使用すると **`/experimental:preprocessor-`** 、従来のプリプロセッサを明示的に指定できます。

この **`/experimental:preprocessor`** オプションは、Visual Studio 2017 バージョン15.8 以降で使用できます。 Visual Studio 2019 バージョン16.5 以降では、新しいプリプロセッサが完成し、コンパイラオプションで使用できるようになりました [`/Zc:preprocessor`](zc-preprocessor.md) 。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. を含めるように " **追加オプション** " プロパティを変更し、[ *`/experimental:preprocessor`* **OK]** を選択します。

## <a name="see-also"></a>参照

[/Zc (準拠)](zc-conformance.md)
