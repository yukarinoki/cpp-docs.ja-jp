---
title: '方法: MSBuild プロジェクトでビルド イベントを使用する'
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 3fe205223b6cf381bbf3e2872b1a84f9d81a3cb7
ms.sourcegitcommit: 2da5c42928739ca8cd683a9002598f28d8ec5f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70060071"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>方法: MSBuild プロジェクトでビルド イベントを使用する

ビルド イベントは、ビルド処理の特定の段階で MSBuild により実行されるコマンドです。 ビルドが開始する前に、"*ビルド前*" イベントが発生します。リンク ステップが開始する前に、"*リンク前*" イベントが発生します。ビルドが正常に完了すると、"*ビルド後*" イベントが発生します。 ビルド イベントは、関連付けられたビルド ステップが発生した場合にのみ発生します。 たとえば、リンク ステップが実行されない場合、リンク前イベントは発生しません。

これら 3 つのビルドイベントはそれぞれ、実行されるコマンド要素 (`<Command>`) と、**MSBuild** でビルド イベントが実行されるときに表示されるメッセージ要素 (`<Message>`) による項目定義グループで表されます。 各要素は省略可能です。同じ要素を複数回指定した場合は、最後の指定が優先されます。

省略可能な *use-in-build* 要素 (`<`*build-event*`UseInBuild>`) をプロパティ グループに指定すると、ビルド イベントが実行されるかどうかを示すことができます。 *use-in-build* 要素の内容の値は、**true** または **false** です。 既定では、対応する *use-in-build* 要素が `false` に設定されていない限り、ビルド イベントが実行されます。

次の表は、各ビルド イベント XML 要素の一覧です。

|XML 要素|説明|
|-----------------|-----------------|
|`PreBuildEvent`|このイベントは、ビルドが開始する前に実行されます。|
|`PreLinkEvent`|このイベントは、リンク ステップが開始する前に実行されます。|
|`PostBuildEvent`|このイベントは、ビルドが完了した後に実行されます。|

次の表は、各 *use-in-build* 要素の一覧です。

|XML 要素|説明|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|*ビルド前*イベントを実行するかどうかを指定します。|
|`PreLinkEventUseInBuild`|*リンク前*イベントを実行するかどうかを指定します。|
|`PostBuildEventUseInBuild`|*ビルド後*イベントを実行するかどうかを指定します。|

## <a name="example"></a>例

次の例は、次のセクションで作成した myproject.vcxproj ファイルの Project 要素の内部に追加できます: 「[チュートリアル: MSBuild を使用した C++ プロジェクトの作成](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)」。 "*ビルド前*" イベントによって、main.cpp のコピーが作成されます。"*リンク前*" イベントによって、main.obj のコピーが作成されます。"*ビルド後*" イベントによって、myproject.exe のコピーが作成されます。 プロジェクトがリリース構成を使用してビルドされる場合、ビルド イベントが実行されます。 プロジェクトがデバッグ構成を使用してビルドされる場合、ビルド イベントは実行されません。

``` xml
<ItemDefinitionGroup>
  <PreBuildEvent>
    <Command>copy $(ProjectDir)main.cpp $(ProjectDir)copyOfMain.cpp</Command>
    <Message>Making a copy of main.cpp </Message>
  </PreBuildEvent>
  <PreLinkEvent>
    <Command>copy $(ProjectDir)$(Configuration)\main.obj $(ProjectDir)$(Configuration)\copyOfMain.obj</Command>
    <Message>Making a copy of main.obj</Message>
  </PreLinkEvent>
  <PostBuildEvent>
    <Command>copy $(ProjectDir)$(Configuration)\$(TargetFileName) $(ProjectDir)$(Configuration)\copyOfMyproject.exe</Command>
    <Message>Making a copy of myproject.exe</Message>
  </PostBuildEvent>
</ItemDefinitionGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
  <PreBuildEventUseInBuild>true</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>true</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>true</PostBuildEventUseInBuild>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
  <PreBuildEventUseInBuild>false</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>false</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>false</PostBuildEventUseInBuild>
</PropertyGroup>
```

## <a name="see-also"></a>関連項目

[コマンド ラインでの MSBuild - C++](msbuild-visual-cpp.md)<br/>
[チュートリアル: MSBuild を使用した C++ プロジェクトの作成](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)
