---
title: '方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する'
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
ms.openlocfilehash: 812932d9e668ab5ee0eb75eadbf75be3d791cddb
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220719"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する

カスタム ビルド ツールは、特定のファイルに関連付けられているユーザー定義のコマンドライン ツールです。

特定のファイルについて、プロジェクト ファイル (.vcxproj) で、実行するコマンド ライン、追加の入力ファイルまたは出力ファイル、および表示するメッセージを指定します。 **MSBuild** で出力ファイルが入力ファイルに関して最新ではないと判断された場合は、メッセージが表示され、コマンドライン ツールが実行されます。

カスタム ビルドツールをいつ実行するかを指定するには、プロジェクト ファイルで `CustomBuildBeforeTargets` および `CustomBuildAfterTargets` XML 要素のいずれかまたは両方を使用します。 たとえば、MIDL コンパイラの後、C/C++ コンパイラの前にカスタム ビルド ツールを実行するように指定できます。 特定のターゲットが実行される前にツールを実行するには `CustomBuildBeforeTargets` 要素を、特定のターゲットの後にツールを実行するには `CustomBuildAfterTargets` 要素を、2 つのターゲットの実行の間にツールを実行するには両方の要素を指定します。 どちらの要素も指定されていない場合、カスタム ビルド ツールは、既定の場所で、つまり **MIDL** ターゲットの前に実行されます。

カスタム ビルド ステップとカスタム ビルド ツールで、`CustomBuildBeforeTargets` および `CustomBuildAfterTargets` XML 要素で指定された情報が共有されます。 これらのターゲットをプロジェクト ファイル内で 1 回指定します。

### <a name="to-add-a-custom-build-tool"></a>カスタム ビルド ツールを追加するには

1. プロジェクト ファイルに項目グループを追加し、入力ファイルごとに項目を追加します。 次に示すように、コマンド、追加の入力、出力、メッセージを項目メタデータとして指定します。 この例では、"faq.txt" ファイルがプロジェクトと同じディレクトリに存在すると想定しています。

    ```
    <ItemGroup>
      <CustomBuild Include="faq.txt">
        <Message>Copying readme...</Message>
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>
        <Outputs>$(OutDir)%(Identity)</Outputs>
      </CustomBuild>
    </ItemGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-tools-will-execute"></a>ビルド内でカスタム ビルド ツールが実行される場所を定義するには

1. プロジェクト ファイルに次のプロパティ グループを追加します。 少なくとも 1 つのターゲットを指定する必要がありますが、ビルド ステップを特定のターゲットの前 (または後) に実行することにのみ関心がある場合は、もう一方を省略できます。 この例では、コンパイル後、リンクの前にカスタム ステップを実行します。

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>関連項目

[チュートリアル: MSBuild を使用した C++ プロジェクトの作成](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[方法: MSBuild プロジェクトでビルド イベントを使用する](how-to-use-build-events-in-msbuild-projects.md)<br/>
[方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](how-to-add-a-custom-build-step-to-msbuild-projects.md)
