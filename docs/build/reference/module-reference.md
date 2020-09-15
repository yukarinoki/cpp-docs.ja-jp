---
title: '/モジュール: リファレンス (名前付きモジュール IFC を使用)'
description: '/Module: reference コンパイラオプションを使用して、指定されたヘッダー名またはインクルードファイルのモジュールヘッダー単位を作成します。'
ms.date: 09/13/2020
f1_keywords:
- /module:reference
helpviewer_keywords:
- /module:reference
- Use named module IFC
ms.openlocfilehash: 5f40f6b700c38f3238cc7a621313621085fbc289
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90079154"
---
# <a name="modulereference-use-named-module-ifc"></a>`/module:reference` (名前付きモジュール IFC を使用)

現在のコンパイルで既存の IFC () を使用するようにコンパイラに指示し *`.ifc`* ます。

## <a name="syntax"></a>構文

> **`/module:reference`** *`module-name=filename`*\
> **`/module:reference`** *`filename`*

### <a name="arguments"></a>引数

*`filename`*\
*IFC data*、事前に構築されたモジュール情報を含むファイルの名前。 複数のモジュールをインポートするには、 **`/module:reference`** ファイルごとに個別のオプションを指定します。

*`module-name`*\
エクスポートされたプライマリモジュールインターフェイスユニット名または完全なモジュールパーティション名の有効な名前。

## <a name="remarks"></a>解説

コンパイラオプションを使用するには、 **`/module:reference`** [`/experimental:module`](experimental-module.md) コンパイラオプションを使用して、 [/std: c + + latest](std-specify-language-standard-version.md) オプションと共に試験的なモジュールのサポートを有効にする必要があります。 このオプションは、Visual Studio 2019 バージョン16.8 以降で使用できます。

**`/module:reference`** 引数がでない場合は *`filename`* *`module-name`* 、実行時にファイルが開かれ、特定の *`filename`* インポートの引数名が検証されます。 多くの引数を持つシナリオでは、実行時のパフォーマンスが低下する可能性があり **`/module:reference`** ます。

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
cl ... /experimental:module /module:reference m.ifc /module:reference m=n.ifc
```

上の例では、コンパイラがを認識した場合、検索は行わ `import m;` *`m.ifc`* れません。

### <a name="examples"></a>例

次の表に示されている3つのモジュールがあるとします。

| モジュール | IFC ファイル |
|--|--|
| *`M`* | *`m.ifc`* |
| *`M:Part1`* | *`m-part1.ifc`* |
| *`Core.Networking`* | *`Networking.ifc`* |

引数を使用した参照オプションは *`filename`* 次のようになります。

```cmd
cl ... /experimental:module /module:reference m.ifc /module:reference m-part.ifc /module:reference Networking.ifc
```

を使用した参照オプションは *`module-name=filename`* 次のようになります。

```cmd
cl ... /experimental:module /module:reference m=m.ifc /module:reference M:Part1=m-part.ifc /module:reference Core.Networking=Networking.ifc
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンを [ **すべての構成**] に設定します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. オプションとその引数を追加するには、[ **追加のオプション** ] プロパティを変更し *`/module:reference`* ます。 次に、[ **OK]** または [ **適用** ] を選択して、変更を保存します。

## <a name="see-also"></a>関連項目

[`/experimental:module` (モジュールのサポートを有効にする)](experimental-module.md)\
[`/headerUnit` (Use header unit IFC)](headerunit.md)\
[`/module:exportHeader` (ヘッダーユニットの作成)](module-exportheader.md)\
[`/translateInclude` (インクルードディレクティブをインポートディレクティブに変換します)](translateinclude.md)
