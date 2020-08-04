---
title: /sourceDependencies (レポートソースレベルの依存関係)
description: Microsoft C++ の/sourceDependencies コンパイラオプションのリファレンスガイドです。
ms.date: 07/29/2020
f1_keywords:
- /sourceDependencies
helpviewer_keywords:
- /sourceDependencies compiler option
- /sourceDependencies
ms.openlocfilehash: 3198353ea7569c426a556522d6b931fe23c7f12c
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520704"
---
# <a name="sourcedependencies-report-source-level-dependencies"></a>`/sourceDependencies`(ソースレベルの依存関係をレポートする)

コンパイル中に使用されるソースレベルの依存関係の詳細を示す JSON ファイルを生成するようにコンパイラに指示します。

JSON ファイルには、次のようなソースの依存関係の一覧が含まれています。
- ヘッダーファイル (推移的なヘッダーと直接付加されたヘッダーの両方)。
- 使用される PCH (が指定されている場合 **`/Yu`** )。
- インポートされたモジュールとインポートされたヘッダーユニット (推移性および直接インポートされたモジュール/ヘッダーユニット)。

## <a name="syntax"></a>構文

> **`/sourceDependencies`***ファイル名*\
> **`/sourceDependencies`***ディレクトリ*

## <a name="arguments"></a>引数

*/db*\
コンパイラは、指定されたファイル名にソースの依存関係の出力を書き込みます。このファイルには、相対パスまたは絶対パスを含めることができます。

*名簿*\
引数がディレクトリの場合、コンパイラは指定されたディレクトリにソース依存関係ファイルを生成します。 出力ファイル名は、入力ファイルの完全な名前に基づき、拡張子が追加され *`.json`* ます。 たとえば、コンパイラに指定されたファイルがの場合、 *`main.cpp`* 生成される出力ファイル名はに *`main.cpp.json`* なります。

## <a name="remarks"></a>Remarks

**`/sourceDependencies`** コンパイラオプションは、Visual Studio 2019 バージョン16.7 以降で使用できます。 既定では有効になっていません。

コンパイラオプションを指定する場合は **`/MP`** 、 **`/sourceDependencies`** ディレクトリ引数と共にを使用することをお勧めします。 1つのファイル名引数を指定すると、コンパイラの2つのインスタンスが同時に出力ファイルを開こうとしてエラーが発生する可能性があります。 の詳細につい **`/MP`** ては、「 [ `/MP` (複数のプロセスを使用したビルド)](mp-build-with-multiple-processes.md)」を参照してください。

致命的ではないコンパイラエラーが発生した場合でも、依存関係情報は出力ファイルに書き込まれます。

すべてのファイルパスは、出力に絶対パスとして表示されます。

### <a name="examples"></a>使用例

次のサンプルコードを指定します。

```cpp
// main.cpp
#include "header.h"
import m;
import "other.h";

int main() { }
```

は、 **`/sourceDependencies`** 残りのコンパイラオプションと共に使用できます。

> `cl ... /sourceDependencies output.json ... main.cpp`

は `...` 、他のコンパイラオプションを表します。 このコマンドラインでは、 *`output.json`* 次のような内容の JSON ファイルが生成されます。

```JSON
{
    "Version": "1.0",
    "Data": {
        "Source": "C:\\...\\main.cpp",
        "PCH": "C:\\...\\pch.pch",
        "Includes": [
            "C:\\...\\header.h"
        ],
        "Modules": [
            "C:\\...\\m.ifc",
            "C:\\...\\other.h.ifc"
        ]
    }
}
```

報告される `...` パスを省略するために使用しました。レポートには絶対パスが含まれています。 報告されるパスは、コンパイラが依存関係を検出した場所によって異なります。 結果が予期しないものである場合は、プロジェクトのインクルードパス設定を確認することをお勧めします。

### <a name="to-set-the-sourcedependencies-compiler-option-in-visual-studio"></a>Visual Studio で/sourceDependencies コンパイラオプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [**追加オプション**] ボックスで、を追加し、[ *`/sourceDependencies: <filename>`* **OK]** または [**適用**] を選択して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- このオプションには、プログラムに相当するものはありません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
