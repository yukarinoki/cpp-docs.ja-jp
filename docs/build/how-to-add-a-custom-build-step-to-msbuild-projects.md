---
title: '方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する'
ms.date: 10/16/2019
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
ms.openlocfilehash: 78d40a5b4a02fe9b065bbbdde33afc6180d75381
ms.sourcegitcommit: 9aab425662a66825772f091112986952f341f7c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444916"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する

カスタム ビルド ステップは、ビルド内のユーザー定義のステップです。 カスタム ビルド ステップは、標準のコンパイルやリンク ツールのステップなど、他の "*コマンド ツール*" のステップと同様に動作します。

カスタム ビルド ステップはプロジェクト ファイル (.vcxproj) 内に指定します。 ステップでは、実行するコマンド ライン、追加の入力または出力ファイル、および表示するメッセージを指定できます。 **MSBuild** で出力ファイルが入力ファイルに関して最新ではないと判断された場合は、メッセージが表示され、コマンドが実行されます。

ビルド ターゲットのシーケンスにおけるカスタム ビルド ステップの場所を指定するには、プロジェクト ファイル内で `CustomBuildAfterTargets` および `CustomBuildBeforeTargets` XML 要素のいずれかまたは両方を使用します。 たとえば、カスタム ビルド ステップをリンク ツール ターゲットの後、マニフェスト ツール ターゲットの前に実行するように指定できます。 使用可能なターゲットの実際のセットは、特定のビルドによって異なります。

特定のターゲットの実行前にカスタム ビルド ステップを実行するには `CustomBuildBeforeTargets` 要素を、特定のターゲットを実行した後にステップを実行するには `CustomBuildAfterTargets` 要素を、または 2 つの隣接するターゲットの間にステップを実行するには両方の要素を指定します。 どちらの要素も指定されていない場合、カスタム ビルド ツールは既定の場所で、つまり**リンク**ターゲットの後に実行されます。

カスタム ビルド ステップとカスタム ビルド ツールで、`CustomBuildBeforeTargets` および `CustomBuildAfterTargets` XML 要素で指定された情報が共有されます。 したがって、これらのターゲットはプロジェクト ファイル内で 1 回だけ指定してください。

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>カスタム ビルド ステップによって実行される内容を定義するには

1. プロパティ グループをプロジェクト ファイルに追加します。 このプロパティ グループで、次の例に示すように、コマンド、その入力と出力、およびメッセージを指定します。 この例では、次のセクションで作成した main.cpp ファイルから .cab ファイルを作成します: 「[チュートリアル: MSBuild を使用した C++ プロジェクトの作成](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)」。

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(ProjectDir)main.cpp</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>ビルド内でカスタム ビルド ステップが実行される場所を定義するには

1. プロジェクト ファイルに次のプロパティ グループを追加します。 両方のターゲットを指定することができます。また、特定のターゲットの前または後にだけカスタム ステップを実行する場合は一方を省略することもできます。 この例では、コンパイル ステップの後、リンク ステップの前にカスタム ステップを実行するように、**MSBuild** に指示します。

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>関連項目

[チュートリアル: MSBuild を使用した C++ プロジェクトの作成](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[方法: MSBuild プロジェクトでビルド イベントを使用する](how-to-use-build-events-in-msbuild-projects.md)<br/>
[方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](how-to-add-custom-build-tools-to-msbuild-projects.md)
