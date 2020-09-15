---
title: /headerunit (Use header unit IFC)
description: /Headerunit コンパイラオプションを使用して、現在のコンパイルでインポートする既存の IFC header ユニットを指定します。
ms.date: 09/13/2020
f1_keywords:
- /headerUnit
helpviewer_keywords:
- /headerUnit
- Use header unit IFC
ms.openlocfilehash: 2734df728b188dcfbbe5f475cfc67715a070975d
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079158"
---
# <a name="headerunit-use-header-unit-ifc"></a>`/headerUnit` (Use header unit IFC)

`#include` `import header-name;` 文字列インクルードを使用するのではなく、インポート可能なヘッダー名のディレクティブをディレクティブに変換するようコンパイラに指示します。

## <a name="syntax"></a>構文

> **`/headerUnit`** *`header-filename`*=*`ifc-filename`*

### <a name="arguments"></a>引数

*`header-filename`*\
コンパイラがを解決するファイルの名前 `header-name` 。 `import header-name ;`コンパイラでは、 `header-name` ディスク上のいくつかのファイルに解決されます。 を使用し *`header-filename`* てそのファイルを指定します。 一致すると、コンパイラはによってという名前の対応する IFC を *`ifc-filename`* インポート用に開きます。

*`ifc-filename`*\
*IFC data*、事前に構築されたモジュール情報を含むファイルの名前。 複数のヘッダー単位をインポートするには、 **`/headerUnit`** ファイルごとに個別のオプションを指定します。

## <a name="remarks"></a>解説

コンパイラオプションを使用するには、 **`/headerUnit`** [`/experimental:module`](experimental-module.md) コンパイラオプションを使用して、 [/std: c + + latest](std-specify-language-standard-version.md) オプションと共に試験的なモジュールのサポートを有効にする必要があります。 このオプションは、Visual Studio 2019 バージョン16.8 以降で使用できます。

コンパイラは、1つのを *`header-name`* 複数の IFC ファイルにマップすることはできません。 複数の *`header-name`* 引数を1つの IFC にマップすることは可能ですが、推奨されません。 IFC の内容は、によって指定されたヘッダーの場合と同じようにインポートされ *`header-name`* ます。

### <a name="examples"></a>例

次の表に示すように、2つのヘッダーファイルとそのヘッダー単位を参照するプロジェクトを指定します。

| ヘッダー ファイル | IFC ファイル |
|--|--|
| *`C:\utils\util.h`* | *`C:\util.h.ifc`* |
| *`C:\app\app.h`* | *`C:\app.h.ifc`* |

これらの特定のヘッダーファイルのヘッダー単位を参照するコンパイラオプションは、次の例のようになります。

```CMD
cl ... /experimental:module /translateInclude /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit C:\app\app.h=C:\app.h.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンを [ **すべての構成**] に設定します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **追加オプション]** プロパティを変更して、 *`/headerUnit`* オプションと引数を追加します。 次に、[ **OK]** または [ **適用** ] を選択して、変更を保存します。

## <a name="see-also"></a>関連項目

[`/experimental:module` (モジュールのサポートを有効にする)](experimental-module.md)\
[`/module:exportHeader` (ヘッダーユニットの作成)](module-exportheader.md)\
[`/module:reference` (名前付きモジュール IFC を使用)](module-reference.md)\
[`/translateInclude` (インクルードディレクティブをインポートディレクティブに変換します)](translateinclude.md)\
