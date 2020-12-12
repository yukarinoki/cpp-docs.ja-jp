---
description: '詳細については、「方法: 検証可能な C++ プロジェクトを作成する (C++/CLI)」を参照してください。'
title: '方法: 確認可能な C++ プロジェクトを作成する (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual Studio C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
ms.openlocfilehash: 5f3a84a4f87db5cf390dcfbad18f167108e0ff08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245994"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>方法: 検証可能な C++ プロジェクトを作成する (C++/CLI)

Visual C++ アプリケーションウィザードでは、検証可能なプロジェクトは作成されません。

> [!IMPORTANT]
> Visual Studio 2015 では非推奨とされ、Visual Studio 2017 では、検証可能なプロジェクトを **/clr: pure** および **/clr: safe** で作成することはできません。 検証可能なコードが必要な場合は、コードを C# に変換することをお勧めします。

ただし、 **/clr: pure** および **/clr: safe** をサポートする古いバージョンの Microsoft C++ コンパイラツールセットを使用している場合は、プロジェクトを検証可能に変換できます。 このトピックでは、プロジェクトのプロパティを設定し、プロジェクトソースファイルを変更して、Visual Studio C++ プロジェクトを変換し、検証可能なアプリケーションを生成する方法について説明します。

## <a name="compiler-and-linker-settings"></a>コンパイラとリンカーの設定

既定では、.NET プロジェクトは/clr コンパイラフラグを使用し、リンカーが x86 ハードウェアを対象とするように構成します。 検証可能なコードの場合は、/clr: safe フラグを使用する必要があります。また、ネイティブマシン命令ではなく MSIL を生成するようにリンカーに指示する必要があります。

### <a name="to-change-the-compiler-and-linker-settings"></a>コンパイラとリンカーの設定を変更するには

1. プロジェクトのプロパティページを表示します。 詳細については、「 [コンパイラとビルドプロパティの設定](../build/working-with-project-properties.md)」を参照してください。

1. [ **全般** ] ページの [ **構成プロパティ** ] ノードで、[ **共通言語ランタイムサポート** ] プロパティを [ **安全な MSIL 共通言語ランタイムサポート (/clr: safe)**] に設定します。

1. [ **詳細設定** ] ページの **[リンカー** ] ノードで、[ **CLR イメージの種類** ] プロパティを [ **安全 IL イメージの強制 (/CLRIMAGETYPE: safe)**] に設定します。

## <a name="removing-native-data-types"></a>ネイティブデータ型の削除

ネイティブデータ型は、実際には使用されていない場合でも検証できないため、ネイティブ型を含むすべてのヘッダーファイルを削除する必要があります。

> [!NOTE]
> 次の手順は、Windows フォームアプリケーション (.NET) プロジェクトとコンソールアプリケーション (.NET) プロジェクトに適用されます。

### <a name="to-remove-references-to-native-data-types"></a>ネイティブデータ型への参照を削除するには

1. Stdafx.h ファイル内のすべてをコメントアウトします。

## <a name="configuring-an-entry-point"></a>エントリポイントの構成

検証可能なアプリケーションは C ランタイムライブラリ (CRT) を使用できないため、標準のエントリポイントとして main 関数を呼び出すために CRT に依存することはできません。 これは、最初にリンカーに呼び出される関数の名前を明示的に指定する必要があることを意味します。 (この場合、main () または _tmain () の代わりに Main () が使用され、CRT 以外のエントリポイントが示されます。ただし、エントリポイントは明示的に指定する必要があるため、この名前は任意です。

> [!NOTE]
> 次の手順は、コンソールアプリケーション (.NET) プロジェクトに適用されます。

#### <a name="to-configure-an-entry-point"></a>エントリポイントを構成するには

1. プロジェクトのメイン .cpp ファイルの _tmain () を Main () に変更します。

1. プロジェクトのプロパティページを表示します。 詳細については、「 [コンパイラとビルドプロパティの設定](../build/working-with-project-properties.md)」を参照してください。

1. [ **詳細設定** ] ページの [ **リンカー** ] ノードで、 `Main` **エントリポイント** プロパティ値として「」と入力します。

## <a name="see-also"></a>関連項目

- [純粋で検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
