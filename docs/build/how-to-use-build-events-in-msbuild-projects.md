---
title: '方法: MSBuild プロジェクトでビルド イベントを使用して |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.usebuildevents
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2367c85dbd4a4ef7b10d927592c0fb10a417f0e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369774"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>方法: MSBuild プロジェクトでビルド イベントを使用する
ビルド イベントは、コマンドを[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]ビルド プロセスで特定のステージでを実行します。 *ビルド前*ビルドの開始前に、イベントが発生した以外の場合は、*リンク前*、リンクの手順を開始する前に発生するイベントと*ビルド後*ビルドの後にイベントが発生します。正常に終了します。 ビルド イベントは、関連するビルド ステップが発生した場合にのみ発生します。 たとえば、リンク ステップが実行されない場合に、このリンク前イベントは発生しません。  
  
 コマンド要素で項目定義グループで表される各 3 つのビルド イベント (`<Command>`) 実行されると、メッセージ要素 (`<Message>`) されているときに表示される**MSBuild**ビルド イベントを実行します。 各要素は省略可能と同じ要素を複数回指定する場合、最後に見つかった位置が優先されます。  
  
 省略可能な*ビルドで使用する*要素 (`<`* ビルド-イベント ***UseInBuild**`>`)、ビルド イベントを実行するかどうかを示すために、プロパティ グループで指定することができます。 コンテンツの値、*ビルドで使用する*要素があるか、`true`または`false`です。 しない限り、既定では、ビルド イベントが実行される、対応する*ビルドで使用する*要素に設定されている`false`です。  
  
 次の表は、各ビルド イベントの XML 要素を示します。  
  
|XML 要素|説明|  
|-----------------|-----------------|  
|`PreBuildEvent`|このイベントは、ビルドの開始前に実行します。|  
|`PreLinkEvent`|このイベントは、リンク ステップを開始する前に実行します。|  
|`PostBuildEvent`|このイベントは、ビルドの完了後に実行します。|  
  
 次の表の各*ビルドで使用する*要素。  
  
|XML 要素|説明|  
|-----------------|-----------------|  
|`PreBuildEventUseInBuild`|実行するかどうかを指定します、*ビルド前*イベント。|  
|`PreLinkEventUseInBuild`|実行するかどうかを指定します、 *pre-link*イベント。|  
|`PostBuildEventUseInBuild`|実行するかどうかを指定します、*ビルド後*イベント。|  
  
## <a name="example"></a>例  
 次の例で作成した myproject.vcxproj ファイルのプロジェクト要素内で追加できる[チュートリアル: MSBuild Visual C プロジェクトの作成を使用した](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)です。 A*ビルド前*main.cpp のコピーを以外の場合は、イベントは*pre-link* main.obj; のコピーと、イベントは*ビルド後*イベントが myproject.exe のコピーを作成します。 プロジェクトをビルドするには、リリース構成を使用して、ビルド イベントが実行されます。 デバッグ構成を使用して、プロジェクトのビルドとビルド イベントは実行されません。  
  
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
 [MSBuild (Visual C)](../build/msbuild-visual-cpp.md)   
 [チュートリアル: MSBuild を使用した Visual C++ プロジェクトの作成](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)