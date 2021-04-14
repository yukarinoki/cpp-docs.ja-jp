---
title: /headerUnit (ヘッダー ユニット IFC の使用)
description: ヘッダーファイルをヘッダー単位に関連付けて、その代わりにインポートするには、/headerunit コンパイラオプションを使用します。
ms.date: 04/13/2021
f1_keywords:
- /headerUnit
helpviewer_keywords:
- /headerUnit
- Use header unit IFC
author: tylermsft
ms.author: twhitney
ms.openlocfilehash: 205809e25644f4beaa0105a2611c7eaa4e6b7b02
ms.sourcegitcommit: bac5dde649d5b0447de1d26a73365e36d74595f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "107381377"
---
# <a name="headerunit-use-header-unit-ifc"></a>`/headerUnit` (ヘッダー ユニット IFC の使用)

ヘッダー単位をインポートするために使用します。 *`.ifc`* 指定したヘッダーのファイル (ヘッダーユニットのバイナリ表現) を検索する場所をコンパイラに指示します。

## <a name="syntax"></a>構文

> **`/headerUnit`** *`header-filename`*=*`ifc-filename`*\
> **`/headerUnit:quote`** \[*`header-filename`*=*`ifc-filename`*\]\
> **`/headerUnit:angle`** \[*`header-filename`*=*`ifc-filename`*\]

### <a name="arguments"></a>引数

*`header-filename`*\
`import header-name;`コンパイラでは、 `header-name` ディスク上のファイルに解決されます。 を使用し *`header-filename`* てそのファイルを指定します。 一致すると、コンパイラはによってという名前の対応する IFC を *`ifc-filename`* インポート用に開きます。

*`ifc-filename`*\
コンパイル済みヘッダーの単位情報を格納しているファイルの名前。 複数のヘッダー単位をインポートするには、 **`/headerUnit`** ファイルごとに個別のオプションを追加します。

## <a name="remarks"></a>解説

**`/headerUnit`** コンパイラオプションには、 [/std: c + + latest](std-specify-language-standard-version.md)オプションが必要です。

**`/headerUnit`** コンパイラオプションは、Visual Studio 2019 バージョン 16.10 preview 2 以降で使用できます。

コンパイラがまたはの間にある場合 `import "file";` `import <file>;` 、このコンパイラスイッチは、コンパイラが、 *`.ifc`* 指定されたヘッダーファイルのコンパイル済みヘッダーユニット () を検索するのに役立ちます。 このファイルへのパスは、次の3つの方法で表すことができます。

**`/headerUnit`** 現在のディレクトリ、またはで指定された場所で、コンパイル済みヘッダーユニットを検索 *`ifc-filename`* します。

**`/headerUnit:quote`** と同じルールを使用して、コンパイル済みヘッダーユニットファイルを検索し `#include "file"` ます。

**`/headerUnit:angle`** と同じルールを使用して、コンパイル済みヘッダーユニットファイルを検索し `#include <file>` ます。

コンパイラは、1つのを複数のファイルにマップすることはできません *`header-name`* *`.ifc`* 。 複数 *`header-name`* の引数を1つのにマップすること *`.ifc`* は可能ですが、推奨されません。 *`.ifc`* によって指定されたヘッダーだけであるかのように、の内容がとしてインポートされ *`header-name`* ます。

コンパイラは、このスイッチを使用するときに、新しいプリプロセッサを暗黙的に有効にします。 つまり、 [`/Zc:preprocessor`](zc-preprocessor.md) コマンドラインでの任意の形式が指定されている場合、はコンパイラによってコマンドラインに追加され `/headerUnit` ます。 暗黙的なをオプトアウトするには `/Zc:preprocessor` 、次のように指定します。 `/Zc:preprocessor-`

新しいプリプロセッサを無効にしても、コンパイルしたファイルがヘッダーユニットをインポートした場合、コンパイラはエラーを報告します。

### <a name="examples"></a>例

次の表に示すように、2つのヘッダーファイルとそのヘッダー単位を参照するプロジェクトを指定します。

| ヘッダー ファイル | IFC ファイル |
|--|--|
| *`C:\utils\util.h`* | *`C:\util.h.ifc`* |
| *`C:\app\app.h`* | *`C:\app\app.h.ifc`* |

これらの特定のヘッダーファイルのヘッダー単位を参照するコンパイラオプションは、次のようになります。

```CMD
cl ... /std:c++latest /headerUnit C:\utils\util.h=C:\util.h.ifc /headerUnit:quote app.h=app.h.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

通常、Visual Studio 開発環境ではこれを設定しないでください。 これは、ビルドシステムによって設定されます。

## <a name="see-also"></a>関連項目

[`/exportHeader` (ヘッダーユニットの作成)](module-exportheader.md)\
[`/headerName` (指定されたヘッダーからヘッダーユニットを作成します)](headername.md)\
[`/reference` (名前付きモジュール IFC の使用)](module-reference.md)
