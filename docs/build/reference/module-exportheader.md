---
title: '/モジュール: exportHeader (ヘッダーユニットの作成)'
description: ExportHeader コンパイラオプションを使用して、指定したヘッダー名またはインクルードファイルのモジュールヘッダー単位を作成します。
ms.date: 09/13/2020
f1_keywords:
- /module:exportHeader
helpviewer_keywords:
- /module:exportHeader
- Create header units
ms.openlocfilehash: f0c0ce1c593df742af77aa36189df1e89de75b6b
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079150"
---
# <a name="moduleexportheader-create-header-units"></a>`/module:exportHeader` (ヘッダーユニットの作成)

入力引数で指定されたヘッダー単位を作成するようにコンパイラに指示します。 コンパイラは IFC () ファイルに出力を生成し *`.ifc`* ます。

## <a name="syntax"></a>構文

> **`/module:exportHeader`** *`header-name`* \[...]\
> **`/module:exportHeader`** *`filename`* \[...]

### <a name="arguments"></a>引数

*`header-name`*\
エクスポートするヘッダーファイル。 引数は、 *`header-name`* ディレクティブの引数と同じ形式である必要があり `#include` ます。

*`filename`*\
ヘッダー単位を作成するヘッダーファイルの相対パスまたは絶対パス。

## <a name="remarks"></a>解説

コンパイラオプションを使用するには、 **`/module:exportHeader`** [`/experimental:module`](experimental-module.md) コンパイラオプションを使用して、 [/std: c + + latest](std-specify-language-standard-version.md) オプションと共に試験的なモジュールのサポートを有効にする必要があります。 このオプションは、Visual Studio 2019 バージョン16.8 以降で使用できます。

1つの **`/module:exportHeader`** コンパイラオプションで、ビルドに必要な数のヘッダー名引数を指定できます。 個別に指定する必要はありません。

既定では、ヘッダーユニットがコンパイルされるときに、コンパイラはオブジェクトファイルを生成しません。 オブジェクトファイルを生成するには、 **`/Fo`** コンパイラオプションを指定します。 詳細については、「 [ `/Fo` (オブジェクトファイル名)](fo-object-file-name.md)」を参照してください。

コンパイラは、 *`header-name`* 指定したものを含め、インクルードディレクトリの検索順序に基づいてを解決します。 詳細については、「 [ `/I` (追加のインクルードディレクトリ)](i-additional-include-directories.md)」を参照してください。

引数は、 *`header-name`* source に表示されるのと同じ方法で指定する必要があります。 引数は、コマンドラインで、引用符規則および and 演算子によって区別され `<` `>` ます。 VS2019 コマンドプロンプトを使用するなど、ヘッダー単位を作成するための適切にエスケープされたコマンドは、 `<vector>` 次のようになります。

```cmd
cl ... /experimental:module /module:exportHeader "<vector>"
```

などのローカルプロジェクトヘッダーをビルドすることは、 `"utils/util.h"` 次のようになります。

```cmd
cl ... /experimental:module /module:exportHeader """util/util.h"""
```

他のコマンドラインプロセッサの引用符規則は異なる場合があります。

の形式を使用する場合は *`header-name`* **`/module:exportHeader`** 、補完的なオプションを使用すると便利です **`/module:showResolvedHeader`** 。 オプションは、 **`/module:showResolvedHeader`** 引数が解決されるファイルへの絶対パスを出力 *`header-name`* します。

**`/module:exportHeader`** では、一度に複数の入力を処理でき **`/MP`** ます。 を使用し **`/module:output <directory>`** て、コンパイルごとに個別の IFC ファイルを作成することをお勧めします。

### <a name="examples"></a>例

ヘッダー `"C:\util\util.h"` と `"C:\app\app.h"` を引数としてエクスポートするには、次の *`header-name`* コマンドを使用します。

```cmd
cl /IC:\ /experimental:module /module:exportHeader """util/util.h""" """app/app.h""" /FoC:\obj
```

次のコマンドを使用して、これらを引数としてエクスポートでき *`filename`* ます。

```cmd
cl /IC:\ /experimental:module /module:exportHeader C:\util\util.h C:\app\app.h /FoC:\obj
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンを [ **すべての構成**] に設定します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **追加オプション** ] プロパティを変更して、 *`/module:exportHeader`* オプションと任意の引数を追加します。 次に、[ **OK]** または [ **適用** ] を選択して、変更を保存します。

## <a name="see-also"></a>関連項目

[`/experimental:module` (モジュールのサポートを有効にする)](experimental-module.md)\
[`/headerUnit` (Use header unit IFC)](headerunit.md)\
[`/module:reference` (名前付きモジュール IFC を使用)](module-reference.md)\
[`/translateInclude` (インクルードディレクティブをインポートディレクティブに変換します)](translateinclude.md)
