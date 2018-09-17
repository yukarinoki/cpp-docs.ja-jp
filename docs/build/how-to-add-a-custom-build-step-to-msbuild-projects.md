---
title: '方法: MSBuild プロジェクトへのカスタム ビルド ステップの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.addcustombuildstep
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca8206024f4fbaf38b8161a9e12672782551db83
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712180"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する

カスタム ビルド ステップは、ビルドでのユーザー定義の手順です。 その他のように動作するカスタム ビルド ステップ*コマンド ツール*など、標準的なコンパイルまたはリンクのツールの手順の手順。

プロジェクト ファイル (.vcxproj) でカスタム ビルド ステップを指定します。 手順では、追加の入力または出力ファイル、および表示するメッセージを実行するコマンドラインを指定できます。 場合**MSBuild**決定、出力ファイルは、入力ファイルに対して最新ではないこと、メッセージを表示し、コマンドを実行します。

カスタム ビルドの場所は、ビルド ターゲットのシーケンスでステップを指定するの一方または両方を使用して、`CustomBuildAfterTargets`と`CustomBuildBeforeTargets`プロジェクト ファイル内の XML 要素。 たとえば、リンク ツールのターゲットの後、マニフェスト ツールのターゲットの前に、カスタム ビルド ステップを実行するかを指定できます。 実際の利用可能なターゲットのセットは、特定のビルドに依存します。

指定、`CustomBuildBeforeTargets`要素は、特定のターゲットが実行する前に、カスタム ビルド ステップを実行する、`CustomBuildAfterTargets`要素は、特定のターゲットを実行した後の手順を実行するか、両方の要素を 2 つの隣接するターゲットの間での手順を実行します。 カスタム ビルド ツールを実行した後は、既定の場所でいずれの要素が指定されている場合、**リンク**ターゲット。

カスタム ビルド ステップとカスタム ビルド ツールで指定された情報を共有、`CustomBuildBeforeTargets`と`CustomBuildAfterTargets`XML 要素。 そのため、これらのターゲット 1 回だけ、プロジェクト ファイルを指定します。

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>カスタム ビルド ステップによって実行される対象を定義するには

1. プロジェクト ファイルには、プロパティ グループを追加します。 次の例に示すように、このプロパティ グループで、コマンド、その入力と出力、およびメッセージを指定します。 この例で作成した main.cpp ファイルから .cab ファイルを作成します[チュートリアル: Visual C プロジェクトを作成するを使用して MSBuild](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)します。

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(TargetFileName)</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>実行するカスタム ビルド ステップ、ビルドの場所を定義するには

1. プロジェクト ファイルに次のプロパティ グループを追加します。 両方のターゲットを指定するか、なら、特定のターゲットの前後を実行するカスタム手順 1 つを省略できます。 この例のように指示**MSBuild**コンパイル手順の後に、リンクの手順の前に、カスタムの手順を実行します。

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>関連項目

[チュートリアル: MSBuild を使用した Visual C++ プロジェクトの作成](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[方法: MSBuild プロジェクトでビルド イベントを使用する](../build/how-to-use-build-events-in-msbuild-projects.md)<br/>
[方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)