---
title: /translateInclude (インクルードディレクティブをインポートディレクティブに変換する)
description: '/TranslateInclude コンパイラオプションを使用して、インポート可能なヘッダー名の #include ディレクティブをインポートヘッダー名ディレクティブに変換します。'
ms.date: 09/13/2020
f1_keywords:
- /translateInclude
helpviewer_keywords:
- /translateInclude
- Translate include directives into import directives
ms.openlocfilehash: 0050f2cb117e48d69cf97a587ef128b9b45790af
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079147"
---
# <a name="translateinclude-translate-include-directives-into-import-directives"></a>`/translateInclude` (インクルードディレクティブをインポートディレクティブに変換します)

`#include` `import header-name;` 文字列インクルードを使用するのではなく、インポート可能なヘッダー名のディレクティブをディレクティブに変換するようコンパイラに指示します。

## <a name="syntax"></a>構文

> **`/translateInclude`**

## <a name="remarks"></a>解説

コンパイラオプションを使用するには、 **`/translateInclude`** [`/experimental:module`](experimental-module.md) コンパイラオプションを使用して、 [/std: c + + latest](std-specify-language-standard-version.md) オプションと共に試験的なモジュールのサポートを有効にする必要があります。 このオプションは、Visual Studio 2019 バージョン16.8 以降で使用できます。

オプションは、 **`/translateInclude`** 次の変換を効果的に行い `<vector>` ます。この例は、インポート可能なヘッダー単位です。

```cpp
#include <vector>
```

コンパイラは、このディレクティブを次のように置き換えます。

```cpp
import <vector> ;
```

MSVC では、インポート可能なヘッダー単位は、参照によって名前が付けられたものです **`/headerUnit`** 。 詳細については、「 [ `/headerUnit` (HEADER unit IFC の使用)](headerunit.md)」を参照してください。

### <a name="examples"></a>例

次の表に示すように、2つのヘッダーファイルとそのヘッダー単位を参照するプロジェクトを指定します。

| ヘッダー ファイル | IFC ファイル |
|--|--|
| *`C:\utils\util.h`* | *`C:\util.h.ifc`* |
| *`C:\app\app.h`* | *`C:\app.h.ifc`* |

*`.cpp`* ヘッダーを含むソースファイル

```cpp
#include "utils/util.h"
#include "app/app.h"

int main() { }
```

オプションを使用すると、ヘッダーを **`/translateInclude`** 再度コンパイルするのではなく、コンパイラがヘッダー単位をインポートできます。 次のコマンドラインの例では、とのインクルードディレクティブを *`util.h`* ヘッダー単位のインポートに変換してい *`app.h`* ます。

```CMD
cl /IC:\ /experimental:module /translateInclude /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit C:\app\app.h=C:\app.h.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンを [ **すべての構成**] に設定します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. オプションを追加するには、[ **追加のオプション** ] プロパティを変更し *`/translateInclude`* ます。 次に、[ **OK]** または [ **適用** ] を選択して、変更を保存します。

## <a name="see-also"></a>関連項目

[`/experimental:module` (モジュールのサポートを有効にする)](experimental-module.md)\
[ `/headerUnit` (HEADER unit IFC を使用](headerunit.md)します)。
[`/module:exportHeader` (ヘッダーユニットの作成)](module-exportheader.md)\
[`/module:reference` (名前付きモジュール IFC を使用)](module-reference.md)
