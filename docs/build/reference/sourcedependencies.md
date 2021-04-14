---
title: /sourceDependencies (レポート ソースレベルの依存関係)
description: Microsoft C++ の/sourceDependencies コンパイラオプションについて説明します。
ms.date: 04/13/2020
author: tylermsft
ms.author: twhitney
f1_keywords:
- /sourceDependencies
helpviewer_keywords:
- /sourceDependencies compiler option
- /sourceDependencies
ms.openlocfilehash: cf76d6e31abc7328b82b877bf6f3e2545efc7878
ms.sourcegitcommit: bac5dde649d5b0447de1d26a73365e36d74595f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "107381351"
---
# <a name="sourcedependencies-list-all-source-level-dependencies"></a>`/sourceDependencies` (すべてのソースレベルの依存関係を一覧表示します)

このコマンドラインスイッチでは、コンパイル中に使用されるソースレベルの依存関係の詳細を示す JSON ファイルが生成されます。 JSON ファイルには、次のようなソースの依存関係の一覧が含まれています。

- ヘッダーファイル。 直接含めることも、ヘッダーに含まれるヘッダーの一覧を含めることもできます。
- 使用される PCH (が指定されている場合 **`/Yu`** )。
- インポートされたモジュールの名前
- インポートされたヘッダーユニットのファイルパスと名前。 直接インポートされたものと、それらのモジュールとヘッダーユニットによってインポートされたものがあります。

これにより、適切な依存関係の順序でモジュールとヘッダーユニットを構築するために必要な情報が提供されます。

## <a name="syntax"></a>構文

> **`/sourceDependencies`** -\
> **`/sourceDependencies`***ファイル名*\
> **`/sourceDependencies`***ディレクトリ*

## <a name="arguments"></a>引数

*`-`*\
単一点ダッシュが指定されている場合、コンパイラは、ソースの依存関係 JSON をに出力し `stdout` ます。または、コンパイラ出力がにリダイレクトされる場所に出力します。

*`filename`*\
コンパイラは、指定されたファイル名にソースの依存関係の出力を書き込みます。このファイルには、相対パスまたは絶対パスを含めることができます。

*`directory`*\
引数がディレクトリの場合、コンパイラは指定されたディレクトリにソース依存関係ファイルを生成します。 出力ファイル名は、入力ファイルの完全な名前に基づき、拡張子が追加され *`.json`* ます。 たとえば、コンパイラに指定されたファイルがの場合、 *`main.cpp`* 生成される出力ファイル名はに *`main.cpp.json`* なります。

## <a name="remarks"></a>解説

**`/sourceDependencies`** コンパイラオプションは、Visual Studio 2019 バージョン16.7 以降で使用できます。 既定では有効になっていません。

コンパイラオプションを指定する場合は **`/MP`** 、 **`/sourceDependencies`** ディレクトリ引数と共にを使用することをお勧めします。 1つのファイル名引数を指定すると、コンパイラの2つのインスタンスが同時に出力ファイルを開こうとしてエラーが発生する可能性があります。 の詳細につい **`/MP`** ては、「 [ `/MP` (複数のプロセスを使用したビルド)](mp-build-with-multiple-processes.md)」を参照してください。

致命的ではないコンパイラエラーが発生した場合でも、依存関係情報は出力ファイルに書き込まれます。

すべてのファイルパスは、出力に絶対パスとして表示されます。

### <a name="examples"></a>例

次のサンプルコードを指定します。

```cpp
// ModuleE.ixx:
export module ModuleE;
import ModuleC;
import ModuleD;
import <iostream>;
```

は、 **`/sourceDependencies`** 残りのコンパイラオプションと共に使用できます。

> `cl ... /sourceDependencies output.json ... main.cpp`

は `...` 、他のコンパイラオプションを表します。 このコマンドラインでは、 *`output.json`* 次のような内容の JSON ファイルが生成されます。

```JSON
{
    "Version": "1.1",
    "Data": {
        "Source": "F:\\Sample\\myproject\\modulee.ixx",
        "ProvidedModule": "ModuleE",
        "Includes": [],
        "ImportedModules": [
            {
                "Name": "ModuleC",
                "BMI": "F:\\Sample\\Outputs\\Intermediate\\MyProject\\x64\\Debug\\ModuleC.ixx.ifc"
            },
            {
                "Name": "ModuleB",
                "BMI": "F:\\Sample\\Outputs\\Intermediate\\ModuleB\\x64\\Debug\\ModuleB.ixx.ifc"
            },
            {
                "Name": "ModuleD",
                "BMI": "F:\\Sample\\Outputs\\Intermediate\\MyProject\\x64\\Debug\\ModuleD.cppm.ifc"
            }
        ],
        "ImportedHeaderUnits": [
            {
                "Header": "f:\\visual studio 16 main\\vc\\tools\\msvc\\14.29.30030\\include\\iostream",
                "BMI": "F:\\Sample\\Outputs\\Intermediate\\HeaderUnits\\x64\\Debug\\iostream_W4L4JYGFJ3GL8OG9.ifc"
            },
            {
                "Header": "f:\\visual studio 16 main\\vc\\tools\\msvc\\14.29.30030\\include\\yvals_core.h",
                "BMI": "F:\\Sample\\Outputs\\Intermediate\\HeaderUnits\\x64\\Debug\\yvals_core.h.ifc"
            }
        ]
    }
}
```

報告される `...` パスを省略するために使用しました。 レポートには絶対パスが含まれます。 報告されるパスは、コンパイラが依存関係を検出した場所によって異なります。 結果が予期しないものである場合は、プロジェクトのインクルードパス設定を確認することをお勧めします。

`ProvidedModule` エクスポートされたモジュールまたはモジュールのパーティション名を一覧表示します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

通常、Visual Studio 開発環境でこれを設定することはできません。 これは、ビルドシステムによって設定されます。

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)<br/>
