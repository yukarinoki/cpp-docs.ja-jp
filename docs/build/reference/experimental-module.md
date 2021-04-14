---
title: '/試験: モジュール (モジュールサポートの有効化)'
description: '名前付きモジュールの試験的なコンパイラサポートを有効にするには、/実験的: module コンパイラオプションを使用します。'
ms.date: 04/13/2021
f1_keywords:
- module
- /experimental:module
helpviewer_keywords:
- module
- /experimental:module
- Enable module support
ms.openlocfilehash: dd9d3c9f571b50b328dbb52ee4e7561d5684de1f
ms.sourcegitcommit: bac5dde649d5b0447de1d26a73365e36d74595f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "107381169"
---
# <a name="experimentalmodule-enable-module-support"></a>/試験: モジュール (モジュールサポートの有効化)

標準テンプレートライブラリの名前付きモジュールの試験的なコンパイラサポートを有効にします。

## <a name="syntax"></a>構文

> **/実験的: モジュール**[ **-** ]

## <a name="remarks"></a>解説

**`/experimental:module`** コンパイラオプションを [/std: c + + latest](std-specify-language-standard-version.md)オプションと共に使用することで、実験的なモジュールのサポートを有効にすることができます。 **`/experimental:module-`** モジュールサポートを明示的に無効にするには、を使用します。

このオプションは、Visual Studio 2015 Update 1 以降で使用できます。 Visual Studio 2019 バージョン16.2 では、Draft C++ 20 Standard モジュールは Microsoft C++ コンパイラで完全には実装されていません。 モジュール機能を使用して、単一パーティションのモジュールを作成し、Microsoft が提供する標準ライブラリモジュールをインポートすることができます。 モジュールとそれを使用するコードは、同じコンパイラオプションを使用してコンパイルする必要があります。

モジュールとその使用方法と作成方法の詳細については、「 [C++ のモジュールの概要](../../cpp/modules-cpp.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンを [ **すべての構成**] に設定します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **言語**] プロパティページを選択します。

1. [ **C++ モジュール (試験段階) を有効にする** ] プロパティを変更し、[ **OK]** をクリックします。

## <a name="see-also"></a>関連項目

[`/headerUnit` (Use header unit IFC)](headerunit.md)\
[`/exportHeader` (ヘッダーユニットの作成)](module-exportheader.md)\
[`/reference` (名前付きモジュール IFC を使用)](module-reference.md)\
[`/translateInclude` (インクルードディレクティブをインポートディレクティブに変換します)](translateinclude.md)\
[`/Zc` 互換性](zc-conformance.md)
