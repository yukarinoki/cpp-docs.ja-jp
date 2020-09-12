---
title: '/Zc: プリプロセッサ (プリプロセッサ準拠モードの有効化)'
description: '標準準拠プリプロセッサのコンパイラサポートを有効にするには、/Zc: プリプロセッサコンパイラオプションを使用します。'
ms.date: 09/10/2020
f1_keywords:
- preprocessor
- /Zc:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /Zc:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 356434e4892966b9a9304021dd5d8770dcc2f8b1
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90043175"
---
# <a name="zcpreprocessor-enable-preprocessor-conformance-mode"></a>`/Zc:preprocessor` (プリプロセッサ準拠モードを有効にする)

このオプションを使用すると、C99 および C++ 11 以降の標準に準拠するトークンベースのプリプロセッサが有効になります。 詳細については、「 [MSVC new プリプロセッサの概要](../../preprocessor/preprocessor-experimental-overview.md)」を参照してください。

## <a name="syntax"></a>構文

> **`/Zc:preprocessor`**[**-**]

## <a name="remarks"></a>注釈

**`/Zc:preprocessor`** コンパイラオプションを使用して、準拠プリプロセッサを有効にします。 オプションを使用すると **`/Zc:preprocessor-`** 、従来の (準拠していない) プリプロセッサを明示的に指定できます。

この **`/Zc:preprocessor`** オプションは、Visual Studio 2019 バージョン16.5 以降で使用できます。 新しいプリプロセッサオプションの以前の不完全なバージョンは、Visual Studio 2017 バージョン15.8 以降のバージョンの Visual Studio で使用できます。 詳細については、「[`/experimental:preprocessor`](experimental-preprocessor.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. を含めるように " **追加オプション** " プロパティを変更し、[ *`/Zc:preprocessor`* **OK]** を選択します。

## <a name="see-also"></a>参照

[/Zc (準拠)](zc-conformance.md)
