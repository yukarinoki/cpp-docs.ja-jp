---
title: /ヘッド (指定されたヘッダーからヘッダーユニットを作成します)
description: ヘッダーファイルと、ビルドするヘッダー単位との間のマッピングを確立するには、/ヘッド ername コンパイラオプションを使用します。
ms.date: 04/13/2021
author: tylermsft
ms.author: twhitney
f1_keywords:
- /headerName
helpviewer_keywords:
- /headerName
- Use header unit IFC
ms.openlocfilehash: cb2b5f6e5a85eb3e14ab3b0139d79fc22b080c37
ms.sourcegitcommit: bac5dde649d5b0447de1d26a73365e36d74595f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "107381719"
---
# <a name="headername-build-a-header-unit-from-the-specified-header"></a>`/headerName` (指定されたヘッダーからヘッダーユニットを作成します)

指定されたヘッダーファイルをヘッダー単位 ( *`.ifc`* ファイル) にビルドします。

## <a name="syntax"></a>構文

> **`/headerName:quote`** `header-filename`\
> **`/headerName:angle`** `header-filename`

### <a name="arguments"></a>引数

*`header-filename`*\
コンパイラがヘッダー単位 (ファイル) にコンパイルするヘッダーファイルの名前 *`.ifc`* 。

## <a name="remarks"></a>解説

**`/headerName`** コンパイラオプションは、Visual Studio 2019 バージョン 16.10 preview 2 以降で使用できます。

**`/headerName`** コンパイラオプションは、すべての形式で、 [/std: c + + latest](std-specify-language-standard-version.md)オプションを必要とします。
を指定する場合は **`/headerName:{quote,angle}`** 、も指定する必要があり [`/exportHeader`](module-exportheader.md) ます。

**`/headerName:quote`***`header-filename`* と同じ規則を使用して検索 `#include "header-name"` し、ヘッダー単位 (ファイル) としてビルドし *`.ifc`* ます。
**`/headerName:angle`***`header-filename`* と同じ規則を使用して検索 `#include <header-name>` し、ヘッダー単位 (ファイル) としてビルドし *`.ifc`* ます。

### <a name="examples"></a>例

として定義されているヘッダーファイルを参照するプロジェクトの場合 `m.h` 、これをヘッダー単位にコンパイルするコンパイラオプションは次のようになります。

```Bash
$ cl /std:c++latest /exportHeader /headerName:quote m.h /Fom.h.obj
```

`/headerName:{quote,angle}`スイッチはフラグのように動作し、引数を明示的に必要としません。 有効な例を次に示します。

```Bash
$ cl /std:c++latest /exportHeader /headerName:angle /MP /Fo.\ vector iostream algorithm
$ cl /std:c++latest /exportHeader /headerName:quote /MP /Fo.\ my-utilities.h a/b/my-core.h
```

同じコマンドラインで複数のスイッチを指定することができ、 `/headerName` そのスイッチの後のすべての引数は、指定された検索規則で処理され *`header-filename`* ます。 次の例では、すべてのヘッダーを、同じ方法で前の2つのコマンドラインの例として処理します。 、、およびのように指定されているかのように、適用された参照ルールを使用して、ヘッダーを検索します。 `#include <vector>` `#include "my-utilties.h"` `#include "a/b/my-core.h"`

```bash
$ cl /std:c++latest /exportHeader /headerName:angle /MP /Fo.\ vector iostream algorithm /headerName:quote my-utilities.h a/b/my-core.h
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

> [!NOTE]
> 通常、ユーザーはこのコマンドラインスイッチを設定しません。 これは、ビルドシステムによって設定されます。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンを [ **すべての構成**] に設定します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **追加オプション]** プロパティを変更して、 *`/headerName`* オプションと引数を追加します。 次に、[ **OK]** または [ **適用** ] を選択して、変更を保存します。

## <a name="see-also"></a>関連項目

[`/exportHeader` (ヘッダーユニットの作成)](module-exportheader.md)\
[`/headerUnit` (ヘッダーユニットの作成)](headerunit.md)\
[`/reference` (名前付きモジュール IFC を使用)](module-reference.md)\
[`/translateInclude` (インクルード ディレクティブをインポート ディレクティブに変換する)](translateinclude.md)
