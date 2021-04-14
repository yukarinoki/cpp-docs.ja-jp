---
title: /translateInclude (インクルード ディレクティブをインポート ディレクティブに変換する)
description: '/TranslateInclude コンパイラオプションを使用すると、インポート可能なヘッダー単位が使用可能な場合に #include ディレクティブを import ステートメントとして扱うことができます。'
ms.date: 4/13/2021
author: tylermsft
ms.author: twhitney
f1_keywords:
- /translateInclude
helpviewer_keywords:
- /translateInclude
- Translate include directives into import directives
ms.openlocfilehash: e700e79c64be466e33e0ee698114c85eba1f7e18
ms.sourcegitcommit: bac5dde649d5b0447de1d26a73365e36d74595f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "107381306"
---
# <a name="translateinclude-translate-include-directives-into-import-directives"></a>`/translateInclude` (インクルード ディレクティブをインポート ディレクティブに変換する)

`#include` `import` ヘッダーユニット () ファイルにあらかじめ構築されているヘッダーのとしてを処理するようにコンパイラに指示し `.ifc` ます。

## <a name="syntax"></a>構文

> **`/translateInclude`**

## <a name="remarks"></a>解説

**`/translateInclude`** コンパイラオプションでは、 [/std: c + + latest](std-specify-language-standard-version.md)オプションを有効にする必要があります。 `/translateInclude` は、Visual Studio 2019 バージョン 16.10 Preview 2 以降で使用できます。

この **`/translateInclude`** オプションは、次の変換を効果的に行います。この場合、この例は、 `<vector>` インポート可能なヘッダー単位にあらかじめ構築されています。

```cpp
#include <vector>
```

コンパイラは、このディレクティブを次のように置き換えます。

```cpp
import <vector>;
```

MSVC では、使用可能なヘッダー単位がオプションによって提供され **`/headerUnit`** ます。このオプションは、ヘッダーファイルを、それに対応する事前インポート可能なヘッダー単位にマップします。 詳細については、「」を参照してください[ `/headerUnit` (ヘッダー `.ifc` 単位ファイルを検索する場所を指定](headerunit.md)します ()。

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

**`/translateInclude`** オプションを使用すると、コンパイラはを、 `#include` 対応する `import` コンパイル済みヘッダーユニットファイル () があり、 *`.ifc`* スイッチを介してコマンドラインで指定されているヘッダーファイルのとしてを扱うことができ `/headerUnit` ます。

スイッチで `#include` 指定された対応するヘッダー単位を持たないが検出されると `/headerUnit` 、プリプロセッサによって通常のディレクティブとして処理され `#include` ます。

 次のコマンドラインの例では、とのインクルードディレクティブを *`util.h`* ヘッダー単位のインポートに変換してい *`app.h`* ます。

```CMD
cl /IC:\ /translateInclude /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit C:\app\app.h=C:\app.h.ifc
```

## <a name="to-set-this-compiler-option-in-visual-studio"></a>このコンパイラ オプションを Visual Studio で使用するには

有効にするには `/translateInclude` 、プロジェクトのプロパティの [ **インクルードをインポートに変換** ] オプションを設定します。

1. プロジェクトのプロパティページの左側のペインで、[**構成プロパティ**] [  >  **C/c + +**  >  **全般**] の順に選択します。
1. [**追加**] の [インポート] ドロップダウンを **[はい]** に変更します。 [ 
 ![ プロジェクトのプロパティ] ダイアログボックスの [インポートに含まれる変換]](../media/vs2019-translate-includes-option.png)


## <a name="see-also"></a>関連項目

[ `/headerUnit` (HEADER unit IFC を使用](headerunit.md)します)。
[`/exportHeader` (ヘッダーユニットの作成)](module-exportheader.md)\
[`/reference` (名前付きモジュール IFC の使用)](module-reference.md)
