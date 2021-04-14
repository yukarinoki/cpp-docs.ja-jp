---
title: /reference (名前付きモジュール IFC を使用)
description: 指定されたヘッダー名またはインクルードファイルのモジュールヘッダーユニットを作成するには、/reference コンパイラオプションを使用します。
ms.date: 04/13/2020
f1_keywords:
- /reference
helpviewer_keywords:
- /reference
- Use named module IFC
ms.openlocfilehash: 00b8938e270ff6e6cd0fc29580b0e8b278888eaa
ms.sourcegitcommit: bac5dde649d5b0447de1d26a73365e36d74595f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "107381325"
---
# <a name="reference-use-named-module-ifc"></a>`/reference` (名前付きモジュール IFC の使用)

現在のコンパイルで既存の IFC () を使用するようにコンパイラに指示し *`.ifc`* ます。

## <a name="syntax"></a>構文

> **`/reference`** *`module-name=filename`*\
> **`/reference`** *`filename`*

### <a name="arguments"></a>引数

*`filename`*\
*IFC データ* を含むファイルの名前。これは、事前に構築されたモジュールの情報です。 複数のモジュールをインポートするには、 **`/reference`** ファイルごとに個別のオプションを指定します。

*`module-name`*\
エクスポートされたプライマリモジュールインターフェイスユニット名または完全なモジュールパーティション名の有効な名前。

## <a name="remarks"></a>解説

ほとんどの場合、このスイッチを指定する必要はありません。これは、プロジェクトシステムによってソリューション内のモジュールの依存関係が自動的に検出されるためです。

**`/reference`** コンパイラオプションでは、 [/std: c + + latest](std-specify-language-standard-version.md)オプションを有効にする必要があります。 この **`/reference`** オプションは、Visual Studio 2019 バージョン 16.10 Preview 2 以降で使用できます。

**`/reference`** 引数がでない場合は *`filename`* *`module-name`* 、実行時にファイルが開かれ、特定の *`filename`* インポートの引数名が検証されます。 多くの引数を持つシナリオでは、実行時のパフォーマンスが低下する可能性があり **`/reference`** ます。

は、 *`module-name`* 有効なプライマリモジュールインターフェイスユニット名または完全なモジュールパーティション名である必要があります。 主なモジュールインターフェイス名の例を次に示します。

- `M`
- `M.N.O`
- `MyModule`
- `my_module`

完全なモジュールパーティション名の例を次に示します。

- `M:P`
- `M.N.O:P.Q`
- `MyModule:Algorithms`
- `my_module:algorithms`

モジュール参照がを使用して作成された場合 *`module-name`* 、コンパイラがその名前のインポートを検出しても、コマンドライン上の他のモジュールは検索されません。 たとえば、次のコマンドラインを指定します。

```cmd
cl ... /std:c++latest /reference m.ifc /reference m=n.ifc
```

上の例では、コンパイラがを認識した場合、検索は行わ `import m;` *`m.ifc`* れません。

### <a name="examples"></a>例

次の表に示されている3つのモジュールがあるとします。

| モジュール | IFC ファイル |
|--|--|
| *`M`* | *`m.ifc`* |
| *`M:Part1`* | *`m-part1.ifc`* |
| *`Core.Networking`* | *`Networking.ifc`* |

引数を使用した参照オプションは次のようになり *`filename`* ます。

```cmd
cl ... /std:c++latest /reference m.ifc /reference m-part.ifc /reference Networking.ifc
```

を使用した参照オプションは次のようになり *`module-name=filename`* ます。

```cmd
cl ... /std:c++latest /reference m=m.ifc /reference M:Part1=m-part.ifc /reference Core.Networking=Networking.ifc
```

## <a name="see-also"></a>関連項目

[`/sourceDependencies:directives` (List モジュールとヘッダーユニットの依存関係)](sourcedependencies-directives.md)\
[`/headerUnit` (Use header unit IFC)](headerunit.md)\
[`/exportHeader` (ヘッダー ユニットの作成)](module-exportheader.md)
