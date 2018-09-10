---
title: '方法: コピー リソース (C++) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
dev_langs:
- C++
helpviewer_keywords:
- resources [C++], moving between files
- resources [C++], copying
- resource files [C++], copying or moving resources between
- resource files [C++], tiling
- .rc files [C++], copying resources between
- rc files [C++], copying resources between
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc0fc8f3177baa01742df84c926a3c6421aa9a16
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314581"
---
# <a name="how-to-copy-resources-c"></a>方法: コピー リソース (C++)

変更せずに別の 1 つのファイルからのリソースをコピーすることができますもできます[コピー中に、言語またはリソースの条件を変更する](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md)します。

現在のリソース ファイルを既存のリソースまたは実行可能ファイルからリソースを簡単にコピーできます。 これを行うには、リソースが含まれると同時に両方のファイルを開くと別に 1 つのファイルから項目をドラッグまたはコピーして貼り付ける 2 つのファイル。 このメソッドは、リソース スクリプト (.rc) ファイルとリソース テンプレート (.rct) ファイル、実行可能ファイル (.exe) ファイルに機能します。

> [!NOTE]
> Visual C には、独自のアプリケーションで使用できるサンプル リソース ファイルが含まれています。 詳細については、次を参照してください。 [CLIPART: 一般的なリソース](https://github.com/Microsoft/VCSamples)します。

開いている .rc ファイル間でドラッグ アンド ドロップを使用する[プロジェクトの外部に](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。

### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>ドラッグ アンド ドロップ メソッドを使用してファイル間でリソースをコピーするには

1. スタンドアロン両方のリソース ファイルを開きます (詳細については、次を参照してください。 [、.rc ファイルの外部のプロジェクトでリソースを表示する](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md))。 たとえば、Source1.rc と Source2.rc を開きます。

2. 最初の .rc ファイル内には、コピーするリソースをクリックします。 たとえば、 `Source1.rc`、 をクリックして**IDD_DIALOG1**します。

3. CTRL キーを押しながらし、2 番目の .rc ファイルにリソースをドラッグします。 たとえば、ドラッグ**IDD_DIALOG1**から`Source1.rc`に`Source2.rc`します。

   > [!NOTE]
   > 保持することがなくリソースをドラッグする、 **Ctrl**キーはコピーすることではなく、リソースが移動します。

### <a name="to-copy-resources-using-copy-and-paste"></a>コピーを使用してリソースをコピーして貼り付ける

1. スタンドアロン両方のリソース ファイルを開きます (詳細については、次を参照してください。 [、.rc ファイルの外部のプロジェクトでリソースを表示する](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md))。 たとえば、Source1.rc と source2.rc を開きます。

2. リソースをコピーするソース ファイル内 (たとえば、 `Source1.rc`) でリソースを右クリックし、選択**コピー**ショートカット メニューから。

3. 貼り付けなど、リソース ファイルを右クリックし (たとえば、 `Source2.rc`)。 選択**貼り付け**ショートカット メニューから。

   > [!NOTE]
   > ドラッグ アンド ドロップ、コピー、切り取り、またはプロジェクト内のリソース ファイル間に貼り付けることはできません (**リソース ビュー**) とスタンドアロンの .rc ファイル (ドキュメント ウィンドウで開きます)。 これは、製品の以前のバージョンで実行できます。

   > [!NOTE]
   > シンボル名または既存のファイル内の値との競合を避けるためには、Visual C が転送されるリソースのシンボル値またはシンボル名や値を変更、新しいファイルをコピーする場合。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[方法: プロジェクトの外側で (スタンドアロンで) リソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
[リソース ファイル](../windows/resource-files-visual-studio.md)  
[リソース エディター](../windows/resource-editors.md)