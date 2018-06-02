---
title: '方法: 確認可能な C++ プロジェクトの作成 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 36e7ee85d97639df6298a346ae83bb090e81bf87
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704764"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>方法: 検証可能な C++ プロジェクトの作成 (C + + CLI)

Visual C アプリケーション ウィザードでは、検証可能なプロジェクトは作成されません。

> [!IMPORTANT]
> Visual Studio 2015 が推奨されておらず、Visual Studio 2017 はサポートしていません、 **/clr: 純粋な**と **/clr:safe**検証可能なプロジェクトを作成します。 検証可能なコードを必要とする場合、コードを c# に変換するをお勧めします。

ただし、古いバージョンをサポートする Visual C コンパイラ ツールセットを使用している場合 **/clr: 純粋な**と **/clr:safe**、検証可能であるプロジェクトを変換することができます。 このトピックでは、プロジェクトのプロパティを設定し、検証可能なアプリケーションを生成するために、Visual C プロジェクトを変換するプロジェクトのソース ファイルを変更する方法について説明します。

## <a name="compiler-and-linker-settings"></a>コンパイラとリンカーの設定

 既定は、.NET プロジェクトは/clr コンパイラ フラグを使用し、ハードウェアの x86 を対象とするようにリンカーを構成します。 検証可能なコードは、/clr:safe フラグを使用する必要があり、ネイティブ機械語命令ではなく MSIL を生成するようにリンカーに指示する必要があります。

### <a name="to-change-the-compiler-and-linker-settings"></a>コンパイラとリンカーの設定を変更するには

1. プロジェクトのプロパティ ページを表示します。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。

1. **全般**ページで、**構成プロパティ**、ノード セット、**共通言語ランタイム サポート**プロパティを**安全な MSIL 共通言語ランタイム サポート (//clr:safe)** です。

1. **詳細**ページで、、**リンカー** 、ノード セット、 **CLR イメージ タイプ**プロパティを**安全 IL イメージの強制 (//clrimagetype:safe)** です。

## <a name="removing-native-data-types"></a>ネイティブ データ型を削除します。

ネイティブ データ型は検証可能ではないので、実際に使用されていない場合でも、ネイティブ型を含むすべてのヘッダー ファイルを削除する必要があります。

> [!NOTE]
> 次の手順は、Windows フォーム アプリケーション (.NET) とコンソール アプリケーション (.NET) のプロジェクトに適用されます。

### <a name="to-remove-references-to-native-data-types"></a>ネイティブ データ型への参照を削除するには

1. Stdafx.h ファイル内のすべてのコメントします。

## <a name="configuring-an-entry-point"></a>エントリ ポイントを構成します。

検証可能なアプリケーションでは、C ランタイム ライブラリ (CRT) を使用できないため、標準的なエントリ ポイントとして main 関数を呼び出すには、CRT 依存ことはできません。 つまり、リンカーに最初に呼び出される関数の名前を明示的に指定する必要があります。 (この場合、main() または _tmain() の代わりに、CRT 以外のエントリ ポイントを指定する Main() が使用されるが、この名前は任意のエントリ ポイントは、明示的に指定する必要があります、ため)。

> [!NOTE]
> 次の手順は、コンソール アプリケーション (.NET) プロジェクトに適用されます。

#### <a name="to-configure-an-entry-point"></a>エントリ ポイントを構成するには

1. プロジェクトのメインの .cpp ファイルの Main() を _tmain() を変更します。

1. プロジェクトのプロパティ ページを表示します。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。

1. **詳細設定**ページで、、**リンカー**ノード、入力`Main`として、**エントリ ポイント**プロパティの値。

## <a name="see-also"></a>関連項目

- [純粋なコードと検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
