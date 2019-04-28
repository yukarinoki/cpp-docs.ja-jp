---
title: '方法: MSBuild プロジェクトでビルド イベントを使用します。'
ms.date: 11/04/2016
f1_keywords:
- msbuild.cpp.howto.usebuildevents
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 7678b975558b245fb730bff35fb156bf21d7f895
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273483"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>方法: MSBuild プロジェクトでビルド イベントを使用します。

ビルド イベントは、ビルド プロセスで特定のステージで MSBuild を実行するコマンドです。 *ビルド前*イベントは、ビルドの開始前に発生します、*リンク前*、リンクの手順を開始する前にイベントが発生した、 *post-build*イベントは、ビルドの後に発生します。正常に終了します。 ビルド イベントは、関連付けられているビルド手順が発生した場合にのみ発生します。 たとえば、リンクの手順が実行されていない場合に、このリンク前イベントは発生しません。

Command 要素で、項目定義グループで表される 3 つのビルド イベントの各 (`<Command>`) 実行されると、メッセージの要素 (`<Message>`) されているときに表示される**MSBuild**ビルド イベントを実行します。 各要素は省略可能で、同じ要素を複数回指定する場合、最後に見つかったが優先されます。

省略可能な*ビルドでの使用*要素 (`<`*ビルド イベント*`UseInBuild>`) をビルド イベントが実行されるかどうかを示すプロパティ グループで指定できます。 コンテンツの価値を*ビルドでの使用*要素は、いずれかの**true**または**false**します。 しない限り、既定では、ビルド イベントが実行される、対応する*ビルドでの使用*要素に設定されて`false`します。

次の表では、各ビルド イベントの XML 要素を示します。

|XML 要素|説明|
|-----------------|-----------------|
|`PreBuildEvent`|このイベントは、ビルドを開始する前に実行します。|
|`PreLinkEvent`|このイベントは、リンクの手順を開始する前に実行します。|
|`PostBuildEvent`|このイベントは、ビルドの完了後に実行します。|

次の表を一覧の各*ビルドでの使用*要素。

|XML 要素|説明|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|実行するかどうかを指定します、*ビルド前*イベント。|
|`PreLinkEventUseInBuild`|実行するかどうかを指定します、 *pre-link*イベント。|
|`PostBuildEventUseInBuild`|実行するかどうかを指定します、 *post-build*イベント。|

## <a name="example"></a>例

作成した myproject.vcxproj ファイルのプロジェクト要素の内部で次の例を追加できる[チュートリアル。MSBuild を使用して、Visual C プロジェクトを作成する](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)します。 A*ビルド前*main.cpp のコピーは、イベントは*リンク前*main.obj; のコピーおよびイベントにより*post-build* myproject.exe のイベントのコピーします。 プロジェクトをビルドするには、リリース構成を使用して、ビルド イベントが実行されます。 デバッグ構成を使用して、プロジェクトのビルドとビルド イベントは実行されません。

```
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

[コマンド ライン - C++ での MSBuild](msbuild-visual-cpp.md)<br/>
[チュートリアル: MSBuild を使用した Visual C++ プロジェクトの作成](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)
