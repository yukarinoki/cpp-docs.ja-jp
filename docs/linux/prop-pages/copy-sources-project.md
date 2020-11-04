---
title: ソースのプロジェクト プロパティのコピー (Linux C++)
ms.date: 10/16/2019
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: 393f1b92bb5185bcd5ce93999e0c13f7d370e78d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924550"
---
# <a name="copy-sources-project-properties-linux-c"></a>ソースのプロジェクト プロパティのコピー (Linux C++)

::: moniker range="msvc-140"

Linux サポートは Visual Studio 2017 以降で使用できます。

::: moniker-end

::: moniker range=">=msvc-150"

このプロパティ ページで設定されたプロパティは、ファイルレベル プロパティが設定されているファイルを除き、プロジェクト内の全ファイルに適用されます。

| プロパティ | 説明 |
|--|--|
| コピーするソース | リモート システムにコピーするソースを指定します。 この一覧を変更すると、リモート システム上でファイルのコピー先のディレクトリ構造がシフトするか、それ以外の場合は影響を受ける可能性があります。 |
| ソースのコピー | ソースをリモート システムにコピーするかどうか指定します。 |
| コピーする追加ソース | リモート システムにコピーする追加ソースを指定します。 オプションで、次のような構文を使用して、リモート マッピング ペアにローカルとして指定します: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2。ここで、ローカル ファイルをリモート システム上の指定したリモートの場所にコピーできます。 |

@SourcesToCopyRemotely および @DataFilesToCopyRemotely は、プロジェクト ファイル内の項目グループを参照します。 リモートでコピーするソースまたはデータ ファイルを変更するには、次のように *vcxproj* ファイルを編集します。

```xml
<ItemGroup>
   <MyItems Include="foo.txt" />
   <MyItems Include="bar.txt" />
   <DataFilesToCopyRemotely Include="@(MyItems)" />
</ItemGroup>
```

::: moniker-end
