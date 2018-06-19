---
title: '方法: カスタム ビルド ツール MSBuild プロジェクトを追加する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.addcustombuildtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3793e4223d00f219cc4f1d7b09e67453901bd6d1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368331"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する
カスタム ビルド ツールは、特定のファイルに関連付けられているユーザー定義のコマンド ライン ツールです。  
  
 特定のファイルを実行するには、プロジェクト ファイル (.vcxproj) コマンド ライン、追加の入力または出力ファイル、および表示するメッセージで指定します。 場合**MSBuild**出力ファイルが、入力ファイルに対して最新でないこと、メッセージが表示され、コマンド ライン ツールを実行することを決定します。  
  
 カスタム ビルド ツールが実行される場合を指定するの一方または両方を使用して、`CustomBuildBeforeTargets`と`CustomBuildAfterTargets`プロジェクト ファイル内の XML 要素です。 たとえば、MIDL コンパイラ後と、C と C++ コンパイラの前に、カスタム ビルド ツールを実行することを指定する場合があります。 指定して、`CustomBuildBeforeTargets`要素は、特定のターゲットが実行されます。 前に、ツールを実行する、`CustomBuildAfterTargets`要素は特定の対象の後に、ツールを実行するか、ツールを実行する、2 つのターゲットの実行間隔の両方の要素。 前に、既定の場所で、カスタム ビルド ツールを実行するいずれの要素が指定されている場合、 **MIDL**ターゲットです。  
  
 カスタム ビルド ステップとカスタム ビルド ツールで指定された情報を共有、`CustomBuildBeforeTargets`と`CustomBuildAfterTargets`XML 要素です。 これらのターゲットに、プロジェクト ファイルで 1 つの時間を指定します。  
  
### <a name="to-add-a-custom-build-tool"></a>カスタム ビルド ツールを追加するには  
  
1.  プロジェクト ファイルに項目グループを追加し、各入力ファイルの項目を追加します。 次に示すように、項目メタデータとして、コマンド、追加の入力、出力、およびメッセージを指定します。 この例では、faq.txt「という名前」ファイルがプロジェクトと同じディレクトリに存在すると仮定します。  
  
    ```  
    <ItemGroup>  
      <CustomBuild Include="faq.txt">  
        <Message>Copying readme...</Message>  
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>  
        <Outputs>$(OutDir)%(Identity)</Outputs>  
      </CustomBuild>  
    </ItemGroup>  
    ```  
  
### <a name="to-define-where-in-the-build-the-custom-build-tools-will-execute"></a>ここで、ビルドで、カスタム ビルド ツールが実行を定義するには  
  
1.  プロジェクト ファイルに次のプロパティ グループを追加します。 少なくとも 1 つのターゲットを指定する必要は関心がある場合のみ、ビルド ステップを実行する前に (または後) に、他の省略できます特定のターゲットです。 この例は、コンパイルした後は、リンクする前に、カスタムの手順を実行します。  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル: MSBuild を使用した Visual C プロジェクトの作成](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [方法: MSBuild プロジェクトでビルド イベントを使用](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)